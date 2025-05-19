## Admin in a day

#### Please note- the exercises provided here should be completed in a non-production environment. Often you will be assigned an environment by your facilitator. However, if you are completing these labs on your own, make sure to provision a developer or trial environment.

# M01-HOL-Securing your Tenant


## Lab Scenario

In this hands-on lab, you will act as an environment administrator for Fabrikam, supporting the adoption of the Power Platform while ensuring compliance with the organization's data and security policies. Your responsibilities include enabling employees to build Power Apps and Power Automate flows to boost productivity, while also maintaining control over data governance. You will begin by assessing existing Power Platform usage across the organization and then implement baseline security policies to align with Fabrikam’s compliance requirements.

## Lab Objectives

In this lab, you will complete the following exercises:

- Exercise 1 - Exploring existing Power Platform usage
- Exercise 2 – Plan an environment strategy
- Exercise 3 – Plan a DLP strategy
- Exercise 4 – Evaluate the impact of adding DLP
- Exercise 5 – Configure a security role

### Lab Test Environment

This lab is designed to be completed in an environment setup for multiple students to complete the Admin in a day series of hands-on labs. We will be providing an environment for you to 
utilize for this course.

You will be assigned one or more users to use to complete the tasks. Because this is a shared environment, some tasks that require a tenant Global Administrator or a Service Administrator will already be completed. Your account will only be an environment administrator.


## Exercise 1: Exploring existing Power Platform usage

### Scenario

In this exercise, you will be exploring the tenant to see what Power Platform assets have already been created. Specifically, you will be looking at the following:

- Environments that have been created
- Data Loss Prevention (DLP) policies.

>**Note**: Before Proceeding with the HOL, rename the default environment display name with **User and Team Productivity**.

### Task 1: Review existing environments

1. Navigate to **Power Platform admin center** by following the link https://aka.ms/ppac, and select **Environments**.

    ![](images/pp-2.png)

2. Review the list of environments. These are the environments that are available for you to manage.

   ![](images/pp-3.png)

3. Notice the **Type** column, you can see Fabrikam is already using several types of environments.

4. You can filter and order environments. Select on the **Type (1)** column, select filter by **Production (2)**, and Select **Apply (3)**.

   ![](images/M01/M1-EX1-T1-S4.png)

5. You should now see only the **Production** type environments.

   ![](images/M01/M1-EX1-T1-S5.png)

6. Select on the **Type (1)** column again and filter by **Default (2)** and **Production (3)**, and select **Apply (4)**.

   ![](images/M01/M1-EX1-T1-S6.png)

7. You should now see **Production** and **Default** environments.

8. Select on the **Environments (1)** column, select **Sort order** by **Ascending (2)**, and select **Apply (3)**.

   ![](images/M01/M1-EX1-T1-S8.png)

9. The list of environments will show **Production** and _Default_ environments ordered by environment name in ascending order.

   ![](images/M01/pp1.png)

10. Now remove the filters, click on **Clear all filters (1)** and then **Apply (2)**. You should see all environments.

    ![](images/M01/pp2.png)

11. Next, notice all the environments with **Thrive Hr** in the name. These are a set of environments Contoso uses to manage the lifecycle of their Thrive apps; a suite of employee 
    engagement apps. They are built in Thrive Hr - Dev and then are promoted to Test -> UAT-> Production after testing by your admin team.

    ![](images/M01/pp3.png)    

12. Select on the **Type (1)** and filter by **Default (2)** and then **Apply (3)**.

    ![](images/M01/pp4.png)  

13. This is the environment in which all users are makers and can build their apps and flows. Think of this environment as supporting personal productivity use of the platform. This 
    is also the default location used by any customizations built with Power Apps in Office apps. The default environment can’t be deleted, but you can rename it to make clear its 
    purpose. For example, some name it _User__and Team Productivity_ like we have in this tenant.

14. Select the default environment by Selecting the name in the list to drill down into the detail page.

    ![](images/M01/pp5.png)

15. In the **Access** section, you’ll notice that there are multiple options to choose from, which can be used to determine who has access to which items.

