---
title: PidTagMessageCcMe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageCcMe
api_type:
- HeaderDef
ms.assetid: 7310a0f2-a109-40a4-99bf-e963d754a067
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8e1578da3a9caea7533b75fe6dc16c3d7c3488d1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777834"
---
# <a name="pidtagmessageccme-canonical-property"></a>PidTagMessageCcMe 规范属性

  
  
**适用于**： Outlook 
  
如果此消息的用户专门命名为此邮件的抄送 (CC) 收件人，而不是通讯组列表的一部分，包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_CC_ME  <br/> |
|标识符：  <br/> |0x0058  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

此属性提供方便地确定是否用户名显式中出现抄送收件人列表中，如果不检查列表中的所有条目。 
  
此属性还可帮助您接收的消息的回执时的自动的处理。 在传输提供程序的选项，此属性包含 FALSE 或未设置如果直接在收件人的表中未列出的消息的用户。 
  
通讯组列表扩展或密件抄送副本标识生成的邮件传递不会导致要设置此属性。 必须明确名为收件人。 
  
通常未发送的邮件不设置此属性， **PR_MESSAGE_RECIP_ME** ([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md)) 或**PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))。 如果它们存在用户可以访问公共消息中的存储区，其他用户的专用存储在磁盘上的文件中或嵌入其他接收的消息，它们通常会包含到他们已设置的值的邮件在上一次传输提供程序发送邮件。 
  
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

