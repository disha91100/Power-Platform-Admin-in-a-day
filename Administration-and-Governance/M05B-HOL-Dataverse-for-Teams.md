## Admin in a day

# M06-Explore the CoE Starter Kit (Optional)

## Lab Scenario

## Lab Objectives

In this lab, you will complete the following exercises:

- Exercise 1 - Explore the CoE Starter Kit
- Exercise 2 - Perform a risk assessment of overshared resources
- Exercise 3 - How much is a connector used in your
- Exercise 4 - Review tenant audit logs 
- Exercise 5 - Application Compliance Process


## Exercise 1: Explore the CoE Starter Kit

### Scenario

In this exercise, you will explore some of the apps and analytics that are part of the Power Platform CoE Starter Kit. We have already installed and configured the starter kit for the 
tenant you are using for this lab. As part of configuring, we imported the solution, shared the apps, configured the flows that synchronize data and published the Power BI report. If you 
were doing this with your tenant, you would follow the instructions to complete these steps.

Now in this exercise, you will explore the following key components:

- Power Platform Admin View app
- Power BI Dashboard
- The business process that is used by the Developer Compliance process.

### Task 1: Explore the Power Platform Admin View app

1. Navigate to **Power Apps maker portal**.

2. Select the **Power Platform CoE** environment in the environment selector.

   ![](images/M02/M2-EX3-T1-S2.png)

3. Select **Apps** from the left side navigation and you should see a list of available apps in this environment, select **Power Platform Admin View**.

   ![](images/M02/M2-EX3-T1-S3.png)

4. When the app starts you will land on the Power Platform Dashboard page. This dashboard gives you a quick look at the most active makers, and environments.

   ![](images/M02/M2-EX3-T1-S4.png)

5. Select **Power Apps** and you will see a list of all apps in all environments without having to visit each environment. The Flows navigation link does the same thing for Microsoft 
   Power Automate flows.

6. Select the **Device Ordering App** in the list to open the app details.

   ![](images/M02/M2-EX3-T1-S6.png)

7. In the **Governance** tab you can see the Business Justification provided by the app maker using the Developer Compliance Center app. The bottom part is where you as an admin can 
   provide your risk assessment. You can also tag the app to show in the App Catalog and make it featured. You can customize the CoE entities to add additional fields here if needed.

   ![](images/M02/M2-EX3-T1-S7.png)

8. Select **Environments** in the left navigation. This will show you a list of all the environments in your tenant and key metrics like several apps. To view all your environments, 
   similar to the image below, switch the view at the top to **Active Environments**.

   ![](images/M02/M2-EX3-T1-S8-1.png)

9. Select the **User and Team Productivity** environment to open the detail form.

10. Review the data available.

11. Select the **Connectors** link from the left navigation. This shows all the connectors available.

    ![](images/M02/M2-EX3-T1-S11.png)

12. In the upper right corner, search for **Microsoft Dataverse**.

    ![](images/M02/M2-EX3-T1-S12.png)

13. In the search results, select the **Microsoft Dataverse** connector.

    ![](images/M02/M2-EX3-T1-S13.png)

14. The **Used in** tab quickly shows you what apps are using this connector in all environments in your tenant.

15. Select **Users**, then **Makers** from the left navigation; this shows you all the people who have built apps in your company.

16. Select one of the Makers and explore the detail form.


### Task 2: Power BI Dashboard

#### Get the environment URL
You need the URL of the Power Platform environment where the CoE Starter Kit is installed. Power BI connects to Dataverse tables in that environment.

