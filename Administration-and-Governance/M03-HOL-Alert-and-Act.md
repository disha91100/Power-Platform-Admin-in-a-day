## Admin in a day

# M03-HOL-Action through Automation

## Lab Scenario

In this hands-on lab, you are an administrator supporting Contoso's efforts to streamline and control Power Platform usage. Contoso has restricted environment creation to global or service admins and wants an automated process for users to request new environments and Dataverse databases without discouraging platform adoption. You will build a Microsoft Form for users to submit requests, and then use Power Automate with administrative connectors and approval workflows to automate the review and provisioning process. The solution will handle approvals, environment creation, and user notifications. You’ll also explore the app auditing process from the CoE Starter Kit by stepping through it as both a maker and an admin, and install a prebuilt flow to identify new app makers, add them to an Office 365 group, and send them a welcome email.


## Lab Objectives

In this lab, you will complete the following exercises:

- Exercise 1 - Create Environment Request Form
- Exercise 2 – Create Environment on Form Submit
- Exercise 3 – Application Compliance Process
- Exercise 4 – Welcome New Makers (Optional if you have time)

### Lab Test Environment

This hands-on lab is designed to be completed in an environment setup for multiple students to complete the Admin in a day series of hands-on labs.

You will be assigned one or more users to use to complete the hands-on tasks. Because this is a shared environment, some tasks that require a tenant Global Administrator or a Service 
Administrator will already be performed.

This lab does not require you to have completed any of the prior labs.

## Exercise 1: Create Environment Request Form

### Scenario

In this exercise, you will be creating an environment request form using Microsoft Forms. This form could
collect additional information allowing it to be tailored to your individual organization's requirements.

### Task 1: Create Microsoft Form

1. Navigate to **Microsoft Forms** with https://forms.office.com/ and close the pop up screen.

2. Select **+ New Form**.

   ![](images/M02/pp52.png)

3. Select the **Untitled Form** Header.

   ![](images/M02/pp53.png)

4. Enter **New Environment Approval Request (1)** for title, enter **New environment request (2)** for description, and select **+ Quick start with (3)**.

   ![](images/M02/pp55.png)

5. Create the **Form** below, by following the below steps.

   ![](images/M03/M3-EX1-T1-S5.png)

6. Select **Text**.

   ![](images/M03/pp56.png)

7. Enter **Environment Name (1)**, make the question **Required (2)**, and select **+ Add new question (3)**.

   ![](images/M03/pp57.png)

8. Select **Text** again.

9. Enter **Business Justification (1)**, select **Long Answer (2)**, and make it **Required (3)** then select **+Add new question (4)**

   ![](images/M03/pp58.png)

10. Select **Text**.

11. Enter **What connectors will you use? (1)** select **Long Answer (2)** and make it **Required (3)**.

    ![](images/M03/pp59.png)

12. The form will be saved automatically.

13. Select **Preview**.

    ![](images/M03/pp60.png)

14. You can see the created form.

    ![](images/M03/pp61.png)


## Exercise 2: Create Environment on Form Submit

### Scenario

In this exercise, you will be building the automated flow to process new form submissions.

**Note**: For this exercise, we have hard-coded the language, currency and environment template. The Power Platform Administration connector has actions allowing you to 
dynamically retrieve these and make the process more flexible. You could allow the user to specify the values, or infer them from the user’s Office 365 profile information using 
the Office 365 connector.

### Task 1: Delete your sandbox environment

1. Navigate to the **Power Platform admin center**.

1. Navigate to **Environment (1)**, select the sandbox environment that you created in module one named **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (2)** in the list of environments.

   ![](images/ppp1.png)

1. Select the **Delete** button.

   ![](images/ppp2.png)

1. Confirm the deletion by typing the environment name **(1)** and then select **Confirm (2)**. We have to delete it to create another Trial environment, which we can only have one at a time.

   ![](images/ppp3.png)

    >**Note**: Environment deletion might take some time, please wait until its get deleted.

### Task 2: Create New Environment Approval Flow

1. Navigate to **Power Automate**.

