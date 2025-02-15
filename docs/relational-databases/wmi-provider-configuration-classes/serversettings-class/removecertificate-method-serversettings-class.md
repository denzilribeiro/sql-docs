---
title: "RemoveCertificate Method (ServerSettings)"
description: "RemoveCertificate Method (ServerSettings Class)"
author: markingmyname
ms.author: maghan
ms.date: "03/14/2017"
ms.service: sql
ms.subservice: wmi
ms.topic: "reference"
ms.custom: seo-lt-2019
helpviewer_keywords:
  - "RemoveCertificate method"
apilocation: "sqlmgmproviderxpsp2up.mof"
apiname: "RemoveCertificate Method (ServerSettings Class)"
apitype: "MOFDef"
---
# RemoveCertificate Method (ServerSettings Class)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## Syntax  
  
```  
  
object.RemoveCertificate()  
```  
  
## Parts  
 *object*  
 A [ServerSettings Class](../../../relational-databases/wmi-provider-configuration-classes/serversettings-class/serversettings-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## Property Value/Return Value  
 A u**int32** value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.  
  
## Remarks  
  
## See Also  
 [Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  
