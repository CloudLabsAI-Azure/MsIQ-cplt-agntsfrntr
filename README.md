# Hands-On Lab: Building Frontier Firm Productivity with Microsoft IQ, Copilot &amp; Agents

## Lab Overview

Building Frontier Firm Productivity with Microsoft IQ, Copilot &amp; Agents is a four-day, hands-on workshop in which learners progress from using pre-built Microsoft 365 Copilot agents to building, extending, governing, and orchestrating enterprise-grade AI agents. The story is anchored in **Zava Retail**, a fast-growing omnichannel retailer, with supporting scenarios at Northstar Community Hospital and Riverbend University that show how the same patterns transfer across industries.

Learners begin with the everyday agent experience — Planner Agent, Researcher, Agent Builder, App Builder, Cowork, and Copilot Chat — then move to knowledge-grounded and SharePoint-grounded agents, Copilot Studio customization, and Agent 365 governance. From there the workshop shifts to pro-code development with the Microsoft 365 Agents Toolkit, TypeSpec, the Microsoft 365 Agents SDK and Semantic Kernel, and finishes with multi-agent orchestration across Copilot Studio, Microsoft Foundry, Microsoft Fabric, Dataverse, and Power Automate.

The lab is delivered through the CloudLabs environment, with a pre-provisioned virtual machine, Microsoft 365 tenant, and lab files supplied for every exercise.

**Total Estimated Duration: 15 Hours (Day 1: 4 h, Day 2: 3 h, Day 3: 4 h, Day 4: 4 h)**

---

## The Four-Day Learning Journey

Each day builds on the previous one, moving from consuming agents to building, governing, and orchestrating them.

| Day | Theme | What you build | Core technologies | Labs |
|---|---|---|---|---|
| 1 | AI-Powered Agents and Workflows | Executive workflows with pre-built and custom agents | Microsoft 365 Copilot, Planner Agent, Researcher, Agent Builder, App Builder, Cowork | 1–6 |
| 2 | Build, Extend, and Govern Copilot Agents | Knowledge-grounded frontline agents with governance | Copilot Agent Builder, SharePoint, Copilot Studio, Copilot in Excel/Teams, Agent 365 | 7–10 |
| 3 | Agents Toolkit and SDK Development | Declarative, custom engine, and low-code agents | M365 Agents Toolkit, TypeSpec, M365 Agents SDK, Semantic Kernel, Microsoft Foundry, Copilot Studio, Power Automate, Dataverse | 11–13 |
| 4 | Multi-Agent AI Systems | Orchestrated multi-agent platforms | Copilot Studio, Dataverse, Microsoft Foundry, Microsoft Fabric, Azure AI Search, Dataverse MCP Server | 14–17 |

---

## Prerequisites

Attendees should bring the following knowledge:

- Basic familiarity with Microsoft 365 applications (Outlook, Teams, SharePoint, Excel).
- Understanding of everyday business processes such as project coordination, retail operations, financial analysis, recruitment, and customer support.
- General awareness of the Microsoft Power Platform (Copilot Studio, Power Automate, Dataverse) for Days 3 and 4.
- For the pro-code labs (Day 3): comfort with Visual Studio Code and Visual Studio 2022, REST API concepts, and running CLI commands; deep coding expertise is not required as all code is provided.
- No prior agent-building experience is required.

All environment configuration (the lab tenant, Microsoft 365 Copilot licences, the lab virtual machine, Azure subscription, and the sample lab files) is provisioned before the session through CloudLabs.

---

## Repository Structure

