# Lab 3 - Build the Zava Retail Workforce Upskilling Learning Agent with Microsoft 365 Copilot

## Estimated Duration: 30 Minutes

## Overview

In this lab, you will explore how to build a **Workforce Upskilling Agent** using Microsoft 365 Copilot Agent Builder. You will learn how to configure the agent aligned to workforce transformation goals, ground it in organizational context using Work IQ principles, and enrich it with enterprise knowledge sources.

Zava Retail — a mid-sized retail chain specializing in consumer electronics and home goods — is eighteen months into a digital transformation initiative. Technology adoption is accelerating faster than employee readiness. To address this challenge, you will build and deploy a Workforce Upskilling Agent that helps identify skill gaps, personalize employee learning journeys, and improve workforce readiness across operations.

## Lab Objectives

In this lab, you will perform the following:

- Exercise 1: Create the Workforce Upskilling Agent
- Exercise 2: Ground the Agent in Organizational Context
- Exercise 3: Diagnose Workforce Skill Gaps
- Exercise 4: Generate Personalized Learning Plans
- Exercise 5: Produce a Workforce Readiness Briefing

## Scenario

You are **Jordan Mercer**, Chief Operating Officer of Zava Retail. The company is rolling out a new Retail Management System (RMS) company-wide, deploying AI-powered inventory forecasting in two regional store clusters, adopting customer behavior analytics tools, and completing an ERP migration next quarter.

**Key Personas**

1. **Jordan Mercer (COO – Primary Persona):** Leads digital transformation strategy and oversees workforce capability planning.
2. **Alex Chen (Store Operations Supervisor):** Frequently overrides AI inventory alerts without reviewing them.
3. **Maria Santos (Supply Chain Analyst):** Leaving in 60 days with undocumented critical supplier knowledge.
4. **Derek Okonkwo (Operations Coordinator):** Low RMS adoption despite extensive legacy systems experience.

## Exercise 1: Creating the Workforce Upskilling Agent

Before the agent can support workforce development, you must first build and configure it inside Microsoft 365 Copilot.

### Task 1: Open Agent Builder

1. Navigate to the following URL to open Microsoft 365 Copilot. Sign in with your credentials.

    ```
    https://m365copilot.com/
    ```

    - **Username**: <inject key="AzureAdUserEmail"></inject> **(1)**

        ![](./media/l3e1t1s1.png)

    - **Password**: <inject key="AzureAdUserPassword"></inject> **(2)**

        ![](./media/l3e1t1s2.png)

        If the **Stay signed in?** prompt appears after sign-in, Click **No.**

        ![](./media/l3e1t1s3.png)

2. Click **Agents (1)** from the left navigation pane, then select **More agents (2)** then click **Create Agent**.

    ![](./media/l3e1t1s4.png)

    ![](./media/l3e1t1s5.png)

3. The **New Agent** page will open. Now click **Skip to configure**.

    ![](./media/l3e1t1s6.png)

    ![](./media/l3e1t1s7.png)

### Task 2: Define and Configure the Agent

1. Paste the following details to define and configure the agent:

    - **Agent Name**: **Zava Retail Workforce Coach (1)**

    - **Agent Description**: 
        ```
        Supports workforce capability development by diagnosing skill gaps, generating personalized learning plans, and assisting leaders with workforce readiness decisions during digital transformation. (2)
        ```

        ![](./media/l3e1t2s1.png)

2. Paste the below prompt in the field and then click the **Execute** button.

    ```
    You are Zava Retail's Workforce Coach.

    Your purpose is to help leaders identify workforce capability gaps,
    generate personalized learning plans, support coaching simulations,
    and recommend interventions during digital transformation.

    Focus on:
    - RMS adoption
    - AI inventory forecasting literacy
    - Customer analytics interpretation
    - Supply chain risk management
    - Change adoption coaching

    Always tailor recommendations based on:
    - Employee role
    - Operational urgency
    - Experience level
    - Retail store cluster context
    ```

    ![](./media/l3e1t2s2.png)

3. In the **Knowledge Sources** section, upload or connect the organizational resources listed below. Select the **Upload from device** icon to upload the files. The required files for this lab are available at **C:\Lab Files\Lab 3 - Lab files**.

    - RMS onboarding guide
    - AI inventory forecasting SOP
    - Store operations handbook
    - Supply chain transition playbook
    - ERP migration training documentation

        ![](./media/l3e1t2s3.png)

        ![](./media/l3e1t2s4.png)

        ![](./media/l3e1t2s5.png)

4. Click **Create** and then select **Go to Agent**.

    ![](./media/l3e1t2s6.png)

    ![](./media/l3e1t2s7.png)

    ![](./media/l3e1t2s8.png)

## Exercise 2: Grounding the Agent in Organizational Context

Once the agent is built, provide the transformation context of Zava Retail.

### Task 1: Initialize Agent Context

1. Paste the following prompt in the chat panel of the **Zava Retail Workforce Coach** agent and click the **Send** button.

    ```
    I am the COO of Zava Retail, a mid-sized retail chain specializing
    in consumer electronics and home goods, with 4 regional store clusters
    and approximately 600 employees across store operations, supply chain,
    customer experience, and merchandising.

    We are currently migrating to a new Retail Management System (RMS)
    and deploying AI-powered inventory forecasting and customer analytics tools.

    Our key upskilling priorities are:
    1. RMS system adoption
    2. AI inventory and analytics supervisory skills
    3. Supply chain risk management for mid-career analysts
    ```

    ![](./media/l3e2t1s1.png)

