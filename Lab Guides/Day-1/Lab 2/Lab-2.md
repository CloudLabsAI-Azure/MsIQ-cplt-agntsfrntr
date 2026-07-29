# Lab 02: Elevate Zava Retail Intelligence with a Researcher Agent for Smarter Insights and Reporting

## Estimated Duration: 40 Minutes

## Overview

In this lab, you will learn how to use the **Researcher Agent** in Microsoft 365 Copilot to gather, summarize, and analyze organization-related information. The Researcher Agent can collect relevant data from your documents, emails, chats, and Teams messages, helping you create summaries, reports, and follow-ups on a given project or topic.

Zava Retail, a fast-growing omnichannel retailer, was preparing for a large-scale Festive Collection campaign launch. Over the last 90 days, multiple teams worked on vendor onboarding, marketing campaigns, inventory planning, and customer support readiness. Critical information was scattered across emails, Teams chats, documents, and meeting notes - making it difficult for leadership to gain a unified view. You will use the Researcher Agent to consolidate, analyze, and transform this fragmented data into actionable business intelligence.

## Lab Objectives

In this lab, you will perform the following:

- Exercise 1: Access the Researcher Agent
- Exercise 2: Run Your First Research Prompt (Campaign Intelligence)
- Exercise 3: Action and Decision Intelligence
  - Task 1: Identify Action Items
  - Task 2: Key Decisions
  - Task 3: Draft Leadership Email
  - Task 4: Meeting Preparation (Executive Readiness)
  - Task 5: Progress and Status Analysis
  - Task 6: Identify Gaps and Risks
  - Task 7: Document Discovery and Insights
  - Task 8: Generate Executive Communication

## Scenario

At Zava Retail, all critical information is scattered across various communication channels - emails (vendor discussions, escalations), Teams chats (campaign planning), documents (strategy decks, reports), and meeting notes. Due to this information fragmentation, there is no single source of truth, and the leadership team cannot see project status, risks, and dependencies.

**Key Personas**

**Patricia Gray - Operations Head:** Oversees campaign readiness, aligns cross-functional teams, and drives executive decisions. Cannot manually review hundreds of emails and documents, and needs quick insights before leadership meetings.

## Exercise 1: Access the Researcher Agent

Patricia logs into Copilot to review Festive Campaign readiness.

1. Navigate to the following URL to open Microsoft 365 Copilot.

    ```
    https://m365.cloud.microsoft/chat/
    ```
    
5. In the left **navigation pane**, look for **New Agents**.

    - If **Researcher** appears directly under the **Agents** section, select **Researcher**.

    ![](./media/b3.png)

    - If not, select **More agents**. In the **Agent Store** window, under the **Built by Microsoft** section, select **Researcher**.

    ![](./media/b4.png)

6. Select **Open** to access the Researcher agent.

    ![](./media/b5.png)

7. The **Researcher Agent window** opens in a new pane.

    ![](./media/b6.png)

## Exercise 2: Run Your First Research Prompt (Campaign Intelligence)

Patricia wants a complete overview of campaign progress for Zava Retail.

1. Before interacting with the agent, send some demo campaign emails to the current lab user from your own email so the Researcher Agent can access relevant data and produce meaningful insights and summaries. You can find the demo campaign emails at `C:\Labfiles\Lab 2 - Lab files`.

    ![](./media/image71.png)

2. To view the sample emails, navigate to the following URL.

    >**Note:** If you are unable to find the existing emails in Outlook, use the provided file and send the emails to the users from your personal email account.

    ```
    https://outlook.office365.com/mail
    ```

    ![](./media/image300.png)

3. Go to the Researcher agent, paste the following prompt in the prompt field, and then click the **Execute** button.

    ```
    Help me gather and summarize all recent discussions, documents, and
    emails related to Zava Retail Festive Campaign from the past 90 days.

    Include:
    - Campaign planning progress
    - Vendor onboarding updates
    - Inventory readiness
    - Marketing campaign activities
    - Key risks or delays
    ```

    ![](./media/image8.png)

