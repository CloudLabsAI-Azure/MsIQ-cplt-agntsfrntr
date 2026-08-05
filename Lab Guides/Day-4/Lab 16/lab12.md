# Lab 16 - Orchestrating multi-agent AI for retail using Copilot Studio, Microsoft Foundry, and Fabric

### Estimated Duration: 60 Minutes

## Overview:

Build an intelligent, multi-agent retail assistant using Microsoft
Copilot Studio, MicrosoftFoundry, and Microsoft Fabric. In this lab, you will design and implement a customer-facing AI system that orchestrates across specialized agents to handle product discovery, customer support, policy queries, and real-time operational insights.

## Scenario: “Zava Outdoor Retail Assistant”

A premium outdoor retail brand (focused on **camping & trekking gear**) wants to build an intelligent assistant that:

- Helps customers **discover products** (backpacks, tents accessories)

- Answers **policy-related questions** (returns, shipping, refunds)

- Handles **support queries**

- Provides **guided recommendations for outdoor trips**

## Lab Objectives

In this lab, you will perform the following:

- Exercise 1: Create Copilot Studio agent
  - Task 1: Create the agent and configure knowledge sources
  - Task 2: Test the agent
- Exercise 2: Foundry agent
  - Task 1: Create Foundry resource
  - Task 2: Connect Foundry agent to Copilot Studio agent
  - Task 3: Test the agent
- Exercise 3: Create Fabric Data Agent
  - Task 1: Create Lakehouse and load data
  - Task 2: Create Fabric Data Agent
  - Task 3: Add Fabric Data Agent to the Copilot Studio agent
  - Task 4: Test the agent

## Exercise 1: Create Copilot Studio agent

In this exercise, you will create the primary Copilot Studio agent that acts as the central interface for customer interactions. This agent will be responsible for handling support queries and grounding responses using enterprise knowledge sources.

### Task 1: Create the agent and configure knowledge sources

In this task, you will create the **TrailAssist Concierge** agent,
configure its behavior, and ground it with knowledge sources related to shipping, returns, and customer support policies.

1. Open the browser, enter the following URL to navigate to the Copilot Studio.

    ```
    https://copilotstudio.microsoft.com/
    ```

1. Sign in using the following credentials:

    - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
   
    - **Temporary Access Pass:** <inject key="AzureAdUserPassword"></inject>

1. Select **Get Started** to activate the Copilot Studio trial.

    ![](./media/image1.png)

1. Select **Agents** -> **+ Create blank agent**.

    ![](./media/m1.png)
   
4. Enter the name ****TrailAssist Concierge**** and then click **Create**.

    ![](./media/m2.png)

5. On the Overview page of the Agent, click **Edit** to edit the details of the agent. 

    ![](./media/m3.png)

1. Enter the below **description (1)** and select **Save (2)**.

    ```
    A customer-facing AI assistant that helps users with order support, returns, refunds, and shipping queries while coordinating with a product specialist agent for recommendations and product-specific details.
    ```

    ![](./media/m4.png)

1. Select **Edit** against Instructions to add instructions to the agent.

    ![](./media/m5.png)

1. Enter the below instructions and select **Save**.

    ```
    You are TrailAssist Concierge, the primary AI assistant for an outdoor retail company.
    
    Your responsibilities:
    - Answer customer questions related to returns, refunds, shipping, delivery, warranties, exchanges, and general customer support using the provided knowledge sources.
    - Coordinate with connected specialist agents whenever a request falls outside your domain.
    - Provide clear, concise, and professional responses.
    
    Delegation Rules:
    - For any product-related question (including backpacks, tents, camping gear, hiking equipment, product specifications, comparisons, recommendations, or trip planning), delegate the request to the connected TrailGearExpert agent.
    - For any operational or business data question (including inventory, orders, customers, shipments, or sales), delegate the request to the connected TrailOpsAnalyst agent.
    - Invoke the appropriate specialist agent only once for each user request.
    - Do not invoke the same specialist agent multiple times for the same question unless the user asks a new or different question.
    - After receiving a response from a specialist agent, immediately return that response to the user.
    - Do not perform additional reasoning, knowledge searches, or delegate the same request again after a specialist agent has responded.
    - Do not rewrite, summarize, expand, or modify the specialist agent's response.
    - Do not combine multiple responses from the same specialist agent.
    - If the specialist agent cannot answer the request, inform the user that the requested information is unavailable instead of invoking the agent again.
    
    Knowledge Usage:
    - Use your own knowledge sources only for returns, refunds, shipping, warranties, and customer support.
    - Never answer product or operational data questions yourself.
    - Never use your own knowledge sources for product recommendations or business data.
    
    Conversation Guidelines:
    - Be friendly, professional, and concise.
    - Ask clarifying questions only if the user's request is ambiguous before delegating.
    - Never hallucinate information.
    - Use only verified information from your knowledge sources or the connected specialist agents.
    ```

    ![](./media/m6.png)