```
├── README.md                              # Lab overview and navigation (this file)
├── Lab Files/                             # Sample documents, datasets, and solution files used across the labs
└── Lab Guides/
    ├── Day-1/                             # Day 1: AI-Powered Agents and Workflows with Microsoft 365 Copilot
    │   ├── Getting-Started.md             # Day 1 scenario, architecture, components, and tenant sign-in steps
    │   ├── masterdoc-day1.json            # CloudLabs render manifest: Getting Started plus Labs 1–6, in order
    │   ├── images/                        # Shared Day 1 screenshots (sign-in, environment, navigation)
    │   ├── Lab 1/
    │   │   ├── Lab-1.md                   # Lab 01: Planner Agent for cross-functional program execution
    │   │   └── media/                     # Lab 1 step screenshots
    │   ├── Lab 2/
    │   │   ├── Lab-2.md                   # Lab 02: Researcher Agent for insights and reporting
    │   │   └── media/                     # Lab 2 step screenshots
    │   ├── Lab 3/
    │   │   ├── Lab-3.md                   # Lab 03: Workforce Upskilling Agent with Agent Builder
    │   │   └── media/                     # Lab 3 step screenshots
    │   ├── Lab 4/
    │   │   ├── Lab-4.md                   # Lab 04: IT Asset Management app with App Builder
    │   │   └── media/                     # Lab 4 step screenshots
    │   ├── Lab 5/
    │   │   ├── Lab-5.md                   # Lab 05: Calendar management with Copilot Cowork
    │   │   └── media/                     # Lab 5 step screenshots
    │   └── Lab 6/
    │       ├── Lab-6.md                   # Lab 06: Marketing Operations Agent in Copilot Chat
    │       └── media/                     # Lab 6 step screenshots
    ├── Day-2/                             # Day 2: Build, Extend, and Govern Copilot Agents for Retail Operations
    │   ├── getting-started.md             # Day 2 scenario, architecture, components, and sign-in steps
    │   ├── masterdoc.json                 # CloudLabs render manifest: Getting Started plus Labs 7–10, in order
    │   ├── media/                         # Shared Day 2 screenshots (sign-in, environment, navigation)
    │   ├── Lab 7/
    │   │   ├── lab5.md                    # Lab 07: Frontline Operations Agent for store coordination
    │   │   └── media/                     # Lab 7 step screenshots
    │   ├── Lab 8/
    │   │   ├── lab6.md                    # Lab 08: SharePoint-grounded Store Operations Assistant + Copilot Studio
    │   │   └── media/                     # Lab 8 step screenshots
    │   ├── Lab 9/
    │   │   ├── lab7.md                    # Lab 09: Financial analysis with Copilot in Excel, Teams, and Chat
    │   │   └── media/                     # Lab 9 step screenshots
    │   └── Lab 10/
    │       ├── Lab10.md                   # Lab 10: Agent governance and monitoring with Agent 365
    │       └── media/                     # Lab 10 step screenshots
    ├── Day-3/                             # Day 3: Building AI Agents with Microsoft 365 Agents Toolkit and SDK
    │   ├── getting-started.md             # Day 3 overview, objectives, prerequisites, and sign-in steps
    │   ├── masterdoc.json                 # CloudLabs render manifest: Getting Started plus Labs 11–13, in order
    │   ├── Lab 11/
    │   │   ├── Lab-11.md                  # Lab 11: Declarative Agent (RepairServiceAgent) with Toolkit and TypeSpec
    │   │   └── media/                     # Lab 11 step screenshots
    │   ├── Lab 12/
    │   │   ├── Lab-12.md                  # Lab 12: Custom engine HR agent with Agents SDK and Semantic Kernel
    │   │   └── media/                     # Lab 12 step screenshots
    │   └── Lab 13/
    │       ├── Lab-13.md                  # Lab 13: Healthcare appointment agent with Copilot Studio + Power Automate
    │       └── media/                     # Lab 13 step screenshots
    └── Day-4/                             # Day 4: Build and Orchestrate Multi-Agent AI Systems
        ├── Getting-Started.md             # Day 4 scenario, architecture, components, and sign-in steps
        ├── masterdoc.json                 # CloudLabs render manifest: Getting Started plus Labs 14–17, in order
        ├── media/                         # Shared Day 4 assets (architecture diagram)
        ├── Lab 14/
        │   ├── lab10.md                   # Lab 14: Autonomous Hiring Operations Platform (multi-agent + triggers)
        │   └── media/                     # Lab 14 step screenshots
        ├── Lab 15/
        │   ├── lab11.md                   # Lab 15: Product Knowledge Agent with Azure AI Search + Foundry models (RAG)
        │   └── media/                     # Lab 15 step screenshots
        ├── Lab 16/
        │   ├── lab12.md                   # Lab 16: Multi-agent retail assistant (Copilot Studio + Foundry + Fabric)
        │   └── media/                     # Lab 16 step screenshots
        └── Lab 17/
            ├── lab13.md                   # Lab 17: Multi-agent student services system (Atlas orchestrator)
            └── media/                     # Lab 17 step screenshots
```

---

