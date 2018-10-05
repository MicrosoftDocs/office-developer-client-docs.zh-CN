---
title: PidTagDisplayTo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayTo
api_type:
- HeaderDef
ms.assetid: 700cc03b-5d98-40ce-adb5-a11fdac8aa28
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0c7ae8951b02f099161871b17ff59ea23f8fbcc4
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396041"
---
# <a name="pidtagdisplayto-canonical-property"></a>PidTagDisplayTo 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含主 （方法） 邮件的收件人，用分号 （;） 分隔的显示名称的列表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |仅包含显示名称，PR_DISPLAY_TO_A，PR_DISPLAY_TO_W  <br/> |
|标识符：  <br/> |0x0E04  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |Message  <br/> |
   
## <a name="remarks"></a>说明

消息存储库使用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法计算这些消息对象的属性。 消息存储还维护这些属性，以便它始终反映消息的上次保存的状态。 在每次调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法时同步值。 
  
如果邮件没有主收件人，消息存储应**仅包含显示名称**的响应返回 S_OK 和为空字符串值的[IMAPIProp::GetProps](imapiprop-getprops.md)呼叫中。 
  
由于可能需要本地化，MAPI 为所有收件人姓名提供以下准则：
  
- 所有名称应该都能够都进行本地化。 
    
- 分号应为用于分隔名称**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))、 **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和**仅包含显示名称**属性中的字符。 MAPI 中的收件人姓名内不允许使用分号分隔。 
    
- 客户端应翻译遇到的每个分号中**仅包含显示名称**和相关的属性设置为之前使信息在用户界面中可见本地化的分隔符。 
    
- 将邮件转发，当客户端不需要翻译主收件人行上的分隔符。 
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
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

