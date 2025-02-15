---
title: "New Alias (Alias Tab)"
description: Learn how to create an alias, an alternate name for a SQL Server instance that is used when connecting to that instance. View examples of when to use an alias.
author: markingmyname
ms.author: maghan
ms.date: "03/14/2017"
ms.service: sql
ms.subservice: tools-other
ms.topic: conceptual
ms.custom: seo-lt-2019
monikerRange: ">=sql-server-2016"
---
# New Alias (Alias Tab)
[!INCLUDE [SQL Server Windows Only](../../includes/applies-to-version/sql-windows-only.md)]
  An alias is an alternate name that can be used to make a connection. The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user. Use the **Alias** page on the **Alias - New** dialog box to specify the elements of the connection string for an alias. To change the connection string of an existing alias, see [&#60;Alias&#62; Properties &#40;Alias Tab&#41;](../../tools/configuration-manager/alias-properties-alias-tab.md).  
  
 All values in the **Properties** grid do not have to be completed. Valid combinations vary depending on the protocol selected. See the topics listed below for examples of valid combinations.  
  
 **Alias Name**  
 The name (alias) that you want to use to refer to this connection.  
  
 **Pipe Name** / **Port No**  
 Additional elements of the connection string. The name of this box varies with the selected protocol.  
  
 **Protocol**  
 The protocol used for the connection.  
  
 **Server**  
 The name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance being connected to.  
  
## When to Use an Alias  
 By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connects to a local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **Shared Memory** protocol, and to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on another computer using either **TCP/IP** or **Named Pipes**. Create an alias when you are using TCP/IP or named pipes, and you want to provide a customized connection string, or when you want to use a name other than the server name for the connection.  
  
### Examples  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not listening on the default TCP/IP port of 1433 so you want to provide a connection string with a different port number.  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not listening on the default named pipe so you want to provide a connection string with a different pipe name.  
  
-   An application expects to connect to a database on the server named `ACCT`, but that database has been consolidated as an instance named `ACCT` on a server named `CENTRAL`. The application cannot easily be changed. Create an alias named `ACCT`, with a connection string pointing to `CENTRAL\ACCT`.  
  
## Creating a Valid Connection String  
 See the following topics for a description and examples of valid combinations of alias properties:  
  
-   [Creating a Valid Connection String Using Shared Memory Protocol](../../tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
-   [Creating a Valid Connection String Using TCP IP](../../tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
-   [Creating a Valid Connection String Using Named Pipes](/previous-versions/sql/sql-server-2016/ms189307(v=sql.130))  
  
