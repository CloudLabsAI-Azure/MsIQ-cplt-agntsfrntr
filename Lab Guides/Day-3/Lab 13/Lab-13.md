# Lab 13: Build a Healthcare Agent to Automate Patient Appointments

### Estimated Duration: 100 Minutes

## Scenario

Northstar Community Hospital operates multiple outpatient clinics and receives hundreds of appointment requests every day through phone calls and emails. This manual scheduling process often results in long wait times, booking conflicts, and increased administrative workload for front-desk staff.

To improve patient experience and operational efficiency, the hospital is implementing an AI-powered patient assistant built with Microsoft Copilot Studio. The assistant enables patients to securely verify their identity, ask hospital-related questions, view available appointment slots, book appointments, and cancel existing bookings. Behind the scenes, Power Automate orchestrates appointment retrieval and booking while Microsoft Dataverse stores appointment information.

By the end of this lab, you will have built an intelligent healthcare agent that combines conversational AI with business process automation to streamline patient appointment management.

## Persona

**Emily Carter**  
**Role:** Digital Transformation Lead - Northstar Community Hospital

Emily is responsible for modernizing patient services by implementing AI-powered healthcare solutions. Her objective is to reduce administrative effort, improve appointment scheduling efficiency, and provide patients with a secure self-service experience while ensuring sensitive healthcare interactions follow responsible AI practices.

## Lab Objectives

In this lab, you will perform the following:

- Exercise 0: Prepare the Healthcare Data Foundation
  - Task 0 Creating solution
  - Task 1 - Create and Populate the Appointment Slot Table
  - Task 3 - Update the action for the agent
  - Task 4 - (Read only) Understand the decorators
  - Task 5 - Test your agent
- Exercise 1 - Build the Conversational Healthcare Agent
  - Task 1 - Create the Northstar Patient Assistant
  - Task 2 - Create the Emergency Assistance Topic
  - Task 3 - Build the Patient Identity Verification Topic
  - Task 4 - Build the Appointment Booking Topic
  - Task 5 - Build the Appointment Cancellation Topic
  - Task 6 - Test the Healthcare Agent
- Exercise 2 - Automate Appointment Management
  - Task 1 - Build the HC-SlotLookup Flow
  - Task 2 - Connect the HC-SlotLookup Flow to the Agent
  - Task 3 - Build HC-BookAppointment Flow
  - Task 4 - Connect the HC-BookAppointment Flow to the Agent
  - Task 5 - Test the End-to-End Appointment Booking Experience

## Exercise 0 - Prepare the Healthcare Data Foundation

Create and populate the Dataverse table that will store appointment slot information used throughout the lab.

### Task 0 - Creating solution

1. Open the browser, enter the following URL to navigate to the Power Apps portal and login using the credentials given in the **Environment tab**:

   ```
   make.powerapps.com
   ``` 

2. From the left navigation pane, select **Tables** **(1)**. On the **Tables** page, select **+ New table** **(2)**, and then choose **Create new tables** **(3)** from the drop-down menu.

    ![](./media/l13-0a.png)

3. Now click on **Switch and create**. It will be created in few minutes.

    ![](./media/l13-0b.png)

    ![](./media/l13-0c.png)

4. In the left navigation, select **Solutions (1)**, and then click **+ New solution (2)**.

    ![](./media/l13-0.png)

5. In the **New solution** pane, enter **HealthcareSolution-<inject key="DeploymentID" enableCopy="false"/> (1)** in **Display name**, enter **HealthcareSolution-<inject key="DeploymentID" enableCopy="false"/> (2)** in **Name**, and then click **+ New publisher (3)**.

    ![](./media/l13-1.png)

6. In the **New publisher** pane, enter **NorthstarHealthcare (1)** in **Display name**, enter **NorthstarHealthcare (2)** in **Name**, enter **nhs (3)** in **Prefix**, and then click **Save (4)**.

    ![](./media/l13-2.png)

7. In the **New solution** pane, verify the solution details and selected publisher, and then click **Create (1)**.

    ![](./media/l13-3.png)

### Task 1 - Create and Populate the Appointment Slot Table