16. Select **See all** under **Security Roles**.

    ![](images/M01/po20.png)

17. From here, you can review all of the security roles for your company and manage their access to the company’s data. By default, users have access to all security roles. The business 
    unit currently listed is the same as the tenant and these are assigned to all users by default. Managed roles can be modified to create.

    ![](images/M01/pp6.png)    

18. Use the search box in the top right and enter **Environment Maker (1)** to find the **Environment Maker (2)** security role, then select the lone result.

    ![](images/M01/pp7.png)
 
    >**Note:** Notice that the org is listed as the **Business Unit**; this means everyone in the organization will have this role by default. For environments other than the default, you control this. 
    However, default is special and Tenant can’t be removed from the role.

20. Go back to the Environment Details page.

    ![](images/M01/pp8.png)

21. In the **Resources** section, Select **Power Apps**.

    ![](images/M01/pp9.png)

22. These are apps built by users in your default environment. Notice many of them are just test names because this is where a lot of users will experiment and build their first app. As 
    you scroll down the list you might notice some names are more deliberate e.g., Product Showcase. Later in the course, we will talk about how to identify these upcoming apps so you 
    can help guide them to ensure they mature and have adequate governance.

    ![](images/M01/pp10.png)


### Task 2: Review existing Data policies

1. Expand **Policies** and select **Data policies** on the left navigation.

    ![](images/M01/pp12.png)

1. Review the list of existing policies.

    - As the login you are using is not a tenant admin but only an environment admin, you will see policies that impact environments of which you are a member.

    - As an environment admin or regular environment user, you will also be able to see any tenant-wide DLP policies applied to your environment. However, you would not be able to edit 
      those tenant-side DLP policies.

    - As a Global Admin, Admin, Power Platform Service Admin or D365 Service Admin in your tenant, you will see all policies that exist in your tenant, even those that you did not 
      create.

1. Notice the Contoso Global DLP policy exists that is intended to span all environments (except selected ones) and represents the global DLP policy. For this lab environment Contoso 
   Global DLP policy has 4 environments selected instead of All except 4.

1. You will also notice a DLP for **Thrive Exceptions**. That team had worked with the IT department to agree on exceptions they needed for their environments and their environment would 
   be excluded from the Contoso Global DLP. This exception DLP policy would have their environments included and apply only to them.

   ![](images/M01/M1-EX1-T2-S5.png)

1. Select the **Contoso Global DLP (1)** and select **Edit Policy (2)**.

   ![](images/M01/M1-EX1-T2-S6.png)

1. Select **Prebuilt connectors (1)** and review the **Business (2)** connectors.

    ![](images/M01/M1-EX1-T2-S7.png)

1. Select **Scope** and **Environments** to see how it they are configured.

   ![](images/M01/M1-EX1-T2-S8.png)

1. Once finished, select **Cancel** button in the bottom right to head back to the Data Policies screen.

   ![](images/M01/pp13.png)

1. Select the **Thrive Exception DLP (1)** and select **Edit Policy (2)**.

    ![](images/M01/M1-EX1-T2-S10.png)

1. Select on the **Prebuilt connectors** and select the **Business** tab. Based on the use case for the Thrive application the connectors in the Business group have been established. 
    You can also see how Scope and Environments are configured to only select the Thrive environments.

    ![](images/M01/M1-EX1-T2-S11.png)

1. To exit this screen, select the **Cancel** button on the bottom right of the screen again.

    ![](images/M01/pp14.png)


## Exercise 2: Plan an environment strategy

In this exercise, you will be reviewing the scenario for Fabrikam that explains their current situation. After reviewing you will evaluate and propose an environmental plan.

### Task 1: Read about the current situation at Fabrikam

In this task, read the following and take notes that would help you propose an environment plan for Fabrikam.