1. Set your environment to **Power Platform CoE**.

   **Note**: This environment is where our CoE starter kit is installed and is intended to be our dedicated admin environment. Even if you don’t use the starter kit, having a dedicated 
   admin environment can be helpful.

   ![](images/M03/M3-EX2-T2-S2.png)

1. Select **My flows (1)**, select **+ New flow (2)** and select **Automated cloud flow (3)**.

   ![](images/M03/pp62.png)

1. Type **New Environment Approval (1)** in the Flow name field. In the **Choose your flow’s trigger** section, search for **When a new response is submitted (2)** then select **When a new response is submitted (3)**, and select **Create (4)**.

   ![](images/M03/pp63.png)

1. Select the **When a new response is submitted** box.

   ![](images/M03/pp64.png)

1. For the **Form Id**, select the **New Environment Approval Request** form you created.

   ![](images/M03/pp65.png)

1. Select **+ Add action**.

   ![](images/M03/pp66.png)

1. Search for **Microsoft Forms (1)** and select **Get response details (2)**.

   ![](images/M03/pp67.png)

1. Select **New Environment Approval Request (1)** for **Form Id** and click on the **dynamic content (2)** symbol to select **Response Id**. 

    ![](images/M03/pp68.png)

1. Select the **Response Id** from the Dynamic content pane.    

    ![](images/M03/M3-EX2-T2-S10.png)

1. Select **+ Add action**.

    ![](images/M03/pp69.png)

1. Search for **Approvals (1)** and select **Start and Wait for an Approval (2)**.

    ![](images/M03/pp70.png)

     >**Note**: If prompted, please click on **Create**.

1. Select **Approve/Reject - First to Respond** for Approval type.

    ![](images/M03/pp71.png)

1. Enter **Environment Approval Requested (1)** for Title.

   - Select the user you are logged in as for **Assigned to** by typing the name into the field and selecting the correct dropdown item **(2)**

   - Type **New Environment was requested by:** in the **Details** field **(3)**

   - Select the Dynamic content symbol to select the Responder email **(4)**

     ![](images/M03/pp72.png)   

   - Select **Responders Email** from the Dynamic content pane.

     ![](images/M03/M3-EX2-T2-S17.png)

1. Hit the enter key and type **Environment Name:** and select **Environment Name** from the Dynamic content pane.

    ![](images/M03/M3-EX2-T2-S18.png)

1. Hit the enter key again and type **Business Justification:** and select **Business Justification** from the Dynamic content pane.

    ![](images/M03/M3-EX2-T2-S19.png)

1. Hit the enter key again type **Connectors:** and select **What connectors will you use?** from the Dynamic content pane.

    ![](images/M03/M3-EX2-T2-S20.png)

1. Select **+ Add Action**.

    ![](images/M03/pp73.png)

1. Search for **Condition (1)** and the select **Condition (2)** Control.

    ![](images/M03/pp74.png)

1. Click on the dynamic content symbol to select the Value.

    ![](images/M03/pp75.png)

1. Select the Choose a value field and select **Outcome**.

    ![](images/M03/pp76.png)

1. Enter **is equals (1)** to for condition, enter **Approve (2)** for value.

    ![](images/M03/pp77.png)

1. Select **Add an action** in the **True**  branch.

    ![](images/M03/pp78.png)

1. Search for **Power Platform for admins** and under **Power Platform for admins** section select **See more (2)**.

    ![](images/M03/pp79.png)

1. Select **Create Environment**.

    ![](images/M03/pp80.png)

1. Click on **Sign in**. Sign in with your lab credentials.

    ![](images/M03/pp81.png)

1. Select **United States (1)** for the **location** and select the dynamic content symbol on the **Display Name** field **(2)**.

    ![](images/M03/pp82.png)

     >**Note:** Location determines the region for the environment, in a real process you might allow this to be auto-determined by the user location or something the requester provides.

1. Select **Environment Name** from the Dynamic content pane.

    ![](images/M03/M3-EX2-T2-S28.png)

1. Select **Trial** for **Environment Sku**.

    ![](images/M03/pp-83.png)

