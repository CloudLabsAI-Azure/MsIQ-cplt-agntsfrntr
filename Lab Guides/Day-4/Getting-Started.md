# Day 4: Build and Orchestrate Multi-Agent AI Systems with Microsoft Copilot Studio

### Overall Estimated Duration: 4 Hours

In this lab, you will get hands-on experience designing, building, and orchestrating intelligent **multi-agent AI systems** using **Microsoft Copilot Studio**, **Microsoft Dataverse**, **Microsoft Foundry**, and **Microsoft Fabric**. Across three real-world scenarios-retail hiring operations, an outdoor retail customer assistant, and university student services-you will learn how to build orchestrator agents that route requests to specialized child agents, ground those agents in trusted enterprise data, extend them with custom models and real-time analytics, and publish them to Microsoft Teams and Microsoft 365 Copilot.

By completing this lab, learners will be equipped to build event-driven, data-grounded, multi-agent platforms that reduce manual effort, deliver accurate and consistent responses, and scale operations efficiently across different industries.

## Objective

By the end of this lab, participants will be able to:

- **Build an Autonomous Hiring Operations Platform** using Microsoft Copilot Studio and Dataverse, creating a centralized Hiring Agent that orchestrates end-to-end recruitment with specialized agents for resume intake and interview preparation, enhanced by event-driven automation that detects resume emails, stores candidate data in Dataverse, and notifies teams in Microsoft Teams.

- **Orchestrate a multi-agent retail assistant** using Copilot Studio, Microsoft Foundry, and Microsoft Fabric, routing customer requests across specialized agents to handle product discovery, policy queries, support, and guided trip recommendations, with responses tailored by Foundry models and enriched by real-time operational insights from Fabric.

- **Build a multi-agent student services system** using Copilot Studio, creating an orchestrator agent (Atlas) connected to specialized child agents for Student Services, Academic, and Admissions-each grounded strictly in approved sources (Dataverse and official prospectuses) with a "no guessing" rule-and publish it to Microsoft Teams and Microsoft 365 Copilot.

## Pre-requisites

Participants should have:

- A Microsoft 365 account with access to Microsoft Copilot Studio and Microsoft Dataverse.

- Access to Microsoft Teams, Microsoft 365 Copilot, Microsoft Foundry, and Microsoft Fabric.

- Basic familiarity with the Power Platform and Microsoft Copilot Studio.

- Understanding of basic business processes such as recruitment, retail customer support, and student services, along with foundational concepts of AI agents and multi-agent orchestration.

## Architecture

In this lab, you will use Microsoft Copilot Studio as the core authoring and orchestration environment to build multi-agent systems across three scenarios. In each, a primary orchestrator agent interprets the incoming request and routes it to the specialized child agent best suited to respond, while grounding every response in trusted organizational data.

The agents are grounded in structured data stored in Microsoft Dataverse (candidate records, fee, grade, and exam data) and in knowledge sources such as official prospectuses, policies, and product content. The retail assistant is further extended with Microsoft Foundry models to tailor tone and responses and with Microsoft Fabric to surface real-time operational insights, while the hiring platform adds event-driven automation to detect and process incoming resume emails automatically. Completed agents are surfaced to end users through Microsoft Teams and Microsoft 365 Copilot.

## Architecture Diagram


## Explanation of Components

The architecture for this lab involves the following key components:

1. **Microsoft Copilot Studio:** The primary authoring and orchestration environment for building agents.
   - Enables system instruction authoring, topic-based routing, and multi-agent orchestration between a primary orchestrator and specialized child agents.
   - Supports grounding agents in enterprise data and knowledge sources, and publishing them to Microsoft Teams and Microsoft 365 Copilot.

1. **Microsoft Dataverse:** A secure, structured data platform used to store and retrieve trusted organizational records.
   - Stores candidate information for the hiring platform and fee, grade, and exam data for student services.
   - Grounds agents so responses draw from authoritative data rather than guesswork.

1. **Microsoft Foundry:** A model platform for integrating custom or bring-your-own models into agents.
   - Tailors agent responses to brand tone, product catalog, and support policies.
   - Enables enterprise-grade, context-aware generation in the retail assistant scenario.

1. **Microsoft Fabric:** A unified analytics platform for surfacing real-time operational data.
   - Provides real-time operational insights that inform the retail assistant's recommendations and answers.
   - Connects analytical data to conversational agent experiences.

1. **Event-Driven Automation:** Trigger-based workflows that automate data intake and notifications.
   - Detects incoming resume emails, processes candidate data automatically, and stores it in Dataverse.
   - Notifies recruitment teams in real time through Microsoft Teams.

1. **Microsoft Teams and Microsoft 365 Copilot:** The end-user channels where the completed agents are surfaced.
   - Deliver agent experiences directly to recruiters, customers, and students within the tools they already use.
   - Serve as the publishing and interaction surface for orchestrator agents such as Atlas.

## Getting Started with Lab

Once you're ready to dive in, your virtual machine and **Guide** will be right at your fingertips within your web browser.

![Image](../Day-2/media/gs1.png)

## Lab Guide Zoom In/Zoom Out

To adjust the zoom level for the environment page, click the **A↕ : 100%** icon located next to the timer in the lab environment.

![Image](../Day-2/media/GettingStarted-01.png)

## Virtual Machine & Lab Guide

Your virtual machine is your workhorse throughout the workshop. The guide is your roadmap to success.

## Exploring Your Lab Resources

To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.

![Image](../Day-2/media/GettingStarted-02.png)

## Utilizing the Split Window Feature

For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the top right corner.

![Image](../Day-2/media/GettingStarted-03.png)

## Managing Your Virtual Machine

Feel free to **start, restart, or stop (2)** your virtual machine as needed from the **Resources (1)** tab. Your experience is in your hands!

![Image](../Day-2/media/GettingStarted-04.png)

## Let's Get Started with Microsoft 365 Copilot

1. On your virtual machine, open a web browser and navigate to the Microsoft 365 Copilot portal.
     ```
     https://m365.cloud.microsoft/
     ```
    ![](../Day-2/media/img0.png)

1. On the **Sign in** page, enter the following email/username and click **Next (2)**.

   * **Email/Username**: <inject key="AzureAdUserEmail"></inject> **(1)**
   
    ![](../Day-2/media/img1.png)
     
1. Now enter the following password and click on **Sign in (2)**.
   
   * **Password**: <inject key="AzureAdUserPassword"></inject> **(1)**
   
    ![](../Day-2/media/img2.png)

      > **Note:** If prompted to Enter Temporary Access Pass, enter the following **Password**: <inject key="AzureAdUserPassword"></inject> **(1)** and click on **Sign in (2)**.

      ![](./images/GS-0.png) 
     
1. If you see the pop-up **Stay Signed in?**, select **No**.

    ![](../Day-2/media/img3.png)

1. If you see the pop-up **You have free Azure Advisor recommendations!**, close the window to continue the lab.

1. If a **Welcome to Microsoft 365** popup window appears, select **Maybe Later** to skip the tour.

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Click **Next >>** from the bottom right corner to embark on your Lab journey!

![Image](../Day-2/media/nxtd1.png)

### Happy Learning!!
