# Lab 10: Govern and Monitor the Zava Retail Agent Ecosystem with Agent 365

## Estimated Duration: 60 minutes

## Overview

In this lab, you will explore how Agent 365 enables organizations to govern, monitor, and manage AI agents deployed across Microsoft 365. As AI adoption grows, administrators must ensure that every agent is visible, properly governed, assigned to a business owner, and managed throughout its lifecycle. Agent 365 provides centralized capabilities to monitor agent activity, review governance metrics, manage approvals, control agent availability, and maintain compliance across the organization.

You will create and publish a new Holiday Returns Helper agent using Microsoft Copilot Studio, review tenant-wide insights through the Agent 365 Overview dashboard, manage agents using the Agent Registry, install and validate agents in Microsoft Teams, perform lifecycle actions such as blocking and unblocking agents, export the agent inventory for audit purposes, and identify governance gaps related to agent ownership. By the end of the lab, you will understand how Agent 365 supports enterprise AI governance while maintaining visibility, accountability, and operational control across the AI agent ecosystem.

## Lab Objectives

In this lab, you will perform the following:

- Exercise 1: Create and publish the Holiday Returns Helper agent using Microsoft Copilot Studio.
- Exercise 2: Explore the Agent 365 Overview dashboard and review tenant-wide governance metrics.
- Exercise 3: Publish, install, and validate the Holiday Returns Helper agent in Microsoft Teams.
- Exercise 4: Manage the lifecycle of an existing agent by blocking and unblocking it through the Agent Registry.
- Exercise 5: Export the complete agent inventory for governance, reporting, and audit purposes.
- Exercise 6: Identify ownerless agents and evaluate governance gaps within the organization.

## Scenario

Zava Retail has adopted **Microsoft 365 Copilot** agents to support multiple business functions across its retail operations. Frontline employees use the Frontline Operations Assistant for operational guidance, while project teams rely on the Project Knowledge Assistant to quickly access project documentation and organizational knowledge. As the holiday shopping season approaches, leadership has requested a new Holiday Returns Helper agent to assist store associates with customer questions related to holiday returns, exchanges, and refund policies.

As the organization's AI Administrator, your responsibility extends beyond creating new agents. You must ensure that every AI agent is properly governed throughout its lifecycle by maintaining centralized visibility, enforcing approval processes, monitoring ownership, validating deployments, and supporting compliance requirements. Using Agent 365, you will publish and validate the new Holiday Returns Helper agent, monitor organization-wide agent activity, manage agent lifecycle actions such as blocking and restoring agents, export governance reports, and identify ownership gaps to ensure that Zava Retail's AI ecosystem remains secure, compliant, and ready for enterprise-scale adoption.

**Key Personas**

1. **Maya Chen - AI Administrator** : Manages the organization's AI agent ecosystem by publishing, governing, monitoring, and maintaining lifecycle controls for all Microsoft 365 Copilot agents.

1. **Jordan Blake - Vice President, Store Operations** : Sponsors the Holiday Returns Helper initiative and ensures frontline employees have timely access to accurate return policy information during the holiday season.

1. **Priya Nair - Store Operations Manager** : Owns the holiday returns process, authors operational guidance, and serves as the business owner responsible for the Holiday Returns Helper agent.

1. **Riley Osei - Compliance & Risk Analyst** : Monitors AI governance and compliance requirements, reviews agent behavior, and requests lifecycle actions such as temporarily blocking agents when policy reviews are required.

## Exercise 1: Create a New Agent - Holiday Returns Helper

Build the Holiday Returns Helper agent from scratch in Copilot Studio,give it clear instructions and a knowledge source, and publish it so it is ready for governance review. You are building this on behalf of Jordan Blake's request, using the return-policy document supplied by Priya Nair as the knowledge source.

1. Open web browser and navigate to Excel using the URL provided and click **Sign in** button.

   ```
   https://copilotstudio.preview.microsoft.com/
   ```

1. Sign in with following  credentials:

	- **Email/Username:** **<inject key="AzureAdUserEmail"></inject>**

    ![](./media/img1.png)

	- **Temporary Acces Password:** **<inject key="AzureAdUserPassword"></inject>**

    ![](./media/img2.png)

1. If **Action required** pop-up window appears, click on **Ask later**.

1. If prompted to **stay signed in**, you can click **No**.

    ![](./media/img3.png)

1. Select **Agent** to build a new agent.

    ![](./media/n1.png)

