## Admin in a day

# M02-HOL-Reporting and Telemetry

### Estimated Duration: 90 minutes

## Lab Scenario

In this Hands-on Lab, you are an administrator helping adopt the Power Platform. An important part of keeping the Power Platform running successfully is monitoring the ongoing usage. In this hands-on lab, you will be using the platform tools and the COE Starter Kit to 
perform usage monitoring.

## Lab Objectives

In this lab, you will complete the following exercises:

- Exercise 1 - Explore the out-of-the-box analytics
- Exercise 2 – Configure Dataverse logging for a table
- Exercise 3 - Set up inventory components


### Lab Test Environment

This lab is designed to be completed in an environment setup for multiple students to complete the Admin in a day series of hands-on labs.

You need to use the assigned user and environment information to complete this lab. You must have completed the prior labs to complete this lab.

## Exercise 1: Explore the out-of-the-box analytics

Now in this exercise, you will explore the out-of-the-box analytics that are available from the Power Platform admin center.

1. Navigate to **Power Platform admin center**.

2. Select **Analytics **(1)**> Power Apps (2)**.

    ![](images/M02/pp120.png)

3. Select the **Overview (1)** tab and select **Enable (2)** to redirect to the Analytics pane.

   ![](images/M02/pp121.png)

4. In the Analytics pane, grant consent for tenant-level analytics by enabling the **Tenant-level analytics** feature and select **Save**.

   ![](images/M02/tenant-save1.png)

   >**Note**: Once enabled, this feature aggregates data from environments across all regions in your tenant and copies it into the default environment region for tenant-level reporting. A tenant-level administrator role is required for the one-time operation of granting consent for tenant-level analytics.

