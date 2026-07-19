# Building AI Agents for Zava Retail with Microsoft 365 Agents Toolkit and SDK

## Overall Estimated Duration: 2 Hours 20 Minutes

## Overview

In this hands-on lab, you will build two different types of AI agents for Zava Retail, a global retail and service organization, using Microsoft's agent development platforms. Across two progressive labs, you will move from creating a **Declarative Agent** with TypeSpec and the Microsoft 365 Agents Toolkit - connecting it to a live Repair Service API - to developing a **custom engine agent** with the Microsoft 365 Agents SDK and Semantic Kernel, grounded in enterprise HR data through Microsoft Foundry, and deployed across Microsoft Teams and Copilot Chat.

>**Disclaimer:** These labs use AI-powered agent platforms, so generated outputs, chart results, and conversational responses may differ across users and sessions. The results you see in this lab may not exactly match the examples shown here. Follow the workflow and expected outcome in the guide rather than expecting identical content.

## Objectives

In this lab, you will perform the following:

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

## Pre-requisites

Participants should have:

- Access to Microsoft 365 Copilot with custom app upload/agent creation enabled
- A Microsoft account with permissions to use Teams, Copilot Chat, and the Microsoft 365 Admin/Teams Developer Portal
- Access to Microsoft Foundry (**https://ai.azure.com**) with permissions to create a project, deploy an agent, and upload documents
- Visual Studio Code with the **Microsoft 365 Agents Toolkit** extension, for building and provisioning the Declarative Agent (Lab 11)
- Visual Studio 2022 with the **Microsoft 365 Agents** project templates and NuGet package support, for building the custom engine agent (Lab 12)
- Azure CLI access (for `az login`) and permissions to create a Dev Tunnel, for testing the SDK agent in Teams
- Access to the provisioned lab virtual machine and its local file system, including the sample HR documents used to ground the Foundry agent
- Basic familiarity with Microsoft 365 applications, REST APIs, and everyday business scenarios

## Getting Started with the Lab

Welcome to the **Building AI Agents for Zava Retail** workshop. In this workshop, you will explore two complementary approaches to extending Microsoft 365 Copilot with custom agents: a low-code **Declarative Agent** built with TypeSpec, and a fully custom **engine agent** built with the Microsoft 365 Agents SDK and Semantic Kernel, grounded in enterprise data through Microsoft Foundry. Through these guided labs, you will learn how to define agent behavior, connect agents to real APIs and documents, enhance responses with Adaptive Cards, and deploy agents across Microsoft Teams and Copilot Chat.

This workshop provides a hands-on experience with modern agent development on Microsoft 365, helping you understand how both declarative and custom engine agents can transform everyday enterprise scenarios like after-sales service and HR support.

![Image](./media/gsd1.png)

## Lab Guide Zoom In/Zoom Out

To adjust the zoom level for the environment page, click the **A↕ : 100%** icon located next to the timer in the lab environment.

![Image](./media/GettingStarted-01.png)

## Virtual Machine & Lab Guide
Your virtual machine is your workhorse throughout the workshop. The guide is your roadmap to success.

## Exploring Your Lab Resources
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.

![Image](./media/GettingStarted-02.png)

## Utilizing the Split Window Feature
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the top right corner.

![Image](./media/GettingStarted-03.png)

## Managing Your Virtual Machine
Feel free to **start, restart, or stop (2)** your virtual machine as needed from the **Resources (1)** tab. Your experience is in your hands!

![Image](./media/GettingStarted-04.png)

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Click **Next >>** from the bottom right corner to embark on your Lab journey!

![Image](./media/nxtd1.png)

### Happy Learning!!