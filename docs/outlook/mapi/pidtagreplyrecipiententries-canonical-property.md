---
title: PidTagReplyRecipientEntries 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReplyRecipientEntries
api_type:
- COM
ms.assetid: a903fd22-a3f2-464f-99b0-c087e211b124
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ce433dda7357bdce964f897ce985286d193ec0b1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576468"
---
# <a name="pidtagreplyrecipiententries-canonical-property"></a>PidTagReplyRecipientEntries 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含要获取回复的收件人的项标识符的大小的数组。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REPLY_RECIPIENT_ENTRIES  <br/> |
|标识符：  <br/> |0x004F  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>注解

此属性包含一个[FLATENTRYLIST](flatentrylist.md)结构，并不是多值的属性。 
  
当此属性不存在时，仅对**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 属性标识的用户发送答复。 定义了这和**PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) 属性，向所有由这两个属性标识的收件人发送答复。 传输提供程序使用这些属性重写通常的应答逻辑。
  
如果设置此属性或**PR_REPLY_RECIPIENT_NAMES**属性，还必须设置其他属性。 这些属性必须包含相同数量的收件人，并且它们必须包含它们的顺序。 遵守这些要求会导致无法预料的结果。 
  
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
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

