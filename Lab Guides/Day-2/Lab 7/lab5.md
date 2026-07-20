# Lab 07: Improve communication and work coordination across Zava Retail stores with a Frontline Agent

## Estimated Duration: 40 Minutes

## Overview

In this lab, you will use **Microsoft 365 Copilot** Agent Builder to create a Frontline Operations Agent that helps Zava Retail employees perform daily operational tasks more efficiently. Rather than relying on managers or searching through multiple documents, frontline workers will be able to interact with an AI-powered assistant that provides instant guidance using enterprise knowledge.

You will build a **Frontline Operations Agent** by defining its purpose and instructions, grounding it with operational knowledge sources such as SOPs, policies, employee handbooks, and store checklists, and publishing it for use across Microsoft 365. You will then access the agent in Microsoft Teams, test it using real-world retail scenarios from multiple personas-including cashiers, store associates, managers, and regional operations leaders-and refine its responses to improve accuracy and relevance.

## Lab Objectives

In this lab, you will perform the following:

- Exercise 1: Create the Frontline Operations Agent
- Exercise 2: Access the Frontline Operations Agent in Microsoft Teams
- Exercise 3: Test the agent using real-world retail operational scenarios and refine its responses

## Scenario

Zava Retail operates 250 stores across multiple regions and supports more than 8,000 frontline employees, including cashiers, store associates, supervisors, and store managers. With high customer volumes, seasonal promotions, and frequent operational activities, frontline employees often need quick access to standard operating procedures, company policies, onboarding materials, and escalation guidance. However, searching through multiple documents or waiting for manager assistance results in slower issue resolution, inconsistent customer experiences, and reduced productivity.

To address these challenges, Zava Retail has decided to deploy a Microsoft 365 Copilot Frontline Operations Agent that provides instant, knowledge-grounded assistance to employees directly within Microsoft 365 and Microsoft Teams. The agent is designed to answer operational questions, guide employees through store procedures, assist with customer service scenarios, provide onboarding support, and help managers prioritize daily operations using enterprise knowledge sources.

**Key Personas**

1. **Patricia Gray - Operations Head** : Oversees operations across multiple stores and is responsible for maintaining operational consistency, monitoring recurring issues, and improving frontline productivity across the organization.

1. **Fratini Greens - Store Manager** : Manages day-to-day store operations, supports frontline staff, oversees staffing and customer service, and ensures store procedures are followed consistently.

1. **Marie Brown - Store Associate** : Assists customers on the sales floor, answers product and promotion questions, manages inventory inquiries, and requires quick access to operational guidance during busy store hours.

1. **David Turner - Cashier** : Handles customer transactions, resolves pricing and discount issues, manages checkout queues, and requires immediate access to return policies and checkout procedures.

## Exercise 1: Create the Frontline Agent

Patricia logs into Copilot to review Festive Campaign readiness.

1. Navigate to Microsoft 365 Copilot using the URL.
     ```
     https://m365.cloud.microsoft/
     ```
1. Sign in with following  credentials:

	- **Email/Username:** **<inject key="AzureAdUserEmail"></inject>**

    ![](./media/img1.png)

	- **Temporary Acces Password:** **<inject key="AzureAdUserPassword"></inject>**

    ![](./media/img2.png)

1. If **Action required** pop-up window appears, click on **Ask later**.

1. If prompted to **stay signed in**, you can click **No**.

    ![](./media/img3.png)

1. Explore the Copilot chat environment.

    ![](./media/q1.png)

1. Expand **navigation pane** and click **New agent (1)** in the left navigation menu, then click **Skip to configure (2)**.

   ![](./media/new12.png)
   
1. When the **Agent creation panel** opens, paste the following details in respective fields to build the agent.

    - **Name:** Frontline Operations Assistant

    - **Description:** Supports store staff, field workers, frontline teams with schedules, SOPs, customer help, daily operations.

    - **Instructions:**
    
        ```
        You are a frontline operations assistant for employees. Help workers with shift guidance, store procedures, customer service responses , escalation steps, daily checklists, safety reminders, and quick answers.Keep responses concise and mobile-friendly.
        ```

    ![](./media/n16.png)

1. Navigate to **Knowledge** section to add knowledge sources. Select **Upload from device**.

    ![](./media/q6.png)

1. Select the below files from **C:\Labfiles\Lab5-Lab files** and select **Open**.

    - SOP PDFs

    - Employee handbook

    - Store checklist

    - FAQ docs

    - Policy docs

    - Shift guides

    ![](./media/q7.png)

1. Verify that all the selected files are uploaded in the Knowledge
    sources.

    ![](./media/q8.png)

1. Click **Create** to publish the agent.

    ![](./media/q9.png)

     >**Note**:Wait for 5-10 minutes for the agent building process
    completion.
    
1. Once the agent is created successfully, click **Go to agent** to
    start using the agent.

    ![](./media/q11.png)
    
## Exercise 2: Access Frontline Operations Agent in Microsoft Teams

Patricia Gray (Regional operations manager) is seeking for an overview of the operational activities and get the key operations related queries of Zava Retail on Microsoft Teams for better visibility.

1. Navigate to Microsoft Teams using the URL and sign in with your credentials if needed.
     
     ```
     https://teams.microsoft.com
     ```

	- **Email/Username:** **<inject key="AzureAdUserEmail"></inject>**

    ![](./media/img1.png)

	- **Temporary Acces Password:** **<inject key="AzureAdUserPassword"></inject>**

    ![](./media/img2.png)

