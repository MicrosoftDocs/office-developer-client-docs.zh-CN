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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339723"
---
# <a name="selecting-a-receive-folder"></a>选择接收文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
接收文件夹是在其中放置特定类的传入邮件的位置。 对于 IPM 和相关报告邮件, MAPI 将收件箱分配为默认接收文件夹。 对于 IPC 和相关报告邮件, MAPI 会将邮件存储区的根文件夹指定为默认的接收文件夹。 您可以更改这些分配或对其他邮件类别进行其他分配。 为客户端支持的邮件类别生成显式接收文件夹分配是可选的。
  
如果传入邮件类没有已分配的接收文件夹, 则邮件存储提供程序将自动使用与传入类的最长可能前缀相匹配的类的接收文件夹。 例如, 如果您的客户端收到一个类为 IPM 的邮件。注意: MyDocument 和已建立的接收文件夹是 IPM 邮件的收件箱, 因此该邮件将放置在收件箱中, 因为 ipm。注意: MyDocument 派生自基类 IPM。
  
为 IPC 邮件分配接收文件夹时, 决不要使用 IPM 子树中的文件夹。 应仅为 IPM 邮件保留这些文件夹。 而不是包含在邮件存储区的根文件夹中的文件夹。 
  
 **为 IPM 邮件类创建接收文件夹**
  
1. 调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。 
    
2. 调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)并将**PR_IPM_SUBTREE_ENTRYID**作为条目标识符, 以打开邮件存储区中的 IPM 子树的根文件夹。 
    
3. 调用[IMAPIFolder:: CreateFolder](imapifolder-createfolder.md)以创建接收文件夹。 
    
4. 调用[IMsgStore:: SetReceiveFolder](imsgstore-setreceivefolder.md)将新文件夹映射到您的 IPM 邮件类。 
    
 **为 IPC 邮件类创建接收文件夹**
  
1. 调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)和 null 条目标识符, 以打开邮件存储区的根文件夹。 
    
2. 调用[IMAPIFolder:: CreateFolder](imapifolder-createfolder.md)以创建接收文件夹。 
    
3. 调用[IMsgStore:: SetReceiveFolder](imsgstore-setreceivefolder.md)将新文件夹映射到 IPC 邮件类。 
    
为用于邮件的接收文件夹分配相关的报告邮件。 例如, 如果您的客户端收到 IPM。注释邮件, 为将来的 IPM 设置一个接收文件夹。注意未来报告的消息和相同的接收文件夹。 IPM. 消息。
  

