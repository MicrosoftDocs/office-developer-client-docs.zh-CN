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
  
发布邮件类似于发送邮件。 主要区别在于目标。 已发布的邮件仍保留在当前邮件存储区中的文件夹中, 而不是定向到一个或多个邮件系统上的一个或多个收件人。
  
### <a name="to-post-a-message"></a>发布邮件
  
1. 通过调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)打开目标文件夹。 如果目标文件夹是收件箱, 则通过调用[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)找到要传递给**OpenEntry**的条目标识符。 
    
2. 调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)以创建邮件。 
    
3. 调用要设置的邮件的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法: 
    
   - **PidTagMessageFlags** ( [PR_MESSAGE_FLAGS](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_READ 标志。
    
   - **PR_SENDER**属性。 
    
   - **PR_SENT_REPRESENTING**属性。 
    
   - **PR_RECEIPT_TIME** ([PidTagReceiptTime](pidtagreceipttime-canonical-property.md)) 属性。
    
   - **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。
    
   - **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性。
    
   - **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。
    
   - 邮件类所需的任何属性。
    
4. 调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以保存该邮件。 
    
5. 如有必要, 请创建一个附件, 设置其属性, 然后保存它。 有关将附件添加到邮件的详细信息, 请参阅[创建邮件附件](creating-a-message-attachment.md)。
    
6. 调用**IMessage:: SaveChanges**以保存邮件。 此时, 它将显示在目标文件夹的 "内容" 表中。 
    
请注意, 您不会创建收件人列表。 而是设置多个通常由传输提供程序为已发送的邮件设置的属性。 
  
如果要在显示在可见文件夹的内容表中之前间歇保存邮件, 请在隐藏文件夹 (如 IPM 子树的根文件夹) 中创建邮件, 然后将其移动到目标文件夹。 
  