4. Wait for the **Researcher Agent** to gather and summarize the data. The Researcher Agent may ask clarifying questions. Select the report length as **Short** and select/enter **"Go ahead with your best judgement"** and select the **Send** button.

    ![](./media/image9.png)

    > **Note:** Ensure that demo campaign emails and Teams messages are shared beforehand so the Researcher Agent can access relevant data and produce meaningful insights and summaries.

5. Review the Researcher agent's response. The agent searches across Outlook, Teams, and SharePoint documents to retrieve the following:

    - Aggregated insights
    - A structured summary
    - Campaign progress
    - Vendor updates
    - Risks
    - Strategic insights

6. Review the output:

    ![](./media/image10.png)

    ![](./media/image11.png)

    ![](./media/image12.png)

    ![](./media/image13.png)

    ![](./media/image14.png)

    ![](./media/image15.png)

    ![](./media/image16.png)

    ![](./media/image17.png)

    > **Note:** Generated outputs are non-deterministic and may vary across users, sessions, and environments.

## Exercise 3: Action and Decision Intelligence

Patricia Gray needs clear next steps and decisions. This exercise will help the Researcher Agent perform a task or take a specific action based on the data, findings, or situation.

### Task 1: Identify Action Items
 
1. In the Researcher agent, paste the below prompt in the field and then click the **Send** button.

    ```
    List all action items related to the Zava Festive Campaign.
    ```

    ![](./media/l2e3t1s1.png)

2. Review the output. Action items such as **Pending approval**, **Pending confirmation**, and **Under review** are identified as **Action Items**.

    ![](./media/l2e3t1s2.png)

    ![](./media/l2e3t1s3.png)

### Task 2: Key Decisions

1. Under the Researcher agent, paste the below prompt in the field and then click the **Send** button.

    ```
    Summarize key decisions made across emails and Teams discussions for the campaign.
    ```

    ![](./media/l2e3t2s1.png)

2. Review the output. The key decisions related to multiple action items and teams are summarized in the output.

    ![](./media/l2e3t2s2.png)

    ![](./media/l2e3t2s3.png)

### Task 3: Draft Leadership Email

1. Select the **new chat** button to start a new chat.

2. Under the Researcher agent, paste the below prompt in the chat panel and then click the **Send** button.

    ```
    Draft an email to the leadership team summarizing campaign readiness and participation.
    ```

    ![](./media/l2e3t3s1.png)

3. Wait for the **Researcher Agent** to gather and summarize the data. The Researcher Agent may ask clarifying questions. Select the report length as **Short** and select/enter **"Go ahead with your best judgement"** and select the **Send** button.

    ![](./media/l2e3t3s2.png)

4. Review the output:

    ![](./media/l2e3t3s3.png)

    ![](./media/l2e3t3s4.png)

    ![](./media/l2e3t3s5.png)

### Task 4: Meeting Preparation (Executive Readiness)

Meeting preparation prompts help you gather background information, summarize key updates, and identify action items or discussion points before a meeting. Patricia has a leadership review meeting next week and wants to be prepared.

1. Under the Researcher agent, paste the below prompt in the field and then click the **Send** button.

    ```
    Help me prepare for an upcoming meeting by summarizing recent communication and shared files about.
    ```

    ![](./media/l2e3t4s1.png)

2. Wait for the **Researcher Agent** to gather and summarize the data. The Researcher Agent may ask clarifying questions. Select the report length as **Short** and select/enter **"Meeting is the Q2 Sales Review on April 10"** and select the **Send** button.

    ![](./media/l2e3t4s2.png)

3. Review the output:

    ![](./media/l2e3t4s3.png)

    ![](./media/l2e3t4s4.png)

    ![](./media/l2e3t4s5.png)

4. Paste the below prompt in the field and then click the **Send** button.

    ```
    What topics have been discussed in past weekly team syncs?
    ```

    ![](./media/l2e3t4s6.png)

5. Review the output:

    ![](./media/l2e3t4s7.png)

    ![](./media/l2e3t4s8.png)

    ![](./media/l2e3t4s9.png)

### Task 5: Progress and Status Analysis

