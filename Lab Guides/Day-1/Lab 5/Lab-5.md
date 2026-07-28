# Lab 05: Streamline Zava Retail Calendar Management with Microsoft 365 Copilot Cowork

## Estimated Duration: 40 Minutes

## Overview

In this lab, you will use **Microsoft 365 Copilot Cowork** as an AI-powered executive assistant to manage calendar conflicts, schedule meetings intelligently, protect focus time, and stay in control of AI-driven changes.

Zava Retail is a growing SMB omnichannel retailer with 12 physical stores and a successful online business, preparing to open two new stores in neighboring cities next quarter. As the **Expansion Program Lead**, Alex Morgan is responsible for coordinating all project activities and keeping stakeholders aligned. The calendar has become increasingly difficult to manage due to conflicting meeting requests, back-to-back meetings, no protected focus time, and meetings scheduled without agendas.

## Lab Objectives

In this lab, you will perform the following:

- Exercise 1: Access the Cowork Agent
- Exercise 2: Populate Your Calendar with Sample Expansion Meetings
- Exercise 3: Detect and Resolve Calendar Conflicts
- Exercise 4: Schedule Meetings Intelligently Using Email Context
- Exercise 5: Apply Executive Calendar Management Rules

## Scenario

Alex Morgan needs an AI-powered executive assistant to manage the calendar during a store expansion program — detecting and resolving scheduling conflicts, scheduling meetings using email context, and setting up standing rules to protect focus time and enforce notice requirements.

**Key Personas**

- **Alex Morgan – Expansion Program Lead (Learner):** Coordinates the entire store expansion program.
- **Rachel Singh – Operations Director:** Requires meetings to be scheduled at least 48 hours in advance with a clear agenda.
- **Tom Bradley – Store Operations Manager:** Frequently schedules operational meetings at short notice, often without an agenda.
- **Lisa Chen – Procurement & Supply Chain Manager:** Works closely with Alex to coordinate supplier onboarding and inventory deliveries.

## Exercise 1: Access the Cowork Agent

In this exercise, you need to sign in to Microsoft 365 Copilot as Alex Morgan and turn on the Cowork agent.

1. Open a **web browser** and navigate to the following URL.

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

4. From the left navigation menu, enable **Cowork**.

    ![](./media/l5e1t1s1.png)

5. Cowork is now active and ready to use as your calendar assistant for the rest of this lab.

## Exercise 2: Populate Your Calendar with Sample Expansion Meetings

Before Cowork can help you manage conflicts and priorities, your calendar needs some real meetings to work with.

### Task 1: Create Sample Meetings Using Copilot Cowork

In this task, you enter a one-shot prompt that asks Cowork to create eight realistic expansion meetings on your calendar, including two with no agenda so you can test agenda-detection later.

1. Enter the following prompt in the Cowork prompt field, then select **Send**.

    ```
    Act as my calendar assistant. I am Alex Morgan, Expansion Program
    Lead at Zava Retail. We are coordinating the opening of two new
    stores next quarter. Please create the following 8 meetings in my
    calendar for next week.

    Important: For meetings 7 and 8, leave the description and body
    completely empty — no agenda text at all.

    1. "Store Expansion Kickoff — Operations Review"
    Monday, 10:00–11:00 AM
    Organiser: Tom Bradley (Store Operations Manager)

    2. "New Store IT Infrastructure Briefing"
    Monday, 10:30–11:30 AM
    Organiser: IT Team

    3. "Supplier Onboarding Planning — City Store 1"
    Tuesday, 9:00–10:00 AM
    Organiser: Lisa Chen (Procurement & Supply Chain Manager)

    4. "Inventory & Delivery Schedule Review"
    Tuesday, 10:00–11:00 AM
    Organiser: Lisa Chen (Procurement & Supply Chain Manager)

    5. "Marketing Campaign Kickoff — Grand Opening"
    Tuesday, 11:00 AM–12:00 PM
    Organiser: Marketing Team

    6. "HR Recruitment Drive — Store Staffing Update"
    Wednesday, 8:00–9:00 AM
    Organiser: HR Team

    7. "Store Operations Weekly Check-in"
    Thursday, 2:00–3:00 PM
    Organiser: Tom Bradley (Store Operations Manager)
    (NO description, NO agenda — leave body completely blank)

    8. "Expansion Progress Review — Leadership Update"
    Friday, 11:00 AM–12:00 PM
    Organiser: Rachel Singh (Operations Director)
    (NO description, NO agenda — leave body completely blank)

    Please create all 8 meetings and confirm when done.
    ```

    ![](./media/l5e2t1s2.png)

