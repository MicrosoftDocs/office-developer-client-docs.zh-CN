---
title: 打开邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 142c4975-08df-4501-9996-557aa44eafb3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf633a971f7e3077ce2f418021ef183a36db8cc8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411090"
---
# <a name="opening-a-message"></a>打开邮件
 
**适用于**：Outlook 2013 | Outlook 2016 
  
### <a name="to-open-a-message"></a>打开邮件
  
1. 从以下源之一检索邮件的条目标识符：
    
   - 表示其父文件夹的内容表中的邮件的行。 有关使用文件夹内容表的信息，请参阅 [Contents Tables](contents-tables.md)。
    
   - 通过新邮件通知 [发送NEWMAIL_NOTIFICATION](newmail_notification.md) **lpEntryID 结构的 lpEntryID** 成员。 有关接收和处理通知的信息，请参阅处理 [通知](handling-notifications.md)。
    
   - 对消息[的 IMAPIProp：：GetProps](imapiprop-getprops.md)方法的调用，该方法PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。  
    
2. 调用下列 **OpenEntry** 方法之一打开邮件，将  _lpEntryID_ 设置为邮件的条目标识符： 
    
   - [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)
    
   - [IMsgStore::OpenEntry](imsgstore-openentry.md)
    
   - [IMAPISession::OpenEntry](imapisession-openentry.md)
    
  最快方法仅对传入邮件可用，涉及调用接收文件夹 **的 IMAPIFolder：：OpenEntry** 方法。 下一个最快方法调用邮件存储 **的 IMsgStore：：OpenEntry** 方法，适用于所有邮件，最慢的方法调用 **IMAPISession：：OpenEntry**。
    
> [!NOTE]
> 文件夹及其内容表随时都可以关闭，而不会对从其中打开的任何邮件造成负面影响。 
  
### <a name="to-open-a-message-that-has-been-saved-on-disk"></a>打开已保存在磁盘上的消息
  
1. 调用 **StgOpenStorage** 以检索 **IStorage** 接口指针，为  _pwcsName 参数传递消息文件_ 的名称。 
    
   ```cpp
    LPSTORAGE pStorage = NULL;
    HRESULT hr = StgOpenStorage (L"MESSAGE.MSG", NULL,
                                STGM_TRANSACTED |
                                STGM_READWRITE |
                                STGM_SHARE_EXCLUSIVE,
                                NULL, 0, &pStorage);
    
   ```

2. 调用 **OpenIMsgOnIStg** 以检索 **IMessage** 接口指针以访问邮件。 
    
   ```cpp
    LPMESSAGE pMessage = NULL;
    LPMALLOC pMalloc = MAPIGetDefaultMalloc();
    hr = OpenIMsgOnIStg (NULL, MAPIAllocateBuffer, MAPIAllocateMore,
                        MAPIFreeBuffer, pMalloc, NULL, pStorage,
                        NULL, 0, 0, &pMessage);
    
   ```


