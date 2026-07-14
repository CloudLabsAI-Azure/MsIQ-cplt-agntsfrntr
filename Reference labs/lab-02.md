# Lab 2 - Enabling Data Connectors & Threat Hunting Across Unified Microsoft Security Telemetry in the Defender Portal

## Estimated Duration: 90 Minutes

## Overview

In this lab, you will enable and configure data connectors in Microsoft Sentinel to ingest logs and events from selected sources such as Microsoft Entra ID, Microsoft Defender for Cloud, Azure Activity, Microsoft 365, and Amazon Web Services (AWS). You will explore available connectors, set up the integration, and verify that data is flowing into your Log Analytics workspace.

Once data connectors are active, you will move on to threat hunting using **Advanced Hunting** in the Microsoft Defender portal. Using KQL queries, you will search for suspicious activity across **Azure** (identity sign-in logs, Azure Activity), **Microsoft 365** (cloud app events), and **AWS** (CloudTrail logs) telemetry - building the skills needed to proactively detect threats before they escalate into incidents.

## Lab Objectives

 In this lab, you will perform the following:

- Task 1: Connect the Microsoft Entra ID connector
- Task 2: Connect the Microsoft Defender for Cloud connector
- Task 3: Connect the Azure Activity connector
- Task 4: Connect the Microsoft 365 connector
- Task 5: Connect the Amazon Web Services (AWS) connector
- Task 6: Hunt across unified Microsoft security telemetry using Advanced Hunting in the Defender portal

### Task 1: Connect the Microsoft Entra ID connector

 In this task, you will connect the Microsoft Entra ID connector to Microsoft Sentinel.

 1. In the new tab of browser window, navigate to the **Microsoft Defender Portal**

      ```
      https://security.microsoft.com/
      ```

 1. On the left side menu, Expand the Show navigation pane select **Microsoft Sentinel (1)** > **Content management (2)** and select **Content hub (3).**

     ![](../images/p1t3s1.png)

1. You will notice a message may appear advising that new spaces are being created, as this may take up to 10 minutes.

    >**Note:** After 10 minutes, sign out of the browser and sign in again to complete the process.
    
    >**Note:** If you don't see this page, you can move to Step 5.

1. In Microsoft Sentinel, navigate to **Content management (1)** and open the **Content hub (2)**.

   ![](../images/e2t3s2a.png)

1. Search for **Microsoft Entra ID (1)**, then select **Microsoft Entra ID (2)** Data connector from the dropdown list and click on **Install (3)** to install it.

    ![](../images/l2t1s4.png)

    >**Note:** If you cannot perform successfully for several minutes, the instructions will redirect to Settings-Sentinel until then. Signing out of all sessions in the browser and then signing in again may speed things up.

 1. From the left hand pane, click on **Configuration (1)** under **Microsoft Sentinel** select **Data connectors (2)** and expand **Microsoft Entra ID (3)** data connector and click on it, then select the **Open connector page (4)** on the connector information blade.

    ![](../images/l2t1s5.png)

    >**Note:** If Microsoft Entra ID option is not present, refresh the tab once.

 1. Scroll down, check the box for **Sign-in Logs (1)** and **Audit Logs (2)** options under the Configuration, then select **Apply Changes (3)**.

    ![](../images/Ex2-16.png)

    ![](../images/l2-t1-s7.png)

    >**Note:** It may take **15-20 minutes** for the **Microsoft Entra ID** data connector to show a **Connected** status after configuration. 

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="2779dc9d-16e3-4342-a61e-be7f4dd346ae" />

### Task 2: Connect the Microsoft Defender for Cloud connector

In this task, you will connect the Microsoft Defender for Cloud connector.

1. On the left side menu, Expand the Show navigation pane select **Microsoft Sentinel (1)** > **Content management (2)** and select **Content hub (3)**.

    ![](../images/p1t3s1.png)

1. On **Content hub** page, search for **Microsoft Defender for Cloud (1)** and **expand it (2)** from the list, then select **Tenant-based Microsoft Defender for Cloud (3)** Data connector and click on **Install Solution (4)** to install it.

    ![](../images/image-7.png)

    >**Note:** The Microsoft Defender for Cloud solution installs the Tenant-based Microsoft Defender for Cloud Data connector, Subscription-based Microsoft Defender for Cloud (Legacy) Data connector, and an Analytics rule.

