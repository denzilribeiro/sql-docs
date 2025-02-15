---
title: "StopService Method (SqlService)"
description: "StopService Method (SqlService Class)"
author: markingmyname
ms.author: maghan
ms.date: "03/03/2017"
ms.service: sql
ms.subservice: wmi
ms.topic: "reference"
ms.custom: seo-lt-2019
helpviewer_keywords:
  - "StopService method"
apilocation: "sqlmgmproviderxpsp2up.mof"
apiname: "StopService Method (SqlService Class)"
apitype: "MOFDef"
---
# StopService Method (SqlService Class)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  Attempts to place the service in the stopped state.  
  
## Syntax  
  
```  
  
object.StopService()  
```  
  
## Parts  
 *object*  
 A [SqlService Class](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) object that represents the service.  
  
## Property Value/Return Value  
 A **uint32** value, which is 0 if the **ResumeService** request was accepted, 1 if the request is not supported, and any other number to indicate an error.  
  
## Remarks  
  
## See Also  
 [Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
