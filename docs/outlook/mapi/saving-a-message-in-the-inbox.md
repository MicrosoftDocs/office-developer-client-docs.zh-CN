---
title: 在收件箱中保存邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3df04d4e-7e80-4232-aadc-c05c99ab59cb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 672a9df55ce711b88451a517a2813c9ad8c599ce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407891"
---
# <a name="saving-a-message-in-the-inbox"></a>在收件箱中保存邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **在收件箱中存储没有任何收件人的邮件**
  
1. 调用 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 检索收件箱的条目标识符。 
    
2. 调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 打开收件箱并检索指向它的指针。 
    
3. 调用收件箱的 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法来创建邮件。 
    
4. 调用邮件的 [IMAPIProp：：SetProps](imapiprop-setprops.md)方法以添加 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 、PR_HTML ([PidTagHtml](pidtaghtml-canonical-property.md)) 或 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 和 **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性。  
    
5. 创建每个附件，设置其属性并保存它。 有关向邮件添加附件的详细信息，请参阅 [创建邮件附件](creating-a-message-attachment.md)。
    
6. 调用 **IMessage：：SaveChanges** 以保存邮件。 此时，它将显示在"收件箱"的"内容"表中。 
    
如果要在邮件显示在收件箱的内容表中之前，在隐藏文件夹中（如 IPM 子树的根文件夹）创建邮件，然后移动到收件箱。 
  