1. Once installed, on the **Content hub** page, select the **Tenant-based Microsoft Defender for Cloud (1)** Data connector, and click **Manage (2)** on the connector information blade to open the connector configuration page.

    ![](../images/image-8.png)

    >**Note:** Clicking **Manage** takes you directly to the connector's configuration page in the Azure portal, where you can review the connection status and configure data ingestion settings.

1. You will now be navigated to the Azure portal connector page. Review the **Status**, **Last Log Received**, and **Data received** fields to confirm the connector is active.

    ![](../images/image-9.png)

1. Under the **Configuration** section on the connector page, ensure that the toggle for **Connect** is set to **On** for your subscription, then click **Connect** if it is not already connected. This enables the ingestion of Microsoft Defender for Cloud security alerts into your Sentinel workspace.

    >**Note:** It may take **15-20 minutes** for the connector status to update to **Connected** after you enable it.

### Task 3: Connect the Azure Activity connector

In this task, you will connect the Azure Activity connector.

1. Go back to the Microsoft Defender portal, On the left side menu, select **Microsoft Sentinel (1)** > **Content management (2)** and select **Content hub (3)** under the Configuration.

    ![](../images/p1t3s1.png)

1. On **Content hub** page, search for **Azure Activity (1)** and select **Azure Activity (2)** Data connector from the list,  and click on **Install (3)** to install it.

    ![](../images/l2t3s2.png)

    >**Note:** If you cannot perform successfully for several minutes, the instructions will redirect to Settings-Sentinel until then. Signing out of all sessions in the browser and then signing in again may speed things up. 

1. Once installed, select **Azure Activity** from the Content hub list and click **Manage (1)** on the connector information blade. This opens the Azure Activity connector configuration page directly in the Azure portal.

    >**Note:** The **Manage** button provides quick access to the connector page where you can configure policy assignments and verify the connection status.

1. Now, On the left side menu, navigate to **Data connectors (1)** page under **Configuration**, select the **Azure Activity (2)** Data connector, and select the **Open connector page (3)** on the connector information blade.

    ![](../images/Ex2-05a.png)

    >**Note:** If Azure Activity option is not present, refresh the tab once.

1. In the Configuration area, scroll down and under "2. Connect your subscriptions..." select **Launch Azure Policy Assignment wizard>**.

    ![](../images/Ex2-07.png)

1. In the **Basics** tab, select the ellipsis button **(...) (1)** next to **Scope** and select your **subscription (2)** from the drop-down list and click **Select (3)**.

    ![](../images/Ex2-08.png)

1. In the **Parameters** tab, click the ellipsis button **(...) (1)** next to **Primary Log Analytics workspace** and select your **workspace (2)** from the drop-down list and click **Select (3)**.

    ![](../images/Ex2-09.png)

1. Select the **Remediation** tab and select the **Create a remediation task** checkbox. This action will apply the policy to existing Azure resources.

    ![](../images/image-11.png)

1. Select the **Managed Identity** tab and select the **Create a Managed Identity (1)** checkbox.

1. Select the **Review + create (2)** button to review the configuration.

    ![](../images/image-12.png)

1. On **Review + create**, select **Create** to finish. 

    ![](../images/image-13.png)

    ![](../images/l2-t3-s10.png)

    > **Note:** It may take **15-20 minutes** for the **Azure Activity** data connector to show a **Connected** status after configuration.

    > **Note:** If the status does not show as connected after 15-20 minutes, close the tab, reopen it, and then check again.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="839e0f6e-c380-4672-9ea5-bbc0fdaae262" />

### Task 4: Connect the Microsoft 365 connector

In this task, you will install and configure the **Microsoft 365** data connector in Microsoft Sentinel. This connector ingests Office 365 audit logs—covering Exchange Online, SharePoint Online, and Microsoft Teams—into your Log Analytics workspace, enabling you to hunt for and detect threats across your Microsoft 365 environment.

1. On the left side menu in the Microsoft Defender portal, select **Microsoft Sentinel (1)** > **Content management (2)** and select **Content hub (3)**.

    ![](../images/p1t3s1.png)