1. Click the **Copilot (1)** icon in the left navigation bar, expand the panel using the **sidebar (2)** toggle, then select **Frontline Operations ... (3)** under **Agents**.

    ![](./media/n1.png)

4. Now, Patricia can use the agent directly inside Teams. **Frontline Operations Agent** can be accessed under Microsoft Teams.

    ![](./media/image15.png)

## Exercise 3: Action and Decision Intelligence

### Task 1: Identify Startup Checklist

1. Navigate to Microsoft 365 copilot page using the URL.

     ```
     https://m365.cloud.microsoft/
     ```

2. Cashier at Zava Retail is starting the day and looking for a quick checklist. To execute this step, go to the Frontline Operations agent, paste the below given prompt in the field, and then click on the **Send** button.

     ```
     I am opening cashier. Give me first 20-minute startup checklist
     ```

    ![](./media/n2.png)

1. Review the output:

    ![](./media/q14.png)
    
    ![](./media/q15.png)

     > Note: Generated outputs are non-deterministic and may vary across users, sessions, and environments.
    
### Task 2: Resolve Customer Issues

1. Store Associate wants to resolve recurring issues faced by customers at the Zava Retail store. To execute this step, go to the Frontline Operations Agent, paste the below given prompt in the field and then click on the **Execute** button.

     ```
     Customer says wrong discount applied. What should I do?
     ```

    ![](./media/n3.png)
    
1. Review the output:

    - The agent will fetch the official policies and SOPs from knowledge
    source and provide the response.

    ![](./media/n4.png)

     > Note: Generated outputs are non-deterministic and may vary across users, sessions, and environments.

4. Paste the below given prompt in the field and then click on the **Send** button.

     ```
     Product out of stock during sale. What are the next steps?
     ```

    ![](./media/n5.png)

5. Review the output:

    ![](./media/n7.png)

     > Note: Generated outputs are non-deterministic and may vary across users, sessions, and environments.

### Task 3: Store Manager Scenario

1. Store Manager wants to understand the top priorities during weekend rush at retail store, retrieve new hires onboarding checklist, and resolve other managerial concerns. To execute this step, go to the Frontline Operations Agent, paste the below given prompt in the field, and then click on the **Send** button. 

     ```
     Create my top 5 priorities for Store \#118 during weekend rush
     ```

    ![](./media/n14.png)

1. Review the output:

    ![](./media/n8.png)

     > Note: Generated outputs are non-deterministic and may vary across users, sessions, and environments.

1. Paste the below given prompt in the field, and then click on
    the **Send** button.

     ```
     A new hire joined today as sales associate. Give Day 1 onboarding checklist.
    ```

    ![](./media/n9.png)

1. Review the output:

    ![](./media/n10.png)

     > Note: Generated outputs are non-deterministic and may vary across users, sessions, and environments.

### Task 4: Multi-persona Role Testing

1. Operations Head is looking for query resolution from multiple roles including cashier, store associate, and new hire. To execute this step, go to the Frontline Operations Agent, paste the below given prompt in the field and then click on the **Send** button.

     ```
     As a regional operations manager, identify top recurring operational issues likely across 250 Zava stores and recommend fixes.

     Cashier: Help with queue rush handling  
     Supervisor: Closing checklist  
     Manager: Weekly priorities  
     New Hire: First shift guidance  
     Regional Lead: Store risk summary
     ```

    ![](./media/n11.png)

2. Review the output:

    ![](./media/n12.png)

     > Note: Generated outputs are non-deterministic and may vary across users, sessions, and environments.

### Task 5: Review and Refine the Output

1. Evaluate whether the Frontline Operations Agent's summary meets your expectations.

2. If results are too broad or missing key details, refine your prompt.

    - **Example**: Narrow this summary to focus only on critical risks and
    delivery blockers.

    ![](./media/n15.png)

1. Review the actions available for the generated response.

     - **Clipboard Icon** - Used for **copying** the response text.
     - **Thumbs-Up Icon** - Used to **like or approve** the response.
     - **Thumbs-Down Icon** - Used to **dislike or flag** the response.
     - **Pencil Icon** - Used to **rewrite or modify** the response.
     - **... (More) Icon** - Opens additional options: **Schedule this prompt** to run the prompt automatically on a recurring basis, **Read aloud** to have the response read out loud, and **Export to Word** to save the response as a Word document.

    ![](./media/n13.png)

**Summary**

In this lab, you completed the following:

- Created a Microsoft 365 Copilot Frontline Operations Agent using Agent Builder and configured its instructions for retail operations.
- Grounded the agent with enterprise knowledge sources, including SOPs, employee handbooks, store checklists, policies, FAQs, and shift guides.
- Published the agent and accessed it from Microsoft Teams.
- Tested the agent using multiple retail scenarios, including cashier startup procedures, customer issue resolution, inventory shortages, store management priorities, onboarding guidance, and regional operations queries.
- Evaluated and refined the agent's responses to improve the quality and relevance of the generated output.

By completing this lab, you learned how Microsoft 365 Copilot custom agents can provide instant, knowledge-grounded assistance to frontline employees, helping improve operational consistency, accelerate issue resolution, streamline onboarding, and enhance productivity across Zava Retail stores.

## You have successfully completed the Lab!

Now, click on **Next >>** from the lower right corner to move on to the next page.

![Image](./media/nxtd1.png)