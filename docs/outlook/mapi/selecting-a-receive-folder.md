---
title: 选择接收文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 144c7179-b390-479f-a2aa-324974f04eba
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 87f8b4f4011e405d9848f12b5cae56f27fff1ab8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778714"
---
# <a name="selecting-a-receive-folder"></a>选择接收文件夹

  
  
**适用于**： Outlook 
  
接收文件夹是特定类的传入消息的放置位置。 有关 IPM 和相关的报告消息，MAPI 分配收件箱，如默认的接收文件夹。 有关 IPC 和相关的报告消息，MAPI 分配消息存储库的根文件夹，如默认的接收文件夹。 您可以更改这些分配或进行的其他邮件类的其他工作分配。 为您的客户端的支持的类是可选的消息进行显式接收文件夹工作分配。
  
当传入的邮件类不具有已分配的接收文件夹时，消息存储提供程序类相匹配的传入类可能的最长前缀自动使用的接收文件夹。 例如，如果您的客户端接收的邮件类 IPM。Note.MyDocument 和仅接收已建立的文件夹的 IPM 邮件收件箱，此消息将放置在收件箱，因为 IPM。Note.MyDocument 派生自基类 IPM。
  
当您要分配 IPC 邮件的接收文件夹时，从不使用从 IPM 子树文件夹。 应仅 IPM 邮件保留这些文件夹。 改用消息存储的根文件夹中包含的文件夹。 
  
 **若要创建 IPM 邮件类的接收文件夹**
  
1. 调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。 
    
2. 调用与**PR_IPM_SUBTREE_ENTRYID** [IMsgStore::OpenEntry](imsgstore-openentry.md)作为消息存储库中打开 IPM 子树的根文件夹的项标识符。 
    
3. 调用[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)创建的接收文件夹。 
    
4. 调用[IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)到邮件类 IPM 映射新文件夹。 
    
 **若要创建 IPC 邮件类的接收文件夹**
  
1. 要打开的邮件存储区的根文件夹的 null 条目标识符调用[IMsgStore::OpenEntry](imsgstore-openentry.md) 。 
    
2. 调用[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)创建的接收文件夹。 
    
3. 调用[IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)映射到您 IPC 邮件类的新文件夹。 
    
分配用于相关的报告邮件的邮件的接收文件夹。 例如，如果您的客户端收到 IPM。说明消息，设置一个将来 IPM 接收文件夹。注意消息和相同接收的未来 Report.IPM.Note 邮件的文件夹。
  