2. Cowork will ask for your approval before creating each event individually. Select **Save** to approve each meeting creation request.

    ![](./media/l5e2t1s3.png)

1. Review the meeting details generated by Copilot Cowork for each scheduled meeting from Monday through Friday, then click **Save** to create the calendar events and continue the workflow until all meetings are successfully created.

   ![](./media/l5e2t1s4.png)

    > **Note:** All eight meetings will be created one at a time, and you'll receive a separate approval prompt for each. Review each request before approving — this is your chance to confirm exactly what Cowork is about to add to your calendar.

    ![](./media/l5e2t1s5.png)

### Task 2: Verify the Meetings

Confirm that all eight meetings actually landed on your calendar by checking the Teams calendar view.

1. Open a **web browser** and navigate to the following URL.

    ```
    https://teams.microsoft.com
    ```

2. In Teams, select **Calendar** from the left navigation to view all eight newly created meetings.

    ![](./media/l5e2t1s6.png)

## Exercise 3: Detect and Resolve Calendar Conflicts

Use Copilot Cowork to identify overlapping meetings and unbroken meeting runs on your calendar, then apply AI-recommended resolutions with your approval.

### Task 1: Scan the Calendar and Prioritize Conflicts

Ask Cowork to review the next five business days, flag every overlap and back-to-back run, and propose fixes — while protecting the two meetings Lisa Chen has already confirmed.

1. Select **New Task**.

    ![](./media/l5e3t1s1.png)

2. Enter the following prompt and select **Send**.

    ```
    I am Alex Morgan, Expansion Program Lead at Zava Retail. We are
    currently coordinating the opening of two new stores in neighbouring
    cities next quarter.

    Scan my calendar for the next 5 business days and do the following:
    1. List every scheduling conflict where two or more meetings overlap
    2. Identify any back-to-back runs of 3 or more consecutive meetings
       with no break between them
    3. For each conflict or back-to-back run, propose a resolution:
       — Which meeting should be moved and why
       — The best alternative time slot that avoids other meetings
       — A polite and professional reschedule message I can send to the organiser

    Priority: Keep the Supplier Onboarding Planning and Inventory &
    Delivery Schedule Review meetings in their current slots if possible,
    as Lisa Chen has confirmed her availability for those times.
    ```

    ![](./media/l5e3t1s2.png)

3. Cowork returns a full conflict report, including the Monday overlap and the Tuesday back-to-back run, with suggested resolutions for each.

    ![](./media/l5e3t1s3.png)

    ![](./media/l5e3t1s4.png)

    ![](./media/l5e3t1s5.png)

    ![](./media/l5e3t1s6.png)
 
### Task 2: Resolve the Monday Conflict

Act on Cowork's recommendation for the overlapping Monday meetings: move the IT briefing and draft a reschedule note, without disturbing the higher-priority Operations Review.

1. With the conflicts identified, ask Cowork to resolve the Monday overlap between the Store Expansion Kickoff and the IT Infrastructure Briefing. Enter the following prompt and select **Send**.

    ```
    For the Monday conflict between the Store Expansion Kickoff —
    Operations Review and the New Store IT Infrastructure Briefing,
    please do the following:
    1. Move the IT Infrastructure Briefing to the next available
       morning slot this week that does not clash with any other
       expansion meetings
    2. Draft a professional reschedule message to the IT Team explaining
       the conflict and proposing the new time
    3. Keep the tone collaborative — mention that the Store Expansion
       Kickoff with Tom Bradley takes priority as it covers operational
       readiness for both new store locations
    ```

    ![](./media/l5e3t2s1.png)

2. Select **Update** to approve the rescheduled IT Infrastructure Briefing.

    ![](./media/l5e3t2s2.png)

3. Cowork confirms the new time and shares the drafted reschedule message.

    ![](./media/l5e3t2s3.png)

    ![](./media/l5e3t2s4.png)

### Task 3: Resolve the Tuesday Back-to-Back Run

Fix the three-meeting Tuesday run by adding prep breaks, keeping Lisa Chen's confirmed slot untouched, and shifting the Marketing kickoff if needed.