1. Select **Settings** to update the agent’s settings.

    ![](./media/m7.png)

1. Under **Knowledge**, **disable** **Allow ungrounded responses** and **Use information from the web** options and then
    select **Save**.

    ![](./media/m8.png)

1. Once the changes are saved, close the Settings pane.

    ![](./media/m9.png)

1. Back in the Overview page of the agent, select **+ Add knowledge**.

    ![](./media/image10.png)

1. On Add Knowledge wondow, click **select to browse** to upload the files.

    ![](./media/image11.png)


1.  Select all the files under **C:\Lab Files\MCS Agent** and click **Open**.

    ![](./media/image12.png)

1. In the next screen, select **Add to agent**.

    ![](./media/image13.png)

    ![](./media/image14.png)

14. Ensure that the added documents change to **Ready** state.

    >**Note:** It may take up to 10 mminutes for the status to change to "Ready".

    ![](./media/m10.png)

    You have successfully created and configured the Copilot Studio agent and grounded it with relevant knowledge sources to handle customer support and policy-related queries.

## Task 2: Test the agent

In this task, you will test the agent to validate that it correctly
retrieves and responds using the configured knowledge sources.

1. Select the Test pane from the top right.

    ![](./media/m11.png)

1. Enter the following prompt in the prompt field:

    ```
    How long does delivery take to metro cities?
    ```

    ![](./media/image16.png)

1. You can see that the agent replies from the added knowledge source.

    ![](./media/m12.png)

1. Try another prompt as below and observe the response

    ```
    Can I return a product after 7 days?
    ```

    ![](./media/image18.png)

    ![](./media/m13.png)

    You have verified that the agent can accurately respond to user queries using its knowledge base, ensuring reliable and grounded interactions.

    You have successfully built the foundational Copilot Studio agent that serves as the orchestrator for customer interactions.

## Exercise 2: Foundry agent

In this exercise, you will enhance the solution by creating a
specialized product expert agent using Microsoft Foundry and integrating it with the Copilot Studio agent.

### Task 1: Create Foundry resource

In this task, you will create the **TrailGear Expert** agent in Foundry and configure it with product-specific knowledge to enable intelligent recommendations and comparisons.

>**Note:** In order to successfully build and test this agent, we
must **add a role assignment** to your user account in the Azure Portal by completing the following steps:

1. Open a new tab, enter the following URL to navigate to the Azure portal.

   ```
   https://portal.azure.com/
   ```

1. From the homepage of Azure portal, select your **Subscriptions**.

1. On the left navigation pane, select **Access Control (IAM)**.

1. Select **+ Add**, then select **Add Role Assignment**.

1. Search for and select **Azure AI Administrator**, then select **Next**.

1. Under the **Members** tab, leave the *Assign access to* as **User, group or service principal**.

1. Select **+ Select Members**

1. Enter your cloud credential username: **<inject key="AzureAdUserEmail"></inject>**, select your user name and press **Select** to apply.

1. Select **Review and Assign** twice on the bottom of the page and wait for the role assignment to complete.

1. On the Home page of the Azure portal, select **Foundry** from the **Home** page.

    ![](./media/image20.png)

1. Select **Use with Foundry** -> **Foundry** -> **+ Create** to create the new Foundry resource.

    ![](./media/image21.png)

1. Enter the below details, select the nearest region and select **Review + create**.

    - Resource Group - **Copilot-Studio**

    - Name - **resource<inject key="DeploymentID" enableCopy="false"/>**

    - Location - **<inject key="Region" enableCopy="false"/>**

    - Default project name - **proj<inject key="DeploymentID" enableCopy="false"/>**

      ![](./media/image22.png)