5.  Enter the following details of the agent:

    - **Name:** Holiday Returns Helper

    - **Instructions:**
        ```
        You are Holiday Returns Helper for Zava Retail.Your role is to assist store associates with questions about holiday returns, exchanges, and refunds.Always answer using information from the uploaded Holiday Return Policy document.Keep responses concise, professional, and suitable for frontline employees using a mobile device.If the information is not available in the knowledge source, state that you couldn't find the answer rather than making assumptions. Do not answer unrelated questions.
        ```

      ![](./media/n2.png)

1. Select **knowledge** from the left navigation menu to add a knowledge source.

    ![](./media/n3.png)

1. Select **Click to upload** the document.

    ![](./media/n4.png)

1. Navigate to **C:\Lab Files\Agent365Lab** and open the **Zava_Retail_Holiday_Returns_Policy** file.
   
    ![](./media/n16.png)

1. Make sure that file is uploaded and then click **Add to agent.**

    ![](./media/n5.png)

1. Remove the **search all website** option.

    ![](./media/n6.png)

1. Click the publish drop-down menu.

    ![](./media/n7.png)

1. Confirm **Teams + Microsoft 365 (1)** is selected as the channel, ensure **Make agent available in Microsoft 365 Copilot (2)** is checked, then click **Save and publish (3)**.

    ![](./media/n8.png)

1. Click **Publish (1)**, then click the **X (2)** to close the dialog.

    ![](./media/n9.png)

1. Select the **preview** tab to test the agent.

    ![](./media/n10.png)

1. Enter the following **prompt (1)** in the prompt field and click the **Send** button.

     ```
    What is the holiday return window?
     ```

    ![](./media/n11.png)

1. The agent should explain the return window using the uploaded policy.

    ![](./media/n12.png)

     > Note: Generated outputs are non-deterministic and may vary across users, sessions, and environments.
    
1. Enter the following prompt and select the **Send** button.

    ```
    Can a customer exchange an item instead of requesting a refund?
    ```

    ![](./media/n14.png)

1. The exchange policy should match the knowledge document.

    ![](./media/n15.png)

     > Note: Generated outputs are non-deterministic and may vary across users, sessions, and environments.

## Exercise 2: Explore the Agent Registry and Monitor Agent Activity

Get a tenant-wide snapshot of Zava Retail's agent ecosystem - total
agents, active usage, open requests, and ownership gaps - before
drilling into individual agents

1. Open a browser and navigate to **Microsoft 365 admin center** using the URL

    ```
    https://admin.cloud.microsoft/
    ```

1. In the left navigation pane, expand **Agents**, and then select **Overview**.

    ![](./media/n17.png)

3. On the **Agent Overview** page, locate the following metrics and note their current values:

    1.  **Agent Registry** - total count of agents in the tenant.

    2.  **Active users** - unique users who interacted with an agent in
        the last 30 days.

    3.  **Pending requests for agents** - open requests to add specific
        agents.

    4.  **Agents without owners** - agents whose owner has left the
        company.

    5.  **Agent analytics** - agents by creators, top platforms used to
        build agents, and active users in Copilot over time.

    ![](./media/n18.png)

    ![](./media/n19.png)

## Exercise 3: Inspect, Publish, and Validate the Holiday Returns Helper Agent

In this exercise, you will review the submitted **Holiday Returns
Helper** agent in the Agent Registry, approve it for organizational use, publish it to the agent store, install it in Microsoft Teams, and verify that it provides accurate responses for frontline retail employees.

### Task 1: Install the Agent in Microsoft Teams

Install the published Holiday Returns Helper agent in Microsoft Teams so it is available to frontline employees during customer interactions.

1. Navigate to Microsoft Teams using the URL.
     ```
     https://teams.cloud.microsoft/
     ```

1. In the left navigation pane, select **Apps** and locate **Holiday Returns Helper**.

    ![](./media/n20.png)

1. Select **Add** to install the agent.

    ![](./media/n21.png)

1. Select **Open**.

    ![](./media/n22.png)

### Task 2: Verify the Agent's Responses

Test the Holiday Returns Helper agent by asking common customer service questions and confirm that it provides accurate and relevant responses.

1. Open the **Holiday Returns Helper** agent in Microsoft Teams.

1. Enter the following prompt and click **Send**

    ```
    Can a customer exchange an item instead of requesting a refund?
    ```

    ![](./media/n23.png)

