# Lab 1: Transform Zava Retail Store Operations with a Smart Email Triage & Productivity Agent

## Estimated Duration: 40 Minutes

## Overview

In this lab, you will explore the **Workflows Agent** in Microsoft 365 Copilot as an AI-powered orchestration engine that goes beyond traditional automation. Instead of building static workflows, you will design intelligent, adaptive workflows (agents) that can plan, execute, and improve tasks using natural language.

You will build an **Intelligent Email Triage Agent** for Zava Retail — a rapidly growing omnichannel retailer facing high volumes of communication across customers, suppliers, and internal teams. The agent will automatically run every weekday morning, review unread emails from the last 24 hours, identify urgent and actionable items, categorize messages intelligently, generate summaries with next steps, and deliver structured output to Microsoft Teams. You will also use Work IQ to provide productivity and workload insights.

## Lab Objectives

In this lab, you will perform the following:

- Exercise 1: Access the Workflows Agent
- Exercise 2: Build the Zava Email Triage Workflow
- Exercise 3: Configure an Autonomous Workflow
- Exercise 4: Integrate Work IQ to Retrieve Zava Leadership Insights

## Scenario

Zava Retail teams receive hundreds of emails daily from customers (complaints, returns, inquiries), suppliers (inventory updates, delays), and internal teams (approvals, escalations). This results in missed urgent emails, slow response times, employee burnout, and lack of visibility into priorities.

**Key Personas**

1. **Marie Brown – Customer Support Manager:** Manages the customer support inbox, handles escalations and SLA compliance, and coordinates with logistics.

2. **David Turner – Supply Chain Coordinator:** Tracks vendor communications, manages inventory updates and delays, and coordinates with warehouses.

3. **Patricia Gray – Operations Head:** Oversees business operations across departments, tracks productivity and workload, and ensures operational efficiency.

## Exercise 1: Access the Workflows Agent

You are Marie (Customer Support Manager) logging into Microsoft 365 Copilot to automate email triage.

1. Navigate to the following URL to open Microsoft 365 Copilot.

    ```
    https://m365.cloud.microsoft/chat/
    ```

2. Sign in with your Microsoft 365 Copilot account credentials.

    - **Username**: <inject key="AzureAdUserEmail"></inject> **(1)**

        ![](./media/image1.png)

    - **Password**: <inject key="AzureAdUserPassword"></inject> **(2)**

        ![](./media/image101.png)

3. Click **Yes** to stay signed in.

    ![](./media/image3.png)

4. After successful login, you will see the **Copilot Chat** home page.

    ![](./media/b1.png)

5. In the **left navigation**, select **Agents** and explore the Agent Store.

    ![](./media/b2.png)

6. Scroll down and look for the **Workflows (Frontier)** option under the **Built by Microsoft** header.

    ![](./media/b4.png)

7. Select **Add** to add the **Workflows  (Frontier)**.

    ![](./media/b5.png)

    Now your agent is ready to use.

    ![](./media/b6.png)

## Exercise 2: Build the Zava Email Triage Workflow

### Task 1: Populate the Inbox with Sample Emails

Populate the Outlook inbox with realistic unread sample emails so the Zava Email Triage Agent can analyze, categorize, and generate actionable insights from them during workflow execution.

1. Navigate to `C:\Lab Files\Lab 1-Lab files` and open the **Sample Emails for Lab1** file. Here you will find all the sample emails that will be used in this lab.

    ![](./media/b7.png)

1. Open a new tab in your browser and navigate to the following Outlook URL:
   ```
   https://outlook.office365.com/mail/
   ```

1. Select the ODL user account

    ![](./media/image15aa.png)

1. Click on the **New mail** button in the top left corner.

    ![](./media/image15a.png)

1. Copy the subject and body of the first sample email from the `Sample Emails for Lab1` file and paste them into the email editor.

1. In the **To** field, enter the current lab user's email address: **Username** - <inject key="AzureAdUserEmail"></inject>

1. Click **Send** to send the email to yourself.

    ![](./media/image15b.png)

1. Repeat the same steps for the remaining 5 sample emails in the file so that there are at least 6 unread sample emails in your inbox.

### Task 2: Describe the Workflow in Natural Language

1. Define Business Logic (Prompt) in the Workflow (Frontier) chat. Paste the below prompt and click **Send**.

    ```
    Each weekday morning, review unread emails from the last 24 hours.
    Focus on:
    - Customer complaints and escalations
    - Supplier/vendor updates
    - Internal approvals or urgent requests

    Categorize emails into:
    - Urgent – Needs immediate action
    - Action Required – Needs response
    - FYI – Informational

    For each email include:
    - Sender
    - Subject
    - Summary
    - Any deadlines
    - Suggested next steps

    Highlight:
    - Customer complaints impacting SLA
    - Supplier delays affecting inventory

    Send the structured summary to myself on Microsoft Teams email id -
    <inject key="AzureAdUserEmail"></inject>.
    ```

    > **Note:** The email ID will be automatically replaced with the username you are currently using to execute this lab.

    ![](./media/image11.png)

