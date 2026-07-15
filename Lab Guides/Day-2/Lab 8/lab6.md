# Lab 6 – Build a Store Operations Assistant Copilot Agent for trusted customer success at Zava Retail

**Estimated Duration:** 40 minutes

## Lab objectives 

This lab provides hands-on experience in building intelligent Copilot
Agents using Microsoft IQ principles. You will create a
SharePoint-integrated agent with trusted knowledge boundaries, apply the
five-step customer success framework to align it with a Core Unit of
Work, and validate it through PoC testing. The lab also covers advanced
customization using Copilot Studio, including custom instructions, topic
routing, and multi-agent orchestration by connecting with a second
specialized agent.

## Scenario

Store associates and shift managers often lose valuable time searching
through SOPs, policy documents, and operational guidelines during busy
trading hours, slowing response times, and impacting customer service.
The Store Operations Assistant Copilot Agent empowers frontline retail
workers with instant, contextual access to accurate store procedures in
the flow of work—helping them resolve customer queries faster, ensure
policy compliance, and keep store operations running smoothly during
peak demand.



## Exercise 1: Creating and Configuring Your Copilot Agent 

Microsoft IQ represents a unified intelligence layer that brings
contextual, work-aware AI into your everyday apps and agents. In this
part, you will create a Copilot Agent in SharePoint that is grounded in
verified, organization-specific content — ensuring responses are both
intelligent and trustworthy.

### Task 1: Access the Agent Creation Tool 

1. Navigate to Microsoft 365 Copilot using the URL.
     ```
     https://m365.cloud.microsoft/
     ```

    ![](./media/n1.png)

1. From the left navigation bar, select **App Launcher (1)** and then select **SharePoint (2)**.
    
    ![](./media/n2.png)

1. On the SharePoint home page, Click **Create site**.
    
    ![](./media/n3.png)

1. Select **Team site** from the **Create a site** dialog.

    ![](./media/n4.png)

1. On the **Select a template** screen, select the **Standard team** template.

   ![](./media/n5.png)

1. Review the **Standard Team** site preview, then click **Use template**.

    ![](./media/n6.png)

1. Enter the site **name (1)**, for example "ZavaSite1," confirming the **Group email address** and **Site address** auto-populate, then click **Next (2)**.

   ![](./media/n7.png)

    >**Note:** If you encounter any error in **site address** please add unique number at the end of ZavaSite to make the address unique.

1. Configure the following and then click **Create site**.
   | Setting | Value |
   |---|---|
   | Privacy settings | **Private - only members can access this site** |
   | Select a language | **English** |

   ![](./media/n8.png)

1. Leave the **Add members** field empty, then click **Finish**.

    ![](./media/n9.png)

1. Click **Documents (1)** in the left navigation menu, click **Create or upload (2)**, then select **Folder upload (3)**.

   ![](./media/n10.png)

1. Navigate to **C:\Labfiles\Lab6-Lab files** and select **HR Document** folder and then select **Open** to add this folder in the site.

    ![](./media/a11.png)

1. Select **Upload** to upload the folder in the site.

    ![](./media/a12.png)
    
1. Similarly add the remaining folders individaully in the site.
    - Product Specs Folder
    - Project Updates
    - Shift Handover notes
    - SOP library

    ![](./media/n11.png)

### Task 2: Create a New Agent  
  
1. Navigate back to M365 Copilot window.
   
1. Click **New agent (1)** in the left navigation menu, then click **Skip to configure (2)**.

   ![](./media/n12.png)

1. When the **Create new agent panel** opens, paste the following
information in the respective fields:

    - **Agent Name**: `Project Knowledge Assistant`

    - **Description**: `Helps users find project documents and summaries`

    - **Instructions**: `Provide concise answers using only verified information from included SharePoint sources` 

      ![](./media/n13.png)
   
1. Navigate back to SharePoint window and copy the **HR Document** folder URL.

   ![](./media/n14.png)
   
1. Navigate back to the M365 Copilot window and under **Knowledge tab** **paste** the copied URL and press **enter** to add the folder in the agent. 

    ![](./media/n15.png)

7. Similarly add the remaining folders.

   ![](./media/n16.png)
   
1. Click **Create** to finalize your agent configuration.  

    ![](./media/n17.png)

9. Select **Got to agent** to open newly created agent.

   ![](./media/n18.png)

   ![](./media/n19.png)

### Task 3: Test Your Agent 

Testing your agent validates both grounding knowledge and the quality of
its responses. This step reflects the Trust dimension of Microsoft IQ —
agents should only surface verified, relevant information.

