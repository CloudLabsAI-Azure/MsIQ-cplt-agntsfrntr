# Lab 04: Automate Zava Retail IT Asset Management with Microsoft 365 Copilot App Builder

## Estimated Duration: 40 Minutes

## Overview

In this lab, you will use **App Builder** inside Microsoft 365 Copilot to create a fully functional business application - using nothing but natural language. You will describe what you want, watch Copilot build it in real time, refine it through conversation, and publish it for your team.

You are an IT Asset Manager at Zava Retail, a growing retail chain with over 1,200 employees across 15 store locations and a central head office. Every quarter, your IT team manually tracks equipment issued to store managers and head office staff using a shared spreadsheet that is constantly out of date. The goal is to build a **Zava Retail IT Asset Tracker** app - a conversational, no-code tool inside the Microsoft 365 Copilot - that gives a live dashboard to manage asset assignments, track request statuses, and flag overdue items within the IT team.

## Lab Objectives

In this lab, you will perform the following:

- Exercise 1: Access App Builder and Describe Your App
- Exercise 2: Refine the App Through Conversation
- Exercise 3: Test the App as a Real IT Team Member Would
- Exercise 4: Publish the App and Share It with Your Team

## Scenario

At Zava Retail, nobody knows at a glance which employees have outstanding equipment requests, which assets are assigned, returned, or pending collection, or which requests are overdue and need chasing. The IT team needs a solution that provides real-time visibility.

**Key Personas**

- **IT Asset Manager (Learner):** Responsible for tracking all IT equipment issued to store managers and head office staff across 15 store locations.

## Exercise 1: Access App Builder and Describe Your App

App Builder works like a conversation. You describe the app you need in plain language - the same way you would brief a colleague - and Copilot builds it.

### Task 1: Access App Builder

1. In your browser, navigate to the following URL. Sign in with your credentials.

    ```
    https://m365.cloud.microsoft/
    ```

    - **Username**: <inject key="AzureAdUserEmail"></inject> **(1)**

        ![](./media/l3e1t1s1.png)

    - **Password**: <inject key="AzureAdUserPassword"></inject> **(2)**

        ![](./media/l3e1t1s2.png)

        If the **Stay signed in?** prompt appears after sign-in, Click **No**

        ![](./media/l3e1t1s3.png)

        ![](./media/l4e1t1s1.png)

2. On the left-hand navigation pane, click **More agents\>App Builder(Frontier)**.

    ![](./media/bb2.png)

3. Select **Add** to add this agent to your environment.  

    ![](./media/bb3.png)

4. The App Builder interface will open with a conversational input
    field - this is where you describe your app.

    ![](./media/bb4.png)

### Task 2: Describe Your App in Natural Language

1. In the App Builder input field, paste the following prompt and click the **Send** button.

    ```
    Build me an IT asset tracking app for Zava Retail. The app should
    let the IT team log equipment assigned to store managers and head office
    employees - including laptops, tablets, POS peripherals, and
    accessories, with an option to add new asset records via a form (Model,
    Serial Number, Type, Status, Assigned Employee). It should track each
    item's status as Assigned, Pending Collection, or Returned. I need a
    dashboard that shows total assets, how many are currently assigned, how
    many are pending, and overall completion rate. I also need a way to view
    all employees with their details visible directly in the main table, 
    manage tasks related to asset setup, and a section for IT resources 
    and policies.
    ```

    ![](./media/l4e1t2s1.png)

2. Once generation is complete, a live preview of your app will appear on the right side of the screen - with a navigation panel showing sections such as **Dashboard (1)**, **Assets (2)**, **Employees (3)**, **Tasks (4)**, **Resources (5)**, and potential **Feedback**.

    ![](./media/l4e1t2s2.png)

3. On the left side, Copilot will summarize what it built and may suggest enhancements. Read through its summary before proceeding.

    ![](./media/l4e1t2s3.png)

## Exercise 2: Refine the App Through Conversation

### Task 1: Add Overdue Flagging to the Dashboard

1. The generated app likely shows asset counts but may not flag overdue items prominently. This is the most operationally critical feature for the IT team.

2. In the App Builder conversation input on the left, paste the below prompt and click the **Send** button.

    ```
    Add a section to the dashboard that highlights overdue asset requests
    - items that have been in Pending Collection status for more than 7
    days. Show the employee's name, asset type, and how many days are
    overdue.
    ```

    ![](./media/l4e2t1s1.png)

3. Confirm the dashboard now includes an overdue section with the fields you specified.

    ![](./media/l4e2t1s2.png)