2. Select **Save** on the top right corner of the **Workflow** window to run the actions automatically. Your workflow is now created and ready to test.

    ![](./media/image12.png)

3. Select **Test** to review the output.

    ![](./media/image13.png)

4. Once the testing is successful, it will show the test duration and result as a success confirmation.

    ![](./media/image14.png)

    Once the test process is completed, review that it:

    - Creates a scheduled trigger (weekday mornings)
    - Connects to:
        - Outlook (email ingestion)
        - Dataverse AI (reasoning)
        - Teams (output delivery)
    - Applies AI reasoning for categorization and summarization.

    > **Note:** You did not configure connectors manually — Copilot did it. Test process can take 5–10 minutes. Wait until the process is completed.

### Task 3: Validate Output

After processing your prompt, you will see the run results:

1. Navigate to the following URL to view emails in Outlook.

    ```
    https://outlook.office365.com/mail/
    ```

    > **Note:** You need to send different types of sample emails to the account to verify that the workflow triggers a notification in Microsoft Teams. If you do not have any new unread emails in your inbox, you will need to send test emails to validate the workflow and outputs.

    ![](./media/image15.png)

2. Review the email categorization accuracy.

    ![](./media/image16.png)

3. Navigate to the following URL to view the output in Microsoft Teams.

    ```
    https://teams.cloud.microsoft/
    ```

    ![](./media/image17.png)

    ![](./media/image18.png)

4. Check for the following test results for Zava Retail:

    - Are customer complaints marked as Urgent?
    - Are supplier delays highlighted?
    - Are summaries actionable?
    - Is the Teams message structured clearly?

## Exercise 3: Autonomous Workflow

Marie Brown (Customer Support Manager) wants to reduce missed follow-ups.

1. Navigate to the following URL to open Microsoft 365 Copilot.

    ```
    https://m365.cloud.microsoft/chat/
    ```

2. Go to the **Workflows (Frontier)** agent.

3. Paste the below prompt in the chat and select **Save**.

    ```
    When a new email arrives in Outlook with "Urgent" in the email subject:
    Send a Microsoft Teams reminder with an Urgent timeline to respond to the email.
    If there is no email response within 5 minutes:
    Send an escalation notification on email and Microsoft Teams.

    When a new email arrives in Outlook with "Urgent" in the email subject:
    Send a Microsoft Teams reminder to "<inject key="AzureAdUserEmail"></inject>" to respond to the email instantly.
    If the email is still not responded to in 2 hours:
    Send an escalation notification to Microsoft Teams.
    ```

    > **Note:** The email ID will be automatically replaced with the username (Email ID) you are currently using to execute this lab.

    ![](./media/image26.png)

4. Once the workflow is saved, select **Test**.

    ![](./media/image27.png)

5. Review the outcome:

    - Automated follow-ups
    - Escalation logic activated

6. Review the automated follow-up message sent on Teams. It ensures that urgent emails are not missed.

    ![](./media/image28.png)

7. Once the mentioned time of 2 hours has passed, review the automated escalation message on Teams.

    > **Note:** Currently, the last step of the workflow cannot be executed until the 2-hour mark is reached. The flow will send the Teams message after the 2-hour mark is reached.

    ![](./media/image29.png)

## Exercise 4: Integrate Work IQ to Retrieve Zava Leadership Insights

Patricia Gray (Operations Head) wants visibility into workload and burnout risks at Zava Retail.

### Task 1: Add Workload Analysis

1. Navigate to the following URL to open Microsoft 365 Copilot.

    ```
    https://m365.cloud.microsoft/chat/
    ```

2. Go to the **Workflows (Frontier)** agent.

3. Paste the below prompt in the chat and select **Save**.

    ```
    Analyze my email workload patterns.
    When a new email arrives in Outlook:

    After every new email received:

    Send me a summary in Microsoft Teams at
    <inject key="AzureAdUserEmail"></inject> that includes:
    - Total number of emails received on the same day
    - Number of emails marked as High Importance on the same day
    - Number of emails received after 6 PM, in non-working hours.

    Include a short note indicating if workload is high based on these counts.
    ```

    > **Note:** The email ID will be automatically replaced with the username (Email ID) you are currently using to execute this lab.

    ![](./media/image30.png)

