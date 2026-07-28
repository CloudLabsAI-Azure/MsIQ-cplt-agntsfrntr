# Lab 06: Build an Enterprise Marketing Operations Agent with Microsoft 365 Copilot

## Estimated Duration: 40 Minutes

## Overview

In this lab, you will use **Microsoft 365 Copilot Chat** to build a reusable custom agent - the **Zava Retail Marketing Operations Advisor** - that plans campaigns to a consistent enterprise structure, generates creative assets, adapts content for different audiences and channels, and prepares executive-ready summaries.

Zava Retail is a growing SMB omnichannel retailer with 12 physical stores and a successful online business. Its marketing team runs frequent, multi-channel campaigns - seasonal sales, product launches, loyalty promotions - but has no consistent, repeatable way to plan them. With a Summer Clearance campaign due for leadership approval by the end of the week, Priya Nair needs a faster, more consistent way to plan the campaign, produce channel-ready assets, adapt it for different audiences and regions, and package it for executive review.

## Lab Objectives

In this lab, you will perform the following:

- Exercise 1: Create and Configure the Marketing Operations Agent
- Exercise 2: Build the Summer Clearance Campaign Brief
- Exercise 3: Generate Multi-channel Campaign Assets
- Exercise 4: Refine the Campaign for Loyalty Members
- Exercise 5: Adapt the Campaign for Regional Stores
- Exercise 7: Prepare the Executive Approval Package

## Scenario

Every campaign brief at Zava Retail looks different depending on who wrote it. Creative assets for email, social, SMS, and in-store signage are produced separately, often inconsistent in tone. Executives receive summaries in varying formats, which slows down approvals. When a campaign needs to be adapted for different audiences or regions, the team frequently starts over.

**Key Personas**

- **Priya Nair - Marketing Operations Lead (Learner):** Owns campaign planning and execution at Zava Retail.
- **David Kim - VP of Marketing:** Requires every campaign brief to include an executive summary, KPIs, and clearly flagged risks before he will approve it.
- **Sam Osei - Creative Director:** Needs channel-ready first-draft copy and imagery across email, social, SMS, and in-store signage.
- **Regional Store Directors - North, South, Urban, Rural:** Require the same campaign to be adapted to local context.

## Exercise 1: Create and Configure the Marketing Operations Agent

In this exercise, you will sign in to Microsoft 365 Copilot Chat as Priya Nair and create a new custom agent from scratch.

### Task 1: Sign In to Microsoft 365 Copilot Chat

1. Open a web browser and navigate to the following URL.

    ```
    https://m365.cloud.microsoft/chat/
    ```

2. Sign in with your Microsoft 365 Copilot account credentials.

     - **Username**: <inject key="AzureAdUserEmail"></inject> **(1)**

        ![](./media/l3e1t1s1.png)

    - **Password**: <inject key="AzureAdUserPassword"></inject> **(2)**

        ![](./media/l3e1t1s2.png)

3. When prompted to **Stay signed in**, select **No**.

    ![](./media/l3e1t1s3.png)


### Task 2: Create the Agent

1. From the left navigation menu, select **New agent**.

    ![](./media/l6e1t1s1.png)

2. Select **Skip to configure**.

    ![](./media/l6e1t1s2.png)

3. Enter the agent's identity:

    - **Name**: ```Campaign Planning Assistant```
    - **Description**: ```Enterprise AI assistant for planning and executing retail marketing campaigns.```
    - **Instruction**: Enter the following instruction:

        ```
        You are the Campaign Planning Assistant, an enterprise AI
        assistant that supports the Zava Retail marketing team in planning,
        creating and preparing multi-channel marketing campaigns for the executive
        approval.

        ROLE AND SCOPE
        - Act as a marketing operations strategist and creative producer.
        - Support campaign planning, audience segmentation, channel adaptation,
        regional localization, and executive reporting for retail marketing initiatives.
        - Stay within marketing, brand, and campaign operations topics. Politely
        decline requests unrelated to marketing operations.

        RESPONSE REQUIREMENTS
        Every campaign-related response must include the following sections, clearly labelled:
        1. Campaign Objective
        2. Target Audience
        3. Key Messaging
        4. Channels
        5. Timeline
        6. KPIs (Key Performance Indicators)
        7. Risks and Assumptions
        8. Executive Summary (3-5 sentences, written for a VP-level audience)
        9. Creative Assets (descriptions and, where requested, generated images)

        STYLE AND TONE
        - Professional, concise, and action-oriented.
        - Default to Zava Retail's brand voice: confident, customer-first, optimistic, and inclusive.
        - Avoid unsubstantiated claims; flag assumptions explicitly.

        BRAND GUARDRAILS
        - Do not fabricate pricing, legal disclaimers, or discount terms beyond what the user specifies.
        - Do not generate content that disparages competitors by name.
        - Always mark placeholder data (e.g., dates, budgets) clearly as [PLACEHOLDER] if not provided by the user.

        WHEN ASKED TO ADAPT CONTENT
        - Preserve the original campaign objective and core value proposition unless explicitly told to change them.
        - Clearly state what was changed and why when adapting for a new audience, channel, or region.

        WHEN ASKED FOR EXECUTIVE MATERIALS
        - Prioritize brevity, business impact, and risk visibility.
        - Use structured, scannable formatting (headers, bullet points, short paragraphs).
        ```

        ![](./media/l6e1t1s3.png)

