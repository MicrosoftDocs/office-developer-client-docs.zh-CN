---
title: 公开邮件存储区中的文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d9309e47-2a92-4576-9921-c89cc48472c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0e7b479931b6b2b00dd3927133187fe058b4c6e4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774888"
---
# <a name="exposing-folders-in-message-stores"></a>公开邮件存储区中的文件夹

  
  
**适用于**： Outlook 
  
每个消息存储提供程序必须提供客户端应用程序的顶级[IMAPIFolder](imapifolderimapicontainer.md)接口。 顶级文件夹对应的整个邮件存储;它提供用户看到的消息存储内容的文件夹的访问。 此外的顶级文件夹通常用作默认的接收文件夹 IPC 邮件文件夹以及从其阅读报告发送。 消息存储提供程序必须还提供 IPM 子树 — 的一组用于包含 IPM 邮件文件夹 — 客户端应用程序。 
  
客户端应用程序可以通过分别对于_cbEntryId_和_lpEntryId_参数，调用带 0 和 NULL 的[IMsgStore::OpenEntry](imsgstore-openentry.md)方法打开的顶级文件夹。 但是，在大多数情况下，客户端应用程序打开的文件夹包含 IPM 邮件的组。 
  
若要获取的消息存储 IPM 文件夹树中的文件夹的列表，请使用以下过程：
  
1. 使用 MAPI 会话调用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法。 
    
2. 使用生成的邮件数据库指针[IMAPIProp::GetProps](imapiprop-getprops.md)方法调用**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。
    
3. 调用具有条目标识符获取**IMAPIFolder**指针[IMsgStore::OpenEntry](imsgstore-openentry.md)方法。 
    
4. 调用[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)方法以获取文件夹的目录。 
    
5. 调用[IMAPITable::QueryRows](imapitable-queryrows.md)方法列表中的顶级文件夹的文件夹。 
    
MAPI 客户端使用这些文件夹以访问其他 folder 对象和邮件存储区中的消息对象。 **IMAPIFolder**和[IMAPIContainer](imapicontainerimapiprop.md)，其父接口包含您的消息存储提供程序必须实现以填充消息对象包含的文件夹和响应客户端请求邮件上运行的方法。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储区中的文件夹](implementing-folders-in-message-stores.md)