1.  Navigate back to SharePoint window. Open **Agent Chat** on the right side of the ZavaSite page.

    ![](./media/n20.png)

1. In the chat field, paste the following prompt and select **Send button**.

     ```
     Summarize the project plan
     ```
    
    ![](./media/n21.png)

1. Review the output:  
      
    ![](./media/n22.png)
    
## Exercise 2: Advanced Instruction Authoring in Copilot Studio

The default Instructions field in SharePoint's agent creator is powerful
but limited. Copilot Studio gives you a richer editing surface —
including System Prompt composition, fallback handling, and topic-based
routing — that lets you control exactly how the agent reasons and
responds.

### Task 1: Open Your Agent in Copilot Studio

1. Navigate back to M365 Copilot window.

1. Click the **... (1)** menu next to **Project Knowledge Assistant**, then select **Edit (2)**.

    ![](./media/n24.png)

3. Select the **ellipsis icon (1)** on the upper left corner. Select **Copy to Copilot studio (2)**.
    
    ![](./media/n25.png)

4. A confirmation prompt window will pop-up. Select **Get Started.**
   
    ![](./media/n26.png)

5. Select your **Default Environment** and Click **Continue**.
   
    ![](./media/n27.png)

6. You will be redirected to the Copilot Studio page. In Copilot Studio, confirm the **Name (1)** field shows **Project Knowledge Assistant**, then review or update the **Instructions (2)**. 

    ```
    You are the Store Operations Assistant for a retail organization. Only answer questions using content from the connected SharePoint sources. Always cite the document name and section. If a question falls outside your knowledge sources, respond: "I don't have that information — please check with your shift manager or visit the intranet." Keep responses to 3–5 bullet points. Do not speculate or summarize information that is not present in a source
    ```
    
    ![](./media/n28.png)
    
7. Click **Create** to ceate the agent.
    
    ![](./media/n29.png)

8. After reviewing your agent, Click **Publish**.

    ![](./media/n30.png)
    
9. Click **Publish** again

    ![](./media/n31.png)

### Task 2: Add a Topic: Out-of-Scope Redirect

Topics in Copilot Studio are rule-based conversation flows that trigger
when specific phrases or conditions are detected. You will create a
short topic that politely redirects users who ask questions outside the
agent's domain.

1. In Copilot Studio, navigate to **Topics** in the upper menu bar.
   
    ![](./media/n32.png)

1. On the **Topics** tab, click **Add a topic (1)**, then select **From blank (2)**.
   
    ![](./media/n33.png)

1. Rename the new topic to **Out-of-Scope Redirect**.
    
    ![](./media/n35.png)
    
1. In the Trigger section, paste the following phrases as trigger
    phrases and click **+ icon** to add new node

    ```
    - I need help with something else

    - Can you help me with HR?

    - This is not related to my work

    - I have a different question
    ```

    ![](./media/n36.png)

1. Select **Send a Message**.

    ![](./media/n37.png)

1. Paste the following text in the message description box:

    ```
    I am specialized for HR & Payroll Assistant questions. For other topics, please contact your team lead or visit the company intranet. Is
    there anything else I can help you with in my area?
    ```

    ![](./media/n38.png)

1. Click **Save** to save the topic and then, select **Publish (2 times)** to publish the agent again.
    
   ![](./media/n39.png)

   ![](./media/n40.png)

### Task 3: Test the agent

1. Select **Test** from the upper navigation bar.
   
    ![](./media/n41.png)

2. Paste the following **prompt (1)**, and select the **Send (2)** button:  

     ```
     Can you help me with HR?
     ```
    
    ![](./media/n42.png)

3.  Review the output:  

    ![](./media/n43.png)

## Exercise 3: Designing a Multi-Agent Orchestration Pattern

Real enterprise deployments rarely rely on a single agent. Complex
workflows such as a procurement request that touches both inventory data
and HR approval processes, that require multiple specialized agents
working in coordination. This exercise introduces the concept of
multi-agent orchestration and help you design (and partially configure)
a handoff pattern between your primary agent and a second specialized
agent.

### Task 1: Create the Handoff Topic

You will now create a new topic in your primary agent that triggers
whenever a user asks a question outside the primary scope. This topic
will surface a handoff message and when the license supports, it
redirects the user to the second agent.

1. In Copilot Studio, navigate to **Topics**, **Add a topic (2)**, and **From blank (3)** to create another topic.

    ![](./media/n44.png)

