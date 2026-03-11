## Overview

Data in SQL databases often needs to be synchronized in real time, but distributing data across multiple servers can be challenging.

Microsoft SQL Server Replication is a feature that enables copying and synchronizing data between databases either continuously or at scheduled intervals.

For the Rideau distributed database system, SQL Server replication has been implemented to synchronize core data between the databases hosted on the servers `dbprodus08\us08` and `dbprodca08\ca08`.

Among the available SQL Server replication types — **Snapshot Replication**, **Transactional Replication**, and **Merge Replication** — **Transactional Replication** has been selected because it provides efficient near real-time synchronization and is well suited for this scenario.
## Databases Used in Replication

- The core data of the three main databases (**Rideau_Master**, **sa_rca**, and **Boutiques**) are configured for replication as shown below.

- The core data includes common lookup tables that need to be synchronized between the Canadian and US servers.

- The data from the **core databases** is published to the main databases (the **subscribers**) through the **transactional replication process**.
  
| Main Database | Core Database | Replication Process in Production |
|---------------|---------------|-----------------------------------|
| Rideau_Master (ERP that handles orders and products) | Rideau_Master_core | <img width="940" height="545" alt="image" src="https://github.com/user-attachments/assets/6ac97a1f-492c-417c-9c87-9aa5e89219b8" />|
| sa_rca (contains details pertaining to points awards and service awards) | sa_rca_core |<img width="940" height="546" alt="image" src="https://github.com/user-attachments/assets/d589d61b-3b58-4e04-a82b-aa3bd79daafc" />|
| Boutiques (custom platform that allows ordering products based on recipient's point balance) | Boutiques_core |<img width="940" height="546" alt="image" src="https://github.com/user-attachments/assets/0725b087-12b0-48bc-9493-2cee93357ff6" />|

## About DBAReplicationVerifier
<img width="428" height="200" alt="image" src="https://github.com/user-attachments/assets/1d3e0944-4e03-46f1-9160-ab9fade47fdc" />

- This table is used to verify that the replication process is working and that the databases are synchronized between the US and Canadian servers.

- Rows inserted into this table are manually checked to confirm that the changes are reflected in the corresponding database tables on the other two servers.
  ## Replication Publishing Model Terminology

The components in a replication topology include **Publisher, Distributor, Publications, Articles, Subscriptions, Subscribers,** and **Replication Agents**.

| Component | Description |
|-----------|-------------|
| **Publisher** | A database that provides the data for replication (e.g., `Boutiques_core`). |
| **Publication** | A set of objects and data to replicate. A publisher (database) can have one or more publications. |
| **Article** | The database objects that are to be replicated, such as tables. |
| **Distributor** | A database that stores the replication metadata and data from one or more publishers before it is delivered to subscribers. |
| **Subscriber** | A database that subscribes to publications from the publisher in order to receive replicated data. Example: `[SQL08PRODCA-01\CA08][Boutique]` and `[SQL08PRODCA-01\US08][Boutique]`. |
| **Subscription** | The link between a publisher and a subscriber. The subscriber connects to the publisher by creating a subscription for a specific publication. |
| **Replication Agent** | Standalone executables responsible for moving data from the publisher to the subscriber. Examples include **Snapshot Agent**, **Log Reader Agent**, and **Distribution Agent**. |
## Data Protection Practices in General

The publication database is a subset of the target subscriber databases in the Rideau system.

Data protection practices are followed to avoid data integrity issues. These include the following:

### 1. Usage of Triggers to Restrict Manual Manipulation (Insert/Update/Delete) of Subscriber Tables

Triggers are created to ensure that data manipulation operations are performed only through the replication process. Any data manipulation attempted through other methods is automatically rolled back.

**Example:** Trigger used to roll back all data manipulation commands on the `dbo.ColorType` table in the `Rideau_Master` database.
<img width="468" height="165" alt="image" src="https://github.com/user-attachments/assets/9d114afd-9f77-4308-82ef-718c37256a68" />
### 2. Usage of Triggers to Restrict Data Deletion in Publisher Tables

This is explained below with an example:

- The publication database (e.g., `Rideau_Master_core`) is a subset of the subscriber database `Rideau_Master`.  
  It does not contain all the foreign keys and dependent tables that exist in the subscriber database.

- It is important to ensure that delete operations are not allowed in `Rideau_Master_core`.  
  If a delete operation occurs in the publication database, the change will be propagated to `Rideau_Master`.  
  This may cause the replication process to fail because the data in `Rideau_Master` must adhere to existing foreign key constraints.

**Example:** Trigger used to roll back all delete operations on the `dbo.ColorType` table in the `Rideau_Master_core` database.
<img width="314" height="168" alt="image" src="https://github.com/user-attachments/assets/ae75ba4f-aec5-4cc7-9823-c5f28194498f" />

**Example:** Trigger `trgColorTypeUpdate` has been created to avoid scenarios like the one described below, which can cause replication to fail due to foreign key violations.

- A record is deleted from the table `dbo.ColorType` in the `Rideau_Master_core` database, and the delete operation is replicated to the subscriber database `Rideau_Master`.

- In the `Rideau_Master` database, the table `dbo.ColorTypeStrings` contains a foreign key that references the `ColorType_Id` column in the `dbo.ColorType` table.

- Because of this foreign key dependency, deleting the record from `dbo.ColorType` causes a foreign key violation, which results in the replication process failing.
<img width="589" height="358" alt="image" src="https://github.com/user-attachments/assets/6a0e8f34-349f-434f-b744-0c575a0acd6d" />
