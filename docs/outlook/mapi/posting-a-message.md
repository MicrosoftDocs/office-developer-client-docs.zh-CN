---
title: 发布邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc3e1546-e58b-413f-82d7-4efeb86b0000
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2c174d48a19e23de725e1d5a1533130175f2ab00
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429766"
---
# <a name="posting-a-message"></a>发布邮件

**适用于**：Outlook 2013 | Outlook 2016 
  
发布邮件类似于发送邮件。 主要区别是目标。 发布的邮件将保留在当前邮件存储中的文件夹中，而不是跨一个或多个邮件系统定向到一个或多个收件人。
  
### <a name="to-post-a-message"></a>发布消息
  
1. 通过调用 [IMsgStore：：OpenEntry 打开目标文件夹](imsgstore-openentry.md)。 如果目标文件夹是收件箱，请通过调用 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md)找到要传递到 **OpenEntry** 的条目标识符。 
    
2. 调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 以创建消息。 
    
3. 调用消息的 [IMAPIProp：：SetProps 方法来](imapiprop-setprops.md) 设置： 
    
   - **PidTagMessageFlags MSGFLAG_READ PidTagMessageFlags** [ ( PR_MESSAGE_FLAGS)](pidtagmessageflags-canonical-property.md)标记。
    
   - 属性 **PR_SENDER** 属性。 
    
   - 属性 **PR_SENT_REPRESENTING** 属性。 
    
   - The **PR_RECEIPT_TIME** ([PidTagReceiptTime](pidtagreceipttime-canonical-property.md)) property.
    
   - The **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) or PR_BODY **(** [PidTagBody](pidtagbody-canonical-property.md)) property.
    
   - The **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.
    
   - The **PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.
    
   - 邮件类所需的任何属性。
    
4. 调用邮件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来保存邮件。 
    
5. 如有必要，创建附件、设置其属性并保存它。 有关向邮件添加附件的信息，请参阅 [创建邮件附件](creating-a-message-attachment.md)。
    
6. 调用 **IMessage：：SaveChanges** 以保存邮件。 此时，它将显示在目标文件夹的内容表中。 
    
请注意，您不会创建收件人列表。 相反，您可以设置通常由传输提供程序为已发送的邮件设置的几个属性。 
  
如果要在消息出现在可见文件夹的内容表中之前间歇性保存消息，请改为在隐藏文件夹（如 IPM 子树的根文件夹）中创建它，然后将它移动到目标文件夹。 
  