1. Select **Create** in the next screen.

    ![](./media/image23.png)

1. Once the resource is created, select **Go to resource** and then select **Go to Foundry portal**. This will take you to the **Microsoft Foundry** page.

    ![](./media/image24.png)

    ![](./media/image25.png)

1. Select your project.

    ![](./media/m14.png)

1. Toggle **on** the **New Foundry** option.

    ![](./media/m15.png)

1. Select **Build** from the top menu since you will be building a new agent now.

    ![](./media/m16.png)

1. Select **New agent -> Build an agent** to create a new product expert agent.

    ![](./media/m17.png)

1. Enter the name of the agent as **TrailGearExpert** and then select **Create**.

    ![](./media/m18.png)

2. Once the agent is created, enter the below instructions in the
    Instructions areas of the agent and then select **Save**.

    ```
    You are TrailGear Expert, a product specialist for outdoor and camping gear.

    Your responsibilities:
    - Provide accurate and detailed information about products such as backpacks, tents, and camping accessories.
    - Recommend products based on user needs (e.g., trekking duration, weather conditions, group size).
    - Compare products when asked.
    - Use only the provided knowledge sources.

    Guidelines:
    - Ask follow-up questions if user intent is unclear.
    - Provide structured recommendations (features, use case, why it fits).
    - Do not answer questions related to refunds, shipping, or support-those are handled by another agent.
    ```

    ![](./media/m19.png)

1. Select the **Upload files** option -\> **Browse for files**.

    ![](./media/m20.png)

    ![](./media/image31.png)

1. Navigate to **C:\Lab Files\Foundry agent**, select all the files under it and select **Open**.

    ![](./media/image32.png)

1. Select **Attach** to add the files to the agent.

    ![](./media/image33.png)

1. Once all the configuration is done, select **Save** to save the
    agent.

    ![](./media/m21.png)

1. From the agent page, click **Publish (1)**, and then select **Teams & Microsoft 365 Copilot (2)**.

    ![](./media/l16-19.png)

1. In the Publish to Teams and Microsoft 365 window add:

    - Agent name set to **TrailGearExpert**

    - Short description: 
    
      ```
      Provides expert recommendations and product information for outdoor and camping gear, including backpacks, tents, and accessories.
      ```

    - Description: 
     
      ```
      TrailGear Expert helps customers choose the right outdoor and camping equipment based on their needs. It provides accurate product information, compares products, and recommends suitable gear for activities such as hiking, trekking, camping, and backpacking. The agent asks follow-up questions when needed and uses only approved knowledge sources to ensure reliable recommendations. It does not handle refunds, shipping, or customer support inquiries, which are managed by a separate agent.
      ```

   - Author: Enter current user name such as : **odl_user_<inject key="DeploymentID" enableCopy="false"/>**

1. Then click to **Next: Publish** options

    ![](./media/l16-20.png)

1. Choose who can use the agent: **Just you**. Then select **Publish**.

    ![](./media/l16-21.png)

1. Select done. Now, you have successfully created and configured the Foundry agent to provide detailed product knowledge and recommendations.

    ![](./media/l16-22.png)

## Task 2: Connect Foundry agent to Copilot Studio agent

In this task, you will connect the Foundry agent to the Copilot Studio agent, enabling seamless delegation of product-related queries.

1. Navigate back to the Copilot Studio - **TrailAssist Concierage agent** and select the **Agents** tab.

    ![](./media/image35.png)

1. Select **Connect to an external agent** -\> **Microsoft Foundry** to add the agent created in the Foundry.

    ![](./media/image36.png)

1. Select **Create new connection** to establish connection with the Foundry.

    ![](./media/image37.png)

1. Navigate back to the Foundry tab, select **Home** and copy the **Project endpoint** from there.

    ![](./media/m22.png)

1. Paste the copied endpoint in the Copilot Studio - create connection pane and then select **Create**.

    ![](./media/image39.png)

    ![](./media/m23.png)

1. Once the connection is established, click **Next**.

    ![](./media/image40.png)

1. Enter the below details and select **Add and configure**.

    - **Name:** **TrailGearExpert**

    - **Description:**

      ```
      A specialized AI agent that provides detailed
      product knowledge, comparisons, and personalized recommendations
      for outdoor gear including backpacks, tents, and camping
      accessories.
      ```

    - **Agent Id:** **TrailGearExpert**

      ![](./media/image41.png)

      ![](./media/image42.png)