Progress and status updates help you review achievements, identify gaps, and plan next steps. Patricia Gray wants to update the current status, blockers, and overall campaign progress to the leadership team.

1. Under the Researcher agent, paste the below prompt in the field and then click the **Send** button.

    ```
    Summarize the current status and blockers for the Zava Festive Campaign.
    ```

    ![](./media/l2e3t5s1.png)

2. Review the output:

    ![](./media/l2e3t5s2.png)

    ![](./media/l2e3t5s3.png)

### Task 6: Identify Gaps and Risks

This section helps identify missing information, unclear points, or areas needing further investigation from research, meetings, or ongoing project activities. Patricia wants to uncover hidden risks.

1. Start a new conversation.

2. Under the Researcher agent window, paste the below prompt in the field and then click the **Send** button.

    ```
    What open questions or gaps remain in the Zava Festive Campaign?
    ```

    ![](./media/l2e3t6s1.png)

3. Wait for the **Researcher Agent** to gather and summarize the data. The Researcher Agent may ask clarifying questions. Select the report length as **Short** and select/enter **"Analyze sales data and customer feedback for gaps"** and select the **Send** button.

    ![](./media/l2e3t6s2.png)

4. Review the output:

    ![](./media/l2e3t6s3.png)

### Task 7: Document Discovery and Insights

This section helps users or AI tools explore, analyze, and extract valuable information from existing documents, reports, or shared repositories. It helps you find the latest campaign documents and insights.

1. Under the Researcher agent, paste the below prompt in the field and then click the **Send** button.

    ```
    Find the latest version of Zava Festive Campaign plan and summarize key updates.
    ```

    ![](./media/l2e3t7s1.png)

2. Review the output:

    ![](./media/l2e3t7s2.png)

    ![](./media/l2e3t7s3.png)

3. Enter the below prompt in the field and then click the **Send** button.

    ```
    Summarize contents of shared documents related to campaign planning.
    ```

    ![](./media/l2e3t7s4.png)

4. Review the output:

    ![](./media/l2e3t7s5.png)

### Task 8: Generate Executive Communication

Use the Researcher Agent to help communicate findings to your team. Patricia needs a leadership update.

1. Under the Researcher Agent, paste the below prompt in the field and then click the **Send** button.

    ```
    Draft an executive summary email on Zava Festive Campaign covering:
    - Progress
    - Risks
    - Key decisions
    - Next steps
    ```

   ![](./media/l2e3t8s1.png)

2. Review the output:

    ![](./media/l2e3t8s2.png)

    ![](./media/l2e3t8s3.png)

3. Evaluate whether the Researcher Agent's summary meets your expectations. If results are too broad or missing key details, refine your prompt.

    > **Knowledge:** "Narrow this summary to focus only on critical risks and delivery blockers."

4. Export or copy the summary for documentation, reports, or meeting notes.

    ![](./media/l2e3t8s3.png)

    > **Note:** Here is a brief overview of the tasks associated with each icon shown in the screenshot:

    1. **Clipboard Icon** - Used for **copying or pasting** content.
    2. **Thumbs-Up Icon** - Indicates **liking or approving** an item or action.
    3. **Thumbs-Down Icon** - Used to **dislike or disapprove** something.
    4. **Speaker Icon** - Represents **audio settings or volume control**.
    5. **Pencil Icon** - Used for **editing or writing** tasks.
    6. **Clock Icon** - **"Schedule this prompt"**, Schedules the selected prompt to run automatically at a specified time and deliver the generated results on a recurring basis.

## Summary

In this lab, you have completed the following:

- Accessed the Researcher Agent in Microsoft 365 Copilot and used natural language prompts to gather, analyze, and refine information efficiently
- Gathered and summarized all recent discussions, documents, and emails related to the Zava Retail Festive Campaign
- Identified action items, key decisions, and gaps across emails, Teams chats, and shared documents
- Drafted a leadership email and prepared an executive readiness briefing for an upcoming leadership review meeting
- Analyzed progress status and blockers, and discovered the latest campaign planning documents
- Generated an executive summary email covering progress, risks, key decisions, and next steps

## You have successfully completed the lab!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](./media/Next.png)