4. Select **Test**.

    ![](./media/image31.png)

5. Review the output:

    - Adds Work IQ intent to workflow
    - Extends AI reasoning layer

6. Review the Email workload summary and intensity.

    ![](./media/image32.png)

### Task 2: Classify Workload

1. Navigate to the following URL to open Microsoft 365 Copilot.

    ```
    https://m365.cloud.microsoft/chat/
    ```

2. Under the **Workflows (Frontier)** agent, paste the below prompt in the chat and select **Save**.

    ```
    Create a workflow to classify the workload into:
    - Low
    - Moderate
    - High
    Also flag the following conditions:
    - Email overload
    - After-hours work
    - Urgent response pressure
    ```

    ![](./media/image33.png)

3. Select **Test**.

    ![](./media/image34.png)

4. Review the output:

    - Adds classification logic
    - Introduces conditional reasoning
    - Tags workload states

5. After the test run, verify:

    - Workload category appears (Low/Moderate/High)
    - Flags are visible in output

    ![](./media/image35.png)

### Task 3: Generate Insights

1. Navigate to the following URL to open Microsoft 365 Copilot.

    ```
    https://m365.cloud.microsoft/chat/
    ```

2. Under the **Workflows (Frontier)** agent, paste the below prompt in the chat to turn raw signals into leadership insights. Select **Save**.

    ```
    When a new email arrives, analyze today's email workload and patterns.

    Based on today's email workload and patterns, identify:
    - Risks such as burnout or overload
    - Inefficiencies in handling emails
    - Missed priorities
    Provide 3 actionable recommendations to improve productivity.
    ```

    ![](./media/image36.png)

3. Once the workflow is saved, select **Test**.

    ![](./media/image37.png)

4. Review the output:

    - Adds insight generation layer
    - Uses AI reasoning to interpret patterns
    - Produces structured recommendations

5. After running the workflow, check that the Teams output includes:

    - Risks (e.g., burnout risk)
    - Inefficiencies
    - Missed priorities
    - 3 recommendations

    ![](./media/image38.png)

### Task 4: Add Adaptive Intelligence

1. Before adding adaptive intelligence, first add some sample tasks to Teams Planner so that the agent can fetch data from there.

2. Navigate to the following URL.

    ```
    https://teams.cloud.microsoft/
    ```

3. From the left navigation, select the **three dots (...)** and then select **Planner**.

4. Click **+ Create a Plan**.

    ![](./media/b8.png)

5. Click **Create basic plan**.

    ![](./media/b9.png)

6. Enter the plan name as +++Zava Retail FY-26+++ and click **Create basic plan**.

    ![](./media/b10.png)

7. Select **+ Add task**.

    ![](./media/b11.png)

8. Enter the task name as +++knowledge transfer with CRM Team+++ set any due date and then click the **Add task** button to add the task to the planner.

    ![](./media/b12.png)

9. Similarly, add the following tasks to the planner:

    - +++Prepare onboarding program training+++
    - +++Prepare training for vendor program+++
    - +++Prepare training for new joiners+++

10. Navigate to the following URL to open Microsoft 365 Copilot.

    ```
    https://m365.cloud.microsoft/chat/
    ```

11. Under the **Workflows (Frontier)** agent, paste the below prompt in the chat to make the agent dynamic and context-aware. Select **Save**.

    ```
    When work activity is detected outside business hours (after 6 PM):

    If the number of assigned tasks is greater than 5:

    Send a notification in Microsoft Teams to me that includes:
    - A message indicating high workload and potential overload risk
    - A list of current tasks

    Also include suggestions to:
    - Delegate some tasks to team members
    - Rebalance workload for the next day
    ```

    ![](./media/image39.png)

12. Select **Test**.

    ![](./media/image40.png)

13. Review the output:

    - Adds **conditional logic (IF-THEN)**
    - Enables adaptive responses
    - Personalizes recommendations

14. Review the output after the test run is completed. When the workload is high, enhanced recommendations will appear automatically. The overload risk is also highlighted explicitly.

    ![](./media/image41.png)

## Summary

In this lab, you have completed the following:

- Accessed the Workflows Agent in Microsoft 365 Copilot and built an Intelligent Email Triage Agent for Zava Retail
- Built a scheduled workflow that runs every weekday, reviews unread emails, categorizes them into Urgent, Action Required, and FYI, and sends structured output to Microsoft Teams
- Configured an autonomous follow-up and escalation workflow triggered by emails with "Urgent" in the subject
- Integrated Work IQ to analyze email workload patterns, classify workload intensity, generate leadership productivity insights, and add adaptive conditional logic to reduce employee burnout

## You have successfully completed the lab!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](./media/Next.png)