5. The **Overview** tab displays a message indicating that tenant-level analytics has been enabled. Typically, these reports are displayed within 24-48 hours of enabling the feature.

   ![](images/M02/pp122.png)

    > **Note**: The below tasks 1,2 and 3 has been made as read only because the service can take 24 to 36 hours to reflect service activities from the previous day. Please go through the provided link for more details [Tenant-level analytics for Power Apps](https://learn.microsoft.com/en-us/power-platform/admin/tenant-level-analytics?tabs=new#how-do-i-enable-tenant-level-analytics)   

### Task 1: Explore the Power Automate analytics (Read only)

1. Navigate to **Power Platform admin center**.

1. Expand **Analytics** and select **Power Automate**.

   ![](images/M02/M2-EX1-T1-S3.png)

1. Ensure you’re under the **Environment View (1)**. Select **Change filters (2)**

   ![](images/M02/pp123.png)

1. Change the Environmnent to **Power Platform COE (1)** environment and the **Apply (2)**.

   ![](images/M03/pp124.png)

1. Review the visuals in the **Runs** tab and then select the **Usage** tab.

   ![](images/M02/M2-EX1-T1-S6.png)

1. Review the visuals in the **Usage** tab.

1. Review the visuals in the rest of the tabs.

1. In the top left corner of the screen, under the header, select **Overview** to review tenant-level
    analytics.

    ![](images/M02/M2-EX1-T1-S9.png)

1. Now you are looking at data for all environments you have access to.

11. Review the **Usage** data available on this tab, and then switch to **Maker Activity** and **Inventory** to review the other data available. Notice you can still filter on more specific criteria using the dropdowns.

    ![](images/M02/M2-EX1-T1-S11.png)

### Task 2: Explore the Power Apps analytics (Read only)

1. In the **Power Platform admin center**. Under **Analytics**, expand **Power Apps (1)**. Change the Primary Tab to **Environment View (2)**. Click on **Change filters (3)**. Switch the environment to **Power Platform COE (4)** by changing the available filters and the click on **Apply (4)**

   ![](images/M03/pp125.png)

1. Review the visuals in **Usage**, and all other tabs.

1. In the top left corner of the screen, under the header, select **Overview** to review tenant-level analytics.

   ![](images/M02/M2-EX1-T2-S6.png)

1. Now you are looking at data for all environments you have access to.

1. Review the **Usage** data available on this tab, and then switch to **Maker Activity** and **Inventory** to review the other data available. Notice you can still filter on more 
   specific criteria.

   ![](images/M02/M2-EX1-T2-S8.png)

1. Hover your mouse over the far-right corner of the unique user's data, and under **Region** you can select **...** to show more options.

   ![](images/M02/M2-EX1-T2-S9.png)

1. Select **Export data**.

    ![](images/M02/M2-EX1-T2-S10.png)

1. If you have Excel installed choose one of the options and select **Export**. After the file downloads review the details available. If you don’t have Excel simply select **Cancel**.

    ![](images/M02/M2-EX1-T2-S11.png)

### Task 3: Explore the Capacity analytics (Read only)

1. Navigate to **Power Platform admin center**.

1. Expand **Resources** and select **Capacity**.

    ![](images/M02/M2-EX1-T3-S2.png)

1. Notice the data in the **Storage capacity usage** panel.

   ![](images/M02/M2-EX1-T3-S3.png)

1. Notice the data under the **Storage capacity by source** panel.

   ![](images/M02/M2-EX1-T3-S4.png)

1. Go to the **Top storage usage by environment** panel and notice the capacity usage by top environments.

   ![](images/M02/M2-EX1-T3-S5.png)

1. Select the **Dataverse** tab from the top row of options.

   ![](images/M02/M2-EX1-T3-S6.png)

1. Locate the **Device Ordering Development** environment storage capacity and select **Details**.

   ![](images/M02/M2-EX1-T3-S7.png)

1. Select the **Chart menu** button at the top right of the first chart and select **Download all tables**.

   ![](images/M02/M2-EX1-T3-S8.png)

1. Open the file that was downloaded as a result.

   ![](images/M02/pp126.png)

1. You should see a list of all tables and their database size in MB.

   ![](images/M02/M2-EX1-T3-S9.png)

1. Close the Excel file. You won’t need to save any changes you’ve made.

1. Go to the navigation pane on the far left and expand **Analytics**, then select **Dataverse**.

    ![](images/M02/M2-EX1-T3-S11.png)

1. Review the visuals.

13. Select **Change filters**.

    ![](images/M02/pp127.png)

14. Change the **From** date to one week prior today’s date **(1)** and the **To** date to today **(2)**. Select **Apply (3)**.

    ![](images/M02/pp128.png)

15. The visuals should change to reflect your changes.

    ![](images/M02/M2-EX1-T3-S15.png)


## Exercise 2: Configure Dataverse logging for a table

In this exercise, you will configure Dataverse logging for a table that requires auditing.

### Task 1: Review audit logging in the environment

1. Navigate to the **Power Apps maker portal**, click on Current Environment **(1)** and select the **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (2)** environment.

   ![](images/pp-1.png)

1. Select **Solutions (1)** and choose the **Fabrikam Project Management (2)** solution to open it.

   ![](images/M02/pp129.png)

1. Select **Tables (1)** and select the **Project (2)** table. Select **Columns (3)** under the **Schema** section.

   ![](images/M02/pp130.png)

1. Locate and select **Due Date** to open it.

   ![](images/M02/M2-EX2-T1-S5.png)

1. Expand the **Advanced Options** section. Check and ensure that **Enable Auditing** is enabled for this column. A notice will be underneath the option, informing you that auditing is not enabled 
   for the organization. We will fix this in a later step.

1. Select **Cancel** to close the field details pane.

   ![](images/M02/M2-EX2-T1-S7.png)

1. Navigate back to the Tables by either selecting the **Tables** on the left side, or by using the breadcrumbs at the top.

   ![](images/M02/M2-EX2-T1-S8.png)

1. Select the **Project (1)** table, and then select **Properties (2)** from the ribbon up top.

   ![](images/M02/pp131.png)

1. Expand the **Advanced options** section.

    ![](images/M02/M2-EX2-T1-S10.png)

1. Scroll down to the **For this table** section.

1. Select the **Audit changes to its data (1)** checkbox and select **Save (2)**.

    ![](images/M02/pp132.png)

1. Select **All** from the left navigation of the solution.

    ![](images/M02/pp133.png)

1. Select **Publish all customizations** and wait for the publishing to be completed. A green banner will appear to let you know when it is complete.

    ![](images/M02/M2-EX2-T1-S14.png)

    ![](images/M02/M2-EX2-T1-S14-1.png)

1. Navigate to **Power Platform admin center** and select **Environments**.

    ![](images/M02/M2-EX2-T1-S15.png)

1. Select the **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (1)** environment and select **Settings (2)** from the ribbon at the top.

    ![](images/M02/po22.png)

1. Expand **Audit and logs** section and select **Audit settings**.

    ![](images/M02/M2-EX2-T1-S17.png)

1. Check on **Start auditing (1)** checkbox, select **Save (2)** and select **Cancel** to close.

    ![](images/M02/pp134.png)

### Task 2: Test auditing

1. Navigate to the **Power Apps** maker portal and make sure your in **My Sandbox-<inject key="Deployment ID" enableCopy="false" />** environment.

1. Select **Apps** and select the **Project Admin** application to launch.

   ![](images/M02/M2-EX2-T2-S2.png)

1. If you can see the **Annual Conference** project select it to open it and skip to step 5, if you do not see it, continue with the steps below.

   ![](images/M02/po24.png)

   - Create a new project by selecting the green **+ New** from the ribbon at the top.

     ![](images/M02/po25.png)

   - For the **Title**, enter **Annual Conference**. Choose the **Due date** as today’s date.

     ![](images/M02/M2-EX2-T2-S5.png)

   - Then, select **Save & Close**.

     ![](images/M02/M2-EX2-T2-S6.png)

1. From this screen, reopen the **Annual Conference** project.

   ![](images/M02/M2-EX2-T2-S7.png)

1. Change the **Due Date** to any date in the future **(1)** and select **Save (2)**.

   ![](images/M02/pp135.png)

1. Change the **Due Date** and save a couple more times.

1. Select **Related** and select **Audit History**.

    ![](images/M02/M2-EX2-T2-S10.png)

1. You should see the change history for each of your changes. Select **Update/Create** to open one of the change history records.

    ![](images/M02/pp136.png)

1. You should see the **Filed Name**, **Old Value** and **New Value**.

1. Select **Close** to close the update record.

    ![](images/M02/pp137.png)

## Exercise 3: Set up inventory components

This article guides you in setting up the inventory component of the CoE Starter Kit. The inventory centralizes data on apps, flows, and makers, helping you monitor and manage your Power Platform environment. It enables admin apps, dashboards, and tools like DLP Editor and Set App Permissions for better governance.

Now in this exercise, you will explore the following key components:

- Import the Creator Kit and make connections
- Set up the Inventory components using the Setup Wizard
- Set up the CoE Admin Command Center app
- Set up Audit Logs solution
- Set up the Power BI dashboard
- Share apps with other admins

### Task 1 :  Import the Creator Kit and make connections

### Installation of Creator Kit
1. Go to the [Creator Kit page on AppSource](https://appsource.microsoft.com/en-US/product/dynamics-365/microsoftpowercatarch.creatorkit1?tab=Overview) page.

    > **Note:** Sign in to an account with ODL Credentials

2. Select the button **Get it now**.

   ![](images/M02/M2-EX3N-T1-S1.png)

3. The App Source install experience will launch the Power Platform admin center and ask you to identify the target Environment. Close the popups and continue.

4. Choose the **Power Platform COE** Environment, review and agree to the two agreement checkboxes, then select the Install button to continue.
    ![](images/M02/M2-EX3N-T1-S2.png)


    >**Note**: Installation may take some time; meanwhile, you can continue with the next steps.

### Create Connections
1. Go to [Power Automate](https://make.powerautomate.com/) in new tab.
2. Select your Power Platform COE environment.

    ![](images/M02/M2-EX3N-T1-S3.png)

3. Select **More** from left navigaation > **Connections** 

    ![](images/M02/M2-EX3N-T1-S4.png)

4. Select **+New Connection** and search for **HTTP with Microsoft Entra ID**.

    ![](images/M02/M2-EX3N-T1-S5.png)

5. Click on **HTTP with Microsoft Entra ID (preauthorized)**, and set **Base Resource URL (1)** and **Microsoft Entra ID Resource URI (Application ID URI) (2)** to https://graph.microsoft.com/. Click **createb (3)**.

    ![](images/M02/M2-EX3N-T1-S6.png)

    > **Note:** Sign in with your ODL credentials.

### Import the core components solution
1. Download the CoE Starter Kit [compressed file](https://aka.ms/CoeStarterKitDownload) to your Virtual Machine.

2. Open File Explorer on your computer.

3. Navigate to the Downloads folder.

4. Locate the downloaded CoEStarterKit.zip file.

5. Right-click on the ZIP file and select "Extract All...".

6. In the dialog box that appears, click the "Extract" button to unzip the contents.

    ![](images/M02/M2-EX3N-T1-S7.png)

    > **Note:** The CoE Starter Kit compressed file contains all solution components in addition to the non–solution-aware components that make up the CoE Starter Kit. 

7. Go to [Power Apps](https://make.powerapps.com/) and sign in.

8. Choose the **Power Platform COE** Environment.

9. In the left menu, click **Solutions**.

    ![](images/M02/M2-EX3N-T1-S8.png)

10. Click the **Import Solution** button at the top.

11. Click Browse, select the **CenterOfExcellenceCoreComponents_x_x_x_xx_managed.zip** solution file from the extracted folder, and click Next.

    ![](images/M02/M2-EX3N-T1-S9.png)

12. Review the details, click next.. next, Leave all environment variable values blank/as it is,  then click Import.

    >**NOTE:** Wait for the import to complete — you'll see a confirmation once it's done. The import can take up to 20-30 minutes to be complete, and upgrades can take up to two hours.

### Install COE Governance Solution.
1. Go to the **Solutions** tab.

2. Click on **Import** Solution.

3. Browse to your **Downloads** folder and locate the **CoEStarteKit** directory.

4. Open the folder and select the following file:
**CenterofExcellenceAuditComponents_3_27_1_managed.zip**
(Full path: C:\Users\demouser\Downloads\CoEStarterKit\CenterofExcellenceAuditComponents_3_27_1_managed.zip

5. Click **Next**, review the connections, click **Next** again, and proceed with the **import** process.


### Task 2: Set up the Inventory components using the Setup Wizard

1. After the solution import is successful, refresh the tab and open the **Center of Excellence - Core Components** solution.

    ![](images/M02/M2-EX3N-T1-S10.png)

2. Play COE Admin Command Center app.

    ![](images/M02/M2-EX3N-T1-S10A.png)

3. Click **Sign In** for RSS, then click **Allow**. 

    ![](images/M02/M2-EX3N-T1-S10B.png)

4. Click **Environment Varibles** under CoE configuration from left navigation pannel and then click **admin_AdminMail**, then click **edit**.

    ![](images/M02/M2-EX3N-T1-S10C.png)

5. Paste <inject key="AzureAdUserEmail"></inject> email id in the **Value** section , then click **Save**

    ![](images/M02/M2-EX3N-T1-S10D.png)

6. Now return to the previous tab where your “Center of Excellence - Core Components” is open. Open the CoE Setup and Upgrade Wizard app. Click **Apps** (1), Click the three ellipses (⋯) next to the **CoE Setup and Upgrade Wizard** (2). Select **Play** (3) to launch the app.

    ![](images/M02/M2-EX3N-T1-S11.png)

3. Grant all app permission and click **Allow**.

    ![](images/M02/M2-EX3N-T1-S12.png)

4. Confirm pre-requisites: Click **Next**.

    ![](images/M02/M2-EX3N-T1-S13.png)

5. Configure communication methods: Click **configure group** and select **Create new group** 
for persona.

    ![](images/M02/M2-EX3N-T1-S14.png)

6. You will be navigate to azure portal. Select **Microsoft 365** (1) for group type. Give group name as **COE Admin Group** (2). Click **No Owners Selected** (3). 

    ![](images/M02/M2-EX3N-T1-S14A.png)

6. Search for and select the **environment email ID**. Similarly, you can select multiple members to assign to the Admin persona.  Once you've made your selections, click Create to proceed.

    ![](images/M02/M2-EX3N-T1-S14B.png)

8. Navigate back to the **CoE Setup and Upgrade Wizard** tab. Refresh the page, then proceed to configure the Admin persona by selecting the newly created group.

    ![](images/M02/M2-EX3N-T1-S14C.png)

8. In the same way, you can create new groups for the Maker persona and User persona. For now, you can select the same **CoE Admin Group** for both, After completing all three configuration, click **Next** to continue.

9. Configure mandatory settings: Review tenant id from Service principal details in the environment section of lab guide and select **Next**

8. Configure inventory data source : Click **Next**.

9. Run setup flows: Click **Refresh**, wait about 5 minutes for the process to complete, then refresh again. Once done, click **Next**.

10. Run Inventory flows: Click toggle button for all the flows available on the page until all the flows are removed from the page. Click **Next**.

    >**Note**: Proceed Next if no flows on the page

11. Configure dataflows: Click **Next**.

12. Share apps: Click **Next**.

13. Publish PowerBI dashboard: Click **Next** and then **Done**
 
14. Navigate to the **More features** page and select **Compliance process**.

    ![](images/M02/M2-EX3N-T1-S15.png)

    > **Note:** The app will guide you through the setup process.

15. Click **Refresh**. If a pop-up appears regarding flow configuration, proceed as prompted.

16. On the **Get Started** screen, click **Next**.

17. On the **Exempt environments from this process** screen, click **Next**.  
    ![](images/M02/M2-EX3N-T1-S16.png)

18. On the **Configure settings** screen, click **Next**.

19. On the **Turn on flows** screen, toggle **On** for all listed flows, then click **Next**.

20. On the **Share Apps** screen, click **Done**.

### Review

In this lab, you have accomplished the following:

- Exercise 1 - Explored the out-of-the-box analytics
- Exercise 2 – Configured Dataverse logging for a table
- Exercise 3 - Set up inventory components

### You have successfully completed this lab.

