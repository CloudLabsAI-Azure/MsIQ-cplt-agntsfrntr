# Building AI Agents for Zava Retail with Microsoft 365 Agents Toolkit and SDK

## Overall Estimated Duration: 4 Hours

## Overview

In this hands-on workshop, you will build **three different AI agents** across two enterprise scenarios - a global retail and service organization (**Zava Retail**) and a community healthcare provider (**Northstar Community Hospital**) - using Microsoft's agent development platforms. Across three progressive labs, you will move from creating a **Declarative Agent** with TypeSpec and the Microsoft 365 Agents Toolkit - connecting it to a live Repair Service API - to developing a **custom engine agent** with the Microsoft 365 Agents SDK and Semantic Kernel, grounded in enterprise HR data through Microsoft Foundry and deployed across Microsoft Teams and Copilot Chat, and finally to building a **low-code healthcare agent** in Microsoft Copilot Studio, orchestrated with Power Automate and backed by Microsoft Dataverse to automate patient appointments.

>**Disclaimer:** These labs use AI-powered agent platforms, so generated outputs, chart results, and conversational responses may differ across users and sessions. The results you see in this lab may not exactly match the examples shown here. Follow the workflow and expected outcome in the guide rather than expecting identical content.

## Objectives

In this workshop, you will perform the following:

- **Lab 11 - Transform After-Sales Repair Operations at Zava Retail with an AI-Powered Declarative Agent**
  - Scaffold a Declarative Agent project (**RepairServiceAgent**) using the Microsoft 365 Agents Toolkit and TypeSpec
  - Define agent metadata, instructions, and conversation starters
  - Connect the agent to a Repair Service API to list, create, update, and delete repair records
  - Configure Adaptive Cards to display repair records in a rich visual layout
  - Provision and test the agent in Microsoft 365 Copilot, including its built-in analytical (chart-generation) capability

- **Lab 12 - Develop a Cross-Channel HR Support Agent for Zava Retail using Microsoft 365 Agents SDK and Semantic Kernel**
  - Configure a custom AI agent (**Zava HR Agent**) in Microsoft Foundry's Agents Playground and ground it with enterprise HR documents
  - Scaffold a custom engine agent using the Microsoft 365 Agents SDK, starting from the Echo Bot template
  - Integrate the Microsoft 365 Agents SDK bot with Semantic Kernel and the Microsoft Foundry agent for real-time, grounded responses
  - Deploy and test the agent in Microsoft Teams using Dev Tunnels and the Microsoft 365 Agents Toolkit
  - Update the app manifest to enable **copilotAgents**, bringing the custom engine agent into Microsoft 365 Copilot Chat

- **Lab 13 - Build a Healthcare Agent to Automate Patient Appointments for Northstar Community Hospital**
  - Build a patient-facing assistant in **Microsoft Copilot Studio** that securely verifies patient identity and answers hospital-related questions
  - Enable patients to view available appointment slots, book appointments, and cancel existing bookings conversationally
  - Use **Power Automate** to orchestrate appointment retrieval and booking behind the scenes
  - Store and manage appointment information in **Microsoft Dataverse**
  - Test the end-to-end appointment workflow and apply responsible AI practices for sensitive healthcare interactions

## Pre-requisites

Participants should have:

- Access to Microsoft 365 Copilot with custom app upload/agent creation enabled
- A Microsoft account with permissions to use Teams, Copilot Chat, and the Microsoft 365 Admin/Teams Developer Portal
- Access to Microsoft Foundry (**https://ai.azure.com**) with permissions to create a project, deploy an agent, and upload documents
- Access to **Microsoft Copilot Studio** with permissions to create, configure, and publish an agent (Lab 13)
- Access to **Power Automate** and a **Microsoft Dataverse** environment (Microsoft Power Platform) with permissions to create tables and cloud flows (Lab 13)
- Visual Studio Code with the **Microsoft 365 Agents Toolkit** extension, for building and provisioning the Declarative Agent (Lab 11)
- Visual Studio 2022 with the **Microsoft 365 Agents** project templates and NuGet package support, for building the custom engine agent (Lab 12)
- Azure CLI access (for `az login`) and permissions to create a Dev Tunnel, for testing the SDK agent in Teams
- Access to the provisioned lab virtual machine and its local file system, including the sample HR documents used to ground the Foundry agent
- Basic familiarity with Microsoft 365 applications, the Microsoft Power Platform, REST APIs, and everyday business scenarios

## Getting Started with the Lab

Welcome to the **Building AI Agents with Microsoft Copilot & Agent Platforms** workshop. In this workshop, you will explore three complementary approaches to building and extending agents on Microsoft's platforms: a low-code **Declarative Agent** built with TypeSpec, a fully custom **engine agent** built with the Microsoft 365 Agents SDK and Semantic Kernel and grounded in enterprise data through Microsoft Foundry, and a low-code **Copilot Studio agent** that combines conversational AI with business process automation using Power Automate and Microsoft Dataverse. Through these guided labs, you will learn how to define agent behavior, connect agents to real APIs, documents, and data stores, enhance responses with Adaptive Cards, automate multi-step business processes, and deploy agents across Microsoft Teams and Copilot Chat.

This workshop provides a hands-on experience with modern agent development across Microsoft 365 and the Power Platform, helping you understand how declarative, custom engine, and low-code Copilot Studio agents can transform everyday enterprise scenarios such as after-sales service, HR support, and healthcare appointment management.

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
    ![](/Lab%20Guides/Day-2/media/img0.png)

1. On the **Sign in** page, enter the following email/username and click **Next (2)**.

   * **Email/Username**: <inject key="AzureAdUserEmail"></inject> **(1)**
   
    ![](/Lab%20Guides/Day-2/media/img1.png)
     
1. Now enter the following password and click on **Sign in (2)**.
   
   * **Password**: <inject key="AzureAdUserPassword"></inject> **(1)**
   
    ![](/Lab%20Guides/Day-2/media/img2.png)

      > **Note:** If prompted to Enter Temporary Access Pass, enter the following **Password**: <inject key="AzureAdUserPassword"></inject> **(1)** and click on **Sign in (2)**.
     
1. If you see the pop-up **Stay Signed in?**, select **No**.

    ![](/Lab%20Guides/Day-2/media/img3.png)

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