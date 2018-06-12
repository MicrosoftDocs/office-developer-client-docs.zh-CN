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
ms.openlocfilehash: 4ea75f723a2fcb242d8b9a516498855aa20cfdd4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776549"
---
# <a name="opening-a-message"></a><span data-ttu-id="a67c6-103">打开邮件</span><span class="sxs-lookup"><span data-stu-id="a67c6-103">Opening a message</span></span>
 
<span data-ttu-id="a67c6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a67c6-104">**Applies to**: Outlook</span></span> 
  
### <a name="to-open-a-message"></a><span data-ttu-id="a67c6-105">要打开邮件</span><span class="sxs-lookup"><span data-stu-id="a67c6-105">To open a message</span></span>
  
1. <span data-ttu-id="a67c6-106">从以下来源之一检索消息的项标识符：</span><span class="sxs-lookup"><span data-stu-id="a67c6-106">Retrieve the message's entry identifier from one of the following sources:</span></span>
    
   - <span data-ttu-id="a67c6-107">表示其父文件夹的内容表中的消息的行。</span><span class="sxs-lookup"><span data-stu-id="a67c6-107">The row that represents the message in the contents table of its parent folder.</span></span> <span data-ttu-id="a67c6-108">有关使用文件夹内容表的详细信息，请参阅[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a67c6-108">For more information about working with a folder contents table, see [Contents Tables](contents-tables.md).</span></span>
    
   - <span data-ttu-id="a67c6-109">发送新邮件通知的[NEWMAIL_NOTIFICATION](newmail_notification.md)结构**lpEntryID**成员。</span><span class="sxs-lookup"><span data-stu-id="a67c6-109">The **lpEntryID** member of the [NEWMAIL_NOTIFICATION](newmail_notification.md) structure that is sent with a new mail notification.</span></span> <span data-ttu-id="a67c6-110">有关接收和处理通知的详细信息，请参阅[处理通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="a67c6-110">For more information about receiving and handling notifications, see [Handling Notifications](handling-notifications.md).</span></span>
    
   - <span data-ttu-id="a67c6-111">对请求的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的消息的[IMAPIProp::GetProps](imapiprop-getprops.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="a67c6-111">A call to the message's [IMAPIProp::GetProps](imapiprop-getprops.md) method requesting the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span> 
    
2. <span data-ttu-id="a67c6-112">调用下列**OpenEntry**方法打开邮件，设置_lpEntryID_消息的项标识符之一：</span><span class="sxs-lookup"><span data-stu-id="a67c6-112">Call one of the following **OpenEntry** methods to open the message, setting  _lpEntryID_ to the message's entry identifier:</span></span> 
    
   - [<span data-ttu-id="a67c6-113">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="a67c6-113">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)
    
   - [<span data-ttu-id="a67c6-114">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="a67c6-114">IMsgStore::OpenEntry</span></span>](imsgstore-openentry.md)
    
   - [<span data-ttu-id="a67c6-115">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="a67c6-115">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
    
  <span data-ttu-id="a67c6-116">最快方法仅用于传入消息是可用，并涉及到调用的接收文件夹**IMAPIFolder::OpenEntry**方法。</span><span class="sxs-lookup"><span data-stu-id="a67c6-116">The fastest method is usable only for incoming messages and involves calling the receive folder's **IMAPIFolder::OpenEntry** method.</span></span> <span data-ttu-id="a67c6-117">是最慢的方法，调用**IMAPISession::OpenEntry**下一个最快方法，调用的消息存储**IMsgStore::OpenEntry**方法，可用于所有邮件。</span><span class="sxs-lookup"><span data-stu-id="a67c6-117">The next fastest method, calling the message store's **IMsgStore::OpenEntry** method, is usable for all messages as is the slowest method, calling **IMAPISession::OpenEntry**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a67c6-118">文件夹和其内容表可以关闭随时而不会产生不利影响任何已在这些时打开的消息。</span><span class="sxs-lookup"><span data-stu-id="a67c6-118">Folders and their contents tables can be closed at any time without adversely affecting any of the messages that were opened from within them.</span></span> 
  
### <a name="to-open-a-message-that-has-been-saved-on-disk"></a><span data-ttu-id="a67c6-119">打开一条消息，保存在磁盘上</span><span class="sxs-lookup"><span data-stu-id="a67c6-119">To open a message that has been saved on disk</span></span>
  
1. <span data-ttu-id="a67c6-120">调用**StgOpenStorage**检索**IStorage**接口的指针，将消息文件_pwcsName_参数的名称传递。</span><span class="sxs-lookup"><span data-stu-id="a67c6-120">Call **StgOpenStorage** to retrieve an **IStorage** interface pointer, passing the name of the message file for the  _pwcsName_ parameter.</span></span> 
    
   ```cpp
    LPSTORAGE pStorage = NULL;
    HRESULT hr = StgOpenStorage (L"MESSAGE.MSG", NULL,
                                STGM_TRANSACTED |
                                STGM_READWRITE |
                                STGM_SHARE_EXCLUSIVE,
                                NULL, 0, &pStorage);
    
   ```

2. <span data-ttu-id="a67c6-121">调用**OpenIMsgOnIStg**检索**IMessage**接口指针访问邮件。</span><span class="sxs-lookup"><span data-stu-id="a67c6-121">Call **OpenIMsgOnIStg** to retrieve an **IMessage** interface pointer to access the message.</span></span> 
    
   ```cpp
    LPMESSAGE pMessage = NULL;
    LPMALLOC pMalloc = MAPIGetDefaultMalloc();
    hr = OpenIMsgOnIStg (NULL, MAPIAllocateBuffer, MAPIAllocateMore,
                        MAPIFreeBuffer, pMalloc, NULL, pStorage,
                        NULL, 0, 0, &pMessage);
    
   ```