1. Go to the [Power Platform admin center](https://aka.ms/ppac).

2. Select Environments, then choose Power platform COE environment.

3. Right-click on the Environment URL and select Copy Link Address.


#### Configure the Production and Governance Power BI dashboard

1. Navigate to PowerBI using the following link https://app.powerbi.com/ in your browser.

1. If prompted, **Sign in** with your lab credentials.

    ![](images/M02/pt3.png)

1. Select **Next**.

    ![](images/M02/pt2.png)

1. If prompted, please solve the puzzle.    

1. Select **Continue**.

    ![](images/M02/pt1.png)

1. On the **Create your account** page, provide the following details and then click on **Get started (4)**.

   - Country: **Unites states (1)**
   - Job: **PowerPlatformEngineer(2)**
   - Phone number: Enter random 10 digits **(3)**

     ![](images/M02/pt4.png)

1. Click on **Get Started**.

    ![](images/M02/pt5.png)

1. Click on the Acoount manager icon **(1)** from the top right corner and then click on **Free trial (2)**.

    ![](images/M02/pt6.png)

1. Select **Activate**.

    ![](images/M02/pt7.png)

1. Select **Stay on current page**.

    ![](images/M02/pt-8.png)

1. On the left side navigation select **Workspaces** and then click on **+ New workspace (2)**.

    ![](images/M02/pt9.png)

1. On the Create panel, provide a unique name like **CoE-LabAdmin<inject key="Deployment ID" enableCopy="false" /> (1)** and your lab admin user number and select **Apply (2)**.

   ![](images/M02/pt10.png)

1. Launch **Power BI Desktop** on your local computer from the desktop.

   ![](images/M02/ppt22.png)

1. Close the popup window.

1. Click on **Sign in** from the top bar, sign-in with your lab admin account credentials.

1. Once signed in, click on **Open (1)**, then **Browse this device (2)**.

    ![](images/M02/pt11.png)

1. Navigate to Downloads folder in File Explorer> COE Starter Kit > Select Production_CoEDashboard_MMMYY.pbit **(1)**, and then **Open (2)**. Wait for sometime you will notice popup appears for org URL

    ![](images/M02/pt11A.png)

1. Enter the URL of your environment instance. Include the https:// prefix for OrgUrl.

**Note:** Paste the Environment URL you copied earlier.

1. The report should load automatically once the refresh has been completed.

1. Follow the steps below to enable **map and filled map visuals**:

     a) Select **File** at the top right, then select **Options and Settings > Options**.
   
     ![](images/M02/M2-EX3-T2-S22-A.png)
   
     b) Select **Security** from the left.
   
     c) Scroll down to the Map and Filled Map visuals section.
   
     d) Check the **Use Map and Filled Map visuals** checkbox.
   
     e) Select **OK** to close the Options dialog.

     ![](images/M02/M2-EX3-T2-S22-E.png)

1. Review the **Introduction** page.

    ![](images/M02/M2-EX3-T2-S23.png)

1. Select the **Overview – Power Apps** tab, notice it gives a good high-level look at our tenant activity. If you have multiple locations, it will quickly highlight which users are 
    more engaged with building apps. You can also quickly see which environments are most active. Additionally, items that are detailed as **(Blank)** indicate that there is no data to 
    reference in the table.

    ![](images/M02/M2-EX3-T2-S24.png)

1. Review each page using the navigation at the bottom of the app and review the insights available.

1. Select the **Environments** page.

    ![](images/M02/M2-EX3-T2-S26.png)

1. On the Environments page, use the date range picker and see how it affects the other data on the page. When you are done leave it set at the max date range.

    ![](images/M02/M2-EX3-T2-S27.png)

1. Select the **Apps** tab from the navigation at the bottom of the screen.

    ![](images/M02/M2-EX3-T2-S28.png)

1. On the Apps page notice the Creation Trend, this is an effective way to watch adoption progress.

    ![](images/M02/M2-EX3-T2-S29.png)

1. Select the other pages via the tabs at the bottom and review the data available.

1. Select **Publish** from the **Home** tab in the ribbon at the top.

    ![](images/M02/M2-EX3-T2-S31.png)

1. Save the report if prompted as **PBI Report (Your Initials)**, which will look something like **PBI** **Report HR** for example.

1. Select the **CoE-LabAdmin<inject key="Deployment ID" enableCopy="false" /> (1)** workspace you created and choose **Select (2)**.

     ![](images/M02/pt13.png)

1. Wait for the publishing to complete and select **Open 'PBI’** Report in Power BI or **Got it**.

     ![](images/M02/M2-EX3-T2-S34.png)

1. If you selected **Open**, skip this step. Otherwise, if you selected ‘Got it’, navigate to Power BI. Select **Workspaces (1)** and then **CoE-LabAdmin<inject key="Deployment ID" enableCopy="false" /> (2)** Workspace you created. Otherwise, skip to step 37.

     ![](images/M02/pt14.png)

