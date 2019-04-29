---
title: 收件人表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02e77317-54c4-4fca-9ab4-835998ce07ce
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8950623308e85de1d239deb322f65ee867a33ca0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437285"
---
# <a name="recipient-tables"></a>收件人表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
收件人表包含有关邮件的所有收件人的信息。 邮件存储提供程序实现收件人表和客户端应用程序使用它们。 客户端通过调用[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)方法或在邮件存储区提供程序支持的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法来访问收件人表。 客户端通过为属性标记指定**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)), 并为接口标识符指定 IID_IMAPITable, 从而访问收件人表和**OpenProperty** 。 可以通过调用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法对收件人表进行更改。 
  
收件人表根据邮件是否已提交而设置了不同的列。 下列属性组成了在收件人表中设置的必需列:
  
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))
    
- **PR_ROWID**([PidTagRowid](pidtagrowid-canonical-property.md))
    
可选属性为:
  
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    
- **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
- **PR_SPOOLER_STATUS**([PidTagSpoolerStatus](pidtagspoolerstatus-canonical-property.md))
    
- **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))
    
已提交的邮件应在其必需的列集中包含这些其他属性:
  
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_RESPONSIBILITY**([PidTagResponsibility](pidtagresponsibility-canonical-property.md))
    
根据提供程序的实现方式, 其他列 (如**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 和[ENTRYID](entryid.md)) 可能位于表中。
  
支持邮件传输的任何邮件存储提供程序, 如在提供程序的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置的 STORE_SUBMIT_OK 位所指示的那样, 应提供对一组特定类型的支持收件人表实现中的限制。 **and**、 **OR**、the 和 property 限制是对收件人表用户可用的限制的类型之一。 在属性限制中, 只需支持等号运算符和不相等运算符。 这些限制必须与下列属性一起使用:
  
- **PR_ADDRTYPE**
    
- **PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 
    
- **PR_RECIPIENT_TYPE**
    
- **PR_RESPONSIBILITY**
    
- **PR_SPOOLER_STATUS**
    
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