1. In the same thread, ask Cowork to fix the Tuesday back-to-back run. Enter the following prompt and select **Send**.

    ```
    For the three back-to-back meetings on Tuesday — Supplier
    Onboarding Planning, Inventory & Delivery Schedule Review, and
    Marketing Campaign Kickoff — please do the following:
    1. Keep the Supplier Onboarding Planning at 9:00 AM as Lisa Chen
       has confirmed her availability
    2. Add a 15-minute preparation break between each meeting
    3. Suggest which meeting is the best candidate to move to a
       later slot if a break cannot be inserted without causing
       further conflicts
    4. Draft a brief note to the Marketing Team explaining that
       their Campaign Kickoff may need to shift by 30 minutes to
       allow preparation time between sessions
    ```

    ![](./media/l5e3t3s1.png)

1. Review the updated meeting schedules generated by Copilot Cowork, then click **Update** for each modified event to apply the proposed time changes and continue the workflow until all meeting updates are completed.

    ![](./media/l5e3t3s2.png)

    ![](./media/l5e3t3s3.png)

2. Cowork proposes the adjusted schedule and a draft note to the Marketing Team.

    ![](./media/l5e3t3s4.png)

    ![](./media/l5e3t3s5.png)

3. Confirm the changes by entering the following prompt.

    ```
    Please apply these schedule changes to the calendar. Then create the
    email as a draft in Outlook — don't send it — so I can review it first.
    ```

    ![](./media/l5e3t3s6.png)

5. Cowork confirms the calendar has been updated and the email has been saved as a draft.

    ![](./media/l5e3t3s7.png)

6. To review the draft email, open the **App Launcher** and select **Outlook** (or use the direct draft link Cowork provides).

    ![](./media/l5e3t3s8.png)

    ![](./media/l5e3t3s9.png)

7. Review the draft email.

    ![](./media/l5e3t3s10.png)

8. Navigate back to **Teams** and refresh the window to view the changes.

    ![](./media/l5e3t3s11.png)

### Task 4: Get a Calendar Health Summary

Wrap up the exercise with an at-a-glance summary of meeting load for the week, plus a recommendation for when to block time for the Master Expansion Plan.

1. Request a summary of the week's calendar health by entering the following prompt and selecting **Send**.

    ```
    Now give me a Calendar Health summary for this week's expansion
    meetings. Include:
    1. Total number of meetings and total meeting hours this week
    2. Any days that are overloaded with meetings
    3. Days that have good availability for focused strategic work
    4. One recommendation for when I should block time to work on
       the Master Expansion Plan document — considering all the
       meetings we have just resolved

    Keep the summary concise and actionable.
    ```

    ![](./media/l5e3t4s1.png)

2. Cowork returns a concise summary of meeting load, overloaded days, and a recommended time to block for focused work.

    ![](./media/l5e3t4s2.png)

    ![](./media/l5e3t4s3.png)

## Exercise 4: Schedule Meetings Intelligently Using Email Context

Real scheduling requests rarely come with a full brief attached — the context often lives in an email thread. In this exercise, you'll send yourself a sample email about supplier onboarding, then ask Cowork to use that context to intelligently schedule a recurring sync with Lisa Chen.

### Task 1: Send a Sample Context Email

Send yourself a short email about supplier onboarding so Cowork has real context to draw on when it drafts the meeting agenda.

1. Navigate to **C:\Lab Files\Cowork** folder and open the **coworkSampleEmail** file to get the sample email for this lab.

    ![](./media/l5e4t1s1.png)

2. Send the sample email about supplier onboarding to the current user using your personal email address.

3. Verify the email has arrived in your inbox.

    ![](./media/l5e4t1s2.png)

### Task 2: Schedule the Weekly Project Sync

Ask Cowork to book a 30-minute sync with Lisa Chen, applying scheduling constraints and pulling talking points straight from the email you just sent.

1. Select **New task**.

    ![](./media/l5e4t2s1.png)

2. Enter the following prompt and select **Send**.

    ```
    Schedule a 30-minute 'Weekly Project Sync' with Lisa Chen next week.
    Constraints: not Monday, not within 30 minutes of either of our
    existing meetings, prefer mornings, and add a Teams link and a draft
    agenda with 3 talking points based on our recent email thread about
    supplier onboarding.
    ```

    ![](./media/l5e4t2s2.png)

3. Cowork reviews the supplier onboarding email you sent to build the agenda talking points.

    ![](./media/l5e4t2s3.png)

4. When prompted, confirm that Cowork should send the meeting invite.

    ![](./media/l5e4t2s4.png)

    ![](./media/l5e4t2s5.png)

5. Open the Teams calendar to verify the **Weekly Project Sync** was created.

    ![](./media/l5e4t2s6.png)

6. Check the personal email address you used earlier — you should receive a meeting request for the newly scheduled sync.

    ![](./media/l5e4t2s7.png)