1. Select **Save**. Do not navigate away from this page.

    ![](images/M03/pp85.png)

### Task 3: Create a Database and Notify the User

1. Select **+ Add an action** under **Create Environment**.

   ![](images/M03/pp84.png)

1. Search for **Power Platform for admins** and under **Power Platform for admins** section select **See more (2)**.

    ![](images/M03/pp79.png)

1. Select **Create CDS Database**.

   ![](images/M03/pp86.png)

1. Select on the **Environment** dropdown and select **Enter Custom Value**.

   ![](images/M03/M3-EX2-T3-S4.png)

1. Select **Name (1)** from the Dynamic content pane.

   ![](images/M03/M3-EX2-T3-S5.png)

1. Select **Show all (2)**.

   ![](images/M03/pp87.png)

1. Enter **1033 (1)** for Base Language and enter **USD (2)** for Currency Code.

1. Enter **D365_CDSSampleApp (3)** for Template Item.

   ![](images/M03/pp89.png)

1. Select **Add an action** under **Create CDS Databse**.

   ![](images/M03/pp90.png)

1. Search for **Send Email (1)** and select **Send an email (V2) (2)**.

   ![](images/M03/pp91.png)

1. Click on **Sign in**. Sign in with the lab credentials.

   ![](images/M03/pp92.png)

1. Click on **Switch to Advanced Mode**.

   ![](images/M03/pp93.png)

1. Select on the **To:** field and select **Responders Email** for the Dynamic Content pane **(1)**.

1. Enter **Your environment was created** for **Subject (2)**.

1. Enter **Environment** in the **Body** field and select **Display Name** from the Dynamic Content pane under the **Create Environment** step and add **was created** in the last **(3)**.

1. Your email should look like the image below.

    ![](images/M03/pp94.png)

1. Go to the **False** branch and select **Add an Action** to create a new connection under the **False** branch.

   ![](images/M03/pp95.png)

1. Search for Send email and select **Send an email (V2) Office 365 Outlook**.

   ![](images/M03/pp96.png)

1. Select **Switch to Advanced Mode**.

   ![](images/M03/pp97.png)

1. Select on the **To:** field and select **Responder’s Email** from the Dynamic Content pane.

   ![](images/M03/pp98.png)

1. Type **Rejected environment request (1)** for **Subject**.

1. Enter **Your request for new environment was rejected (2)** in the **Body**.

1. Your email should now look like the image below.

    ![](images/M03/pp99.png)

1. Select **Save**.

    ![](images/M03/M3-EX2-T3-S21.png)

1. Select **Flow checker** and make sure there are no errors.

    ![](images/M03/pp101.png)

    ![](images/M03/pp102.png)

1. Close the **Flow checker** pane with the X to the right of the pane header.

1. Select the **Back** button.

    ![](images/M03/pp103.png)

### Task 4: Test the Flow

1. Navigate to **Microsoft Forms** and open the form you created.

   ![](images/M03/pp104.png)

1. Select **Collect responses**.

   ![](images/M03/pp105.png)

1. **Copy** the link.   

   ![](images/M03/M3-EX2-T4-S2-1.png)

1. Paste the link in the browser and navigate to it.

   ![](images/M03/pp106.png)

1. The form should load, provide the following details and then click on **Submit (4)**.

   - Environment name: Provide **Central Apps Test (1)**
   - Business Justification: **We will use this Environment for training new employees (2)**
   - What connector will you use: **Microsoft Dataverse (3)**. 

     ![](images/M03/pp107.png)   
   
      >**Note**: For this course, we 
   will be using this environment we created here later in another lab to deploy the Device Ordering solution using Azure Dev Ops, for that lab it will serve as the Test environment which 
   is why we are suggesting naming it Central Apps Test. In real word use, most likely it would be a team/project development environment that would be requested using a form like this.

1. Navigate back to the **Power Automate** portal, Go to **My flows (1)** list and open the flow you created **(2)**.

   ![](images/M03/pp108.png)

1. You should see the flow running. Select the start date to open it.

   ![](images/M03/pp109.png)

