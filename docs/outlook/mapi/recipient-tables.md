---
title: 收件人表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02e77317-54c4-4fca-9ab4-835998ce07ce
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fdca2f65c73c0db0fa0b7d59b8d49b218aeb2330
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565086"
---
# <a name="recipient-tables"></a>收件人表

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
收件人表包含有关所有邮件的收件人信息。 消息存储提供程序实现收件人表，客户端应用程序使用它们。 客户端通过[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法调用访问收件人的表或消息存储提供程序是否支持， [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。 客户端访问收件人表与**OpenProperty**通过为接口标识符属性标记和 IID_IMAPITable 指定**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))。 可以通过调用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法来发出对收件人的表的更改。 
  
收件人表具有一个不同的列，具体取决于是否已提交邮件设置。 以下属性构成收件人表中所需的列：
  
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))
    
- **PR_ROWID**([PidTagRowid](pidtagrowid-canonical-property.md))
    
可选属性包括：
  
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    
- **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
- **PR_SPOOLER_STATUS**([PidTagSpoolerStatus](pidtagspoolerstatus-canonical-property.md))
    
- **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))
    
提交的邮件应在其所需的列集包含这些其他属性：
  
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_RESPONSIBILITY**([PidTagResponsibility](pidtagresponsibility-canonical-property.md))
    
具体取决于提供程序的实现，附加列，如**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 和[ENTRYID](entryid.md)，可能表中。
  
支持消息传输任何消息存储提供程序 — 由提供商的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中所设置的 STORE_SUBMIT_OK 位 — 应提供一组特定的支持在收件人表实现的限制。 **AND**、**或**，存在，并且属性限制是应为可供收件人表用户的限制的类型。 只有等于和不等于运算符需要支持在属性限制。 这些限制必须使用以下属性：
  
- **PR_ADDRTYPE**
    
- **PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 
    
- **PR_RECIPIENT_TYPE**
    
- **PR_RESPONSIBILITY**
    
- **PR_SPOOLER_STATUS**
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