1. Select the **CoE Starter** with the type of **Report** from the list. You’ll notice a few other items have been generated; these are done by default.

     ![](images/M02/pt15.png)

1. Once the report loads, select the Environments page. Use the date slider to ensure the date range includes the last month.

     ![](images/M02/M2-EX3-T2-S37.png)

1. You have now successfully deployed the Power BI reports that come with the CoE starter kit.


## Exercise 2: Perform a risk assessment of overshared resources

### Scenario

We were going to perform a risk assessment to look for apps that have been shared with your tenant. To accomplish this, you are going to use the Power BI report that you just published 
to look for apps that are over-shared.

### Task 1: Locate Overshared Apps

1. Navigate to the **Power BI report** you just published.

2. Select the **Apps** page in the report.

3. Select the Show navigation button and select **Apps Risk Assessment**. This will take you to the risk assessment page of the report.

   ![](images/M02/M2-EX4-T1-S3.png)

4. The list of apps you'll see now is the ones that qualify for the default criteria. We want to focus on the ones that have been shared with the entire organization and validate that 
   they are appropriate.

   ![](images/M02/M2-EX4-T1-S4.png)

5. In the filter panel, select True in the Shared with Everyone section.

   ![](images/M02/M2-EX4-T1-S5.png)

6. The filter will take place immediately and you will see a small list of apps that have been shared with everyone. In many cases, a quick evaluation of the name of the app would 
   indicate whether it was appropriate, but it also allows you to drill down into more details by hovering your mouse pointer over the name of the app. You might also use the owner’s 
   name to contact the person who made the app to get more details to determine if it was appropriate to share with everyone.


## Exercise 3: How much is a connector used in your

### Scenario

Using the Power BI report, you can easily see what apps and flows are using a connector. In this exercise, you will find out who is using the SharePoint connector.

### Task 1: Locate resources that use the SharePoint connector

1. Navigate to the **Power BI report** you just published.

2. Select the **App Connections** page in the report.

   ![](images/M02/M2-EX5-T1-S2.png)

3. In the filter panel, in the **Connector** section search for **Office 365 Outlook** and select it.

   ![](images/M02/M2-EX5-T1-S3.png)

4. The page will now filter on makers, and apps that use Office 365.

5. Using this you could evaluate things like the impact of changing DLP policies or other governance or training that might be needed related to a connector.


## Exercise 4: Review tenant audit logs 

### Scenario

All other auditing of Power Apps and Power Automate flows (other than CDS data modification) are viewed through the Microsoft Purview site.

Before use, this must be enabled by a global tenant administrator using these instructions. In the tenant you are using we have already completed that for you as well as permitting you to view the audit log data for the tenant. That was done using the PowerShell command Add-RoleGroupMember “Compliance Management” -Member your user.

In this exercise, you will be using the log search and alert tools to work with the audit data.

### Task 1: Review audit logging in the environment

1. Navigate to **Microsoft purview** using the following link https://purview.microsoft.com/.

1. Click on **Get Started**.

   ![](images/M02/ppt23.png)

1. Select **Solution (1)** and then choose **Audit (2)** on the left side navigation.

   ![](images/M02/ppt24.png)

1. Click on the **Start recording user and admin activity**.

   ![](images/M02/ppt25.png)

1. Select **Search** using the default search criteria.

   ![](images/M02/M2-EX6-T1-S3.png)

1. The **Job Status** will read as **Queued** once it has been set to process. **Refresh** the audit every few minutes or so until the status reads as **Completed**.

   ![](images/M02/M2-EX6-T1-S5.png)

1. Select the Search name, which defaults to the audit date if no name has been inputted.

   ![](images/M02/M2-EX6-T1-S6.png)

    >**Note**: Portal will be updating your organization to support customization. So it might take around 24 to 48 hours to show the data and activities.

     ![](images/M02/ppt26.png)    

1. Please go through the steps, no need to perform as currently there is no data available.     

1. Review the items displayed; drill into a few of them to see the type of data available.

   ![](images/M02/M2-EX6-T1-S7.png)

1. Select **Export** if you’d like to download the data for later viewing. Using export, you can open the data in other tools for analysis.

   ![](images/M02/M2-EX6-T1-S8.png)

1. The export will begin and may take some time to complete.

    ![](images/M02/M2-EX6-T1-S9.png)