You have recently joined the newly formed Power Platform center of Excellence team at Fabrikam and are responsible for establishing a governance strategy. Currently, there is no 
governance process established and employees can create apps, flows and even environments without any control. Fabrikam has been in existence for 40 years and has 4,500 employees 
at multiple office locations in the US, UK and EU. Fabrikam employees are all licensed for Office 365 E3 and a growing number of them have either Power Automate or Power Apps per user 
licenses. Over the last 6 months, Fabrikam’s management realized that this was greatly improving productivity, but they recognised without some planned governance it could easily get 
out of control. About 50 of the users are more advanced power users of the platform always looking at ways to push its limits. Fabrikam’s sales team of 100 users also use a heavily 
customized Dynamics 365 Sales app deployment.


One of the first things you did was look in the admin center to see how many environments were there. Currently, in the tenant, there are 45 environments with a variety of names that users 
choose. The majority of the applications looked like they were in the default environment or a couple of other custom environments that had been created. There was one environment that 
was the production Dynamics 365 application environment used by the sales team.

The most organized department is market research, they built an application that is used daily for conducting their market surveys. Currently, there is just a single custom environment 
named Market Research that supports the application. There are a couple of people in the department who are app makers making all the changes. They tend to do them in the late 
afternoons and evenings and publish them when nobody's around to avoid impacting other users. There is not currently any testing done before the app is published other than by the person 
making the changes. They are open to the testing idea but are not sure how to do it with a single environment.

You found out that the new environments have stopped being created simply because they have run out of storage from creating too many environments. When you asked about this you were 
handed a stack of requests that claimed they needed new environments. The following are the priority requests; we will ask you to help identify how to handle these when you fill out the 
environment strategy template.

- Request 1: A user would like to build a set of Power Automate flows that help organize their Outlook inbox and tag emails.

- Request 2: The VP of Service wants to build some custom apps to support their teams; like how the market research team has done.
    
- Request 3: Marketing wants to build an app that makes it easy to publish tweets on Twitter using the Twitter connector. They also plan to create Power Automate flows that notify 
    them of mentions along with the sentiment of the message.

- Request 4: HR would like to try the Crisis Comms app that Microsoft published and would like an environment for it to run in.
    
- Request 5: A user would like to build an app that uses a custom connector for a 3rd party service and also uses the DropBox connector.

Yesterday you got some good news, another 30GB of storage capacity for environments had been procured. You also got permission to put in place the necessary steps to ensure it does not 
get wasted.

### Task 2: Build an Environment Plan

In this task, you use the information from Task 1’s scenario to help you propose an environment plan for Fabrikam. To help you build the plan we have prepared a worksheet with questions 
for you to answer.

1. Open the File explorer, navigate to `C:\LabFiles\PPAdminAttendee%20(1)\PPAdminAttendee\M01 - HOL - Securing your tenant\Resources` **(1)** then select **M01 – HOL Environment Plan Worksheet.docx (2)** from the Resources folder.

    ![](images/M01/pp15.png)

1. Complete it by answering each of the questions. You should spend no more than 10 minutes on this before 
   proceeding to the next task.


### Task 3: Review the example environment plan and compare it to yours

In this task, we have provided you with a completed environment plan. Review the answers and compare them to the ones you built in the prior task.

1. Open the Example Environment Plan document **M01 – HOL Environment Plan Example.docx** and compare the answers to the one you completed in the previous task.

    ![](images/M01/pp16.png)

2. Talk to your trainer about any significant differences that do not make sense to you.


## Exercise 3: Plan a DLP strategy

### Scenario

In this exercise, you will be planning a DLP strategy for Fabrikam using the same scenario background information from the last exercise.

### Task 1: Build a DLP Plan

In this task, you use the information from the last exercise’s scenario to help you propose a DLP plan for Fabrikam. To help you build the plan we have prepared a worksheet with questions 
for you to answer.

1. Open **M01 – HOL DLP Plan Worksheet.docx** from the Resources folder and complete it by answering each of the questions. You should spend no more than 10 minutes on this before proceeding 
   to the next task.

 

### Task 2: Review the example DLP plan and compare it to yours

In this task, we have provided you with a completed environment plan. Review the answers and compare them to the ones you built in the prior task.

1. Open the Example Environment Plan document **M01 – HOL DLP Plan Example.docx** and compare the answers to the one you completed in the previous task.

2. Talk to your trainer about any significant differences that do not make sense to you.


## Exercise 4: Evaluate the impact of adding DLP

