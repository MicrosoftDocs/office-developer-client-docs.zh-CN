---
title: PidTagSpamThreshold 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2b2d6b8e-e3dd-4a9b-8bb5-53add675605d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a9a5e72a585a2af8914b858cb4d174899706797e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566773"
---
# <a name="pidtagspamthreshold-canonical-property"></a>PidTagSpamThreshold 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
Long 值，该值指示垃圾邮件筛选的级别。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SPAM_THRESHOLD  <br/> |
|长 ID （盖）：  <br/> | 0x041B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="values"></a>Values

垃圾邮件筛选的值如下所示：
  
|**垃圾邮件级别**|**值**|
|:-----|:-----|
|无  <br/> |0xFFFFFFFF  <br/> |
|Low  <br/> |0x00000006  <br/> |
|Medium  <br/> |0x00000005  <br/> |
|High  <br/> |0x00000003  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Microsoft Exchange Server 协议规范的引用。
    
[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许处理的允许/阻止列表，并确定的垃圾邮件。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

