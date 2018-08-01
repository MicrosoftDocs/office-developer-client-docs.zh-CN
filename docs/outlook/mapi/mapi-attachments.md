---
title: MAPI 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6e6c6ad9-1e07-4234-a5ef-18020d7ce468
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c6538f8fef7d8ccb87b6e6d9d2b9c68779ca8582
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776203"
---
# <a name="mapi-attachments"></a>MAPI 附件

  
  
**适用于**： Outlook 
  
某些消息存储提供程序使客户端与邮件相关联的文件、 OLE 对象、 邮件或二进制数据形式添加了的信息。 此添加了的信息称为邮件附件。 附件是创建、 维护和只能通过其邮件访问，因为它们被视为消息子对象。 而不是具有访问的项标识符，附件具有附件编号的顺序的数字已知。 此号码唯一标识在其消息中，但不是一定的消息存储中的附件。 两个不同的消息可以具有不同附件具有相同的附件编号。 只要邮件处于打开状态，并存储在**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，附件号码才有效。
  
若要访问所有邮件的附件的摘要信息，客户端检索其附件表。 附件表包含客户端可以使用直接访问附件，例如其附件编号和记录的键的信息。 客户端可取回附件的表：
  
- 调用**IMessage::GetAttachmentTable**。 有关详细信息，请参阅[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)。
    
- 调用**IMAPIProp::OpenProperty**。 有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。
    
消息存储提供程序需要支持这两种方法。 **OpenProperty**方法需要呼叫者指定为接口标识符和**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) IID_IMAPITable 属性标记为。 **PR_MESSAGE_ATTACHMENTS**是一个表示一条消息的附件表的表对象属性。 消息存储提供程序所需设置**PR_MESSAGE_ATTACHMENTS**关于每封邮件，并将其加入属性标记从**IMAPIProp::GetPropList**方法返回的数组。 有关详细信息，请参阅[IMAPIProp::GetPropList](imapiprop-getproplist.md)。
  
 可以使用**PR_MESSAGE_ATTACHMENTS** : 
  
- 与**IMAPIProp::OpenProperty**访问附件或收件人的表。 
    
- 与**IMAPIProp::CopyTo**或**IMAPIProp::CopyProps**排除或包括附件时复制。 有关详细信息，请参阅[IMAPIProp::CopyTo](imapiprop-copyto.md)和[IMAPIProp::CopyProps](imapiprop-copyprops.md)。
    
- 在以指明子限制应该应用到的附件的子对象限制。
    
有关详细信息，请参阅[附件表](attachment-tables.md)。
  