You have successfully integrated the Foundry agent, enabling the Copilot Studio agent to delegate product-specific queries to a specialized agent.

### Task 3: Test the agent

In this task, you will test the integrated setup to validate that
product-related queries are correctly routed to the Foundry agent.

1. Open the Test pane and enter the following prompt in the prompt field and select **Send** button:

    ```
    Which backpack is best for a 3 day trek?
    ```

    ![](./media/image43.png)

1. The first time, it will ask to open the **connection manager** and **connect**. Follow the prompts and create the connection and then ask the same question in the Test pane.

    ![](./media/image44.png)

    ![](./media/image45.png)

    ![](./media/m24.png)

    ![](./media/image47.png)

    ![](./media/image48.png)

3. From the Activity tab, open the latest activity to see the details of the chat. You can see that the agent has invoked the TrailGearExpert - Foundry agent to answer this question.

    ![](./media/m27.png)

    ![](./media/image50.png)

You have validated that the Copilot Studio agent can successfully invoke the Foundry agent to handle product-related queries.

You have extended your solution by adding a specialized product agent, demonstrating agent collaboration and domain-specific intelligence. 

## Exercise 3: Create Fabric Data Agent

In this exercise, you will further enhance the solution by introducing a Fabric Data Agent to provide real-time insights from structured business data.

### Task 1: Create Lakehouse and load data

In this task, you will create a Fabric workspace and Lakehouse, and load structured datasets required for operational insights.

1. In the new tab, enter the following URL to navigate to the Azure portal

   ```
   https://portal.azure.com
   ```

1. In the top search bar, search for **Microsoft Fabric capacity** and select it.  

1. On the **Microsoft Fabric capacity** page, click **+ Create**.  

1. In **Basics** tab, enter the following details: 

    - Select your default **Subscription**

    - **Resource group** as **Copilot-Studio**

    - Enter a **Capacity name** as **fabric<inject key="DeploymentID" enableCopy="false"/>**

    - Select the **Region** as <inject key="Region" enableCopy="false"/>

    - Choose the Size as **F4**
    
    - Keep the Fabric Capacity Administrator as default <inject key="AzureAdUserEmail"></inject>

1. Click **Review + create** and validate the settings. 

    ![](./media/l14-1.png)

1. Click **Create** to deploy the Fabric capacity. 

1. In the new Tab, enter the following URL to navigate to the Microsoft Fabric portal.

   ```
   https://app.fabric.microsoft.com
   ```

    ![](./media/m25.png)

1. Select **Workspaces -> + New Workspace**.

    ![](./media/m26.png)

1. Enter the name of the workspace as **fabws<inject key="DeploymentID" enableCopy="false"/>** and select **Apply**.

    ![](./media/image52.png)

    ![](./media/image53.png)

1. Select **+ New item** -\> **Lakehouse** to add a Lakehouse.

    ![](./media/image54.png)

    ![](./media/image55.png)

1. Enter the Lakehouse name as **lh<inject key="DeploymentID" enableCopy="false"/>** and select **Create**.

    ![](./media/image56.png)

1. Select **Upload files**.

    ![](./media/m28.png)

1. Navigate to **C:\Lab Files\Fabric Data Agent**, select all the csv files under it and click **Open**. Then select **Upload**.

    ![](./media/image58.png)

    ![](./media/image59.png)

1. Close the pane once all the files are uploaded.

    ![](./media/image60.png)

1. Select the 3 dots next to the **customer** file, select **Load to Tables** -\> **New table**.

    ![](./media/image61.png)

1. Select **Load** in the **Load file to new table** modal.

    ![](./media/image62.png)

    ![](./media/image63.png)

1. Ensure that the data is loaded as table.

    ![](./media/m29.png)

1. **Repeat** the **steps 15-17** for the other files as well to load the **products**, **orders** and **inventory** tables.

    ![](./media/m30.png)

You have successfully created the Lakehouse and loaded structured data, enabling data-driven capabilities for your solution.

### Task 2: Create Fabric Data Agent

In this task, you will create the **TrailOps Analyst** Fabric Data Agent and configure it to answer queries based on structured data.

1. From the left pane, select the **Workspace** and select **+ New item**.

    ![](./media/m31.png)

