# Getting Started with Spend Analytics

The **Spend Analytics App** is an innovative tool that allows users to create a single unified view of their entire security spend.

The app currently supports:

- Selection of security vendors and products  
- Management of contracts  
- Defining cost pools  
- Managing the entire security spend budget  

Features such as an **intuitive dashboard**, **renewals calendar**, and the **Cyber Coverage Matrix** provide users with a **360-degree view of their entire security spend**.

This short guide will walk you through the steps needed to perform the initial setup before you start deriving the real benefits of Spend Analytics.
## ShiftRight Sign-up / Sign-in

### Sign-in
If you already have a **ShiftRight account** because you signed up for our other services, you do not need to create another account for the Spend App.

We provide two options for signing in to your Spend App account:

- **Magic Link Login**  
  Enter your work email in the sign-in box, and we will send you an email with a magic link.  
  Clicking the **Login** button in the email will log you in to **Spend Analytics**.

- **Google Account Login**  
  Alternatively, you can sign in using your existing **Google account**.

### Sign-up
If this is the first time you are using any service from **ShiftRight**, you need to sign up using your **work email address** before you can start using the **Spend App**.

Follow these steps in sequential order to get started with the **Spend Analytics application**.
### STEP 1: Account Setup

Setting up your account is a simple process. **Account Setup** can be found under **Settings → Account** after you log in to **Spend Analytics**.

We require only basic information about your company to get you started, as shown below.
 <img width="979" height="379" alt="image" src="https://github.com/user-attachments/assets/fec270f2-be91-46ef-b8e4-4d733cb1effa" />

- **Customer Name** – Name of your company.

- **Financial Year Start Month** – Select the month in which the financial year starts.

- **Financial Data Frequency** – Select the frequency (**Monthly / Quarterly**) at which financial data is captured.

- **SLA Targets**

  - **SLA in Days** – The target resolution time (in days) for security incidents corresponding to each severity level.

  - **Weights** – Used to calculate risk scores in security incidents. Enter the weight associated with each pair (**Severity & SLA**). Valid entries range from **1 through 10**.
 
### STEP 2: Add Vendors and Security Products

The next step in setting up **Spend Analytics** is choosing your security vendors and products.

The **Products Setup** page shows the products that were added earlier. To add a new product, simply use the **Add Product** option after selecting a vendor, complete a simple product entry form, and your product will be added to the **Spend Dashboard**.
<img width="979" height="393" alt="image" src="https://github.com/user-attachments/assets/e1ce2206-51af-415c-8736-618d91f269bb" />
- **Owner** – Enter the primary contact details for this product.

- **Department** – Select the department or organizational unit where this product will be primarily used.

- **Lifecycle** – Select the appropriate phase in terms of product deployment.

- **Primary Spend Asset Class** – Select the primary type of assets protected by the product.

- **Product Prioritization**
  - **Essential** – Must have  
  - **Standard** – Good to have  
  - **Ideal** – Desirable to have  

- **Asset Count** – Enter the number of assets.

- **Primary Spend Category** – Select the primary spend category applicable for this product.

- **Primary Spend Sub Category** – Select the primary spend subcategory applicable for this product.

- **Cyber Coverage Capabilities** – Click the options to map appropriate product capabilities to asset classes.
> It is important to add all the security products that you are currently using to get a complete picture of your organization's spend in the dashboard.

### STEP 3: Define Spend

This involves the setup of **Contracts, Cost Pools, and Spend Plan**.

### I. Adding Contracts

This is a critical component in spend setup, as it has a direct impact on spend analytics. Adding vendor and product contracts allows the **Spend App** to determine the estimated vs. committed spend for a particular product. The Spend App also allows you to add more than one contract for a product.

**Key fields are defined below:**

- **Contract Name** – Enter the name of the contract.

- **Start Date / End Date** – Start and end dates for your contract.  
  The **End Date** is not applicable for perpetual contracts.

- **Auto Renew** – Check this to indicate that the contract is set up for automatic renewal.

- **Cancel Renewal By** – The date by which you can cancel the automatic renewal of your subscription.

- **Renewal Term in Months** – The period (in months) for which the product will auto-renew after the current subscription term expires.