### Scenario

In this exercise, you will create an environment, and a flow, and then view the impact of adding a DLP policy.

### Task 1: Create a trial environment

1. Navigate to the Power Platform admin center.

2. Select **Environments (1)** and select **+ New (2)**.

   ![](images/M01/pp19.png)

3. Enter **My Sandbox-<inject key="Deployment ID" enableCopy="false" />** for Name, select Region as **United States - Default**, select **Trial** as Type, select **Yes** for Add a Dataverse data store?, and select **Next**.

   ![](images/M01/po6.png)

4. Leave the default values for **Language (1)** and **Currency (2)**. Under Security group select **+ Select (3)**.

    ![](images/M01/pp20.png)

1. Then set your security group to **All Contoso users (1)** then select **Done (2)**.

   ![](images/M01/pp21.png)

1. Select **Save**.

   ![](images/M01/po7.png)

5. Wait for the environment to be created. The state will change to **Ready** when the environment is ready.


### Task 2: Create a flow to get the weather

1. Navigate to the **Power Apps** maker portal, click on the Environment **(1)** and select the environment you created **(2)**.

   ![](images/M01/pp23.png)

2. Select **Flows (1)** from the left, select **+ New flow (2)** and select **Scheduled cloud flow (3)**.

   ![](images/M01/M1-EX4-T2-S2-1.png)

3. Enter **Weather Flow (1)** for **Name**, select **Repeat every 1 Day (2)**, and select **Create (3)**.

    ![](images/M01/pp24.png)

4. Select **+ New step**.

5. Search for **MSN (1)** and select **Get current weather MSN Weather (2)**.

   ![](images/M01/M1-EX4-T2-S5.png)

6. Provide your **Location (1)**, select your preferred **Units (2)**, and select **+ New step (3)**.

   ![](images/M01/M1-EX4-T2-S6.png)

7. Search for **Send an email (1)** and select **Send an email (V2) Office 365 Outlook (2)**.

   ![](images/M01/M1-EX4-T2-S7.png)

8. Provide your email for **To:** **<inject key="AzureAdUserEmail"></inject> (1)** and enter **Current Weather (2)** for **Subject**.

9. Select on the Body enter `Current weather for:` **(3)** and select **Location (4)** from the Dynamic content pane.

   ![](images/M01/pp25.png)

10. Hit the **[ENTER]** key **,** enter **Temperature:** and search for **Temperature** and then select **Temperature** from the Dynamic content pane.

11. Hit the **[ENTER]** key **,** enter **Conditions:** and select **Conditions** from the Dynamic content pane.

12. You may add other values to the email.

    ![](images/M01/M1-EX4-T2-S10.png)

13. Select **Save**.

    ![](images/M01/po10.png)

14. Go to My Flows by selecting the back arrow button located on the top left of the page.

    ![](images/M01/M1-EX4-T2-S14.png)

15. Select to open the flow **(1)** and Select **Run (2)**.

    ![](images/M01/pp26.png)

17. Select **Run flow**.

    ![](images/M01/pp27.png)

18. Select **Done** and wait for the flow run to complete. 

19. Copy and paste the following link in browser https://outlook.office365.com/ to navigate to **Outlook** and You should get an email with the weather information.

    ![](images/M01/po12.png)

### Task 3: Create a DLP Policy

In this task, you will create an environment-specific DLP and see how it impacts your workflow.

1. Navigate back to the **Power Platform admin center**. If you’re on the **Power Apps** website, you can do this by selecting the **gear** in the header, and selecting **Admin Center**.

   ![](images/M01/M1-EX4-T3-S1.png)

1. Select **Data policies (1)** and Select **+ New Policy (2)**.

   ![](images/M01/M1-EX4-T3-S2.png)

1. Enter **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (1)** for **Name** and select **Next (2)**.

   ![](images/M01/pp28.png)

1. Search for Microsoft Dataverse, search for **Microsoft Dataverse (1)** then select **Microsoft Dataverse (2)**, and select **Move to Business (3)**. Choose carefully, you may have to expand the Name column to differentiate 
   between connectors in your search results.

   ![](images/M01/pp29.png)

