---
title: 打开邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 142c4975-08df-4501-9996-557aa44eafb3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e0701e64469576a8241002a6ff11299d1c343556
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582978"
---
# <a name="opening-a-message"></a>打开邮件
 
**适用于**：Outlook 2013 | Outlook 2016 
  
### <a name="to-open-a-message"></a>要打开邮件
  
1. 从以下来源之一检索消息的项标识符：
    
   - 表示其父文件夹的内容表中的消息的行。 有关使用文件夹内容表的详细信息，请参阅[内容表](contents-tables.md)。
    
   - 发送新邮件通知的[NEWMAIL_NOTIFICATION](newmail_notification.md)结构**lpEntryID**成员。 有关接收和处理通知的详细信息，请参阅[处理通知](handling-notifications.md)。
    
   - 对请求的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的消息的[IMAPIProp::GetProps](imapiprop-getprops.md)方法的调用。 
    
2. 调用下列**OpenEntry**方法打开邮件，设置_lpEntryID_消息的项标识符之一： 
    
   - [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)
    
   - [IMsgStore::OpenEntry](imsgstore-openentry.md)
    
   - [IMAPISession::OpenEntry](imapisession-openentry.md)
    
  最快方法仅用于传入消息是可用，并涉及到调用的接收文件夹**IMAPIFolder::OpenEntry**方法。 是最慢的方法，调用**IMAPISession::OpenEntry**下一个最快方法，调用的消息存储**IMsgStore::OpenEntry**方法，可用于所有邮件。
    
> [!NOTE]
> 文件夹和其内容表可以关闭随时而不会产生不利影响任何已在这些时打开的消息。 
  
### <a name="to-open-a-message-that-has-been-saved-on-disk"></a>打开一条消息，保存在磁盘上
  
1. 调用**StgOpenStorage**检索**IStorage**接口的指针，将消息文件_pwcsName_参数的名称传递。 
    
   ```cpp
    LPSTORAGE pStorage = NULL;
    HRESULT hr = StgOpenStorage (L"MESSAGE.MSG", NULL,
                                STGM_TRANSACTED |
                                STGM_READWRITE |
                                STGM_SHARE_EXCLUSIVE,
                                NULL, 0, &pStorage);
    
   ```

2. 调用**OpenIMsgOnIStg**检索**IMessage**接口指针访问邮件。 
    
   ```cpp
    LPMESSAGE pMessage = NULL;
    LPMALLOC pMalloc = MAPIGetDefaultMalloc();
    hr = OpenIMsgOnIStg (NULL, MAPIAllocateBuffer, MAPIAllocateMore,
                        MAPIFreeBuffer, pMalloc, NULL, pStorage,
                        NULL, 0, 0, &pMessage);
    
   ```


