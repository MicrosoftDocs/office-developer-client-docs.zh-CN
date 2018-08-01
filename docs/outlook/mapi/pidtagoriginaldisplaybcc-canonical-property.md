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
ms.openlocfilehash: 15615a2de54cf42399007268cc07cbe2ab776ee8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777923"
---
# <a name="pidtagoriginaldisplaybcc-canonical-property"></a>PidTagOriginalDisplayBcc 规范属性

  
  
**适用于**： Outlook 
  
包含原始邮件的任何密件抄送 (BCC) 收件人的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_DISPLAY_BCC，PR_ORIGINAL_DISPLAY_BCC_A，PR_ORIGINAL_DISPLAY_BCC_W  <br/> |
|标识符：  <br/> |0x0072  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

这些属性包含由分号分隔的列表。 他们提供的 MAPI，并生成传递或原件报表或读取或 nonread 的报表时直接从**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 复制。 这些属性可能会出现在由其邮件类别定义其他消息。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象在允许的操作。
    
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

