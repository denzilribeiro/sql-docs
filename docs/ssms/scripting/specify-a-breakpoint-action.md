---
title: Specify a Breakpoint Action
titleSuffix: T-SQL debugger
description: Learn now to specify a What Hit action - a custom task for the Transact-SQL debugger to perform when a breakpoint is hit and certain other conditions are satisfied.
author: markingmyname
ms.author: maghan
ms.date: 12/04/2019
ms.service: sql
ms.subservice: ssms
ms.topic: conceptual
ms.custom: seo-lt-2019
helpviewer_keywords:
  - "Transact-SQL debugger, breakpoint action"
  - "Transact-SQL debugger, breakpoint when hit action"
monikerRange: ">=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current"
---

# Specify a Breakpoint Action

 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

A breakpoint **When Hit** action specifies a custom task that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger performs for a breakpoint. If the specified hit count is reached and any specified breakpoint condition is satisfied, the debugger performs the action specified for the breakpoint.

[!INCLUDE[ssms-old-versions](../../includes/ssms-old-versions.md)]
  
##  <a name="BKMK_ActionConsiderations"></a> Action Considerations

The default action for a breakpoint is to break execution when both the hit count and breakpoint condition have been satisfied. The primary use of a **When Hit** action in the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger is to instead print information to the debugger **Output** window by specifying a print message.  
  
A print message is specified in the **Print a Message** option, and is specified as a text string that includes expressions containing information from the [!INCLUDE[tsql](../../includes/tsql-md.md)] being debugged. Expressions include:  
  
-   A [!INCLUDE[tsql](../../includes/tsql-md.md)] expression contained in curly braces ({}). The expressions can include [!INCLUDE[tsql](../../includes/tsql-md.md)] variables, parameters, and built-in functions. Examples include {@MyVariable}, {@NameParameter}, {@@SPID}, or {SERVERPROPERTY('ProcessID')}.  
  
-   One of the following keywords:  
  
    1.  $ADDRESS returns the name of the stored procedure or user-defined function where the breakpoint is set. If the breakpoint is set in the editor window, $ADDRESS returns the name of the script file being edited. $ADDRESS and $FUNCTION return the same information in the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.  
  
    2.  $CALLER returns the name of the unit of [!INCLUDE[tsql](../../includes/tsql-md.md)] code that called a stored procedure or function. If the breakpoint is in the editor window, $CALLER returns \<No caller available>. If the breakpoint is in a stored procedure or user-defined function called from the code in the editor window, $CALLER returns the name of the file being edited. If the breakpoint is in a stored procedure or user-defined function called from another stored procedure or function, $CALLER returns the name of the calling procedure or function.  
  
    3.  $CALLSTACK returns the call stack of functions in the chain that called the current stored procedure or user-defined function. If the breakpoint is in the editor window, $CALLSTACK returns the name of the script file being edited.  
  
    4.  $FUNCTION returns the name of the stored procedure or user-defined function where the breakpoint is set. If the breakpoint is set in the editor window, $FUNCTION returns the name of the script file being edited.  
  
    5.  $PID and $PNAME return the ID and name of the operating system process running the instance of the Database Engine where the [!INCLUDE[tsql](../../includes/tsql-md.md)] is running. $PID returns the same ID as SERVERPROPERTY('ProcessID'), except that $PID is a hexadecimal value while SERVERPROPERTY('ProcessID') is a decimal value.  
  
    6.  $TID and $TNAME return the ID and name of the operating system thread running the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch. The thread is one associated with the process running the instance of the Database Engine. $TID returns the same value as SELECT kpid FROM sys.sysprocesses WHERE spid = @@SPID, except that $TID is a hexadecimal value while kpid is a decimal value.  
  
-   You can also use the backslash character (\\) as an escape character to allow curly braces and backslashes in the message: \\{, \\}, and \\\\.  
  
#### To Specify a When Hit Action  
  
1.  In the editor window, right-click the breakpoint glyph, and then click **When Hit** on the shortcut menu.  
  
     -or-  
  
     In the **Breakpoints** window, right-click the breakpoint glyph, and then click **When hit** on the shortcut menu.  
  
2.  In the **When Breakpoint Is Hit** dialog box, select the behavior you want:  
  
    1.  Select **Print a Message** to print a message in the debugger Output window when the breakpoint is hit.  
  
    2.  The **Run a Macro** option is not available from the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, and is greyed out.  
  
    3.  Select **Continue execution** if you do not want the breakpoint to pause execution. This option is active only if you have selected the **Print a Message** option.  
  
3.  Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.  
  
## See Also  
 [Specify a Breakpoint Condition](./specify-a-breakpoint-condition.md)   
 [Specify a Hit Count](./specify-a-hit-count.md)