### Task 3: Add a Knowledge Source

1. Move to the **Knowledge** section and upload the required files available at **C:\Lab Files\Lab 6 - Lab files**.

    ![](./media/image7.png)

### Task 4: Enable Capabilities

1. Scroll down and navigate to the **Capabilities** section. Make sure the **Create images** capability is enabled.

    ![](./media/image8.png)

2. Click **Create** to publish the agent.

    ![](./media/image9.png)

3. Select **Go to agent**.

    ![](./media/image10.png)

    Now the agent is ready to use.

    ![](./media/image11.png)

## Exercise 2: Build the Summer Clearance Campaign Brief

David Kim has asked Priya for a complete campaign plan for the Summer Clearance event before he'll consider it for approval. In this exercise, you will test whether a single prompt produces a complete, structured campaign brief.

### Task 1: Generate the Campaign Brief

1. Open a chat with the **Zava Retail Marketing Operations Advisor**.

    ![](./media/image11.png)

2. Enter the following prompt, then select **Send**.

    ```
    Create a complete Summer Clearance campaign (up to 50% off apparel)
    with the full 9-section structure, and generate (render, don't just
    describe) a hero banner image for the Creative Assets section that
    reflects the offer and Zava Retail's brand voice.
    ```

    ![](./media/image12.png)

3. Confirm the **Creative Assets** section includes a promotional banner concept, and that an image has been generated if Image Generation is enabled.

    ![](./media/image13.png)

    > **Note:** Generated outputs are non-deterministic and may vary across users, sessions, and environments.

4. Review the response and confirm it includes all nine required sections: **Campaign Objective**, **Target Audience**, **Key Messaging**, **Channels**, **Timeline**, **KPIs**, **Risks and Assumptions**, **Executive Summary**, and **Creative Assets**.

    ![](./media/image14.png)
    ![](./media/image15.png)
    ![](./media/image16.png)
    ![](./media/image17.png)
    ![](./media/image18.png)
    ![](./media/image19.png)
    ![](./media/image20.png)
    ![](./media/image21.png)
    ![](./media/image22.png)

    > **Note:** Generated outputs are non-deterministic and may vary across users, sessions, and environments.

## Exercise 3: Generate Multi-channel Campaign Assets

Sam Osei's creative team needs a running start across every channel. In this exercise, you will ask the agent to translate the Summer Clearance campaign into channel-ready assets for seven distinct formats in a single request.

### Task 1: Generate Channel Assets

1. In the same conversation as Exercise 2 (to preserve campaign context), enter the following prompt, then select **Send**.

    ```
    Generate assets for this campaign across the following channels: Email,
    Teams announcement, LinkedIn, Instagram, Facebook, SMS, and in-store
    digital signage. For each channel, provide the copy, tone adjustments,
    and any format-specific notes (e.g., character limits, image aspect ratio).
    ```

    ![](./media/image23.png)

2. Review each of the seven channel outputs and confirm they are adapted to the channel.

    ![](./media/image24.png)
    ![](./media/image25.png)
    ![](./media/image26.png)
    ![](./media/image27.png)
    ![](./media/image28.png)

### Task 2: Generate a Promotional Image

