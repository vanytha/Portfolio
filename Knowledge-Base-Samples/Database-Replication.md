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