- **Internal Contact** – Primary contact person for this contract within the organization.

- **Vendor Contact** – Primary vendor contact for this contract.

- **Organization / Team** – Organization or team for which the contract is created.

- **Select Contract Spend Type** – Click an option to enter spend details at the contract level **(a)** or itemized spend **(b)**.

   #### a) Contract with **Term Contract Spend**

   A contract with the **Term Contract Spend** option will have committed and estimated **CAPEX** and **OPEX** values.

   - **Term Committed CAPEX Spend** – Capital expense committed as per the contract’s terms.

   - **Term Committed OPEX Spend** – Operating expense committed as per the contract’s terms.

   - **Estimated Overage CAPEX Spend** – Estimated capital expense above the amount committed in the contract’s terms.

   - **Estimated Overage OPEX Spend** – Estimated operating expense above the amount committed in the contract’s terms.

  #### b) Contract with **Spend per Item**

  A contract with **Spend per Item** can have one of the following license types for items:

  - **One-Time (Perpetual)** – This type of itemization allows users to define total spend and a depreciation schedule, if any, for the contract item.

  - **Subscription** – Subscription-based licensing allows users to define various combinations of license types and **capacity & spend options**.

Click **Save** after uploading the essential financial documents.

### II. Defining Cost Pools

**Cost Pools** are used to segregate product spend across multiple groups for accounting purposes. Cost Pools allow users to define where and how they are actually spending their security budgets.

Cost Pools can be defined based on **Location, Environment, Initiatives**, or any other logical entity where a part of the cost is apportioned.

For example, one can define **“Environment”** as a Cost Pool with **“Development,” “Staging,” and “Production”** as members to correctly reflect which part of the security budget is spent on which assets.

Cost Pools defined once can be used globally across products. This implies that **Cost Pool names should be unique and not repeated**.
 <img width="979" height="412" alt="image" src="https://github.com/user-attachments/assets/3912e494-333f-4c66-b50c-68cb46cc4aa4" />
While adding a new **Cost Pool**, specify the following:

- **Cost Pool Name** – Financial spend categories used to group and classify spend (e.g., Department, Location, Environment).

- **Member Name** – Logical groupings where part of the overall spend is utilized.  
  *Example:* A **Department** Cost Pool could have **Engineering** and **Marketing** as members.

- **Percentage** – The percentage of spend allocated to the member.
### III. Define Your Budget or Spend Plan

Defining the **Spend Plan** is the key to unlocking many of the **Spend App** features.

The **Spend Plan** allows you to enter your actual spend data based on the frequency you have chosen (**Monthly or Quarterly**). The entire **Spend Analytics Dashboard** is based on these numbers. Take utmost care to specify accurate numbers so that they are correctly reflected in the **Spend Analytics Dashboard**.

We have modeled the entry of spend data exactly like **Excel**, and we support features such as **copy and paste** and **drag-to-fill data**.
<img width="979" height="401" alt="image" src="https://github.com/user-attachments/assets/34029c51-4ed7-4cba-8604-80abfe0dafd0" />

The expense amounts are separated into **CAPEX** and **OPEX** and are divided across months/quarters based on the **Financial Data Frequency** (**Monthly / Quarterly**) specified in the account setup.

> **Note:** The **CAPEX** column is not shown by default. It can be included by selecting it from the **Select Columns** dropdown.

- **CAPEX** – Anything that is bought or sold as a unit or item is considered CAPEX. It is an outright purchase since it is fully paid for at once, with complete ownership rights upon payment.  
  *Examples:* Server, Hardware Appliance, Firewall, MS Office, Operating System.

- **OPEX** – OPEX refers to expenses incurred when entering into a service agreement that involves a subscription or service fee. In this case, you do not own the software; you simply use it.  
  *Example:* Office 365.

The **Estimate** fields are populated from the contract details specified earlier (if the **Data Source** is **Contract**).

Based on the **Financial Data Frequency** (**Monthly / Quarterly** as specified in account setup), you need to input the **actual CAPEX and OPEX values for all products**.

Products can be added in between using the **Add after selected row** option or at the end using the **Add Row** option.