1. The flow is waiting for approval.

   ![](images/M03/M3-EX2-T4-S8.png)

1. Navigate to Outlook.

1. You should have an approval request email, select to open it.

    ![](images/M03/M3-EX2-T4-S10.png)

1. Select **Approve**.

    ![](images/M03/pp110.png)

1. Select **Submit**.

1. Go back to the flow browser tab.

1. The flow should succeed.

    ![](images/M03/pp111.png)

1. Navigate to the **Power Platform admin center**, and select **Environments**. The new environment should be listed there.

    ![](images/M03/M3-EX2-T4-S15.png)

1. You should also get an email.
 
    ![](images/M03/pp112.png)

1. You may test for request rejection if you like.


## CoE Environment Management Sample Implementation

#### The CoE starter kit includes a sample implementation of an environment management process you can tailor to your own needs. The following diagram illustrates the high-level process.

![](images/M03/M3-EX3-overview.png)

##### You can learn more about the details in How to use the Environment Management components - Power Platform | Microsoft Docs

##### Using the starter kit process can save you time, but as you saw in Exercises 1 and 2 the platform also supports you in building your custom processes.


## Exercise 3: Application Compliance Process

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


## Exercise 4: Welcome New Makers (Optional if you have time)

In this exercise, you will be importing a pre-built flow that is designed to identify new app makers and welcome them by sending an email with some information for new makers. 
Additionally, the flow will add the user to an Office 365 group, so you have an easy way to communicate with all the makers in the company.

### Task 1: Create Office 365 Group

1. Navigate to the **Azure portal** from the desktop.

1. If prompted to stay signed in, you can click **No**.

1. If an **Action required** pop-up window appears, click on **Ask later**.

1. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **"Cancel"** to skip the tour.

1. Select **Microsoft Entra ID**.

   ![](images/M03/Entra-ID.png)

1. Select **Groups**.

   ![](images/M03/Entra-ID-1.png)

1. Select **+ New group**.

   ![](images/M03/M3-EX4-T1-S4.png)

1. Select **Microsoft 365** for Group Type, enter **Lab Admin Makers** for Group Name, set the **Azure AD Roles** to **No**, and select **Create**.

   ![](images/M03/M3-EX4-T1-S5.png)

1. Open the group after it gets created.

   ![](images/M03/M3-EX4-T1-S6.png)

1. Select **Properties** and copy the **Object id**.

   ![](images/M03/M3-EX4-T1-S7.png)

1. Paste the object ID to a notepad, you will need it in future steps.


### Task 2: Import Flow

1. Navigate to **Power Automate**.

2. Make sure **Power Platform COE** environment is selected. Note: While we are using this here, in your tenant you might do this in an admin-focused environment or where you have 
   installed the CoE Starter Kit.

   ![](images/M03/M3-EX4-T2-S2.png)

3. Select **My Flows** and click **Import** and select **Import Package (Legacy)**. (For this step, you may not be able to access the content while you are in Incognito mode. If this is the case, simply switch to your normal browser).

   ![](images/M03/M3-EX4-T2-S3.png)

4. Select **Upload**.

5. Select the **Send Welcome Email** zip file and select **Open**. This will be in your lab resource files you downloaded named **SendWelcomeEmailToNewPowerAppsMakers_20190529192359.zip**.

   ![](images/M03/M3-EX4-T2-S5.png)

6. Select Configure for the flow.

   ![](images/M03/M3-EX4-T2-S6.png)

7. Select **Create as new** and select **Save**.

   ![](images/M03/M3-EX4-T2-S7.png)

8. Select **Configure** for **Power platform for Admins Connection**.

    ![](images/M03/M3-EX4-T2-S8.png)

9. Select the available connection and select **Save**.

   ![](images/M03/M3-EX4-T2-S9.png)

10. Select Action for **Office 365 Outlook Connection**.

11. Select the available connection and select **Save**.

12. Select **Configure** for **PowerApps for Admins Connection**.

    ![](images/M03/M3-EX4-T2-S12.png)

13. Select to select the available connection and select **Save**.

    ![](images/M03/M3-EX4-T2-S9.png)