## Day 1: Build AI-Powered Agents and Workflows with Microsoft 365 Copilot

**Estimated Duration: 4 Hours** — [Getting Started](Lab%20Guides/Day-1/Getting-Started.md)

### [Lab 01: Transform Cross-Functional Program Execution at Zava Retail with Planner Agent](Lab%20Guides/Day-1/Lab%201/Lab-1.md)

**Estimated Duration: 40 minutes**

Step into the role of a Regional Operations Manager and use Planner Agent to monitor the Peak Season Readiness Program — reviewing project plans, identifying risks and overdue work, and generating leadership-ready insights.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 0 | Lab Setup — Create the Planner plan, buckets, and tasks | 12 min |
| Exercise 1 | Explore Planner Agent | 4 min |
| Exercise 2 | Analyze the Peak Season Readiness Program | 8 min |
| Exercise 3 | Identify Priorities and Risks | 8 min |
| Exercise 4 | Generate Leadership Insights | 8 min |

### [Lab 02: Elevate Zava Retail Intelligence with a Researcher Agent for Smarter Insights and Reporting](Lab%20Guides/Day-1/Lab%202/Lab-2.md)

**Estimated Duration: 40 minutes**

Use the Researcher Agent to gather and summarize fragmented campaign information from emails, Teams chats, and documents — surfacing action items, key decisions, gaps, and executive communications for the Zava Festive Campaign.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Access the Researcher Agent | 5 min |
| Exercise 2 | Run Your First Research Prompt (Campaign Intelligence) | 10 min |
| Exercise 3 | Action and Decision Intelligence (8 tasks: action items, key decisions, leadership email, meeting prep, status analysis, gaps and risks, document discovery, executive communication) | 25 min |

### [Lab 03: Build the Zava Retail Workforce Upskilling Learning Agent with Microsoft 365 Copilot](Lab%20Guides/Day-1/Lab%203/Lab-3.md)

**Estimated Duration: 40 minutes**

Build a custom Workforce Upskilling Agent with Copilot Agent Builder, ground it in enterprise knowledge sources, diagnose workforce skill gaps, and generate personalized learning plans and readiness briefings.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Create the Workforce Upskilling Agent | 12 min |
| Exercise 2 | Ground the Agent in Organizational Context | 6 min |
| Exercise 3 | Diagnose Workforce Skill Gaps | 9 min |
| Exercise 4 | Generate Personalized Learning Plans | 8 min |
| Exercise 5 | Produce a Workforce Readiness Briefing | 5 min |

### [Lab 04: Automate Zava Retail IT Asset Management with Microsoft 365 Copilot App Builder](Lab%20Guides/Day-1/Lab%204/Lab-4.md)

**Estimated Duration: 40 minutes**

Use App Builder to create a fully functional IT asset tracking application from natural language, refine it conversationally, test it as an IT team member would, and publish it for your team.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Access App Builder and Describe Your App | 12 min |
| Exercise 2 | Refine the App Through Conversation | 10 min |
| Exercise 3 | Test the App as a Real IT Team Member Would | 8 min |
| Exercise 4 | Publish the App and Share It with Your Team | 10 min |

### [Lab 05: Streamline Zava Retail Calendar Management with Microsoft 365 Copilot Cowork](Lab%20Guides/Day-1/Lab%205/Lab-5.md)

**Estimated Duration: 40 minutes**

Use Cowork as an AI-powered executive assistant during a store expansion program — detecting and resolving calendar conflicts, scheduling meetings from email context, and applying standing calendar rules.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Access the Cowork Agent | 3 min |
| Exercise 2 | Populate Your Calendar with Sample Expansion Meetings | 8 min |
| Exercise 3 | Detect and Resolve Calendar Conflicts | 13 min |
| Exercise 4 | Schedule Meetings Intelligently Using Email Context | 8 min |
| Exercise 5 | Apply Executive Calendar Management Rules | 8 min |

### [Lab 06: Build an Enterprise Marketing Operations Agent with Microsoft 365 Copilot](Lab%20Guides/Day-1/Lab%206/Lab-6.md)

**Estimated Duration: 40 minutes**