1. On the **Content hub** page, search for **Microsoft 365 (1)**, then select **Microsoft 365 (2)** from the list and click **Install (3)** to install the solution.

    ![](../images/l2t4s2.png)

    >**Note:** The Microsoft 365 solution deploys the Office 365 data connector along with associated analytics rules and workbooks that are pre-built for M365 threat detection.

1. Once installation completes, select **Microsoft 365** from the Content hub list and click **Manage (1)** on the connector information blade.

    ![](../images/l2t4s3-manage.png)

    >**Note:** Clicking **Manage** opens the connector configuration page where you can select which Microsoft 365 services to ingest logs from.

1. On the Microsoft 365 solution page, select **Microsoft 365 (formerly, Office 365) (1)** and click **Open connector page (2)** to open the Microsoft 365 data connector configuration page.

    ![](../images/l2t4s4-open-page.png)

1. On the **Microsoft 365** connector page, review the **Prerequisites** section to confirm that the required permissions are in place. Scroll down to the **Configuration** section.

1. Under **Configuration (1)**, check the boxes for the following log sources to enable ingestion:
   - **Exchange** - captures email flow and mailbox audit events
   - **SharePoint** - captures file access and sharing events
   - **Teams** - captures meeting and messaging activity

    Then click **Apply Changes (2)**.

    ![](../images/l2t4s5-config.png)

    >**Note:** It may take **15-20 minutes** for the **Microsoft 365** data connector to show a **Connected** status and for logs to begin flowing into the `OfficeActivity` table in your workspace.

### Task 5: Connect the Amazon Web Services (AWS) Connector

In this task, you will install and configure the **Amazon Web Services** data connector in Microsoft Sentinel. This connector uses an AWS SQS queue to pull logs—such as CloudTrail, GuardDuty, and VPC Flow Logs—from an S3 bucket into your Log Analytics workspace, enabling cross-cloud threat detection.

> **Note:** Completing the full AWS connector configuration requires access to an active AWS account with the appropriate IAM roles and S3/SQS resources configured. In this lab, you will walk through the installation and configuration steps to understand the process; however, since no AWS account is connected, queries against AWS tables will return no results. This is expected behavior.

1. On the left side menu in the Microsoft Defender portal, select **Microsoft Sentinel (1)** > **Content management (2)** and select **Content hub (3)**.

    ![](../images/p1t3s1.png)

1. On the **Content hub** page, search for **Amazon Web Services**, select **Amazon Web Services (1)** from the list, and click **Install (2)** to install the solution.

    ![](../images/l2t5s2.png)

    >**Note:** The Amazon Web Services solution deploys multiple connectors including the AWS connector (for CloudTrail, GuardDuty, VPC Flow Logs) and the legacy CloudTrail connector.

1. Once installation completes, select **Amazon Web Services** from the Content hub list and click **Manage (1)** on the connector information blade.

    ![](../images/l2t5s3-manage.png)

    >**Note:** The **Manage** button opens the connector detail page, which lists all individual AWS connectors included in the solution and their current connection status.

1. Select **Amazon Web Services (1)**, review the available **data types**, and then click **Open connector page (2)**.

    ![](../images/l2t5s3-manage-2.png)

1. On the **Amazon Web Services** connector page, review the **Prerequisites** and **Configuration** sections.

2. Under **Configuration**, click **Connect AWS to Microsoft Sentinel** to begin configuring the connector. Ensure the following AWS prerequisites are met:

   * An **AWS IAM role** with permissions to read from **Amazon S3** and **Amazon SQS**.

   * An **Amazon S3 bucket** configured to forward logs.

   * An **Amazon SQS queue** configured to receive S3 event notifications.

    ![](../images/l2t5s5-config.png)

    > **Note:** Full setup instructions, including the AWS CloudFormation template, are available through the connector instructions. Since this lab environment does not include a connected AWS account, you will only review the configuration options and will not complete the connector configuration.
    >
    >**Note:** Once a valid AWS account is connected and the SQS/S3 resources are configured, logs will flow into tables such as `AWSCloudTrail`, `AWSGuardDuty`, and `AWSVPCFlow` in your Log Analytics workspace.

### Task 6: Hunt Across Unified Microsoft Security Telemetry Using Advanced Hunting in the Defender Portal