14. Select **Configure** for **Office 365 Group Connection**.

15. Select **+ Create new**.

    ![](images/M03/M3-EX4-T2-S15.png)

16. Select **+ New connection**.

    ![](images/M03/M3-EX4-T2-S16.png)

17. Search for **Office 365 Groups** and select **Add**.

    ![](images/M03/M3-EX4-T2-S17.png)

18. Select **Create**.

19. Login with your maker credentials.

20. You should now have the connections listed in the image below.

    ![](images/M03/M3-EX4-T2-S20.png)

21. Go back to the Flow import.

22. Select **Refresh list**, select the connection you just added, and select **Save**.

    ![](images/M03/M3-EX4-T2-S22.png)

23. Select Action for **Office 365 Users Connection**.

24. Select the available connection and select **Save**.

25. Repeat this for the **Office 365 Outlook Connection**.

26. Select **Import** and wait for the import to complete.

    ![](images/M03/M3-EX4-T2-S26.png)

27. The flow should import successfully.

    ![](images/M03/M3-EX4-T2-S27.png)


### Task 3: Edit and Test Flow

1. Navigate to the maker portal https://make.powerapps.com and select the **Central Apps Test** **environment**.

   ![](images/M03/M3-EX4-T3-S1.png)

1. Select **Apps (1)**, then **+ New app** > **Start with a page design (2)**.

   ![](images/M04/po29.png)

1. Click on **+** on blank canvas app. Make sure **Tablet** is selected.

   ![](images/M04/po30.png)

4. Enter **Test app** for App name, select **Tablet** for format, and select **Create**.

   ![](images/M03/M3-EX4-T3-S4.png)

5. The app designer should open. Select **Save** at the top right of the page.

   ![](images/M03/M3-EX4-T3-S5.png)

6. Select the **Back** button.

   ![](images/M03/M3-EX4-T3-S6.png)

7. Go back to the app maker main page by selecting the **Back** button.

8. Select **Solutions**.

9. Select **Publish all customizations** and wait for the publishing to complete.

   ![](images/M03/M3-EX4-T3-S9.png)

10. Navigate to Power Automate and select the **Power Platform CoE** environment.

11. Select **My Flows**.

12. Locate the flow you imported and select **Edit**.

    ![](images/M03/M3-EX4-T3-S12.png)

13. Expand the **Recurrence** and make sure the flow is set to run once a day.

    ![](images/M03/M3-EX4-T3-S13.png)

14. Expand the **Office Group ID** step.

15. Clear the current **Group ID**.

16. Copy the **Group ID** from your notepad and paste it here.

    ![](images/M03/M3-EX4-T3-S16.png)

17. You may examine the steps of the flow.

18. Select **Save**.

19. Select on the back button.

    ![](images/M03/M3-EX4-T3-S19.png)

20. **Turn on** the flow if needed.

21. Select **Run**.

    ![](images/M03/M3-EX4-T3-S21.png)

22. Select **Run Flow**.

    ![](images/M03/M3-EX4-T3-S22.png)

23. Select **Done**.

24. **Refresh** every few seconds until the flow status changes.

25. Your flow run should succeed.

    ![](images/M03/M3-EX4-T3-S25.png)

26. Go back to the Azure portal

27. Select **Microsoft Enta ID**.

28. Select **Groups** and open the group you created.

    ![](images/M03/M3-EX4-T3-S28.png)

29. Select **Members**. You should have at least one member.

    ![](images/M03/M3-EX4-T3-S29.png)
    
31. Navigate to Outlook.

32. You should get a welcome email. Open the email. If you don’t get an email, it is probably because you didn’t create an application in the past 24 hours, create a new Power App and run 
    the flow again.
    
    ![](images/M03/M3-EX4-T3-S31.png)

### Review

In this lab, you have accomplished the following:

- Exercise 1 - Created Environment Request Form
- Exercise 2 – Created Environment on Form Submit
- Exercise 3 – Application Compliance Process
- Exercise 4 – Welcome New Makers (Optional if you have time)


### You have successfully completed this lab.