Build a reusable Marketing Operations Agent in Copilot Chat that enforces a consistent 9-section campaign structure, generates multi-channel assets and imagery, and prepares an executive approval package.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Create and Configure the Marketing Operations Agent | 10 min |
| Exercise 2 | Build the Summer Clearance Campaign Brief | 7 min |
| Exercise 3 | Generate Multi-channel Campaign Assets | 8 min |
| Exercise 4 | Refine the Campaign for Loyalty Members | 5 min |
| Exercise 5 | Adapt the Campaign for Regional Stores | 5 min |
| Exercise 6 | Prepare the Executive Approval Package | 5 min |

---

## Day 2: Build, Extend, and Govern Copilot Agents for Retail Operations

**Estimated Duration: 3 Hours** — [Getting Started](Lab%20Guides/Day-2/getting-started.md)

### [Lab 07: Improve Communication and Work Coordination Across Zava Retail Stores with a Frontline Agent](Lab%20Guides/Day-2/Lab%207/lab5.md)

**Estimated Duration: 40 minutes**

Build a Frontline Operations Agent grounded in SOPs, handbooks, and store checklists, publish it, and test it in Microsoft Teams against realistic cashier, associate, and manager scenarios.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Create the Frontline Operations Agent | 15 min |
| Exercise 2 | Access the Frontline Operations Agent in Microsoft Teams | 5 min |
| Exercise 3 | Test with Real-World Retail Scenarios and Refine Responses (5 tasks) | 20 min |

### [Lab 08: Build a Store Operations Assistant Copilot Agent for Trusted Customer Success at Zava Retail](Lab%20Guides/Day-2/Lab%208/lab6.md)

**Estimated Duration: 40 minutes**

Create a SharePoint-grounded Store Operations Assistant, enhance it in Copilot Studio with advanced instructions and topic-based routing, and build a multi-agent handoff to a specialized HR &amp; Payroll Assistant.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Create and Configure a SharePoint-Grounded Copilot Agent | 15 min |
| Exercise 2 | Advanced Instruction Authoring in Copilot Studio | 10 min |
| Exercise 3 | Design a Multi-Agent Orchestration Pattern with an HR &amp; Payroll Assistant | 15 min |

### [Lab 09: Optimize Financial Analysis and Reporting for Zava Retail Finance Operations with Microsoft 365 Copilot](Lab%20Guides/Day-2/Lab%209/lab7.md)

**Estimated Duration: 40 minutes**

Use Copilot in Excel, Teams, and Copilot Chat to analyze Cost of Goods Sold (COGS) data, summarize finance meetings with task lists and follow-ups, and evaluate a potential business acquisition.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Use Copilot in Excel to Analyze New Product Line COGS | 13 min |
| Exercise 2 | Use Copilot in Teams to Summarize Meeting Notes | 13 min |
| Exercise 3 | Use Copilot Chat to Analyze a Potential Acquisition | 14 min |

### [Lab 10: Govern and Monitor the Zava Retail Agent Ecosystem with Agent 365](Lab%20Guides/Day-2/Lab%2010/Lab10.md)

**Estimated Duration: 60 minutes**

Act as the AI Administrator: publish a Holiday Returns Helper agent from Copilot Studio, review tenant-wide governance dashboards, manage agent lifecycle actions, export the agent inventory, and identify ownerless agents.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Create and Publish the Holiday Returns Helper Agent | 20 min |
| Exercise 2 | Explore the Agent 365 Overview Dashboard | 8 min |
| Exercise 3 | Publish, Install, and Validate the Agent in Microsoft Teams | 10 min |
| Exercise 4 | Block and Unblock the Frontline Operations Assistant | 10 min |
| Exercise 5 | Export the Agent Inventory | 6 min |
| Exercise 6 | Identify Ownerless Agents | 6 min |

---

## Day 3: Building AI Agents with Microsoft 365 Agents Toolkit and SDK

**Estimated Duration: 4 Hours** — [Getting Started](Lab%20Guides/Day-3/getting-started.md)

### [Lab 11: Transform After-Sales Repair Operations at Zava Retail with an AI-Powered Declarative Agent](Lab%20Guides/Day-3/Lab%2011/Lab-11.md)

**Estimated Duration: 60 minutes**

Scaffold a Declarative Agent (RepairServiceAgent) with the Microsoft 365 Agents Toolkit and TypeSpec, connect it to a Repair Service API with full CRUD operations, add Adaptive Cards, and test it in Microsoft 365 Copilot.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Build the Base Agent with TypeSpec Using Microsoft 365 Agents Toolkit (scaffold, define, actions, test) | 30 min |
| Exercise 2 | Enhance Agent Capabilities (CRUD operations, Adaptive Cards, provision and test) | 30 min |

