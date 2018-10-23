---
title: 公开邮件存储中的文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d9309e47-2a92-4576-9921-c89cc48472c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 62f50ed7925305eca7432da17130d2be0365ef03
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582593"
---
# <a name="exposing-folders-in-message-stores"></a>公开邮件存储中的文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个邮件存储提供程序都必须向客户端应用程序提供顶级 [IMAPIFolder](imapifolderimapicontainer.md) 界面。 顶级文件夹对应整个邮件存储；它提供用户看作邮件存储内容的文件夹的访问权限。 此外，顶级文件夹通常用作 IPC 邮件的默认接收文件夹和发送已读报表的文件夹。 邮件存储提供程序还必须向客户端应用程序提供 IPM 子树 — 用于包含 IPM 邮件的文件夹集。 
  
客户端应用程序可以通过调用 [IMsgStore::OpenEntry](imsgstore-openentry.md) 方法打开顶级文件夹，_cbEntryId_ 和 _lpEntryId_ 参数分别 0 和 NULL。 但是，在大多数情况下，客户端应用程序会打开包含 IPM 邮件的文件夹集。 
  
若要获取邮件存储 IPM 文件夹树中的文件夹列表，请使用以下过程：
  
1. 使用 MAPI 会话来调用 [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) 方法。 
    
2. 使用结果邮件数据库指针来调用 **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性的 [IMAPIProp::GetProps](imapiprop-getprops.md) 方法。
    
3. 使用条目标识符调用 [IMsgStore::OpenEntry](imsgstore-openentry.md) 方法以获取 **IMAPIFolder** 指针。 
    
4. 调用 [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) 方法以获取文件夹内容表。 
    
5. 调用 [IMAPITable::QueryRows](imapitable-queryrows.md) 方法以列出顶级文件夹中的文件夹。 
    
MAPI 客户端使用这些文件夹访问邮件存储中的其他文件夹对象和邮件对象。 **IMAPIFolder** 及其父界面 [IMAPIContainer](imapicontainerimapiprop.md) 包含邮件存储提供程序必须实现的方法，以使用邮件对象填充文件夹并响应客户端操作邮件的请求。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储中的文件夹](implementing-folders-in-message-stores.md)