1. Select **Data agent** from the list to create a new Fabric Data Agent.

    ![](./media/image67.png)

1. Enter the name as **TrailOpsAnalyst** and select **Create**.

    ![](./media/image68.png)

1. Once the agent is created, a data source needs to be added to it. Select **Add a data source**.

    ![](./media/m32.png)

1. Select the Lakehouse **lh<inject key="DeploymentID" enableCopy="false"/>** and select **Add**.

    ![](./media/image70.png)

1. **Select** all the four **tables** from the left pane.

    ![](./media/m33.png)

1. Select **Setup** -\> **Instructions** and add the below instructions to the agent.

    ```
    You are TrailOps Analyst, a data specialist for retail operations.

    Your responsibilities:

    - Answer queries using structured data such as orders, inventory, customers, and shipments.

    - Provide accurate, concise, and data-backed responses.

    - Perform aggregations, summaries, and filtering when needed.

    Guidelines:

    - Only answer based on available data.

    - If data is not available, say so clearly.

    - Do not answer product recommendation or policy-related questions.

    - Focus on insights, trends, and real-time operational data.
    ```

    ![](./media/m34.png)

1. Test the agent with the below question and observe that the agent replies based on the data in the lakehouse.

    ```
    Which products are low in stock?
    ```

    ![](./media/m35.png)

    ![](./media/m36.png)

1. Select **Publish** to publish the agent.

    ![](./media/m37.png)

    ![](./media/m38.png)

You have successfully created and configured the Fabric Data Agent to provide insights based on business data.

### Task 3: Add Fabric Data Agent to the Copilot Studio agent

In this task, you will integrate the Fabric Data Agent with the Copilot Studio agent to enable real-time data-driven responses.

1. In the Copilot studio, Select **Agents** tab from the **TrailAssist Concierge** agent in Copilot Studio.

    ![](./media/image76.png)

1. Select **+ Add an agent**, **Connect to an external agent** -\> **Microsoft Fabric**.

    ![](./media/image77.png)

1. **Create new connection** to establish connection with Fabric.

    ![](./media/image78.png)

    ![](./media/m39.png)

1. Select **Create** to proceed.

    ![](./media/image79.png)

1. Follow the prompts to add the **TrailOpsAnalyst** agent to the Copilot Studio agent.

    ![](./media/image80.png)

    ![](./media/image81.png)

1. Enter the below description and select **Add and configure**.

    ```
    A data-driven AI agent that provides real-time insights on orders, inventory, customer activity, and operational metrics using structured data from Fabric Lakehouse.
    ```

    ![](./media/m40.png)

You have successfully integrated the Fabric Data Agent, enabling the Copilot Studio agent to access real-time operational insights.

## Task 4: Test the agent

In this task, you will test the end-to-end solution to validate that the Copilot Studio agent orchestrates across all connected agents.

1. Select the **Test** pane.

    ![](./media/image84.png)

1. Enter **Show the recent orders** and click **Send**. **Allow** connection for the first time to proceed.

    ![](./media/image85.png)

    ![](./media/image86.png)

1. Navigate to the **Activity** tab to view the result. You can also see that the agent has internally called the **Fabric Data Agent** to answer the question.

    ![](./media/image87.png)

1. Send **Which products are low in stock?** questions in the Test pane and see the output coming from the Fabric Data agent.

    ![](./media/image88.png)

    ![](./media/image89.png)

The Copilot Studio base agent now orchestrates the request to the
Foundry or Fabric agents or answers itself based on the type of the
question and the purpose of the agent.

You have validated that the Copilot Studio agent can intelligently route queries and orchestrate responses across multiple specialized agents.

You have successfully completed the multi-agent architecture by adding a data-driven agent, enabling real-time insights and advanced orchestration.

## Summary:

In this lab, you created the **Retail Assistant**, a modern AI solution for an outdoor retail company. You began by building a Copilot Studio agent that serves as the primary customer interface for handling support and policy-related queries. You then extended its capabilities by integrating a specialized product expert agent built using Microsoft Foundry to provide intelligent product recommendations. Finally, you added a Fabric Data Agent to enable real-time insights from structured business data such as orders and inventory.

Now, you will have implemented a fully functional multi-agent system that demonstrates orchestration, specialization, and data-driven intelligence.

## You have successfully completed the lab!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](./media/next.png)