### [Lab 12: Develop a Cross-Channel HR Support Agent for Zava Retail Using Microsoft 365 Agents SDK and Semantic Kernel](Lab%20Guides/Day-3/Lab%2012/Lab-12.md)

**Estimated Duration: 80 minutes**

Configure a grounded HR agent in Microsoft Foundry, scaffold a custom engine agent with the M365 Agents SDK in Visual Studio, integrate Semantic Kernel, test it in Teams via Dev Tunnels, and bring it into Microsoft 365 Copilot Chat.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Prepare Your Agent in Microsoft Foundry | 20 min |
| Exercise 2 | Build Your First Agent Using the M365 Agents SDK | 15 min |
| Exercise 3 | Configure Agent Properties and Test on Teams | 10 min |
| Exercise 4 | Integrate the Microsoft Foundry Agent with the M365 Agents SDK | 25 min |
| Exercise 5 | Bring Your Agent to Copilot Chat | 10 min |

### [Lab 13: Build a Healthcare Agent to Automate Patient Appointments](Lab%20Guides/Day-3/Lab%2013/Lab-13.md)

**Estimated Duration: 100 minutes**

Build the Northstar Patient Assistant in Copilot Studio with identity verification, appointment booking and cancellation topics, and Power Automate flows over Dataverse for end-to-end appointment management with responsible AI safeguards.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 0 | Prepare the Healthcare Data Foundation (solution + Appointment Slot table) | 20 min |
| Exercise 1 | Build the Conversational Healthcare Agent (agent, emergency, identity, booking, and cancellation topics, testing) | 40 min |
| Exercise 2 | Automate Appointment Management (HC-SlotLookup and HC-BookAppointment flows, end-to-end test) | 40 min |

---

## Day 4: Build and Orchestrate Multi-Agent AI Systems with Microsoft Copilot Studio

**Estimated Duration: 4 Hours** — [Getting Started](Lab%20Guides/Day-4/Getting-Started.md)

### [Lab 14: Build Autonomous Hiring Operations Platform for Zava Retail Using Microsoft Copilot Studio](Lab%20Guides/Day-4/Lab%2014/lab10.md)

**Estimated Duration: 60 minutes**

Build a centralized Hiring Agent that orchestrates recruitment with an Application Intake child agent, an Interview Prep connected agent, Dataverse storage, and event-driven email automation with Teams notifications.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Import the Solution | 8 min |
| Exercise 2 | Import Sample Data | 7 min |
| Exercise 3 | Create the Hiring Agent | 5 min |
| Exercise 4 | Add the Application Intake Agent (flow, tools, instructions, testing) | 20 min |
| Exercise 5 | Add the Interview Prep Connected Agent | 10 min |
| Exercise 6 | Automate Candidate Application Emails | 7 min |
| Exercise 7 | Test the Event Trigger | 3 min |

### [Lab 15: Modernize Customer Support at Zava Retail with an AI-Powered Product Knowledge Agent Using Azure AI Search and Foundry Models](Lab%20Guides/Day-4/Lab%2015/lab11.md)

**Estimated Duration: 60 minutes**

Build a RAG-based Retail Assistant by indexing product documents with Azure AI Search and Azure OpenAI embeddings, grounding a Copilot Studio agent in the vector index, and connecting a Microsoft Foundry model through a custom prompt.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Create an Azure AI Search Resource | 8 min |
| Exercise 2 | Create a Storage Account | 8 min |
| Exercise 3 | Create an Azure OpenAI Service and Deploy a Model | 10 min |
| Exercise 4 | Create a Vector Index | 8 min |
| Exercise 5 | Create a Retail Assistant Agent | 5 min |
| Exercise 6 | Add Azure AI Search as a Knowledge Source | 8 min |
| Exercise 7 | Deploy a Model in Microsoft Foundry | 5 min |
| Exercise 8 | Use the Foundry Model from a Copilot Studio Prompt | 8 min |

### [Lab 16: Orchestrating Multi-Agent AI for Retail Using Copilot Studio, Microsoft Foundry, and Fabric](Lab%20Guides/Day-4/Lab%2016/lab12.md)

