---
title: "Run SQL queries with the ExecuteXMLReader method"
description: Learn how to run SQL queries using the ExecuteXmlReader method of the SqlXmlCommand object to execute commands.
author: MikeRayMSFT
ms.author: mikeray
ms.date: "03/14/2017"
ms.service: sql
ms.subservice: xml
ms.topic: "reference"
ms.custom: seo-lt-2019
helpviewer_keywords:
  - "queries [SQLXML], SQLXML Managed Classes"
  - "SQLXML Managed Classes, executing SQL queries"
  - "Managed Classes [SQLXML], executing SQL queries"
  - "ExecuteXmlReader method"
  - "SQL queries [SQLXML]"
monikerRange: "=azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current"
---
# Executing SQL Queries by Using the ExecuteXMLReader Method
[!INCLUDE [SQL Server Azure SQL Database](../../../includes/applies-to-version/sql-asdb.md)]
  Instead of using the ExecuteToStream method, you can use the ExecuteXmlReader method of the SqlXmlCommand object to execute commands. This method returns an XmlReader object that can be used for further processing of the result (which in this example is printing the element or attribute names and the values).  
  
> [!NOTE]  
>  In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
using System.Xml;  
   class Test  
   {  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks2012;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         SqlXmlParameter p;  
         XmlReader Reader;  
         XmlTextWriter tw;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "select FirstName, LastName from Person.Person where LastName = ? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         Reader = cmd.ExecuteXmlReader();  
            tw = new XmlTextWriter(Console.Out);  
         Reader.MoveToContent();  
         tw.WriteNode(Reader, false);  
         tw.Flush();  
         tw.Close();  
         Reader.Close();  
  
         return 0;  
      }  
  
      static int Main(string[] args)  
      {  
         testParams();  
         return 0;  
      }  
   }  
```  
  
### To test the application  
  
1.  Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.  
  
2.  Save the C# code (DocSample.cs) that is provided in this topic in a folder.  
  
3.  Compile the code. To compile the code at the command prompt, use:  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     This creates an executable (DocSample.exe).  
  
4.  At the command prompt, execute DocSample.exe.  
  
  
