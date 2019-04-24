---
title: MAPI 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6e6c6ad9-1e07-4234-a5ef-18020d7ce468
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 90fbec8b61499f383228823d69b041a21199a22e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297870"
---
# <a name="mapi-attachments"></a>MAPI 附件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些邮件存储提供程序使客户端能够将文件、OLE 对象、消息或二进制数据的格式添加的信息与邮件相关联。 此添加的信息称为邮件的附件。 由于附件是通过其邮件进行创建、维护和访问的, 因此它们被视为邮件子消息。 附件具有称为附件编号的连续号码, 而不是访问的条目标识符。 此数字唯一标识其邮件中的附件, 但不一定是邮件存储区中的附件。 两个不同的邮件可以具有具有相同附件编号的不同附件。 附件编号仅在邮件打开并存储在**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中时才有效。
  
若要访问有关邮件所有附件的摘要信息, 客户端将检索其附件表。 附件表包含客户端可直接访问附件的信息, 如附件编号和记录密钥。 客户端可以通过以下方式检索附件表:
  
- 调用**IMessage:: GetAttachmentTable**。 有关详细信息, 请参阅[IMessage:: GetAttachmentTable](imessage-getattachmenttable.md)。
    
- 调用**IMAPIProp:: OpenProperty**。 有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)。
    
邮件存储提供程序应支持这两种方法。 **OpenProperty**方法要求调用方将 IID_IMAPITable 指定为接口标识符, 并将**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 指定为属性标记。 **PR_MESSAGE_ATTACHMENTS**是一个 table 对象属性, 该对象代表邮件的附件表。 邮件存储提供程序需要设置每个邮件的**PR_MESSAGE_ATTACHMENTS** , 并将其包含在从**IMAPIProp:: GetPropList**方法返回的属性标记数组中。 有关详细信息, 请参阅[IMAPIProp:: GetPropList](imapiprop-getproplist.md)。
  
 可以使用**PR_MESSAGE_ATTACHMENTS** : 
  
- 使用**IMAPIProp:: OpenProperty**访问附件或收件人表。 
    
- 使用**IMAPIProp:: CopyTo**或**IMAPIProp:: CopyProps**在复制时排除或包含附件。 有关详细信息, 请参阅[IMAPIProp:: CopyTo](imapiprop-copyto.md) and [IMAPIProp:: CopyProps](imapiprop-copyprops.md)。
    
- 在子元素限制中, 指示应将子限制应用于附件。
    
有关详细信息, 请参阅[附件表](attachment-tables.md)。
  