Create the Appointment Slot Dataverse table and import the provided appointment schedule so the healthcare agent has appointment data available during booking.

1. In the solution command bar, click **+ New (1)**, select **Table (2)**, and then select **Tables (3)**.

    ![](./media/l13-4.png)

1. Select **Import an Excel file or .CSV**.

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image4.png)

21. In the Browse file window, browse to **C:/Lab Files/Healthcare/** **(1)**, select **AppointmentSlot.csv file (2)**, and then click **Open (3)**.

    ![](./media/l13-5.png)

1. In the **Import an Excel or .CSV file** dialog, confirm that **AppointmentSlot.csv** is included, and then click **Import (1)**.

    ![](./media/l13-6.png)

7. Select all the columns and click **Save**.

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image6.png)

8. Select **Save and exit(twice).**

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image7.png)

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image8.png)

9. Your table will appear in the table list. Select the **Appointment
    Slot** table.

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image9.png)

10. Select **Columns**-\>Save these name values for the next exercise.

    ![](./media/image10.png)

    ![](./media/image11.png)

## Exercise 1 - Build the Conversational Healthcare Agent

Develop a secure patient assistant using Copilot Studio that can answer
hospital questions, verify patient identity, and manage appointment
conversations.

### Task 1 - Create the Northstar Patient Assistant

Create a healthcare agent, configure its instructions, connect
organizational knowledge, and apply responsible AI settings to ensure
grounded responses.

1. In a new tab, enter the following URL to navigate to the Copilot Studio portal:

    ```
    https://copilotstudio.microsoft.com
    ```

1. Click **Agents** from the left-navigation menu, and then select
    **+Create a blank agent.**

    ![](./media/image12.png)

1. In the **Name your agent** dialog, enter **Northstar Patient Assistant (1)**, expand **Agent settings (Optional) (2)**, select **HealthcareSolution (3)** from the drop-down, and then click **Create (4)**.

    ![](./media/l13-8.png)

1. After the agent is provisioned, on the **Overview** tab, click **Edit (1)**.

    ![](./media/l13-9.png)

1. Enter the following agent’s description, then click **Save**.

    ```
    An AI assistant that helps patients book and cancel appointments
    while answering hospital-related questions.
    ```

    ![](./media/image14.png)

1. Now, scroll down to the **Instructions** section, click **Edit (1)**.

    ![](./media/l13-10.png)

1. Enter the following instructions in the field, then click on **Save**.

    ```
    You are the Northstar Patient Assistant.
    Use the connected SharePoint knowledge only to answer operational questions such as clinic opening hours, appointment preparation instructions, insurance information, parking, accessibility, and contact details.
    Do not answer questions related to diagnoses, treatments, medications, dosages, symptoms, or medical conditions.
    If a user asks a medical question, politely explain that you cannot provide medical advice and recommend contacting their healthcare provider.
    At the end of every informational response generated from the knowledge source, include the following disclaimer:
    This information is provided for general guidance only. Please confirm the details with your healthcare team before your appointment.  
    ```

    ![](./media/l13-11.png)

6. In the knowledge section, select **Add knowledge** to add a
    knowledge source to the agent.

    ![](./media/image16.png)

8. In the file picker, browse to **C:/Lab Files/Healthcare/ (1)**, select the clinic information files shown **(2)**, and then click **Open (3)**.

    - Clinic_Opening_Hours_and_Contact_Det...
    - Insurance_and_Billing_FAQs
    - Parking_and_Accessibility_Guide
    - Pre-Procedure_Preparation_Instructions

      ![](./media/l13-12.png)

9. Click **Add to agent**.

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image18.png)

10. Disable the **web search** option.

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image19.png)

11. Select **Setting**.

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image20.png)

12. Now set the following settings in the setting window:

    - Set Content moderation level to **medium**.

    - Turn off **Allow ungrounded responses** in the knowledge section.

    - Click **Save** to save the changes.

    - Close the setting window

      ![A screenshot of a computer AI-generated content may be incorrect.](./media/image21.png)

      ![A screenshot of a computer AI-generated content may be incorrect.](./media/image22.png)

### Task 2: Create the Emergency Assistance Topic

Build a safety topic that immediately identifies emergency medical
situations and directs patients to emergency services instead of
continuing the conversation.

1. Navigate to **Topics** tab, select **+ Add a topic**, then click **From blank**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image23.png)

2. Enter the name of the topic as **Emergency Assistance**.

3. Enter the following value in the trigger:

    ```
    Use this topic when a user reports a medical emergency or mentions
    symptoms such as chest pain, difficulty breathing, severe bleeding,
    unconsciousness, or asks for emergency medical assistance.
    ```

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image24.png)

4. Click the **plus sign(+)** below trigger and then select **Send a
    message**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image25.png)

5. Enter the following message in the message box:

    ```
    If you believe you are experiencing a medical emergency, call your
    local emergency services 999 immediately or visit the nearest
    emergency department. I can't provide assistance in emergency medical situations.
    ```

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image26.png)

6. Click the **plus sign** below the message box and select **Topic management**-\>select **End conversation**.

    ![](./media/image27.png)

7. Click the **Save** button to save the topic.

    ![](./media/image28.png)

### Task 3 - Build the Patient Identity Verification Topic

Create a reusable topic that securely collects patient identity
information before allowing appointment-related actions.

1. Navigate to **Topics** tab, select **+ Add a topic**, then click **From blank**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image23.png)

2. Enter the name of the topic as **Verify Patient Identity**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image29.png)

3. Enter the **description**:

    ```
    Internal helper topic. This topic is only called from other topics. It should verify the patient's identity once and then immediately return control to the calling topic. It should never be selected directly based on user input or called more than once in the same conversation.
    ```

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image30.png)

4. Click the plus sign(+) and select **Ask a question** from the drop-down.

    ![](./media/image31.png)

5. Enter the following details:

    - Message: **Please enter your Patient ID (for example, NH1234)**

    - Identify: Select **User's entire response**

    - Set Variable: Enter **PatientID**. Make it **Global**.

      ![](./media/image32.png)

      ![](./media/image33.png)

      ![](./media/image34.png)

6. Select Sign (+) below the previous node and add **Ask Question**.

7. Enter the following details:

    - Question: **Please enter your date of birth in YYYY-MM-DD format**

    - Identify: Select **User's entire response**

    - Set Variable: Enter ** **DateOfBirth** **. Make it **Global**.

    ![](./media/image35.png)

8. Select the **+** button below the node. Select **Ask a question.**

9. Enter the following details:

    - Question: **Please enter your full name.**

    - Select **Person Name** in the identify field.

    - Create a new variable name as: **PatientName** and make it
    **Global,** so that we can access it outside of this topic.

      ![A screenshot of a computer AI-generated content may be incorrect.](./media/image36.png)

1. Select the **+** button below the previous node. Select **Ask a question**.

1. Enter the following message:

    ```
    Thank you. Your identity has been verified. Let's continue with
    your appointment request.
    ```

    ![](./media/image37.png)

1. Select the **+** button below the previous node. Select **Topic management-\>End current topic**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image38.png)

1. Select **Save** to save the topic.

    ![](./media/image39.png)

### Task 4 - Build the Appointment Booking Topic

Design the conversation that collects appointment preferences and
prepares the booking request for automation.

1. Go to **Topics**. Select **+ Add a topic**. Select **From blank**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image40.png)

2. Enter:

    - Topic Name: **Book Appointment**

    - Topic Description: 
    
       ```
       Use this topic when a patient wants to book, schedule, or make an appointment with a healthcare provider.
       ```

       ![A screenshot of a computer AI-generated content may be incorrect.](./media/image41.png)

3. Click the **+ sign** below the previous node. Select **Topic Management -\> Go to another topic-\> Verify Patient Identity**.

    ![](./media/image42.png)

4. Click the **+ sign** below the previous node. Select **Ask a question**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image43.png)

5. Enter the following details:

    - Enter question: 

        ```
        Which speciality would you like to book an
        appointment with?

        - Cardiology

        - Dermatology

        - Orthopaedics

        - General Practice

        - Physiotherapy
        ```

    - Identify: Select **User’s entire response**

    - Set variable: Enter **specialty**

      ![A screenshot of a computer AI-generated content may be incorrect.](./media/image44.png)

6. Click the **+ sign** below the previous node. Select **Ask a question.**

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image45.png)

7. Enter the following details:

    - Question: Enter **Is this your first visit or a follow-up appointment?**

    - Identify: Select **User’s entire response**

    - Save user response as **AppointmentType**

      ![A screenshot of a computer AI-generated content may be incorrect.](./media/l13-13.png)

8. Click the **+ sign** below the previous node. Select **Ask a question.**

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image48.png)

    - Question: **Please briefly describe the reason for your
    appointment.**

    - Identify: Select **User’s entire response**

    - Save user response as ****ReasonForVisit****

      ![A screenshot of a computer AI-generated content may be incorrect.](./media/image49.png)

9. Click the **+ sign** below the previous node. Select **Send a message.**

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image50.png)

10. Enter the following message:

    ```
    I can help you schedule your appointment, but I can't provide medical advice. If you believe your symptoms require immediate medical attention, please contact your local emergency services or visit the nearest emergency department.
    ```

    ![A screenshot of a chat AI-generated content may be incorrect.](./media/image51.png)

11. Click the **+ sign** below the previous node. Select **send a message.**

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image52.png)

12. Enter the following message:

    ```
    Thank you. I've collected the information needed for your appointment request.

    In the next exercise, this topic will be enhanced to retrieve
    available appointment slots, allow you to select a preferred time, and confirm your booking using Power Automate flows.
    ```

    ![A screenshot of a computer screen AI-generated content may be  incorrect.](./media/image53.png)

13. Click the **+ sign** below the previous node. Select Topic Management → End current topic.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image54.png)

14. Select **Save** to save the topic.

    ![](./media/image55.png)

### Task 5 - Build the Appointment Cancellation Topic

Create a conversation that allows patients to securely cancel existing
appointments after confirming their identity

1. Navigate to **Topics**. Select **+ Add a topic**. Select **From blank**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image56.png)

2. Enter the following details:

    - Topic Name: **Cancel Appointment**

    - Description: **Use this topic when a patient wants to cancel an existing appointment.**

      ![A screenshot of a computer AI-generated content may be incorrect.](./media/image57.png)

3. Click the **+ sign** below the previous node. Select **Topic Management -\> Go to another topic-\> Verify Patient Identity**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image58.png)

4. Click the **+ sign** below the previous node. Select Ask question.

    ![](./media/image59.png)

5. Enter the following details:

    - Question: Please enter your appointment reference number(AB2039).

    - Identify: User’s entire response

    - Save User response as: AppointmentReference

      ![A screenshot of a computer AI-generated content may be incorrect.](./media/image60.png)

6. Click the **+ sign** below the previous node. Select Ask a question.

7. Enter the bellow details:

    - Question: Are you sure you want to cancel this appointment?

    - Identify: Multiple choice options

    - Options for users: Select +New option-\>Enter **Yes++

    - Select +New option -\>Enter **No**

    - Save response as: CancelConfirmation

      ![](./media/image61.png)

8. Click the **+ sign** below the previous Yes node. Select Add a message.

    ![](./media/image62.png)

9. Enter the following message:

    ```
    Thank you. Your cancellation request has been recorded.
    ```

    ![](./media/image63.png)

10. Click the **+ sign** below the previous No node. Select Add a
    message.

    ![](./media/image64.png)

11. Enter the following message:

    ```
    No problem. Your appointment has not been cancelled. If you need
    further assistance, let me know.
    ```

    ![](./media/image65.png)

12. Click the **+ sign** below the previous node. Select **Topic Management → End current topic**

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image66.png)

13. Save the topic.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image67.png)

14. Select publish(twice) to publish the agent.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image68.png)

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image69.png)

### Task 6 - Test the Healthcare Agent

Validate the conversational experience by testing emergency handling,
knowledge retrieval, and appointment booking interactions.

1. Select **Test** from the upper-right corner of Copilot Studio.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image70.png)

2. Start a new conversation. Enter the following prompt and click Send button:

    ```
    I have chest pain.
    ```

    ![A screenshot of a chat AI-generated content may be incorrect.](./media/image71.png)

3. **Review the output:**

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image72.png)

4. Start a **new test session:** Enter the following prompt:

    ```
    Which insurance providers do you accept?
    ```

    ![](./media/image73.png)

5. Now you can see the agent is accessing the genral informations:

    ![](./media/image74.png)

6. Started a new conversation: Enter the following prompt:

    ```
    I want to book an appointment.
    ```

    ![](./media/image75.png)

7. Enter follow-up questions:

    - Enter your Patient ID: **NH2201**

    - Please enter your date of birth: **2/11/1985**

    - Please enter your name: **James Ortiz**

    - Which speciality would you like to book an appointment with:
    **Cardiology**

    - Is this your first visit or a follow-up appointment: Select First
    Visit

    - Please briefly describe the reason for your appointment: **I m
    feeling little pain in my chest**

      ![](./media/image76.png)

      ![](./media/image77.png)

      ![](./media/image78.png)

## Exercise 2 — Automate Appointment Management

Integrate Power Automate with Copilot Studio to retrieve appointment
availability and automatically confirm bookings.

### Task 1 — Build the HC-SlotLookup Flow

Create a Power Automate flow that retrieves available appointment slots
from Dataverse based on the patient's selected medical specialty.

1. Open a new tab and navigate to **make.powerautomate.com**.

2. Select **Create** from the left navigation menu. Then choose **Instant cloud flow**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image79.png)

3. Enter the flow name as **HC-SlotLookup**. Then choose **When an agent calls the flow** trigger. Select **Create** to create the flow.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image80.png)

4. Select the **When an agent calls the flow** trigger and then click **+Add an input**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image81.png)

5. Select **Text**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image82.png)

6. Enter the first input parameter name as **specialty**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image83.png)

7. Select **+Add an input,** then add **patient_id**.

    ![](./media/image84.png)

8. Click the **+ sign** below the previous node. Search for **List rows** in the search bar. Select **List rows** from Dataverse.

    ![](./media/image85.png)
   Note: If you face the following error while sign-in then open the pop-ups blocked. Select Allows allow pop-up and Select Done.
   ![](./media/aa1.png)

9. Enter Connection name as: **<inject key="AzureAdUserEmail"></inject>**. Click **Sign in** to connect to Dataverse.

    ![](./media/image86.png)

10. Select the **Table name** field and choose the **Appointment Slot**
    table.

    ![](./media/image87.png)

11. In the filter field, **enter **nhs_specialty eq '** -\> click daynamic symbol -\> select insert specialty dynamic value -\> enter **' and nhs_doctorstatus eq 1****.

    >**Note:** The Dataverse schema prefix (for example, **cr14f**,
    **cr41f**, **crbab**,**nhs** etc.) is automatically generated when the table is created and **may be different in your environment**. Always verify the actual schema name of your columns before using them in Power Automate expressions.

    ![](./media/aa2.png)

12. Enter the Row count as 4.

    ![](./media/image89.png)

13. Click the **+ sign** below the previous node. Search **search**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image90.png)

14. In From section, select thunderbolt icon -\> select body/value.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image91.png)

15. Switch to text mode.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image92.png)

16. Select the **fx** and enter the following expression and then click **Add**.

    ```
    concat(
    '📅 Appointment',
    decodeUriComponent('%0A'),
    'Date: ',
    formatDateTime(item()?['nhs_appointmentdatetime'], 'dd MMM yyyy'),
    decodeUriComponent('%0A'),
    'Time: ',
    formatDateTime(item()?['nhs_appointmentdatetime'], 'hh:mm tt'),
    decodeUriComponent('%0A'),
    '👨‍⚕️ Doctor: ',
    item()?['nhs_clinicianname'],
    decodeUriComponent('%0A'),
    '📍 Location: ',
    item()?['nhs_location'],
    decodeUriComponent('%0A'),
    '🆔 Slot ID: ',
    item()?['nhs_slotid'],
    decodeUriComponent('%0A'),
    '────────────────────────'
    )
    ```

    >**Note:** The Dataverse schema prefix (for example, **cr14f**,
    **cr41f**, **crbab**, **nhs** etc.) is automatically generated when the table is created and **may be different in your environment**. Always verify the actual schema name of your columns before using them in Power Automate expressions

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image93.png)

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image94.png)

17. Click the **+ sign** below the previous node. Search for **compose**+.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image95.png)

18. Select the **fx** and enter the following expression, then select **Add**.

    ```
    concat(
        decodeUriComponent('%0A'),
        join(outputs('Select')?['body'], decodeUriComponent('%0A%0A'))
    )
    ```

    ![](./media/image96.png)

19. Click the **+ sign** below the previous node. Select **Respond to
    the agent** under AI capabilities.

    ![](./media/image97.png)

20. Select **+Add an Output**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image98.png)

21. Select **Text**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image99.png)

22. Enter **AppointmentSlots**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image100.png)

23. Select **Dynamic content** -\> select **Outputs** under **Compose**.

    ![](./media/image101.png)

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image102.png)

24. Click the **save** button to save the changes.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image103.png)
25. After successfully saving the flow, select the **back** button from the top left of the navigation bar.
26. Select **Solutions** from the left navigation. Then select **HealthcareSolution**.
    ![](./media/aa3.png)
27. You will be navigated to Power Apps. Expand the menu.
    ![](./media/aa4.png)
28. Select Objects -> Cloud flows.
    ![](./media/aa5.png)
29. Select Add existing -> Automation -> Cloud flow
    ![](./media/aa6.png)
30. Select HC-SlotLoopup flow. Then click Add to add this flow to the Healthcare solution.
    ![](./media/aa7.png)
31. Select Publish all customizations.
    ![](./media/aa8.png)


### Task 2 - Connect the HC-SlotLookup Flow to the Agent

Integrate the HC-SlotLookup flow with the booking conversation so
patients can view available appointment slots directly within the chat.

1. Navigate back to Copilot Studio.

2. Select Agents-\> select Northstar Patient Assistant.

    ![](./media/image104.png)

3. Select Topics -\> open **Book Appointment** topic.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image105.png)

4. After the” I can help you schedule your appointment, but I can't provide medical advice.” **Message** node, click + sign. Select **Add a tool -\>HC-SlotLookup.**

    ![](./media/image106.png)

5. In the Action tool, in the specialty field, click the three dots(…).
Select **specialty** variable.

    ![](./media/image107.png)

6. Similarly, in the patient_id field, click the three dots(…). Select the **PatientID** variable.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image108.png)

7. Under the Action node, click the (+) sign. Select **Send a message**.

8. In the send a message node, Enter the following message:

    ```
    I found the following available appointments:
    ```

    Then select variable(X)-\>select AppointmentSlots variable.

    It will display all the available slots.

    ![](./media/image109.png)

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image110.png)

9. Click the **+ sign** below the previous node. Select **Ask a question**.

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image111.png)

10. Enter the following details:

    - Question: 
    
       ```
       Which appointment would you like to book? Please enter the Slot ID.
       ```

    - Identify: Select **User’s entire response**

    - Save user response as **selectedSlot**

       ![](./media/image112.png)

11. Select **Save** to save the updates.

### Task 3 — Build HC-BookAppointment Flow

Create a Power Automate flow that reserves the selected appointment
slot, updates Dataverse, and returns a booking confirmation.

1. Open a new browser tab and enter the following URL to navigate to the PowerAutomate.
    
    ```
    https://make.powerautomate.com
    ```

2. Select **Create** from the left navigation menu, then choose **Instant cloud flow**.

    ![](./media/image113.png)

3. Enter the flow name as **HC-BookAppointment**. Select the **When an agent calls the flow** trigger and click **Create**.

    ![](./media/image114.png)

4. Select the **When an agent calls the flow** trigger, then click **+
    Add an input**.

5. Select **Text**.

6. Enter the first input parameter name as:****slot_id****

7. Click **+ Add an input** and create the following input parameters
    one by one:

    | **Name**                  | **Type** |
    |-----------------------|------|
    | **patient_id**         | Text |
    | **patient_name**       | Text |
    | **date_of_birth**       | Date |
    | **specialty**           | Text |
    | **appointment_type**    | Text |
    | **reason_for_visit**    | Text |

    ![](./media/image115.png)

8. Click the **+** sign below the trigger. Search for **List a row** and select **List rows** from **Microsoft Dataverse**.

    ![](./media/image116.png)

9. If prompted, create a Dataverse connection.

10. Select the **Appointment Slot** table.

    ![](./media/image117.png)

11. In the **Filter rows** field, enter the following expression: **nhs_slotid eq '** -\>Select **Dynamic content** and insert the **slot_id** parameter -\> **’**

    >**Note:** The Dataverse schema prefix (for example, **cr14f**,
    **cr41f**, **crbab**, **nhs** etc.) is automatically generated when the table is created and **may be different in your environment**. Always verify the actual schema name of your columns before using them in Power Automate expressions

    ![](./media/aa9.png)

    ![](./media/aa10.png)

12. Enter **1** in the **Row count** field.

    ![](./media/image120.png)

13. Click the **+** sign below **List rows**. Search for **Apply to each** and select it.

    ![](./media/image121.png)

14. In the **Select an output from previous steps** field, choose **value** from the **List rows** action.

    ![](./media/image122.png)

    ![](./media/image123.png)

15. Inside the **Apply to each** action, click **+ sign**. Search for **Update a row** and select **Update a row** from Microsoft Dataverse.

    ![](./media/image124.png)

16. Select the **Appointment Slot** table.

    ![](./media/image125.png)

17. For the **Row ID**, select **Appointment Slot** as the unique identifier from the current item returned by **List rows**.

    ![](./media/image126.png)

18. Select Show all and update the following columns.

    | Dataverse Column   | Value to Select      | Where to Select It From                          |
    |--------------------|----------------------|--------------------------------------------------|
    | Doctor Status      | `Booked`             | Type/select the choice value manually            |
    | Patient ID         | `patient_id`         | When an agent calls the flow → `patient_id`      |
    | Patient Name       | `patient_name`       | When an agent calls the flow → `patient_name`    |
    | Date Of Birth      | `date_of_birth`      | When an agent calls the flow → `date_of_birth`   |
    | Specialty  | `specialty`          | When an agent calls the flow → `specialty`       |
    | Reason For Visit   | `reason_for_visit`   | When an agent calls the flow → `reason_for_visit`|
    | Status(Status of Appointment)             | `Confirmed`          | Select the choice value manually                 |

    ![](./media/image127.png)

    ![](./media/image128.png)

    ![](./media/image129.png)

    ![](./media/image130.png)

19. Click the **+** sign below the **Apply to each** action. Search for **Compose** and select **Compose**.

    ![](./media/image131.png)

20. Enter manually:

    **✅ Your appointment has been confirmed.**

    **Appointment Reference:**

    Insert the **slot_id** dynamic content from **When an agent calls the
    flow**.

    Continue typing: **Patient Name:**

    Insert **patient_name** dynamic content.

    Continue typing: **Specialty:**

    Insert **specialty** dynamic content.

    Finally type: **Status: Booked**

    ![](./media/image132.png)

21. Click the **+** sign below the **Compose** action. Select **Respond
    to the agent**.

    ![](./media/image133.png)

22. Select **Respond to the agent**, it will open an pop-up windows. Now click **+ Add an output**. Select **Text**.

23. Enter the output name as: **BookingConfirmation**

24. Select **Dynamic content**. Select **Outputs** from the **Compose**
    action.

    ![](./media/image134.png)

    ![](./media/image135.png)

25. Click **Save** to save the flow.

    ![](./media/image136.png)
26. After successfully saving the flow, select the back button from the top left of the navigation bar.
    ![](./media/aa11.png)
27. Select Solutions from the left navigation. Then select HealthcareSolution.
    ![](./media/aa12.png)
28. You will be navigated to Power Apps. Expand the menu.
    ![](./media/aa13.png)
29. Select Objects -> Cloud flows
    ![](./media/aa14.png)
30. Select Add existing -> Automation -> Cloud flow
    ![](./media/aa15.png)
31. Select HC-BookAppointment flow. Then click Add to add this flow to the Healthcare solution.
    ![](./media/aa16.png)
32. Select Publish all customizations.
    ![](./media/aa17.png)


### Task 4 — Connect the HC-BookAppointment Flow to the Agent

Integrate the booking flow with the conversation so appointment requests
are automatically processed and confirmed.

1. Navigate back to Copilot Studio.

2. Select Agents from the left-navigation panel and then open the **Northstar Patient Assistant** agent.

    ![](./media/image137.png)

3. Select **Topics** -\> Open the **Book Appointment** topic.

    ![](./media/image138.png)

4. In the Book Appointment topic, Locate the question: **“Which appointment would you like to book? Please enter the Slot ID.”**

5. Click the + **sign** immediately below this question. Select **Add a tool** -\> Select **HC-BookAppointment**.

    ![](./media/image139.png)

6. Map the following variables.

    | Flow Input          | Agent Variable    |
    |---------------------|-------------------|
    | `slot_id`           | `selectedSlot`    |
    | `patient_id`        | `PatientID`       |
    | `patient_name`      | `PatientName`     |
    | `date_of_birth`     | `DateOfBirth`     |
    | `specialty`         | `specialty`       |
    | `appointment_type`  | `AppointmentType` |
    | `reason_for_visit`  | `ReasonForVisit`  |

    Verify that all input parameters have been mapped correctly.

    ![](./media/image140.png)

    ![](./media/image141.png)

7. Replace the previous placeholder message. Select {X} to add new variable -\> Select **BookingConfirmation** output returned by the flow.

    ![](./media/image142.png)

    ![](./media/image143.png)

8. The message node should display the booking confirmation returned by Power Automate.

9. Click the + **sign** below the booking confirmation message node. Select Topic management-\>End current topic.

    ![](./media/image144.png)

10. Select **Save**.

    ![](./media/image145.png)

11. Select **Publish**, then select **Publish** again to publish the latest changes.

### Task 5 - Test the End-to-End Appointment Booking Experience

Validate the complete appointment booking process and verify that
booking details are correctly stored in Dataverse.

1. Select Test to test the agent.

2. Enter the following prompt:

    ```
    I want to book an appointment.
    ```

    ![](./media/image146.png)

3. Enter the follow up questions:

    - Enter your Patient ID: **NH2201**

    - Please enter your date of birth: **1985-11-02**

    - Please enter your name: **James Ortiz**

    - Which speciality would you like to book an appointment with: **Orthopaedics**

    - Is this your first visit or a follow-up appointment: **First Visit**

    - Please briefly describe the reason for your appointment: **I m feeling a little pain in my right Knee**

    - Which appointment would you like to book? Please enter the Slot ID: **APT1024**.

    ![](./media/image147.png)

    ![](./media/image148.png)

    ![](./media/image149.png)

    ![](./media/image150.png)

4. Navigate to **<https://make.powerapps.com/>** to verify the booking.

5. Select Tables-\> AppointmentSlot.

    ![](./media/image151.png)

6. Select **+ 19 additional rows** to view all the rows.

    ![](./media/image152.png)

7. Locate Slot Id: APT1024 and you can see that the appointment is booked.

    ![](./media/image153.png)

## Lab Summary

In this lab, you built an AI-powered healthcare appointment assistant
using Microsoft Copilot Studio, Microsoft Dataverse, and Power Automate.
You created a secure conversational experience that verifies patient
identity, answers hospital-related questions using organizational
knowledge, handles emergency scenarios responsibly, and enables patients
to book or cancel appointments.

You also automated the appointment management process by integrating
Power Automate flows with Copilot Studio, allowing the agent to retrieve
available appointment slots, update appointment records in Dataverse,
and return booking confirmations in real time. Finally, you validated
the complete end-to-end solution by testing patient interactions and
confirming successful appointment bookings.

## You have successfully completed the lab!
