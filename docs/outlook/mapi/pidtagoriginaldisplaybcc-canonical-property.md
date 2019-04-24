---
title: PidTagOriginalDisplayBcc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalDisplayBcc
api_type:
- COM
ms.assetid: 7bf66f0c-3095-4b4a-a32e-db278e1adc5a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3fbd7205901616695bcdcd012601afd252ac05f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355641"
---
# <a name="pidtagoriginaldisplaybcc-canonical-property"></a>PidTagOriginalDisplayBcc 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含原始邮件的任意密件抄送 (BCC) 收件人的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_DISPLAY_BCC、PR_ORIGINAL_DISPLAY_BCC_A、PR_ORIGINAL_DISPLAY_BCC_W  <br/> |
|标识符:  <br/> |0x0072  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

这些属性包含以分号分隔的列表。 它们由 MAPI 提供, 并在生成传递或 nondelivery 报告或已读或未读报告时直接从**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 进行复制。 这些属性可能出现在由其邮件类别定义的其他邮件上。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定在电子邮件对象上允许的属性和操作。
    
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

