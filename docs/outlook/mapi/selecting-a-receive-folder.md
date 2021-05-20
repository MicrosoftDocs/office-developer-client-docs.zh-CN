---
title: 选择接收文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 144c7179-b390-479f-a2aa-324974f04eba
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9151b76f74dead5cac771dbdc091bbee03359aec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428415"
---
# <a name="selecting-a-receive-folder"></a>选择接收文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
接收文件夹是放置特定类的传入邮件的位置。 对于 IPM 和相关报告邮件，MAPI 将收件箱分配为默认接收文件夹。 对于 IPC 和相关报告邮件，MAPI 将邮件存储的根文件夹分配为默认接收文件夹。 您可以更改这些分配或为其他邮件类进行其他分配。 为客户端支持的邮件类进行显式接收文件夹分配是可选的。
  
当传入邮件类没有分配的接收文件夹时，邮件存储提供程序会自动使用与传入类的最长前缀匹配的类的接收文件夹。 例如，如果客户端收到 IPM 类消息。注意.MyDocument 和唯一已建立的接收文件夹是 IPM 邮件的收件箱，此邮件将放置在收件箱中，因为 IPM。注意.MyDocument 派生自基类 IPM。
  
为 IPC 邮件分配接收文件夹时，切勿使用 IPM 子树中的文件夹。 这些文件夹应仅为 IPM 邮件保留。 请改为使用包含在邮件存储的根文件夹中的文件夹。 
  
 **为 IPM 邮件类创建接收文件夹**
  
1. 调用消息存储的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索 **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。 
    
2. 调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) **PR_IPM_SUBTREE_ENTRYID作为条目** 标识符，以打开邮件存储中 IPM 子树的根文件夹。 
    
3. 调用 [IMAPIFolder：：CreateFolder](imapifolder-createfolder.md) 以创建接收文件夹。 
    
4. 调用 [IMsgStore：：SetReceiveFolder](imsgstore-setreceivefolder.md) 将新文件夹映射到 IPM 邮件类。 
    
 **为 IPC 邮件类创建接收文件夹**
  
1. 使用 [空条目标识符调用 IMsgStore：：OpenEntry](imsgstore-openentry.md) 以打开邮件存储的根文件夹。 
    
2. 调用 [IMAPIFolder：：CreateFolder](imapifolder-createfolder.md) 以创建接收文件夹。 
    
3. 调用 [IMsgStore：：SetReceiveFolder](imsgstore-setreceivefolder.md) 将新文件夹映射到 IPC 邮件类。 
    
分配用于相关报告邮件的邮件的接收文件夹。 例如，如果客户端接收 IPM。注意邮件，为将来的 IPM 设置一个接收文件夹。记下未来 Report.IPM.Note 邮件的邮件和相同的接收文件夹。
  