2. Review the output:

    ![](./media/l3e2t1s2.png)

    ![](./media/l3e2t1s3.png)

    ![](./media/l3e2t1s4.png)

    > **Note:** AI-generated responses are non-deterministic and may vary across environments, sessions, and prompts.

### Task 2: Validate Agent Understanding

1. To test the agent, enter the following prompt and click the **Send** button.

    ```
    What are the most critical workforce skill domains I should prioritize during this retail digital transformation?
    ```

     ![](./media/l3e2t2s1.png)

2. Review the output:

    ![](./media/l3e2t2s2.png)

    ![](./media/l3e2t2s3.png)

    > **Note:** AI-generated responses are non-deterministic and may vary across environments, sessions, and prompts.

## Exercise 3: Diagnosing Workforce Skill Gaps

### Task 1: Diagnose Alex Chen

1. Paste the following prompt and click the **Send** button to diagnose workforce skill gaps.

    ```
    I have a Store Operations Supervisor named Alex who is consistently
    overriding AI-powered inventory replenishment alerts without reviewing
    them — approximately 3 times per week over the past month. Based on this
    behavioral signal, what skill gaps should I hypothesize, and what targeted
    learning plan should I create?
    ```

    ![](./media/l3e3t1s1.png)

2. Review the output:

    ![](./media/l3e3t1s2.png)

    ![](./media/l3e3t1s3.png)

### Task 2: Diagnose Maria Santos

1. Paste the following prompt and click the **Send** button to diagnose workforce skill gaps.

    ```
    One of our supply chain analysts, Maria, is leaving in 60 days. She
    owns four sole-source supplier relationships with no documented handover
    process.
    What urgent learning and knowledge transfer plan should I implement?
    ```

    ![](./media/l3e3t2s1.png)

2. Review the output:

    ![](./media/l3e3t2s2.png)

    ![](./media/l3e3t2s3.png)

### Task 3: Diagnose Derek Okonkwo

1. Paste the following prompt and click the **Send** button to diagnose workforce skill gaps.

    ```
    Our RMS went live 6 months ago. Derek is at 31% system utilization —
    lowest on his team.
    He has 11 years of legacy system experience.
    What resistance patterns and skill gaps should I address?
    ```

     ![](./media/l3e3t3s1.png)

2. Review the output:

    ![](./media/l3e3t3s2.png)

    ![](./media/l3e3t3s3.png)

## Exercise 4: Generating Personalized Learning Plans

### Task 1: Generate Alex's 6-Week Plan

1. To generate a plan for Alex, paste the following prompt and click the **Send** button.

    ```
    Generate a structured 6-week learning plan for Alex with:
    - Learning objectives
    - Weekly activities
    - Resources
    - Checkpoints
    - Success metrics
    ```

    ![](./media/l3e4t1s1.png)

2. Review the output:

    ![](./media/l3e4t1s2.png)

    ![](./media/l3e4t1s3.png)

### Task 2: Maria's 60-Day Transition Plan

1. To generate a plan for Maria, paste the following prompt and click the **Send** button.

    ```
    Generate a 60-day knowledge transfer and upskilling plan for Maria's
    transition scenario.
    Include parallel tracks for:
    1. Knowledge transfer
    2. Analyst upskilling
    ```

    ![](./media/l3e4t2s1.png)

2. Review the output:

    ![](./media/l3e4t2s2.png)

### Task 3: Derek's RMS Adoption Plan

1. To generate a plan for Derek, paste the following prompt and select the **Send** button.

    ```
    Create an 8-week adoption-focused learning plan for Derek that positions RMS mastery as a career growth opportunity.
    ```

    ![](./media/l3e4t3s1.png)

2. Review the output:

    ![](./media/l3e4t3s2.png)

## Exercise 5: Workforce Readiness Briefing

### Task 1: Generate Executive Briefing

1. To test the workforce readiness and generate a briefing plan, paste the below prompt and click the **Send** button.

    ```
    Generate a workforce readiness briefing for Zava Retail covering:
    1. Current risk summary
    2. Intervention status
    3. What I need from Store Managers
    4. 30-day watch list
    ```

    ![](./media/l3e5t1s1.png)

2. Review the output:

    ![](./media/l3e5t1s2.png)

### Task 2: Tailor for VP of HR

1. To tailor the workforce readiness summary for the VP of HR, paste the below prompt and click the **Send** button.

    ```
    Condense this into a 5-bullet summary for my VP of HR focused only on HR action items.
    ```

    ![](./media/l3e5t2s1.png)

2. Review the output:

    ![](./media/l3e5t2s2.png)

## Summary

In this lab, you have completed the following:

- Built a custom **Workforce Upskilling Agent** in Microsoft 365 Copilot Agent Builder and configured it with enterprise knowledge sources
- Grounded the agent in organizational context by providing Zava Retail's digital transformation priorities and upskilling goals
- Used operational behavior signals to diagnose workforce skill gaps for Alex Chen (AI literacy), Maria Santos (knowledge transfer), and Derek Okonkwo (RMS adoption resistance)
- Generated personalized learning plans tailored to each employee's role, urgency, and experience level
- Produced workforce readiness briefings for executive stakeholders and tailored a concise summary for the VP of HR

## You have successfully completed the lab!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](./media/Next.png)
