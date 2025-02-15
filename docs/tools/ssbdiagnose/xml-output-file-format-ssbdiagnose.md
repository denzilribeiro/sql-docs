---
title: XML Output File Format
description: In SQL Server, the ssbdiagnose utility can deliver its output as an XML file. Create an application to analyze or report errors or view them in an XML editor.
author: markingmyname
ms.author: maghan
ms.date: 03/01/2017
ms.service: sql
ms.subservice: tools-other
ms.topic: conceptual
ms.custom: seo-lt-2019
helpviewer_keywords:
  - "XML output file format [ssbdiagnose]"
  - "ssbdiagnose"
---

# XML Output File Format (ssbdiagnose)

 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

The **ssbdiagnose** utility delivers its output as an XML file when you run it with the **-XML** switch. The XML output file lists header information and the errors that it found in the [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration or conversation that was analyzed. You can write an application to analyze or report on the errors listed in the file. Or, you can view the XML file in a general XML editor, such as XML Notepad.  
  
 An **ssbdiangose** output file contains a DiagnosticInformation root element with two child types:  
  
-   A Banner element with header information.  
  
-   An Issue element for each issue that is reported by **ssbdiagnose**.  
  
## DiagnosticInformation Root Element  
  
-   [DiagnosticInformation Element &#40;ssbdiagnose&#41;](../../tools/ssbdiagnose/diagnosticinformation-element-ssbdiagnose.md)  
  
## Banner Element  
  
-   [Banner Element &#40;ssbdiagnose&#41;](../../tools/ssbdiagnose/banner-element-ssbdiagnose.md)  
  
## Issue Element  
  
-   [Issue Element &#40;ssbdiagnose&#41;](../../tools/ssbdiagnose/issue-element-ssbdiagnose.md)  
  
## See Also  
 [ssbdiagnose Utility &#40;Service Broker&#41;](../../tools/ssbdiagnose/ssbdiagnose-utility-service-broker.md)  
  
  
