---
title: PidTagOriginalSenderName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSenderName
api_type:
- COM
ms.assetid: 5e3b7764-b122-4405-be4f-7fec571c7dfc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ae0ae8536f4f088bae4561e123afce716b623414
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777952"
---
# <a name="pidtagoriginalsendername-canonical-property"></a>PidTagOriginalSenderName 规范属性

  
  
**适用于**： Outlook 
  
包含一条消息，即之前正在转发或答复邮件的第一个版本的发件人的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_SENDER_NAME，PR_ORIGINAL_SENDER_NAME_A，PR_ORIGINAL_SENDER_NAME_W  <br/> |
|标识符：  <br/> |0x005A  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

这些属性是一条消息的原始发件人的地址属性的示例。 在首次提交邮件，客户端应用程序应将这些属性设置为**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 属性的值。 当转发或答复邮件永远不会更改它。
  
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

