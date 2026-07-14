# Lab 2 - Enabling Data Connectors in Microsoft Sentinel in Microsoft Defender Portal

## Estimated Duration: 40 Minutes

## Overview

In this lab, you will enable and configure data connectors in Microsoft Sentinel to ingest logs and events from selected sources such as Microsoft Entra ID. You will explore available connectors, set up the integration, and verify that data is flowing into your Log Analytics workspace. This process establishes the data foundation required for analytics, threat hunting, and incident response in subsequent labs.


## Lab Objectives
 In this lab, you will perform the following:

- Task 1: Connect the Microsoft Entra ID connector
- Task 2: Connect the Microsoft Defender for Cloud connector
- Task 3: Connect the Azure Activity connector

### Task 1: Connect the Microsoft Entra ID connector

 In this task, you will connect the Microsoft Entra ID connector to Microsoft Sentinel.

 1. In the new tab of browser window, navigate to the **Microsoft Defender Portal**

      ```
      https://security.microsoft.com/
      ```

 1. On the left side menu, Expand the Show navigation pane select **Microsoft Sentinel (1)** > **Content management (2)** and select **Content hub (3).**

     ![Picture 1](../images/p1t3s1.png)

1. You will notice a message may appear advising that new spaces are being created, as this may take up to 10 minutes.

    >**Note:** After 10 minutes, sign out of the browser and sign in again to complete the process.

    ![Image](../images/l2t1s3.png)
    
    >**Note:** If you don't see this page, you can move to Step 5.
1. In Microsoft Sentinel, navigate to **Content management (1)** and open the **Content hub (2)**.

   ![Image](../images/e2t3s2a.png)

1. Search for **Microsoft Entra ID (1)**, then select **Microsoft Entra ID (2)** Data connector from the dropdown list and click on **Install (3)** to install it.

    ![Picture 1](../images/l2t1s4.png)

    >**Note:** If you cannot perform successfully for several minutes, the instructions will redirect to Settings-Sentinel until then. Signing out of all sessions in the browser and then signing in again may speed things up.

 1. From the left hand pane, click on **Configuration (1)** under **Microsoft Sentinel** select **Data connectors (2)** and expand **Microsoft Entra ID (3)** data connector and click on it, then select the **Open connector page (4)** on the connector information blade.

    ![Picture](../images/l2t1s5.png)

    >**Note:** If Microsoft Entra ID option is not present, refresh the tab once.

 1. Scroll down, check the box for **Sign-in Logs (1)** and **Audit Logs (2)** options under the Configuration, then select **Apply Changes (3)**.

    ![Picture](../images/Ex2-16.png)

    ![Picture](../images/l2-t1-s7.png)

    >**Note:** It may take **15–20 minutes** for the **Microsoft Entra ID** data connector to show a **Connected** status after configuration. 

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="2779dc9d-16e3-4342-a61e-be7f4dd346ae" />

### Task 2: Connect the Microsoft Defender for Cloud connector

In this task, you will connect the Microsoft Defender for Cloud connector.

1. On the left side menu, Expand the Show navigation pane select **Microsoft Sentinel (1)** > **Content management (2)** and select **Content hub (3)**.

    ![Picture 1](../images/p1t3s1.png)

1. On **Content hub** page, search for **Microsoft Defender for Cloud (1)** and **expand it (2)** from the list, then select **Tenant-based Microsoft Defender for Cloud (3)** Data connector and click on **Install Solution (4)** to install it.

    ![Picture 1](../images/image-7.png)

    >**Note:** The Microsoft Defender for Cloud solution installs the Tenant-based Microsoft Defender for Cloud Data connector, Subscription-based Microsoft Defender for Cloud (Legacy) Data connector, and an Analytics rule.

1. On the **Content hub** page, select the **Tenant-based Microsoft Defender for Cloud (1)** Data connector, and select the **Open connector page (2)** on the connector information blade.
   
    ![Picture](../images/image-8.png) 

1. You will now be navigated to the Azure portal, where you can see the information like **Last Log Received**, **Data received**.

    ![Picture](../images/image-9.png) 

### Task 3: Connect the Azure Activity connector

In this task, you will connect the Azure Activity connector.

1. Go back to the Microsoft Defender portal, On the left side menu, select **Microsoft Sentinel (1)** > **Content management (2)** and select **Content hub (3)** under the Configuration.

    ![Picture 1](../images/p1t3s1.png)

1. On **Content hub** page, search for **Azure Activity (1)** and select **Azure Activity (2)** Data connector from the list,  and click on **Install (3)** to install it.

    ![Picture](../images/l2t3s2.png)

    >**Note:** If you cannot perform successfully for several minutes, the instructions will redirect to Settings-Sentinel until then. Signing out of all sessions in the browser and then signing in again may speed things up. 

1. Now, On the left side menu, navigate to **Data connectors (1)** page under **Configuration**, select the **Azure Activity (2)** Data connector, and select the **Open connector page (3)** on the connector information blade.

    ![Picture](../images/Ex2-05a.png)

    >**Note:** If Azure Activity option is not present, refresh the tab once.

1. In the Configuration area, scroll down and under "2. Connect your subscriptions..." select **Launch Azure Policy Assignment wizard>**.

    ![Picture](../images/Ex2-07.png)

1. In the **Basics** tab, select the ellipsis button **(...) (1)** next to **Scope** and select your **subscription (2)** from the drop-down list and click **Select (3)**.

    ![Picture](../images/Ex2-08.png)

1. In the **Parameters** tab, click the ellipsis button **(...) (1)** next to **Primary Log Analytics workspace** and select your **workspace (2)** from the drop-down list and click **Select (3)**.

    ![Picture](../images/Ex2-09.png)

1. Select the **Remediation** tab and select the **Create a remediation task** checkbox. This action will apply the policy to existing Azure resources.

    ![Picture](../images/image-11.png)

1. Select the **Managed Identity** tab and select the **Create a Managed Identity (1)** checkbox.

1. Select the **Review + create (2)** button to review the configuration.

    ![Picture](../images/image-12.png)

1. On **Review + create**, select **Create** to finish. 

    ![Picture](../images/image-13.png)

    ![Picture](../images/l2-t3-s10.png)

    > **Note:** It may take **15–20 minutes** for the **Azure Activity** data connector to show a **Connected** status after configuration.

    > **Note:** If the status does not show as connected after 15–20 minutes, close the tab, reopen it, and then check again.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="839e0f6e-c380-4672-9ea5-bbc0fdaae262" />

### Summary
In this lab, you have integrated log data from various data sources within the organization into Microsoft Sentinel using appropriate data connectors.

## You have successfully completed the lab!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](../images/Next.png)