### Task 2: Add Task Priority Indicators

1. In the conversation input, paste the following prompt and click the **Send** button.

    ```
    In the Tasks section, add priority indicators - High, Medium, and
    Low - for each task. Also add a Due This Week view that filters to show
    only tasks due within the next 7 days.
    ```

    ![](./media/l4e2t2s1.png)

2. Once the response is generated, review the updated **Tasks** section in the preview.

3. Click into the **Tasks** section and confirm:

    - Priority labels are visible on each task
    - A **Due This Week** filter or view is available

        ![](./media/l4e2t2s2.png)

### Task 3: Enhance the Employee Section

The IT team needs to see not just a list of employees, but a clear record of what each person has been issued and whether their setup is complete.

1. In the conversation input, paste the following prompt and click the **Send** button.

    ```
    In the Employees section, add a column showing each employee's asset
    setup status - either Complete or In Progress. Also add a filter so the
    IT team can view only employees with In Progress status who may need
    follow-up.
    ```

    ![](./media/l4e2t3s1.png)

2. Review the updated **Employees** section.

    ![](./media/l4e2t3s2.png)

## Exercise 3: Test the App as a Real IT Team Member Would

### Task 1: Log a New Asset Assignment

1. In the app preview, navigate to the **Asset** section.

    ![](./media/l4e3t1s1.png)

2. To add a new asset record, paste the following details into the respective fields:

    - **Model**: ```Macbook Air```
    - **Serial Number**: ```AB568J```
    - **Type**: Select **Laptop**
    - **Status**: Select **Pending Collection**

        > **Note:** This asset is yet to be assigned.

        ![](./media/l4e3t1s2.png)

3. Confirm the record.

    ![](./media/l4e3t1s3.png)

### Task 2: Complete a Task and Check Progress

1. Navigate to the **Tasks** section.

    ![](./media/l4e3t2s1.png)

1. From the left navigation pane, select **Tasks**.

2. On the **Setup Tasks** page, review the available task categories:

   * **All**
   * **To Do**
   * **In Progress**
   * **Completed**
   * **Due This Week**

3. Select each category to filter the displayed tasks and verify that the task list updates accordingly.

    ![](./media/l4e3t2s1a.png)

1. Select any one of the task checkbox to mark it as completed.

    ![](./media/l4e3t2s2.png)

3. Return to the **Dashboard** and review that the overall completion percentage changes accordingly.

    ![](./media/l4e3t2s4.png)

## Exercise 4: Publish the App and Share It with Your Team

### Task 1: Publish the App

1. In App Builder, click the **Publish** button in the top-right corner of the screen.

    ![](./media/l4e4t1s1.png)

3. Once published, App Builder will generate a direct link to your app. Select **Share > Copy link** to copy this link.

    ![](./media/l4e4t1s2.png)

4. Select **Copy** to copy the link.

    ![](./media/l4e4t1s3.png)

    > **Note:** Save the link in your notes. It will be used in the upcoming task.

### Task 2: Validate the Published App

1. Open a new browser tab and paste the direct link you copied in Task 1 of the same exercise.

    ![](./media/l4e4t2s1.png)

2. Review that the app loads correctly with:

    - The correct app name and dashboard visible
    - Navigation sections (Employees, Tasks, Resources) accessible
    - The overdue items section present on the dashboard

        ![](./media/l4e4t2s2.png)

### Task 3: Share and Brief Your Team

1. Return to App Builder. In the conversation input, paste the following prompt and click the **Send** button.

      ```
      Draft a brief message I can send to the Zava Retail IT team
      explaining what this app does, how to log a new asset assignment, and
      how to check overdue items.
      ```

      ![](./media/l4e4t3s1.png)

2. Copilot will generate a ready-to-send team briefing. Review the briefing and note any required edits.

      ![](./media/l4e4t3s2.png)

3. Copy the briefing and the direct app link - these are what you would share with the IT team in a real deployment.

      ![](./media/l4e4t3s3.png)

## Summary

In this lab, you have completed the following:

- Accessed **App Builder** inside Microsoft 365 Copilot and used natural language to describe the Zava Retail IT Asset Tracker, resulting in a functional generated app
- Navigated through all sections of the generated app and refined it with at least three targeted conversational prompts (overdue flagging, task priority indicators, employee status column)
- Tested the app end-to-end through a realistic IT scenario that includes logging a new asset assignment, marking a task as complete, and verifying dashboard progress
- Published the app, validated the live published experience, and generated a team briefing using App Builder's conversational interface

## You have successfully completed the lab!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](./media/Next.png)