1. Enter the following prompt, then select **Send**.

    ```
    Generate a promotional image for the Instagram post that matches the
    Summer Clearance campaign's messaging and Zava Retail's brand voice.
    ```

    ![](./media/image29.png)

2. Confirm that an image is generated and visually consistent with the campaign messaging.

    ![](./media/image30.png)

## Exercise 4: Refine the Campaign for Loyalty Members

David Kim has a follow-up request: loyalty program members shouldn't receive the same "everything must go" clearance messaging as everyone else - they should feel like they're getting early, exclusive access. In this exercise, you will refine the existing campaign without starting over.

### Task 1: Refine for Audience and Brand Tone

1. In the same conversation, enter the following prompt, then select **Send**.

    ```
    Refine this campaign for loyalty program members, with a more premium
    brand feel. Preserve the original campaign objective and KPIs, but
    adjust messaging, tone, and offer framing accordingly.
    ```

    ![](./media/image31.png)

2. Review the response and confirm it explicitly states:

    - What changed (e.g., messaging shifted from "clearance" to "exclusive loyalty access")
    - What was preserved (objective, KPIs, timeline)

3. Confirm the tone reads as more premium - word choice, pacing, and framing should feel distinct from the original mass-market version.

    ![](./media/image32.png)
    ![](./media/image33.png)
    ![](./media/image34.png)

## Exercise 5: Adapt the Campaign for Regional Stores

Zava Retail's regional store directors have flagged that a single national message doesn't land the same way in every market. In this exercise, you will generate four regional versions of the same campaign.

### Task 1: Generate Regional Variants

1. In the same conversation, enter the following prompt, then select **Send**.

    ```
    Create four regional versions of this campaign for: North stores, South
    stores, Urban stores, and Rural stores. Highlight any differences in
    messaging, product mix emphasis, or channel priority for each version,
    while keeping the core campaign objective identical.
    ```

    ![](./media/image35.png)

2. Review each of the four versions and confirm:

    - Each has a distinct regional angle (e.g., Urban emphasizes foot traffic and digital signage; Rural emphasizes SMS and local relevance)
    - All four versions stay consistent with the original campaign objective and KPIs
    - There are no contradictory claims between versions

    ![](./media/image36.png)
    ![](./media/image37.png)
    ![](./media/image38.png)
    ![](./media/image39.png)

## Exercise 7: Prepare the Executive Approval Package

David Kim has one rule for Friday's leadership review: every campaign pitch must be scannable in under two minutes. In this exercise, you will generate a complete executive approval package from the campaign you've built.

### Task 1: Generate the Executive Approval Package

1. In the same conversation, enter the following prompt, then select **Send**.

    ```
    Prepare an executive approval package for this campaign, including:
    - Executive summary
    - Expected business impact
    - Campaign risks
    - Assumptions
    - Success metrics
    - Approval checklist
    ```

    ![](./media/image40.png)

2. Review the response. It must cover the following points:

    - **Executive Summary**: 3-5 sentence overview for a VP-level decision-maker
    - **Expected Business Impact**: quantified or directional impact (revenue, traffic, engagement)
    - **Campaign Risks**: realistic risks (e.g., inventory shortfall, message fatigue, timing conflicts)
    - **Assumptions**: explicitly flagged placeholders (budget, dates, inventory levels)
    - **Success Metrics**: tied back to the KPIs from Exercise 3
    - **Approval Checklist**: actionable items (e.g., Legal review, Brand review, Budget sign-off, Channel scheduling confirmed)

    ![](./media/image41.png)
    ![](./media/image42.png)
    ![](./media/image43.png)

## Summary

In this lab, you have completed the following:

- Built a custom **Marketing Operations Agent** in Microsoft 365 Copilot Chat with enterprise-grade instructions that enforce a consistent 9-section campaign structure
- Generated a full campaign brief and multi-channel creative assets for the Zava Retail Summer Clearance campaign, including a hero banner image
- Produced channel-ready assets across 7 formats (Email, Teams, LinkedIn, Instagram, Facebook, SMS, and in-store digital signage)
- Refined the campaign for a premium loyalty program audience, preserving the original objective and KPIs while adjusting messaging and tone
- Adapted the campaign across four regional store variants (North, South, Urban, Rural) with distinct local angles
- Packaged the campaign for executive approval with a summary, business impact analysis, risks, assumptions, success metrics, and an approval checklist

## You have successfully completed the lab!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](./media/Next.png)
