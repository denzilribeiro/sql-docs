---
title: "OnlineIndexOperation Element (DTA)"
description: In the dta utility, the OnlineIndexOperation element specifies whether items that Database Engine Tuning Advisor recommends can be created online.
author: markingmyname
ms.author: maghan
ms.date: 03/01/2017
ms.service: sql
ms.subservice: tools-other
ms.topic: conceptual
ms.custom: seo-lt-2019
helpviewer_keywords:
  - "OnlineIndexOperation element"
dev_langs:
  - "XML"
---

# OnlineIndexOperation Element (DTA)

 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Specifies whether the indexes, indexed views, or partitions that Database Engine Tuning Advisor recommends can be created online.  
  
## Syntax  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <OnlineIndexOperation>...</OnlineIndexOperation>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|**Data type and length**|**string**, no maximum length.|  
|**Allowed values**|**OFF**<br /> No recommended physical design structures can be created online.<br /><br /> **ON**<br /> All recommended physical design structures can be created online.<br /><br /> **MIXED**<br /> Database Engine Tuning Advisor attempts to recommend physical design structures that can be created online when possible.<br /><br /> Use one of these values with this element. If indexes are created online, the keyword **ONLINE = ON** is appended to its object definition.|  
|**Default value**|None.|  
|**Occurrence**|Optional. If used, can only be used once for the **TuningOptions** element.|  
  
## Element Relationships  
  
|Relationship|Elements|  
|------------------|--------------|  
|**Parent element**|[TuningOptions Element &#40;DTA&#41;](../../tools/dta/tuningoptions-element-dta.md)|  
|**Child elements**|None.|  
  
## Example  
 For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](../../tools/dta/simple-xml-input-file-sample-dta.md).  
  
## See Also  
 [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
