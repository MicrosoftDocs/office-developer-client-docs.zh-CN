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
# <a name="opening-a-message"></a><span data-ttu-id="81574-103">打开邮件</span><span class="sxs-lookup"><span data-stu-id="81574-103">Opening a message</span></span>
 
<span data-ttu-id="81574-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81574-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
### <a name="to-open-a-message"></a><span data-ttu-id="81574-105">打开邮件</span><span class="sxs-lookup"><span data-stu-id="81574-105">To open a message</span></span>
  
1. <span data-ttu-id="81574-106">从以下源之一检索邮件的条目标识符：</span><span class="sxs-lookup"><span data-stu-id="81574-106">Retrieve the message's entry identifier from one of the following sources:</span></span>
    
   - <span data-ttu-id="81574-107">表示其父文件夹的内容表中的邮件的行。</span><span class="sxs-lookup"><span data-stu-id="81574-107">The row that represents the message in the contents table of its parent folder.</span></span> <span data-ttu-id="81574-108">有关使用文件夹内容表的信息，请参阅 [Contents Tables](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="81574-108">For more information about working with a folder contents table, see [Contents Tables](contents-tables.md).</span></span>
    
   - <span data-ttu-id="81574-109">通过新邮件通知 [发送NEWMAIL_NOTIFICATION](newmail_notification.md) **lpEntryID 结构的 lpEntryID** 成员。</span><span class="sxs-lookup"><span data-stu-id="81574-109">The **lpEntryID** member of the [NEWMAIL_NOTIFICATION](newmail_notification.md) structure that is sent with a new mail notification.</span></span> <span data-ttu-id="81574-110">有关接收和处理通知的信息，请参阅处理 [通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="81574-110">For more information about receiving and handling notifications, see [Handling Notifications](handling-notifications.md).</span></span>
    
   - <span data-ttu-id="81574-111">对消息[的 IMAPIProp：：GetProps](imapiprop-getprops.md)方法的调用，该方法PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="81574-111">A call to the message's [IMAPIProp::GetProps](imapiprop-getprops.md) method requesting the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span> 
    
2. <span data-ttu-id="81574-112">调用下列 **OpenEntry** 方法之一打开邮件，将  _lpEntryID_ 设置为邮件的条目标识符：</span><span class="sxs-lookup"><span data-stu-id="81574-112">Call one of the following **OpenEntry** methods to open the message, setting  _lpEntryID_ to the message's entry identifier:</span></span> 
    
   - [<span data-ttu-id="81574-113">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="81574-113">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)
    
   - [<span data-ttu-id="81574-114">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="81574-114">IMsgStore::OpenEntry</span></span>](imsgstore-openentry.md)
    
   - [<span data-ttu-id="81574-115">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="81574-115">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
    
  <span data-ttu-id="81574-116">最快方法仅对传入邮件可用，涉及调用接收文件夹 **的 IMAPIFolder：：OpenEntry** 方法。</span><span class="sxs-lookup"><span data-stu-id="81574-116">The fastest method is usable only for incoming messages and involves calling the receive folder's **IMAPIFolder::OpenEntry** method.</span></span> <span data-ttu-id="81574-117">下一个最快方法调用邮件存储 **的 IMsgStore：：OpenEntry** 方法，适用于所有邮件，最慢的方法调用 **IMAPISession：：OpenEntry**。</span><span class="sxs-lookup"><span data-stu-id="81574-117">The next fastest method, calling the message store's **IMsgStore::OpenEntry** method, is usable for all messages as is the slowest method, calling **IMAPISession::OpenEntry**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="81574-118">文件夹及其内容表随时都可以关闭，而不会对从其中打开的任何邮件造成负面影响。</span><span class="sxs-lookup"><span data-stu-id="81574-118">Folders and their contents tables can be closed at any time without adversely affecting any of the messages that were opened from within them.</span></span> 
  
### <a name="to-open-a-message-that-has-been-saved-on-disk"></a><span data-ttu-id="81574-119">打开已保存在磁盘上的消息</span><span class="sxs-lookup"><span data-stu-id="81574-119">To open a message that has been saved on disk</span></span>
  
1. <span data-ttu-id="81574-120">调用 **StgOpenStorage** 以检索 **IStorage** 接口指针，为  _pwcsName 参数传递消息文件_ 的名称。</span><span class="sxs-lookup"><span data-stu-id="81574-120">Call **StgOpenStorage** to retrieve an **IStorage** interface pointer, passing the name of the message file for the  _pwcsName_ parameter.</span></span> 
    
   ```cpp
    LPSTORAGE pStorage = NULL;
    HRESULT hr = StgOpenStorage (L"MESSAGE.MSG", NULL,
                                STGM_TRANSACTED |
                                STGM_READWRITE |
                                STGM_SHARE_EXCLUSIVE,
                                NULL, 0, &pStorage);
    
   ```

2. <span data-ttu-id="81574-121">调用 **OpenIMsgOnIStg** 以检索 **IMessage** 接口指针以访问邮件。</span><span class="sxs-lookup"><span data-stu-id="81574-121">Call **OpenIMsgOnIStg** to retrieve an **IMessage** interface pointer to access the message.</span></span> 
    
   ```cpp
    LPMESSAGE pMessage = NULL;
    LPMALLOC pMalloc = MAPIGetDefaultMalloc();
    hr = OpenIMsgOnIStg (NULL, MAPIAllocateBuffer, MAPIAllocateMore,
                        MAPIFreeBuffer, pMalloc, NULL, pStorage,
                        NULL, 0, 0, &pMessage);
    
   ```


