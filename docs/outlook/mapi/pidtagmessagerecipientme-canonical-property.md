---
title: PidTagMessageRecipientMe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageRecipientMe
api_type:
- HeaderDef
ms.assetid: 90333258-8913-4f98-aefb-4cc2ab34abcf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 78423e874becdfc232b0dd964b32ae0c4530d19e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382461"
---
# <a name="pidtagmessagerecipientme-canonical-property"></a>PidTagMessageRecipientMe 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果此消息的用户 （收件人）、 抄送 (CC) 或此邮件的密件抄送 (BCC) 收件人为主专门名为而不是通讯组列表的一部分，包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_RECIP_ME  <br/> |
|标识符：  <br/> |0x0059  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

此属性提供方便地确定是否用户名显示显式在收件人列表中，如果不检查列表中的所有条目。 值表示逻辑**或**运算属性**PR_MESSAGE_CC_ME** ([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md)) 和**PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md)) 和密件抄送信息 (其否则未显示在属性）。 
  
此属性可帮助您接收的消息的回执时的自动的处理。 在传输提供程序的选项，此属性包含 FALSE 或时不包括直接在收件人的表中未列出的消息的用户。 
  
邮件传递的通讯组列表扩展的结果不会导致要设置此属性。 必须明确名为收件人。 
  
通常未发送的邮件不设置此属性、 **PR_MESSAGE_CC_ME**或**PR_MESSAGE_TO_ME**。 如果它们存在用户可以访问公共消息中的存储区，其他用户的专用存储在磁盘上的文件中或嵌入其他接收的消息，它们通常会包含到他们已设置的值的邮件在上一次传输提供程序发送邮件。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
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

