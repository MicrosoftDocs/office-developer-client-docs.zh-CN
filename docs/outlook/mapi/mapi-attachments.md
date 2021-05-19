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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417831"
---
# <a name="mapi-attachments"></a>MAPI 附件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些邮件存储提供程序使客户端可以将添加的信息以文件、OLE 对象、邮件或二进制数据的形式与邮件关联。 此添加的信息称为邮件附件。 由于附件仅通过邮件创建、维护和访问，因此被视为邮件子对象。 附件具有一个称为附件编号的顺序编号，而不是具有用于访问的条目标识符。 此编号唯一标识邮件中的附件，但不一定是邮件存储中的附件。 两个不同的邮件可以具有相同的附件号的不同附件。 只有邮件已打开且存储在[PidTagAttachNumber](pidtagattachnumber-canonical-property.md) PR_ATTACH_NUM (中，附件) 有效。
  
若要访问有关邮件的所有附件的摘要信息，客户端将检索其附件表。 附件表包含客户端可用于直接访问附件的信息，例如附件编号和记录密钥。 客户端可以检索附件表，方法为：
  
- 调用 **IMessage：：GetAttachmentTable**。 有关详细信息，请参阅 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md)。
    
- 调用 **IMAPIProp：：OpenProperty**。 有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。
    
邮件存储提供程序应支持这两种方法。 **OpenProperty** 方法要求调用方将 IID_IMAPITable 指定为接口标识符，PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性标记。  **PR_MESSAGE_ATTACHMENTS** 是一个 table 对象属性，表示邮件的附件表。 邮件存储提供程序需要为PR_MESSAGE_ATTACHMENTS设置值，并包括到 **从 IMAPIProp：：GetPropList** 方法返回的属性标记数组中。 有关详细信息，请参阅 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)。
  
 **PR_MESSAGE_ATTACHMENTS** 可以使用： 
  
- 使用 **IMAPIProp：：OpenProperty** 访问附件或收件人表。 
    
- 使用 **IMAPIProp：：CopyTo** 或 **IMAPIProp：：CopyProps** 在复制时排除或包括附件。 有关详细信息，请参阅 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 和 [IMAPIProp：：CopyProps](imapiprop-copyprops.md)。
    
- 在子对象限制中，指示子限制应应用于附件。
    
有关详细信息，请参阅附件 [表](attachment-tables.md)。
  

