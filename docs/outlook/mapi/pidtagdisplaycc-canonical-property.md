---
title: PidTagDisplayCc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayCc
api_type:
- HeaderDef
ms.assetid: 00377e78-a208-4942-a7a6-893b2a71ab0b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3d27ad5fbc02e3883d6f74129323165394c4cf2b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577728"
---
# <a name="pidtagdisplaycc-canonical-property"></a>PidTagDisplayCc 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含任何抄送 (CC) 收件人，用分号 （;） 分隔的显示名称 ASCII 的列表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DISPLAY_CC，PR_DISPLAY_CC_A，PR_DISPLAY_CC_W  <br/> |
|标识符：  <br/> |0x0E03  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |Message  <br/> |
   
## <a name="remarks"></a>注解

消息存储库使用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法计算这些消息对象的属性。 消息存储还维护这些属性，以便它始终反映消息的上次保存的状态。 在每次调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)时同步值。 
  
如果邮件没有抄送收件人，消息存储应当给出答复的返回值为 S_OK 和这些属性为空字符串[IMAPIProp::GetProps](imapiprop-getprops.md)呼叫。 
  
由于可能需要本地化，MAPI 为所有收件人姓名提供以下准则：
  
- 所有名称应该都能够都进行本地化。 
    
- 分号应为用于分隔名称**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))、 **PR_DISPLAY_CC**和**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 属性中的字符。 MAPI 中的收件人姓名内不允许使用分号分隔。 
    
- 客户端应翻译使属性信息的用户界面中可见之前遇到本地化的分隔符对此属性中的每个分号。 
    
- 将邮件转发，当客户端不需要翻译抄送收件人行上的分隔符。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
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

