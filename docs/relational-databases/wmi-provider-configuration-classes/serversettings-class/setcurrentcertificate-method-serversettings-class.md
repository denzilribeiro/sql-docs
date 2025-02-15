---
title: "SetCurrentCertificate Method (ServerSettings)"
description: "SetCurrentCertificate Method (ServerSettings Class)"
author: markingmyname
ms.author: maghan
ms.date: "03/14/2017"
ms.service: sql
ms.subservice: wmi
ms.topic: "reference"
ms.custom: seo-lt-2019
helpviewer_keywords:
  - "SetCurrentCertificate method"
apilocation: "sqlmgmproviderxpsp2up.mof"
apiname: "SetCurrentCertificate Method (ServerSettings Class)"
apitype: "MOFDef"
---
# SetCurrentCertificate Method (ServerSettings Class)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  Sets the current security certificate.  
  
## Syntax  
  
```  
  
object.SetCurrentCertificate(SHA)  
```  
  
## Parts  
 *object*  
 A [ServerSettings Class](../../../relational-databases/wmi-provider-configuration-classes/serversettings-class/serversettings-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
#### Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|*SHA*|A string value that specifies the current security certificate.|  
  
## Property Value/Return Value  
 A **uint32** value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.  
  
## Remarks  
  
## See Also  
 [Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  
