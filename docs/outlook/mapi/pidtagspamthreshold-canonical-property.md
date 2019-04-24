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
ms.openlocfilehash: d43a0229f232f9437d1746799534c0f2d6fba83f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346310"
---
# <a name="pidtagspamthreshold-canonical-property"></a>PidTagSpamThreshold 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
long 值, 用于指示垃圾邮件筛选的级别。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SPAM_THRESHOLD  <br/> |
|长 ID (盖子):  <br/> | 0x041B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="values"></a>值

垃圾邮件筛选的值如下所示:
  
|**垃圾邮件级别**|**值**|
|:-----|:-----|
|无  <br/> |0xFFFFFFFF  <br/> |
|低  <br/> |0x00000006  <br/> |
|中等  <br/> |0x00000005  <br/> |
|高  <br/> |0x00000003  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Microsoft Exchange Server 协议规范的引用。
    
[[毫秒-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 启用对允许/阻止列表的处理以及确定垃圾邮件。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