1. Paste the following information in the topic and Click **+** to add a new node.

     - **Name**: Handoff to Secondary Agent

     - **Trigger phrases**: "payroll", "leave request", "HR policy", "annual leave", "employee record"

    ![](./media/n45.png)

1. Select **Send a Message** to add a message node.
   
    ![](./media/n46.png)

1. In the Message description box, paste the following information:
   
     ```
     That question is outside my area. I'm connecting you to the HR &Payroll Agent who can help with that — one moment please
     ```

    ![](./media/n47.png)
    
1. Click **Save (1)** and **Publish (2)** to save the node and publish.

    ![](./media/n48.png)

1. Click **Publish** on the confirmation pop-up to publish.

    ![](./media/n49.png)
    
### Task 2: Configure the Secondary Agent

Now, we will create a lightweight secondary agent to handles the
out-of-scope queries using multi-agent connections.

1. In Copilot Studio home page, select **Agents (1)** from the left navigation bar and then select **+ Create blank agent (2)**.
    
    ![](./media/n50.png)

1. Enter the agent name **HR & Payroll Assistant (1)** and click **Create (2)**
    
    ![](./media/n51.png)

1. In the **Instructions** field, click **Edit (1)** and then paste the following instructions and click **Save** to save the instruction.

     ```
     You are the HR & Payroll Assistant. You handle queries specifically related to store operations. Use only verified content from your connected sources. Always cite source and section. If a query falls outside your scope, say: "That's outside my remit. Please contact the appropriate team
     ```

    ![](./media/n52.png)

1. In the Knowledge section, Click **+ Add Knowledge** to add knowledge to the agent.

    ![](./media/n53.png)

1. Select **SharePoint** as the knowledge source.

    ![](./media/n54.png)

1. Paste the SharePoint folder URL **(1)** into the field, click **Add (2)**, then click **Add to agent (3)**.

    ![](./media/n56.png)

    - **Note**: Navigate back to SharePoint window and copy the **HR Document** folder URL.

      ![](./media/n14.png)
    
1. Confirm the **HR Document** knowledge source shows a **ready (1)** status, then click **Publish (2)**.

   ![](./media/n57.png)
   
1. Click **Publish** on the confirmation pop-up to publish.

    ![](./media/n58.png)
    
### Task 3: Add the Secondary Agent to the Primary Agent. 

1. Click **Agents (1)** in the left navigation menu, then select **Project Knowledge Assistant (2)** from the **My agents** list.
   
    ![](./media/n59.png)

1. Click the **Agents (1)** tab, then click **Add (2)**.
   
    ![](./media/n60.png)

1. Confirm the **Connected agents (1)** filter is selected, then select **HR & Payroll Assistant (2)** from the list.

    ![](./media/n61.png)

1. Add the following in the **Description (1)** and  leave **Pass conversation history to this agent (2)** checked, then click **Add and configure (3)**.
   
     ```
     Use this agent when users ask about HR or payroll matters, including payslips, leave balances, salary deductions, attendance, tax forms,employee benefits, or HR policy questions. Routes employee-related workforce support queries to the HR & Payroll Assistant for accurate resolution
     ```

    ![](./media/n62.png)

1. Click **Completion (1)** in the left panel, set **After running (2)** to **Send specific response (specify below)**, then paste the following message to display:  
  
     ```
     Your request relates to HR and payroll support. Transferring you now to the HR & Payroll Assistant for accurate assistance
     ```

    ![](./media/n63.png)

1. Click **Save (1)** and **Publish (2)** to save the node and publish.

    ![](./media/n64.png)

1. Click **Publish** on the confirmation pop-up to publish.

    ![](./media/n65.png)
    
### Task 4: Test the End-to-End Orchestration

With both agents published, validate the complete handoff flow using the
test scenarios below.

1. Click **Test (1)**, enter the **prompt (2)** in the message field, then click the **Send (3)** button.
      
    ![](./media/n66.png)

2.  Review the output:  

    ![](./media/n67.png)
    
## Summary 

In this lab, you created and configured a SharePoint-grounded Project
Knowledge Assistant in Microsoft Copilot Studio, using verified
SharePoint content to ensure accurate and trusted responses. You scoped
and prioritized agent use cases, defined a Core Unit of Work, and mapped
capabilities using the Work IQ framework. You also conducted a
structured proof of concept, evaluated results for scaling
opportunities, authored advanced conditional instructions, created
out-of-scope redirects, and designed a multi-agent orchestration flow
with structured handoffs between primary and specialized agents.