In this task, you will use the **Advanced Hunting** capability in the Microsoft Defender portal to proactively search for threats across unified Microsoft security telemetry - spanning **Azure** (identity and control-plane logs ingested via Sentinel data connectors), **Microsoft 365** (Office 365 audit logs and cloud app events from Microsoft Defender XDR), and **AWS** (CloudTrail logs ingested via the AWS connector). Advanced Hunting provides a unified KQL editor where you can query both Microsoft Defender XDR and Microsoft Sentinel workspace data in a single interface.

> **Note:** Advanced Hunting surfaces data from **three distinct telemetry domains**: (1) **Azure telemetry** - `SigninLogs` and `AzureActivity` tables populated by the Sentinel data connectors you configured in Tasks 1-3, (2) **Microsoft 365 telemetry** - `OfficeActivity` and `CloudAppEvents` tables sourced from the Microsoft 365 connector (Task 4) and Microsoft Defender XDR, and (3) **AWS telemetry** - `AWSCloudTrail` table populated by the Amazon Web Services connector configured in Task 5. Querying across all three gives you a unified multi-cloud view without switching portals.

1. In the Microsoft Defender portal, on the left-side navigation menu, select **Hunting (1)**, then click **Advanced hunting (2)**.

    ![](../images/l2t4s1.png)

    >**Note:** Advanced Hunting in the unified Defender portal lets you run KQL queries across both Microsoft Defender XDR signals and your connected Microsoft Sentinel workspace tables - including Azure, Microsoft 365, and AWS telemetry ingested via Sentinel data connectors.

1. In the query editor, enter the following KQL query to detect anomalous sign-in patterns across your cloud identities. This query correlates `SigninLogs` data ingested via the Microsoft Entra ID connector you set up in Task 1:

    ```kql
    SigninLogs
    | where TimeGenerated > ago(7d)
    | where ResultType != 0
    | summarize FailedAttempts = count(), Locations = make_set(Location), Apps = make_set(AppDisplayName)
        by UserPrincipalName
    | sort by FailedAttempts desc
    ```

    Click **Run query (1)** to execute it against your ingested telemetry.

    ![](../images/l2t4s3.png)

    >**Note:** If the query returns no results, this is expected in a lab environment with limited log history. Focus on understanding the query logic and the columns returned.

1. Review the query results. Note columns such as **UserPrincipalName**, **FailedAttempts**, **Locations**, and **Apps** that help identify suspicious sign-in patterns across your connected cloud identities.

    ![](../images/l2t4s4.png)

1. To explore data from **Azure Activity**, modify the query to look at control-plane operations across your subscription:

    ```kql
    AzureActivity
    | where TimeGenerated > ago(7d)
    | summarize count() by ActivityStatusValue
    ```

    Click **Run query (1)** to execute.

    ![](../images/l2t4s5.png)

    >**Note:** The `AzureActivity` table is populated by the **Azure Activity** data connector configured in Task 3. This covers Azure control-plane telemetry - distinct from the identity telemetry queried in the previous step.

1. Now shift to **Microsoft 365 telemetry** by querying the `OfficeActivity` table, which is sourced from the **Microsoft 365** data connector configured in Task 4. This query surfaces file and sharing activity across SharePoint and OneDrive within your M365 tenant:

    ```kql
    OfficeActivity
    | where TimeGenerated > ago(7d)
    | where RecordType in ("SharePointFileOperation", "OneDrive")
    | summarize EventCount = count(), UniqueFiles = dcount(OfficeObjectId)
        by UserId, Operation, RecordType
    | sort by EventCount desc
    | take 20
    ```

    Click **Run query (1)** to execute.

    >**Note:** This query returns results if Exchange, SharePoint, or Teams activity has occurred in your M365 tenant within the last 7 days and logs have begun flowing via the Microsoft 365 connector. If no results appear, it is normal in a fresh lab environment — the `OfficeActivity` table may still be populating.

1. Finally, shift to **AWS telemetry** by querying the `AWSCloudTrail` table, which is populated by the **Amazon Web Services** connector configured in Task 5. This query surfaces API activity logged in AWS CloudTrail to detect unusual or high-volume operations across your AWS environment:

    ```kql
    AWSCloudTrail
    | where TimeGenerated > ago(7d)
    | summarize EventCount = count(), UniqueRegions = dcount(AWSRegion)
        by UserIdentityArn, EventName, EventSource
    | sort by EventCount desc
    | take 20
    ```

    Click **Run query (1)** to execute.

    >**Note:** **This query is expected to return no results in this lab environment.** Since no AWS account has been connected (the AWS connector in Task 5 was reviewed but not fully configured with a live SQS/S3 source), the `AWSCloudTrail` table contains no ingested data. In a production environment where the AWS connector is fully configured with a valid IAM role and SQS queue, this table would be populated with CloudTrail events and the query would return meaningful results.

