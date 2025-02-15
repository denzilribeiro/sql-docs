---
title: Stop a Trace
titleSuffix: SQL Server Profiler
description: Discover how to stop a trace that is running in SQL Server Profiler, change any properties you want to adjust, and save the captured data.
author: markingmyname
ms.author: maghan
ms.date: 03/01/2017
ms.service: sql
ms.subservice: profiler
ms.topic: conceptual
ms.custom: seo-lt-2019
---

# Stop a Trace (SQL Server Profiler)

 [!INCLUDE [SQL Server Azure SQL Managed Instance](../../includes/applies-to-version/sql-asdbmi.md)]

This topic describes how to stop a trace that is running by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].  
  
 Stopping a trace stops data from being captured. After a trace is stopped, it cannot be restarted without losing previously captured data, unless the data has been captured to a trace file or trace table. You can also save the collected data to a table or file after stopping a trace. All trace properties that were previously selected are preserved when a trace is stopped. When a trace is stopped, you can change the name, events, columns, and filters.  
  
### To stop a trace  
  
1.  Select a trace that is running.  
  
2.  On the **File** menu, click **Stop Trace**.  
  
## See Also  
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
