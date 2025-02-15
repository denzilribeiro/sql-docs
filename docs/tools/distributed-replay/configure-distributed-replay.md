---
title: Configure distributed replay
titleSuffix: SQL Server Distributed Replay
description: This article describes product requirements to consider before you use the Distributed Replay feature of SQL Server.
author: markingmyname
ms.author: maghan
ms.reviewer: mikeray
ms.date: 06/20/2022
ms.service: sql
ms.subservice: distributed-replay
ms.topic: conceptual
ms.custom: seo-lt-2019
monikerRange: ">= sql-server-2016 || >= sql-server-linux-2017"
---

# Configure Distributed Replay

[!INCLUDE [sqlserver2016-2019-only](../../includes/applies-to-version/sqlserver2016-2019-only.md)]

[!INCLUDE [distributed-replay-sql-server-2022](../../includes/distributed-replay-sql-server-2022.md)]

The Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay configuration details are specified in XML files on the Distributed Replay controller, clients, and where the administration tool is installed. These files include the following:

- [Controller configuration file](#DReplayController)

- [Client configuration file](#DReplayClient)

- [Preprocess configuration file](#PreprocessConfig)

- [Replay configuration file](#ReplayConfig)

## <a name="DReplayController"></a> Controller Configuration File: DReplayController.config

When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service starts, it loads the logging level from the controller configuration file, `DReplayController.config`. This file is located in the folder where you installed the Distributed Replay controller service:

**\<controller installation path>\DReplayController.config**

The logging level specified by the controller configuration file includes the following:

|Setting|XML Element|Description|Allowed Values|Required|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|Logging level|`<LoggingLevel>`|Specifies the logging level for the controller service.|`INFORMATION` &#124; `WARNING` &#124; `CRITICAL`|No. By default, the value is `CRITICAL`.|

### Example

This example shows a controller configuration file that has been modified to suppress `INFORMATION` and `WARNING` log entries.

```xml
<?xml version='1.0'?> 
<Options> 
<LoggingLevel>CRITICAL</LoggingLevel> 
</Options> 
```

## <a name="DReplayClient"></a> Client Configuration File: DReplayClient.config

When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay client service starts, it loads configuration settings from the client configuration file, `DReplayClient.config`. This file is located on each client, in the folder where you installed the Distributed Replay client service:

**\<client installation path>\DReplayClient.config**

The settings specified by the client configuration file include the following:

|Setting|XML Element|Description|Allowed Values|Required|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|Controller|`<Controller>`|Specifies the computer name of the controller. The client will attempt to register with the Distributed Replay environment by contacting the controller.|You can use "`localhost`" or "`.`" to refer to the local computer.|No. By default, the client tries to register with the controller instance that is running locally ("`.`"), if it exists.|  
|Client working directory|`<WorkingDirectory>`|Is the local path on the client where the dispatch files are saved.<br /><br /> The files in this directory are overwritten on the next replay.|A full directory name, starting with the drive letter.|No. If no value is specified, the dispatch files will be saved in the same location as the default client configuration file. If a value is specified and that folder doesn't exist on the client, the client service won't start.|  
|Client result directory|`<ResultDirectory>`|Is the local path on the client where the result trace file from the replay activity (for the client) is saved.<br /><br /> The files in this directory are overwritten on the next replay.|A full directory name, starting with the drive letter.|No. If no value is specified, the result trace file will be saved in the same location as the default client configuration file. If a value is specified and that folder doesn't exist on the client, the client service won't start.|  
|Logging level|`<LoggingLevel>`|Is the logging level for the client service.|`INFORMATION` &#124; `WARNING` &#124; `CRITICAL`|No. By default, the value is `CRITICAL`.|

### Example

This example shows a client configuration file that has been modified to specify that the controller service is running on a different computer, a computer named `Controller1`. The `WorkingDirectory` and `ResultDirectory` elements have been configured to use folders `c:\ClientWorkingDir` and `c:\ResultTraceDir`, respectively. The logging level has been changed from the default value to suppress `INFORMATION` and `WARNING` log entries.

```xml
<?xml version='1.0'?> 
<Options> 
    <Controller>Controller1</Controller> 
    <WorkingDirectory>c:\ClientWorkingDir</WorkingDirectory> 
    <ResultDirectory>c:\ResultTraceDir</ResultDirectory> 
    <LoggingLevel>CRITICAL</LoggingLevel> 
</Options> 
```

## <a name="PreprocessConfig"></a> Preprocess Configuration File: DReplay.exe.preprocess.config

When you use the administration tool to initiate the preprocess stage, the administration tool loads the preprocess settings from the preprocess configuration file, `DReplay.exe.preprocess.config`.

Use the default configuration file or use the administration tool **-c** parameter to specify the location of a modified preprocess configuration file. For more information about using the preprocess option of the administration tool, see [Preprocess Option &#40;Distributed Replay Administration Tool&#41;](../../tools/distributed-replay/preprocess-option-distributed-replay-administration-tool.md).

The default preprocess configuration file is located in the folder where you installed the administration tool:

**\<administration tool installation path>\DReplayAdmin\DReplay.exe.preprocess.config**

The preprocess configuration settings are specified in XML elements that are children of the `<PreprocessModifiers>` element in the preprocess configuration file. These settings include the following:

|Setting|XML Element|Description|Allowed Values|Required|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|Include system session activities|`<IncSystemSession>`|Indicates whether system session activities during the capture will be included during replay.|`Yes` &#124; `No`|No. By default, the value is `No`.|  
|Maximum idle time|`<MaxIdleTime>`|Caps the idle time to an absolute number (in seconds).|An integer that is >= -1.<br /><br /> `-1` indicates no change from the original value in the original trace file.<br /><br /> `0` indicates that there's some activity going on at any given point in time.|No. By default, the value is `-1`.|

### Example

The default preprocess configuration file:

```xml
<?xml version='1.0'?> 
<Options> 
    <PreprocessModifiers> 
        <IncSystemSession>No</IncSystemSession> 
        <MaxIdleTime>-1</MaxIdleTime> 
    </PreprocessModifiers> 
</Options> 
```

## <a name="ReplayConfig"></a> Replay Configuration File: DReplay.exe.replay.config

When you use the administration tool to initiate the event replay stage, the administration tool loads the replay settings from the replay configuration file, `DReplay.exe.replay.config`.

Use the default configuration file or use the administration tool **-c** parameter to specify the location of a modified replay configuration file. For more information about using the replay option of the administration tool, see [Replay Option &#40;Distributed Replay Administration Tool&#41;](../../tools/distributed-replay/replay-option-distributed-replay-administration-tool.md).

The default replay configuration file is located in the folder where you installed the administration tool:

**\<administration tool installation path>\DReplayAdmin\DReplay.exe.replay.config**

The replay configuration settings are specified in XML elements that are children of the `<ReplayOptions>` and `<OutputOptions>` elements of the replay configuration file.

### \<ReplayOptions> Element

The settings specified by the replay configuration file in the `<ReplayOptions>` element include the following:

|Setting|XML Element|Description|Allowed Values|Required|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|Target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (the test server)|`<Server>`|Specifies the name of the server and instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to connect to.|*server_name*[\\*instance_name*]<br /><br /> You can't use "`localhost`" or "`.`" to represent the local host.|No, if the server name is already specified by using the **-s**_target server_ parameter with the **replay** option of the administration tool.|  
|Sequencing mode|`<SequencingMode>`|Specifies the mode that is used for event scheduling.|`synchronization` &#124; `stress`|No. By default, the value is `stress`.|  
|Stress scale granularity|`<StressScaleGranularity>`|Specifies whether all connections on the Service Profile Identifier (SPID) should be scaled together (SPID) or independently (Connection) under stress mode.|SPID &#124; Connection|Yes. By default, the value is `SPID`.|  
|Connect time scale|`<ConnectTimeScale>`|Is used to scale the connect time in stress mode.|An integer between `1` and `100`.|No. By default, the value is `100`.|  
|Think time scale|`<ThinkTimeScale>`|Is used to scale think time in stress mode.|An integer between `0` and `100`.|No. By default, the value is `100`.|  
|Use connection pooling|`<UseConnectionPooling>`|Specifies whether connection pooling will be enabled on each Distributed Replay client.|Yes &#124; No|Yes. By default, the value is `Yes`.|  
|Health monitor interval|`<HealthmonInterval>`|Indicates how often to run the health monitor (in seconds).<br /><br /> This value is only used in synchronization mode.|Integer >= 1<br /><br /> (`-1` to disable)|No. By default, the value is `60`.|  
|Query time-out|`<QueryTimeout>`|Specifies the query time-out value, in seconds. This value is only effective until the first row has been returned.|Integer >= 1<br /><br /> (`-1` to disable)|No. By default, the value is `3600`.|  
|Threads per client|`<ThreadsPerClient>`|Specifies the number of replay threads to use for each replay client.|An integer between `1` and `512`.|No. If not specified, Distributed Replay will use a value of `255`.|

### \<OutputOptions> Element

The settings specified by the replay configuration file in the `<OutputOptions>` element include the following:

|Setting|XML Element|Description|Allowed Values|Required|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|Record row count|`<RecordRowCount>`|Indicates whether the row count should be recorded for each result set.|`Yes` &#124; `No`|No. By default, the value is `Yes`.|  
|Record result set|`<RecordResultSet>`|Indicates whether the content of all result sets should be recorded.|`Yes` &#124; `No`|No. By default, the value is `No`.|

### Example

The default replay configuration file:

```xml
<?xml version='1.0'?> 
<Options> 
    <ReplayOptions> 
        <Server></Server> 
        <SequencingMode>stress</SequencingMode> 
        <ConnectTimeScale></ConnectTimeScale> 
        <ThinkTimeScale></ThinkTimeScale> 
        <HealthmonInterval>60</HealthmonInterval> 
        <QueryTimeout>3600</QueryTimeout> 
        <ThreadsPerClient></ThreadsPerClient> 
    </ReplayOptions> 
    <OutputOptions> 
        <ResultTrace> 
            <RecordRowCount>Yes</RecordRowCount> 
            <RecordResultSet>No</RecordResultSet> 
        </ResultTrace> 
    </OutputOptions> 
</Options> 
```

### Possible Issue When Running With Synchronization Sequencing Mode

You may encounter a symptom in which the replay functionality appears to "stall", or replays events slowly. This phenomenon can occur if the trace being replayed relies on data and/or events that don't exist in the restored target database.

One example is a captured workload that uses WAITFOR, such as in Service Broker's WAITFOR RECEIVE statement. When using the synchronization sequencing mode, batches are replayed serially. If an INSERT occurs against the source database after the database backup, but before the replay capture trace is started, the WAITFOR RECEIVE issued during replay may have to wait the entire duration of the WAITFOR. Events set to be replayed after the WAITFOR RECEIVE will be stalled. This can result in the Batch Requests/sec performance monitor counter for the replay database target dropping to zero until the WAITFOR completes.

If you need to use synchronization mode and wish to avoid this behavior, you must do the following:

1. Quiesce the databases that you'll be using as the replay targets.

2. Allow all pending activity to complete.

3. Back up the databases and allow backups to complete.

4. Start the distributed replay trace capture and resume the normal workload.

## See also

- [Administration Tool Command-line Options &#40;Distributed Replay Utility&#41;](../../tools/distributed-replay/administration-tool-command-line-options-distributed-replay-utility.md)
- [SQL Server Distributed Replay](../../tools/distributed-replay/sql-server-distributed-replay.md)
- [SQL Server Distributed Replay Forum](https://social.technet.microsoft.com/Forums/sl/sqldru/)
- [Using Distributed Replay to Load Test Your SQL Server - Part 2](/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2)
- [Using Distributed Replay to Load Test Your SQL Server - Part 1](/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)
