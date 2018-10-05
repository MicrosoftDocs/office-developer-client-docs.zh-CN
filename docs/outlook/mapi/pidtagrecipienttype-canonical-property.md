---
title: PidTagRecipientType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientType
api_type:
- COM
ms.assetid: 67e31027-6bc2-4a40-9b00-d61baef4ab0f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9d74fdb3acb6db94078d6090f0def050fb564cd9
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385842"
---
# <a name="pidtagrecipienttype-canonical-property"></a>PidTagRecipientType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件收件人的收件人类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECIPIENT_TYPE  <br/> |
|标识符：  <br/> |0x0C15  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 收件人  <br/> |
   
## <a name="remarks"></a>说明

此属性中包含的收件人类型包括一个必选的值和一个可选标志。
  
此属性必须包含完全下列值之一：
  
MAPI_TO 
  
> 收件人是主 （给） 收件人。 客户端需要处理主收件人。 所有其他类型是可选的。
    
MAPI_CC 
  
> 收件人抄送 (CC) 收件人收到除了主收件人的邮件的收件人。
    
MAPI_BCC 
  
> 收件人是密件抄送 (BCC) 收件人。 主和抄送副本收件人不知道密件抄送收件人的存在。 
    
MAPI_P1 
  
> 收件人未成功接收邮件在上一次尝试。 这是早期传输重新。
    
此外，可以设置以下标记：
  
MAPI_SUBMITTED 
  
> 收件人已接收邮件，并不需要再次出现。 这是早期传输重新。 此标志设置与**MAPI_TO**、 **MAPI_CC**和**MAPI_BCC**值结合使用。 
    
正在一条消息，指出由于原件到一个或多个预期收件人时，将使用 MAPI_P1 值和**MAPI_SUBMITTED**标志。 为此重新传输，客户端上不需要该消息，但应显示的收件人列表中每个收件人设置**MAPI_SUBMITTED** 。 用于每个未以前接收邮件的收件人，客户端不变，其**PR_RECIPIENT_TYPE**值保留原始收件人，但此外提交一份收件人提供 MAPI_P1 代替的原始值。 此副本，将被丢弃实际交付之前，强制进入 P1 信封的收件人，并向该收件人保证物理重新传输。 MAPI_P1 收件人**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE。
  
当客户端显示重新发送窗体时，仅 MAPI_P1 收件人是可见的。 用户输入其他收件人的邮件传递时，除非收件人列表将显示首次发送邮件时完全相同。 
  
**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))、 **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 属性与收件人类型。 当客户端呼叫消息的**IMAPIProp::SaveChanges**没有至少一个收件人的收件人列表中，消息存储提供程序，如下所示设置这些属性： 
  
|**属性**|**说明**|
|:-----|:-----|
|仅包含显示名称  <br/> |如果一个或多个收件人**MAPI_TO**收件人，则设置为 TRUE。  <br/> |
|PR_DISPLAY_CC  <br/> |如果一个或多个收件人**MAPI_CC**收件人，则设置为 TRUE。  <br/> |
| PR_DISPLAY_BCC  <br/> |如果一个或多个收件人**MAPI_BCC**收件人，则设置为 TRUE。  <br/> |
   
在 X.400，P1 或传递信封是一条消息，包括收件人的地址属性和控制传递和回复任何选项标志提供所需的信息。 P2 或显示信封是通常显示每个收件人的消息文本本身以外的信息。 它通常包括主题、 重要性、 优先级、 敏感度，和提交时间，以及主要和复制收件人姓名。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagRecipientStatus 规范属性](pidtagrecipientstatus-canonical-property.md)
  
[PidTagDisplayTo 规范属性](pidtagdisplayto-canonical-property.md)
  
[PidTagDisplayBcc 规范属性](pidtagdisplaybcc-canonical-property.md)
  
[PidTagDisplayCc 规范属性](pidtagdisplaycc-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

