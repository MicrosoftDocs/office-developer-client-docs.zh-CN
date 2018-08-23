---
title: 保存收件箱中的某封邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3df04d4e-7e80-4232-aadc-c05c99ab59cb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e79133ed4928495dcf75b59877a82d3228773883
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586282"
---
# <a name="saving-a-message-in-the-inbox"></a>保存收件箱中的某封邮件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 **若要在没有任何收件人的收件箱中存储一条消息**
  
1. 调用[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)检索的收件箱的项标识符。 
    
2. 调用[IMsgStore::OpenEntry](imsgstore-openentry.md)打开收件箱并检索指向它的指针。 
    
3. 调用收件箱的[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法来创建邮件。 
    
4. 调用消息的[IMAPIProp::SetProps](imapiprop-setprops.md)方法来添加**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))、 **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 或**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 和**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性。 
    
5. 创建每个附件，设置其属性，并将其保存。 有关将附件添加到邮件的详细信息，请参阅[创建邮件附件](creating-a-message-attachment.md)。
    
6. 调用**IMessage::SaveChanges**保存邮件。 此时将显示内容表的收件箱中。 
    
如果您希望让其出现在收件箱的内容表之前保存消息 intermittantly，改为在隐藏的文件夹，如 IPM 子树的根文件夹中创建它，然后将其移至收件箱。 
  