1. Review the response and verify that the exchange policy is explained correctly.

    ![](./media/n24.png)

1. Enter the following prompt and click **Send**

    ```
    What refund methods are supported?
    ```

    ![](./media/n25.png)

1. Review the response and verify that the supported refund methods are accurately described.

    ![](./media/n26.png)

## Exercise 4: Block and Unblock the Frontline Operations Assistant

Practice the emergency control every AI admin needs: immediately
stopping an agent tenant-wide, and safely restoring it once a concern has been resolved. Riley Osei from Compliance & Risk has asked you to pause Sam Torres's Frontline Operations Assistant while a policy-wording issue is reviewed.

### Task 1: Block an Agent

Use the Registry to halt the Frontline Operations Assistant for all
users and record why it was blocked, per Riley Osei's request.

1. Expand **Agents (1)** in the left navigation menu, click **All agents (2)**, then select **Registry (3)** tab.

    ![](./media/n27.png)

1. Search for **Frontline Operations Assistant (1)** in the search field, then click **Frontline Operations Assistant (2)** from the results.

    ![](./media/n28.png)

1. On the details panel, select **Block**.

    ![](./media/n29.png)

1. Select the **Block agent (1)** checkbox, then click **Save (2)**.

    ![](./media/n30.png)

1. Confirm that Frontline Operations Assistant now displays a **Blocked** status.

    ![](./media/n31.png)

### Task 2: Unblock an Agent

Restore the Frontline Operations Assistant to Active status once Riley Osei confirms the policy-wording review is complete and the block is no longer needed.

1. Select the block agent.

    ![](./media/image43.png)

2. On the **Unblock agent** pane, select the **Unblock agent** checkbox.

    ![](./media/n32.png)

1. Select the unblock agent checkbox. Select **Save** and close the details panel.

    ![](./media/n33.png)

1. Confirm that Frontline Operations Assistant now displays an **Active** status.

    ![](./media/n34.png)

## Exercise 5: Export the Agent Inventory

Produce an offline, shareable record of every agent in the tenant -
useful for audits, leadership reporting, or compliance reviews outside the admin center.

1. On the Registry tab, select Export on the toolbar above the agent list.

    ![](./media/n35.png)

     >Note: If an Export button is not visible in the toolbar, select the ellipsis (...) menu in the toolbar to locate the export option.

1. Confirm the download in the confirmation dialog. Wait for the export file to be generated and downloaded to your lab VM.

    ![](./media/n36.png)

1. Open the downloaded CSV file.

1. Confirm that the file contains rows for Project Knowledge Assistant,Frontline Operations Assistant, HR & Payroll Assistant, and Holiday Returns Helper.

1. Confirm that the following columns are present: agent name, publisher, creator, creation date, host products, and availability status.

    ![](./media/image50.png)

6.  Close the CSV file.

## Exercise 6: Identify Ownerless Agents

Use the Registry's ownerless filter to check whether any of Zava
Retail's three agents lack a business owner, and understand what that gap would mean for accountability. Sam Torres already owns Frontline Operations Assistant, but Holiday Returns Helper should be assigned to Priya Nair - confirm whether that assignment has taken effect.

1. On the Registry tab, select the Missing an owner card.

1. Review the list of agents that are displayed after applying the ownerless filter.

    ![](./media/image51.png)

     >**Note** : Review the list of agents displayed after applying the ownerless filter. The results may vary depending on the agents deployed in your organization's environment. Any agents displayed indicate missing ownership information and should be reviewed to ensure an appropriate business owner is assigned.

## Summary

In this lab, you completed the following:

- Created and published the Holiday Returns Helper agent in Microsoft Copilot Studio using a trusted knowledge source.
- Explored the Agent 365 Overview dashboard to monitor tenant-wide agent metrics, activity, and governance insights.
- Published, installed, and validated the Holiday Returns Helper agent in Microsoft Teams to ensure it responded accurately to frontline retail scenarios.
- Used the Agent Registry to manage agent lifecycle actions by blocking and restoring an existing agent during a compliance review.
- Exported the organization's AI agent inventory to support governance, reporting, and audit requirements.
- Identified ownerless agents and evaluated governance gaps to improve accountability across the AI agent ecosystem.

By completing this lab, you learned how Agent 365 provides centralized governance, monitoring, lifecycle management, and compliance capabilities for Microsoft 365 Copilot agents, enabling organizations to securely deploy, manage, and scale AI solutions across the enterprise

## You have successfully completed the Lab!