**Estimated Duration: 60 minutes**

Build the TrailAssist Concierge orchestrator in Copilot Studio and route customer requests across a Foundry-hosted product specialist (TrailGear Expert) and a Fabric Data Agent (TrailOps Analyst) grounded in Lakehouse data.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 1 | Create the Copilot Studio Agent and Configure Knowledge Sources | 15 min |
| Exercise 2 | Create the Foundry Agent and Connect It to Copilot Studio | 20 min |
| Exercise 3 | Create the Fabric Data Agent (Lakehouse, data agent, connection, testing) | 25 min |

### [Lab 17: Build a Multi-Agent System for the Education Industry to Automate Student Services](Lab%20Guides/Day-4/Lab%2017/lab13.md)

**Estimated Duration: 60 minutes**

Build Atlas, an orchestrator agent for Riverbend University, connected to specialist Student Services, Academic, and Admissions agents that use the Dataverse MCP Server, knowledge sources, and skills — then publish to Teams and Microsoft 365 Copilot.

| Exercise | Topic | Approx. Duration |
|------|-------|----------|
| Exercise 0 | Provision the Dataverse Data Foundation | 10 min |
| Exercise 1 | Build Atlas, the Orchestrator Agent | 8 min |
| Exercise 2 | Build the Student Services Agent with Live Dataverse Access | 8 min |
| Exercise 3 | Build the Academic Agent with MCP, Knowledge, and Skills | 12 min |
| Exercise 4 | Build the Admissions Agent with Knowledge and Skills | 8 min |
| Exercise 5 | Connect All Specialist Agents to Atlas and Validate Routing | 8 min |
| Exercise 6 | Publish Atlas to Microsoft Teams and Microsoft 365 Copilot | 6 min |

---

## Key Technologies Covered

| Technology | Description |
|-----------|-------------|
| **Microsoft 365 Copilot** | The core AI assistant across Chat, Excel, Teams, and the Copilot portal, and the surface where all agents are consumed. |
| **Copilot Agent Builder** | No-code creation of custom agents with instructions and uploaded knowledge sources. |
| **App Builder (Frontier)** | Conversational, no-code business application generation inside Microsoft 365 Copilot. |
| **Microsoft 365 Copilot Cowork** | AI-powered executive calendar assistant for conflict detection, scheduling, and standing rules. |
| **Microsoft SharePoint** | Trusted content platform that grounds agents in verified organizational knowledge. |
| **Microsoft Copilot Studio** | Advanced agent authoring: instructions, topics, tools, skills, and multi-agent orchestration. |
| **Agent 365 (Microsoft 365 admin center)** | Tenant-wide agent governance: registry, lifecycle actions, inventory export, and ownership insights. |
| **Microsoft 365 Agents Toolkit &amp; TypeSpec** | Pro-code scaffolding of Declarative Agents with API actions and Adaptive Cards. |
| **Microsoft 365 Agents SDK &amp; Semantic Kernel** | Custom engine agents in Visual Studio that run across Teams and Copilot Chat. |
| **Microsoft Foundry** | Platform for building, grounding, and publishing AI agents and deploying models. |
| **Azure AI Search &amp; Azure OpenAI** | Vector indexing and embeddings powering retrieval-augmented generation (RAG). |
| **Microsoft Dataverse &amp; Power Automate** | Structured data storage and flow automation behind agents, including the Dataverse MCP Server. |
| **Microsoft Fabric** | Lakehouse and Data Agent providing real-time operational insights to conversational agents. |

---

## Additional Resources

- [Microsoft 365 Copilot documentation](https://learn.microsoft.com/microsoft-365-copilot/)
- [Agents for Microsoft 365 Copilot](https://learn.microsoft.com/microsoft-365-copilot/extensibility/)
- [Microsoft Copilot Studio documentation](https://learn.microsoft.com/microsoft-copilot-studio/)
- [Microsoft 365 Agents Toolkit](https://learn.microsoft.com/microsoft-365/developer/agents-toolkit/)
- [Microsoft 365 Agents SDK](https://learn.microsoft.com/microsoft-365/agents-sdk/)
- [Azure AI Search documentation](https://learn.microsoft.com/azure/search/)
- [Microsoft Fabric data agents](https://learn.microsoft.com/fabric/data-science/concept-data-agent)