1. Now explore **Microsoft 365 cloud app activity** by querying the `CloudAppEvents` table, which is sourced from **Microsoft Defender XDR** (not a Sentinel connector). This query surfaces anomalous or high-volume cloud app activity across your M365 tenant:

    ```kql
    CloudAppEvents
    | where TimeGenerated > ago(7d)
    | where ActionType in ("FileDownloaded", "FileUploaded", "FileSyncDownloadedFull")
    | summarize EventCount = count(), UniqueFiles = dcount(ObjectName)
        by AccountDisplayName, IPAddress, Application
    | where EventCount > 50
    | sort by EventCount desc
    | take 20
    ```

    Click **Run query (1)** to execute.

    >**Note:** This query might return no results since you haven't performed any operations in M365 apps yet. The CloudAppEvents table covers Microsoft 365 apps such as SharePoint, OneDrive, Exchange Online, and Teams - a different telemetry domain from the Azure logs queried earlier. Running both in the same Advanced Hunting session shows the unified telemetry surface of the Defender portal.

1. In **Microsoft Defender**, under **Investigation & response > Hunting**, select **Advanced hunting (1)**. In the **Schema** pane on the left, browse the table categories (e.g., **Alerts & behaviors**, **Apps & identities**, **Email & collaboration**) to explore available data sources, or use the **Search** box to find a specific table.

    To review previously run queries, select the **Query history (2)** tab below the query editor, which lists past queries along with their run time, query time, and completion state.

    ![](../images/l2t4s6.png)

1. Advanced Hunting also supports a broader investigative workflow beyond simply running one-off queries.
    > 
    > **Bookmarking findings:** When a query surfaces something worth flagging, results can be saved as bookmarks. A bookmark preserves not just the raw result rows but also contextual notes and tags added by the analyst, making it easier to return to a finding later or hand it off to another team member. All saved bookmarks are collected in the **Bookmarks** tab, where they can be reviewed at any time.
    > 
    > **Investigating entity relationships:** From a saved bookmark, an analyst can open the investigation graph to visualize how entities involved in that finding - users, devices, IP addresses, and so on - relate to one another. This is particularly useful for tracing lateral movement or correlating activity across multiple data sources.
    > 
    > **Promoting queries to detections:** A hunting query that consistently surfaces high-confidence threats doesn't have to remain a manual, one-off check. It can be converted into a custom analytics rule, which then runs automatically against future ingested data and generates alerts whenever the query's conditions are met. This is the mechanism that bridges ad hoc threat hunting with ongoing, automated detection - turning a pattern an analyst discovered by hand into something Sentinel watches for continuously.
    > 
    > Together, these capabilities mean a single suspicious result doesn't have to be a dead end: it can be bookmarked for follow-up, investigated visually through entity relationships, and ultimately operationalized as a standing detection rule.

## Summary

In this lab, you have completed the following:

- Connected the Microsoft Entra ID data connector to ingest identity sign-in and audit logs
- Connected the Microsoft Defender for Cloud connector for cloud security posture telemetry
- Connected the Azure Activity connector to capture control-plane activity across your subscription
- Installed and configured the **Microsoft 365** data connector to ingest Office 365 audit logs (Exchange, SharePoint, Teams) into the `OfficeActivity` table
- Installed and reviewed the **Amazon Web Services** connector, understanding the AWS-side prerequisites (IAM role, S3 bucket, SQS queue) required for cross-cloud log ingestion
- Performed threat hunting across **Azure** (identity sign-in logs and Azure Activity), **Microsoft 365** (Office 365 activity and cloud app events), and **AWS** (CloudTrail — no results expected without a connected AWS account) telemetry using KQL in the Advanced Hunting editor of the Defender portal, and leveraged bookmarks and detection rules for continuous monitoring

## You have successfully completed the lab!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](../images/Next.png)