1. Search for SharePoint, select **SharePoint (1)** and select **Move to Business (2)**.

   ![](images/M01/M1-EX4-T3-S5-1.png)

1. Search for Outlook, select **Office 365 Outlook (1)** and select **Move to Business (2)**.

   ![](images/M01/M1-EX4-T3-S6-1.png)

1. Select the **Business** tab.

1. You should now have three connectors moved to Business. Select **Next**.

   ![](images/M01/po14.png)

1. Skip the Custom connector by Selecting the **Next** button, we won’t be using any in this example.

1. Select **Add multiple environments (1)** from the options, then select **Next (2)**.

    ![](images/M01/M1-EX4-T3-S10.png)

1. Choose the environment you created **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (1)** and select **+ Add to Policy (2)**.

    ![](images/M01/po15.png)

1. Once done, select **Next**.

1. Review the policy, to make sure you have **(3) Business** connectors added, and only one **Environment** selected and select **Create policy**.

    ![](images/M01/M1-EX4-T3-S13.png)

1. From the **Power Apps** portal, click on **Power Platform (1)** and then select **Power Automate (2)**.

    ![](images/M01/pp30.png)

1. Make sure you are in the sandbox environment.    

    ![](images/M01/pp31.png)

1. Select **My flows**.

    ![](images/M01/M1-EX4-T3-S15.png)

1. The flow should now be suspended because of the **DLP** you created. Select to open the flow. This can take up to 5 minutes, wait a few minutes and then select refresh.

    ![](images/M01/M1-EX4-T3-S16.png)

     >**Note:** If your not able to see the status as **Suspended**. Navigate to **Weather Flow** flow and the click on **Save** again. Because sometimes Policy may not get reflected immediately. 

