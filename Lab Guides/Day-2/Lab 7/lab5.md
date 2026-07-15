# Lab 5 - Improve communication and work coordination across Zava Retail stores with a Frontline Agent

**Estimated Duration:** 40 minutes

## Lab objectives

In this lab, you will create a Frontline Operations Agent using
Microsoft 365 Copilot Agent Builder. The agent will help frontline
workers, store managers, and supervisors handle daily operations,
customer service, shift readiness, compliance, and escalation workflows.
You will configure agent instructions, upload enterprise knowledge
sources, test prompts, validate outputs, and optimize responses. After
completing this lab, you will be able to: 

- Create a Microsoft 365 Copilot custom agent

- Configure frontline retail agent instructions

- Upload knowledge sources for grounding

- Test store operations prompts

- Improve frontline productivity with AI

- Build reusable retail frontline agent templates

## Scenario

Zava Retail is a rapidly expanding multi-format retail chain operating:

- 250 stores across urban, suburban, and tier-2 markets

- 8,000 employees including cashiers, floor associates, warehouse staff,
  supervisors, and managers

- Presence across multiple regions, each with different staffing
  patterns and customer behavior

- Heavy seasonal demand spikes during festivals, clearance sales, school
  openings, and holiday promotions

- Thousands of frontline operational requests every week

Zava Retail has invested in Microsoft 365 and wants to modernize store
execution using a Microsoft 365 Copilot Frontline Agent.

**Key Challenges:**

- Managers spend too much time answering repetitive questions

- Store processes are inconsistent across locations

- Seasonal sales create staffing and service pressure

- New hire onboarding takes too much manual effort

- Operational issues are escalated at a slow pace

To solve these challenges, Zava Retail deploys a **Microsoft 365 Copilot
Frontline Agent** accessible in Copilot chat, Microsoft Teams, and
mobile devices for store workers. The agent becomes a 24x7 AI operations
Assistant for multiple retail stores. The Zava Frontline Agent will help
8,000 employees across 250 stores work more efficiently by giving
instant, consistent answers and reducing dependence on managers.

**Key Personas:**

**Patricia Gray – Operations Head**

The regional operations manager at Zava Retail oversees multiple stores
and ensures consistent execution across locations. The major challenges
include:

- Needs visibility into recurring issues across stores

- Tracks store performance and staffing gaps

- Requires faster escalation handling across regions

**Marie Brown – Store / Sales Associate**

The store associate at Zava Retail supports customers on the sales
floor, manages shelf availability, and assists with promotions. The
major challenges include:

- Needs quick answers on product locations and promotions

- Faces stock shortage questions from customers

- Requires guidance during peak store traffic

**David Turner – Cashier**

The cashier at Zava Retail handles billing transactions, customer
payments, and checkout queues. The major challenges include:

- Needs support resolving pricing or discount issues

- Manages long queues during rush hours

- Requires quick access to refund and return policies

**Fratini Greens – Store Manager**

The store manager at Zava Retail is responsible for store performance,
customer satisfaction, and team productivity. The major challenges
include:

- Receives repetitive operational questions from staff

- Needs visibility into daily store priorities

- Must balance staffing, sales, and service quality

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

1. Expand **navigation pane** and click **New agent (1)** in the left navigation menu, then click **Skip to configure (2)**.

   ![](./media/new12.png)
   
1. When the **Agent creation panel** opens, paste the following details
    in respective fields to build the agent.

    - **Name:** Frontline Operations Assistant

    - **Description:** Supports store staff, field workers, frontline teams with schedules, SOPs, customer help, daily operations.

    - **Instructions:**
    
        ```
        You are a frontline operations assistant for employees. Help workers with shift guidance, store procedures, customer service responses , escalation steps, daily checklists, safety reminders, and quick answers.Keep responses concise and mobile-friendly.
        ```

    ![](./media/n16.png)

1. Navigate to **Knowledge** section to add knowledge sources.
    Select **Upload from device**.

    ![](./media/q6.png)

1. Select the below files from **C:\Labfiles\Lab5-Lab files** and select **Open**.

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

1. Click **Create** to publish the agent.

    ![](./media/q9.png)

     >**Note**:Wait for 5-10 minutes for the agent building process
    completion.
    
1. Once the agent is created successfully, click **Go to agent** to
    start using the agent.

    ![](./media/q11.png)
    
## Exercise 2: Access Frontline Operations Agent in Microsoft Teams

Patricia Gray (Regional operations manager) is seeking for an overview
of the operational activities and get the key operations related queries
of Zava Retail on Microsoft Teams for better visibility.

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

4. Now, Patricia can use the agent directly inside Teams. **Frontline Operations Agent** can be accessed under Microsoft Teams.

    ![](https://raw.githubusercontent.com/technofocus-pte/MsIQ-cplt-agntsfrntr/refs/heads/main/Lab%20Guides/Lab%205/media/image15.png)
    
## Exercise 3: Action and Decision Intelligence

### Task 1: Identify Startup Checklist

1. Navigate to `https://m365.cloud.microsoft/` Microsoft 365 copilot page.

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

1. Paste the below given prompt in the field, and then click on
    the **Send** button. 

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

     - **Clipboard Icon** – Used for **copying** the response text.
     - **Thumbs-Up Icon** – Used to **like or approve** the response.
     - **Thumbs-Down Icon** – Used to **dislike or flag** the response.
     - **Pencil Icon** – Used to **rewrite or modify** the response.
     - **... (More) Icon** – Opens additional options: **Schedule this prompt** to run the prompt automatically on a recurring basis, **Read aloud** to have the response read out loud, and **Export to Word** to save the response as a Word document.

    ![](./media/n13.png)

**Summary**

In this lab, learners explored how Zava Retail can improve store
operations using a **Microsoft 365 Copilot Frontline Operations Agent**.
With 250 stores, 8,000 employees, and high seasonal demand, Zava Retail
needed a scalable solution to reduce manager workload, improve
consistency, and support frontline staff in real time.

In this lab, you created a custom agent to help store associates,
cashiers, supervisors, and managers with daily tasks such as opening and
closing procedures, shift readiness, promotions, returns, stock issues,
safety incidents, and escalations.

The agent was grounded using SOPs, policies, FAQs, checklists, and
training documents, then tested through real retail scenarios and
persona-based prompts.

By the end of the lab, learners demonstrated how the Zava Frontline
Agent can:

- Reduce repetitive questions to managers

- Improve consistency across stores

- Speed up onboarding for new hires

- Enable faster issue resolution

- Improve frontline productivity and customer service

This lab showed how AI-powered frontline agents can help Zava Retail
scale operations while empowering employees with instant support.

 
