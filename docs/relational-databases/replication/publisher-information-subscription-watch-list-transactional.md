---
title: "Publisher Information, Subscription Watch List (Transactional)"
description: "Publisher Information, Subscription Watch List (Transactional)"
author: "MashaMSFT"
ms.author: "mathoma"
ms.date: "03/07/2017"
ms.service: sql
ms.subservice: replication
ms.topic: conceptual
f1_keywords:
  - "sql13.rep.monitor.publisherinfo.subscriptionssummary.tran.f1"
monikerRange: "=azuresqldb-mi-current||>=sql-server-2016"
---
# Publisher Information, Subscription Watch List (Transactional)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]
  The **Subscription Watch List** tab is available for Distributors running SQL Server 2005 and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher. You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions. This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box. Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.  
  
## Options  
 For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu. To change the way that the grid displays data, right-click the grid, and then click one of the following options:  
  
-   **Sort**: Sort on one or more columns in the **Sort Columns** dialog box.  
  
-   **Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.  
  
-   **Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.  
  
-   **Clear Filter**: Clear any filter settings for the grid.  
  
 Filter settings are specific to each grid. Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.  
  
 **Show Transactional Subscriptions**  
 Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.  
  
 **Show**  
 Select the subscription states to display for the selected subscription type. For example, you can select to display only those subscriptions that have an error.  
  
 **Status**  
 The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).  
  
 By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status). The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).  
  
-   Error  
  
-   Performance critical  
  
-   Expiring soon/Expired  
  
-   Uninitialized subscription  
  
-   Retrying failed command  
  
-   Not Running  
  
-   Running  
  
 The sort order also determines which value is displayed if a given subscription is in more than one state. For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.  
  
 The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings. When a warning is displayed, the **Status** column also displays if an agent is running. For example, the status could be **Running, Performance critical**.  
  
 The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set. For information about performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](../../relational-databases/replication/monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](../../relational-databases/replication/monitor/set-thresholds-and-warnings-in-replication-monitor.md).  
  
 **Subscription**  
 The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.  
  
 **Publication**  
 The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.  
  
 **Performance**  
 The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance. Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**. The performance rating is one of the following values:  
  
-   Excellent  
  
-   Good  
  
-   Fair  
  
-   Poor  
  
-   Critical  
  
 If performance is critical, **Performance Critical** is displayed in the **Status** column. For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](../../relational-databases/replication/monitor/monitor-performance-with-replication-monitor.md).  
  
 **Latency**  
 The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber. The latency displayed is based on the most recent measurements taken by Replication Monitor. For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](../../relational-databases/replication/monitor/measure-latency-and-validate-connections-for-transactional-replication.md).  
  
 **Last Synchronization**  
 The time when the Distribution Agent last ran. If synchronization is in progress, **In progress** is displayed.  
  
## See Also  
 [Start the Replication Monitor](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [View Information and Perform Tasks for a Publisher &#40;Replication Monitor&#41;](../../relational-databases/replication/monitor/view-information-and-perform-tasks-replication-monitor.md)   
 [Monitoring Replication](../../relational-databases/replication/monitor/monitoring-replication.md)  
  
  