1. You should not be able to run the flow. There will be a notice at the top showing that the DLP is active and restricting access, and the **Status** should be suspended. Feel free to close the webpage/tab once you’ve confirmed it has been suspended.

    ![](images/M01/M1-EX4-T3-S17.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

   <validation step="3379fa81-ffc4-49c5-82db-97274e81a612" />


## Exercise 5: Configure a security role

### Scenario

In this exercise, you are going to import a pre-built Power Apps canvas app that was built in another environment. The application allows users to see a list of Projects stored in 
Dataverse. After importing you will build a Security Role to allow users to work with the Project table data. Finally, you will see how to share the application with a Microsoft Entra 
ID Security group and assign the security role you just built.

### Task 1: Import project management solution

1. Navigate to the **Power Apps** maker portal, click on **Environment (1)** and select The My Sandbox environment named **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (2)** you created.

   ![](images/pp-1.png)

2. Select **Solutions (1)** and select **Import solution (2)**.

   ![](images/M01/M1-EX5-T1-S2.png)

3. Select **Browse**.

4. Navigate to **C:\LabFiles\PPAdminAttendee%20(1)\PPAdminAttendee\M01 - HOL - Securing your tenant\Resources (1)** folder, select the **Fabrikam Project Management (2)** solution and select **Open (3)**.

   ![](images/M01/pp32.png)

5. Select **Next**.

   ![](images/M01/M1-EX5-T1-S5.png)

6. Select **Import** and wait for the import to complete. You should get a notification when the import succeeds.

7. Select **Publish all customizations** and wait for the publishing to complete.

   ![](images/M01/M1-EX5-T1-S7.png)

8. Select to open the solution you just imported.

   ![](images/M01/M1-EX5-T1-S8.png)

9. The solution should have six components.

    ![](images/M01/M1-EX5-T1-S9.png)

10. Select to open the **Import Sample Data – Projects** flow. You are going to run this flow to insert some sample project data for the app to use.

    ![](images/M01/M1-EX5-T1-S10.png)

11. Select **Edit**.

    ![](images/M01/M1-EX5-T1-S11.png)

12. At this point, you may be asked to sign in to the flow, click on **Sign in**.

    ![](images/M01/pp33.png)

    - Select **Continue**.

      ![](images/M01/M1-EX5-T1-S12.png)

13. Select to expand the **Parse JSON** step.

    ![](images/M01/M1-EX5-T1-S13.png)

14. Examine the sample records the flow will create.

15. Select **Save** and wait for the flow to be saved.

    ![](images/M01/M1-EX5-T1-S15.png)

16. Go back to the details view of the flow by selecting the back button.

    ![](images/M01/M1-EX5-T1-S16.png)

17. Open the flow again.

18. **Turn on** the flow if Status is off.

    ![](images/M01/M1-EX5-T1-S18.png)

19. Select **Run** to run the flow.

    ![](images/M01/M1-EX5-T1-S19.png)

20. Select **Run flow**.

    ![](images/M01/M1-EX5-T1-S20.png)

21. If prompted, select **Done** and wait for the run to complete.

    ![](images/M01/M1-EX5-T1-S21.png)

22. Select the browser back button.

    ![](images/M01/pp35.png)

23. Go back to the solution page, by selecting the **Back to Solutions** button. Click on the back arrow untill you get the **Power Apps**, **Solution** page.

    ![](images/M01/M1-EX5-T1-S23.png)

24. Select **Apps (1)** and select **Project List (2)** and click on **Play (3)** to run canvas application.

    ![](images/M01/pp36.png)

25. The application should load, and you should see the sample project records the flow created. Select the **+ New** to create a new Project.

    ![](images/M01/pp37.png)

26. Enter **Test Project (1)** for **Title**, select **Due date (2)** and select **Save and Close (3)**.

    ![](images/M01/pp38.png)

27. The application should create a new record and take you back to the list of projects.

     ![](images/M01/pp39.png)

28. Close the Project List application browser window or tab.


### Task 2: Create a security role

1. Navigate to the Power Apps maker portal and make sure you have your sandbox environment selected.

1. Select **Solutions (1)** and select to open the **Fabrikam Project Management (2)** solution.

   ![](images/M01/M1-EX5-T2-S2.png)

1. Select **+ New (1)** and select **Security (2)** > **Security role (3)**.

    ![](images/M01/M1-EX5-T2-S3.png)

1. Enter **Project Manager (1)** for **Role Name**, select the **Business unit (2)** from the drop down and select **Save (3)**.

   ![](images/M01/pp40.png)

1. Search for **Project (1)**, locate the **Project** table and click on the name of the entity. This action will give this role User rights to the Project entity **(2)**.

    ![](images/M01/pp42.png)

1. By clicking on the dropdown for the permissions, if you kept selecting the **Organization** on the label it would increase the permissions.

   ![](images/M01/pp43.png)

1. You will now give this role organization **Read** privilege. Select **Organization (1)** from the **None** drop down and click on **Save (2)**.

   ![](images/M01/pp44.png)

1. Click on **<-Back** to navigate back to the Fabrikam Project Management page.

   ![](images/M01/pp45.png)

1. Select **Publish all customizations** and wait for the publishing to be completed.

    ![](images/M01/M1-EX5-T2-S12.png)

1. Do not navigate away from this page.

### Task 3: Share app

1. Go back to the **Solutions** page by selecting the **Back to Solutions** button. Keep selecting the back arrow untill you get the **Power Apps, Solution** page.

   ![](images/M01/pp46.png)

1. Click on **Apps (1)**, then choose **Project List (2)** application, and select **Share (3)**.

   ![](images/M01/po19.png)

1. Search for **lab back office (1)** and select it **(2)**.

    ![](images/M01/pp47.png)

1. Select **Manage access**.

   ![](images/M01/pp48.png)

1. Navigate to **Pending invites (1)** tab, Click on the **Data access (2)** drop down then select the **Project Manager (3)**. Make sure **User (4)** role is selected for **Apps** and then select **Share (5)**.

   ![](images/M01/pp50.png)

1. Close the share pane.
 

### Review

In this lab, you have accomplished the following:

- Exercise 1 - Explored existing Power Platform usage
- Exercise 2 – Planned an environment strategy
- Exercise 3 – Planned a DLP strategy
- Exercise 4 – Evaluated the impact of adding DLP
- Exercise 5 – Configured a security role


### You have successfully completed this lab.