1. Select **Audit search** breadcrumb at the top of the page to navigate back to the search. This will not interrupt the export.

    ![](images/M02/M2-EX6-T1-S10.png)

1. Select the **Activities** dropdown and select all Power Apps and Power Automate activities.

    ![](images/M02/M2-EX6-T1-S11.png)

1. Select **Search** again and review the results once the status is Completed.

1. Look for an activity of Edited Flow, and select the item to open the detail. Review what data is provided.

1. A common task is to look at all of the activity for a particular user. Copy the user from this Edited flow activity and go back to the Audit search.

1. Paste the user you copied into the Users filter and select search again. Now you are looking at all the activity for a single user.

1. Try selecting an item to view detail. Copy the Item field and then go back to the list and select the filter results. Paste the item info you just copied into the file. The results list will now only show activities related to that item. For example, you could use this to show all activities for a specific flow.


**Note:** Any information from before auditing was enabled, cannot be retrieved. This can be seen by selecting a date range from before the auditing was enabled.

## Exercise 5: Application Compliance Process

In this exercise, you will be walking through the application compliance process that has been put in place using the CoE Starter Kit. As part of this, you will be playing both the role of 
the application developer and the administrator see both sides of the process.

The goal of this process is to help IT that doesn't know what all these apps are intended for or how to support individual apps when the helpdesk is called, and it's unclear whether all 
the apps are being maintained to any standard. They can see details like the description and number of shared users from the Power Apps for Admins connector, but they need to communicate 
directly with the app owner to fully understand the situation around the apps. Especially in a large organization, it's not feasible for the IT team to be responsible for manually 
reaching out to each app owner individually, and those details can't be stored in email conversations.

To automate this, a flow **Admin | Compliance Detail Request** is used to iterate through all the apps in the tenant and check whether the apps are compliant. If the owner hasn't 
submitted a business justification and the app was shared broadly (in this example, with more than 20 users or at least one group), the flow sends the owner an email to notify them that 
their specific app isn't in compliance with the policy. The email contains a link to the Developer Compliance Center canvas app, where the owner can provide the business justification details 
in a form submission. The Developer Compliance Center app also contains details about the compliance thresholds and has links to the app settings, so the owner can configure the 
description and republish if needed.

This app auditing sample process showcases how your CoE department or IT administrators can automate an auditing process on an app-level basis to gather additional information about an 
app, like business justification and the impact of an outage, from the maker.

### Task 1: Complete Developer Compliance

In this task, you will be performing the role of the developer and completing the application information that will be requested by the automated process.

1. When the full process runs the maker will receive an email like the following, with a link to the Developer Compliance Center. For our exercise, we will briefly review and then we will 
   launch the app from the maker portal.

   ![](images/M03/M3-EX3-T1-S1.png)

1. Navigate to **Power Apps** and select the **OTU WA (default)** environment.

   ![](images/M03/pp113.png)

1. Select **Apps** from the left-side navigation.

    ![](images/M03/M3-EX3-T1-S3.png)

1. Select **Apps (1)**, then **+ New app (2)** > **Start with page design (3)**.

   ![](images/M04/po29.png)

1. Click on **+** on blank canvas app. Make sure **Tablet** is selected.

    ![](images/M04/po30.png)

1. Click on **Save** on the top right corner 

    ![](images/M03/pp114.png)

1. Enter name as **Test App (Initials) (1)** and then **Save (2)**. 

    ![](images/M03/pp115.png)

1. Click on **elipses...(1)** then select **Settings (2)** from the ribbon at the top.

    ![](images/M03/pp116.png)

1. Under **General**, enter **Description** as **An App that counts for you (1)**. Then, close the settings with the **X (2)** at the top right.

    ![](images/M03/pp117.png)

1. If enabled, select **Save** at the top right.

    ![](images/M03/M3-EX3-T1-S8.png)

1. Then select **Publish**.    

    ![](images/M03/pp118.png)

1. From here, we can review the changes we made to the description as well as the app name and icon associated with it. Select **Publish this version**.

    ![](images/M03/M3-EX3-T1-S9.png)

1. Wait for the publishing to complete, then select the **Back** button.

     ![](images/M03/M3-EX3-T1-S10.png)

