---
title: PidTagReplyRecipientNames 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReplyRecipientNames
api_type:
- COM
ms.assetid: f5ae6124-3e44-400f-95c2-24b19f3085b5
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5abbe14576bec9f03f0b1bf5578b68032f95f8a9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778200"
---
# <a name="pidtagreplyrecipientnames-canonical-property"></a>PidTagReplyRecipientNames 规范属性

  
  
**适用于**： Outlook 
  
包含要获取回复的收件人的显示名称的列表。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_REPLY_RECIPIENT_NAMES，PR_REPLY_RECIPIENT_NAMES_A，PR_REPLY_RECIPIENT_NAMES_W  <br/> |
|标识符:  <br/> |0x0050  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

这些属性包含由分号分隔的显示名称。
  
当此属性不存在时，仅对**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 属性标识的用户发送答复。 定义了**PR_REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和这些属性，向所有由这两个属性标识的收件人发送答复。 传输提供程序使用这些属性重写通常的应答逻辑。
  
如果设置**PR_REPLY_RECIPIENT_ENTRIES**或这些属性，还必须设置其他属性。 这些属性必须包含相同数量的收件人，并且它们必须包含它们的顺序。 遵守这些要求会导致无法预料的结果。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件中允许的操作。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