## Exercise 5: Apply Executive Calendar Management Rules

In this exercise, you'll move from one-off fixes to standing rules — the kind of protections a real executive assistant would maintain automatically.

### Task 1: Define Standing Calendar Rules

Set up two ongoing rules: flag any meeting requested with less than 48 hours' notice, and protect a 90-minute daily focus block for the Master Expansion Plan.

1. Select **New task**.

    ![](./media/l5e4t2s1.png)

2. Enter the following prompt in the prompt field and click the **Send** button.

    ```
    I want to apply two standing rules to my calendar going forward: (1)
    Any meeting requested with less than 48 hours' notice should be
    flagged, and I should be prompted before accepting — this is requirement from my Operations Director. (2) Protect a daily
    90-minute focus block each morning this week for the Master Expansion
    Plan document — no meetings should be scheduled over it without my
    explicit approval. Show me what this looks like on my calendar before
    making any changes.
    ```

    ![](./media/l5e5t1s1.png)

3. In the response card, select **Fix Tuesday only** for the focus-block recommendation, click **Next**, then on the final confirmation card select **Set up both** and click **Submit** to apply the standing calendar rules.

    > **Note:** Cowork's responses are AI-generated, so exact wording may vary from what's shown here.

    ![](./media/l5e5t1s2.png)

    ![](./media/l5e5t1s3.png)

4. Review the proposed **Focus — Master Expansion Plan** calendar update, then click **Update** to apply the focus-block changes and continue the rule setup process.

    ![](./media/l5e5t1s4.png)

5. Review the **Under-48h meeting invite flag** trigger configuration, then click **Set up** to create the automatic notification rule for short-notice meeting invitations.

    ![](./media/l5e5t1s5.png)

6. Review the **Focus block guard — Master Expansion Plan** trigger settings, then click **Set up** to create the automatic alert rule that protects focus blocks from conflicting meeting invitations.

    ![](./media/l5e5t1s6.png)

7. Verify that the focus blocks were updated and both standing rules (**Under-48-hour flag** and **Focus-block guard**) are now active, confirming the calendar management workflow completed successfully.

    ![](./media/l5e5t1s7.png)

### Task 2: Test the 48-Hour Notice Rule

Simulate a real short-notice request from Tom Bradley to confirm the new notice rule actually triggers as expected.

1. Enter the following prompt to test the rule you just created, then select **Send**.

    ```
    Tom Bradley just messaged asking for a 30-minute call tomorrow morning
    to discuss a staffing issue at City Store 1 — no agenda given. Can you
    find time?
    ```

    ![](./media/l5e5t2s1.png)

2. Cowork flags the request as short-notice and asks for your permission before proceeding.

    ![](./media/l5e5t2s2.png)

    ![](./media/l5e5t2s3.png)

3. Review and approve the proposed meeting slot when prompted.

    ![](./media/l5e5t2s4.png)

### Task 3: Get an Executive Summary

Ask Cowork to confirm focus time is protected, flag any meetings still missing an agenda, and verify Alex is on track for the Leadership Update.

1. Enter the following prompt in the prompt field and click the **Send** button.

    ```
    Give me an executive summary of my calendar for the rest of this week:
    confirm my focus blocks are protected, flag any meetings that still
    don't have an agenda, and tell me if I'm on track to have
    uninterrupted time to finish the Master Expansion Plan before Friday's
    Leadership Update with Operations Director.
    ```

    ![](./media/l5e5t3s1.png)

2. Cowork returns an executive summary confirming your protected focus time, any meetings still missing an agenda, and whether you're on track for Friday's Leadership Update.

    ![](./media/l5e5t3s2.png)

    ![](./media/l5e5t3s3.png)

## Summary

In this lab, you have completed the following:

- Signed in to Microsoft 365 Copilot Cowork and used it as an AI-powered executive calendar assistant for Alex Morgan's store expansion program
- Populated the calendar with eight expansion meetings using a single prompt, and resolved a Monday overlap and a Tuesday back-to-back run with AI-recommended fixes
- Scheduled a weekly project sync with Lisa Chen by pulling talking points directly from an email context, with scheduling constraints applied automatically
- Set up two standing calendar rules — a 48-hour notice flag and a 90-minute daily focus block — and tested the notice rule against a real short-notice request from Tom Bradley
- Generated an executive summary confirming protected focus time, meetings missing agendas, and on-track status for the Friday Leadership Update

## You have successfully completed the lab!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](./media/Next.png)