1. Select the Current environment **(1)** then Switch to the **Power Platform COE (2)** environment.

     ![](images/M03/pp119.png)

1. Select **Solutions** from the left-side navigation, then the **Center of Excellence – Core Components** solution.

     ![](images/M03/M3-EX3-T1-S12.png)

1. Select **Objects > Apps** from the menu on the left,

     ![](images/M03/M3-EX3-T1-S13.png)

1. Select the **∙∙∙** next to the **Power Platform Admin View** model-driven app and select **Play**.

     ![](images/M03/M3-EX3-T1-S14.png)

1. Select **PowerApps Apps** and search in the box at the top right for the **Lab Admin X** app, where X is your lab user number or the test app we created. Select the appropriate result.

     ![](images/M03/M3-EX3-T1-S15.png)

1. Select the **Governance** tab and set the **Admin Risk Assessment State** to **Requested**.

     ![](images/M03/M3-EX3-T1-S16.png)

1. **Save & Close** at the top left.

     ![](images/M03/M3-EX3-T1-S17.png)

1. Close the **Power Platform Admin View** application.

1. Navigate back to Solutions via the left-side navigation and select the **Center of Excellence –** **Governance Components**.

     ![](images/M03/M3-EX3-T1-S19.png)

1. Select Apps from the **Objects** menu, then select **Developer Compliance Center**.

    ![](images/M03/M3-EX3-T1-S20.png)

1. The application will list all the apps that you are the owner of. The information at the bottom of each card will indicate what is preventing your app from reaching full compliance.

1. You should see at least one app that has the name lab admin and your number or the **Test App** name. Select the card to review the details of the app.

     ![](images/M03/M3-EX3-T1-S22.png)

1. Review the App Compliance section which gives clear guidance on what needs to be updated. Select the icon next to **Missing support details** to open the **Support Details** panel.

     ![](images/M03/M3-EX3-T1-S23.png)

1. In the **Support Details** section fill in all the fields with information about your application, you can make it as detailed as you want but submit information for each field in this section.

1. Normally we would also adjust the description by editing the app, but for this lab will skip that.

1. Select **Save** to save the information about the application and close the Support Details panel.

     ![](images/M03/M3-EX3-T1-S26.png)


### Task 2: Admin Review

In this task, you will be performing the administrative review of the application details that were submitted by the developer.

1. In the maker portal, with the **Power Platform CoE** environment selected, select Apps.

2. Launch the **Power Platform Admin View** app.

   a. Select PowerApps Apps in the left navigation and change the view to **Compliance-Submitted**.

   ![](images/M03/M3-EX3-T2-S2.png)

3. Locate your application. It will be Lab Admin and your # or Test App and your initials and select it to open it.

   ![](images/M03/M3-EX3-T2-S3.png)

4. Select **Validate Maker Business Requirements** in the process guide. This shows you the current stage of the review process and highlights the progress. Notice it says the maker 
   provided the business requirements. Set **Confirm Business Impact** to **Low Risk** and close by selecting the X at the top right of the card.

   ![](images/M03/M3-EX3-T2-S4.png)

5. Review the information provided by the maker by selecting the **Governance** tab.

   ![](images/M03/M3-EX3-T2-S5.png)

6. In the Admin section change the Risk Assessment to Minor.

   ![](images/M03/M3-EX3-T2-S6.png)

7. After reviewing you can advance the process to the next stage by selecting the Next Stage.

   ![](images/M03/M3-EX3-T2-S7.png)

8. The process guide will now have either a Mitigation plan as the active stage or an Access risk depending
    on if the maker indicated the app is critical or not, select Next Stage again to advance.

9. In the final stage you can choose a category for the app in the catalog and indicate if it was featured.
    Make your selections and then select Finish.

10. You have now completed the full review process. This is an example that is provided with the starter kit you can tailor the process to your own organization's needs including adding 
    stages and steps to the process and requiring additional data from the maker.


### Review

In this lab, you have accomplished the following:

- Exercise 1 - Explore the CoE Starter Kit
- Exercise 2 - Perform a risk assessment of overshared resources
- Exercise 3 - How much is a connector used in your
- Exercise 4 - Review tenant audit logs
- Exercise 5 - Application Compliance Process

### You have successfully completed this lab.  