---
title: IMsgStoreGetOutgoingQueue
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.GetOutgoingQueue
api_type:
- COM
ms.assetid: 8316ff89-104d-43fd-902b-476fe567e23b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8ccb732dd587b2e5107290b2db7c48e85d0145d4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434149"
---
# <a name="imsgstoregetoutgoingqueue"></a><span data-ttu-id="8040b-103">IMsgStore::GetOutgoingQueue</span><span class="sxs-lookup"><span data-stu-id="8040b-103">IMsgStore::GetOutgoingQueue</span></span>

  
  
<span data-ttu-id="8040b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8040b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8040b-105">提供对传出队列表的访问，该表包含有关邮件存储的传出队列中所有邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="8040b-105">Provides access to the outgoing queue table, a table that has information about all of the messages in the message store's outgoing queue.</span></span> <span data-ttu-id="8040b-106">此方法仅由 MAPI 后台处理程序调用。</span><span class="sxs-lookup"><span data-stu-id="8040b-106">This method is called only by the MAPI spooler.</span></span>
  
```cpp
HRESULT GetOutgoingQueue(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="8040b-107">参数</span><span class="sxs-lookup"><span data-stu-id="8040b-107">Parameters</span></span>

 <span data-ttu-id="8040b-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8040b-108">_ulFlags_</span></span>
  
> <span data-ttu-id="8040b-109">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="8040b-109">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="8040b-110">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="8040b-110">_lppTable_</span></span>
  
> <span data-ttu-id="8040b-111">[out]指向传出队列表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8040b-111">[out] A pointer to a pointer to the outgoing queue table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8040b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="8040b-112">Return value</span></span>

<span data-ttu-id="8040b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8040b-113">S_OK</span></span> 
  
> <span data-ttu-id="8040b-114">已成功返回传出队列表。</span><span class="sxs-lookup"><span data-stu-id="8040b-114">The outgoing queue table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8040b-115">备注</span><span class="sxs-lookup"><span data-stu-id="8040b-115">Remarks</span></span>

<span data-ttu-id="8040b-116">**IMsgStore：：GetOutgoingQueue** 方法为 MAPI 后台处理程序提供了对显示邮件存储的传出邮件队列的表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8040b-116">The **IMsgStore::GetOutgoingQueue** method provides the MAPI spooler with access to the table that shows the message store's queue of outgoing messages.</span></span> <span data-ttu-id="8040b-117">通常，在调用邮件 [的 IMessage：：SubmitMessage](imessage-submitmessage.md) 方法后，邮件会放置在传出队列表中。</span><span class="sxs-lookup"><span data-stu-id="8040b-117">Typically, messages are placed in the outgoing queue table after their [IMessage::SubmitMessage](imessage-submitmessage.md) method is called.</span></span> <span data-ttu-id="8040b-118">但是，由于提交顺序会影响预处理的顺序以及提交到传输提供程序的顺序，因此一些标记为发送的邮件可能不会立即显示在传出队列表中。</span><span class="sxs-lookup"><span data-stu-id="8040b-118">However, because the order of submission affects the order of preprocessing and submission to the transport provider, some messages that have been marked for sending might not appear in the outgoing queue table immediately.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="8040b-119">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="8040b-119">Notes to implementers</span></span>

<span data-ttu-id="8040b-120">有关必须作为列包含在传出队列表中的属性的列表，请参阅 Outgoing [Queue Tables。](outgoing-queue-tables.md)</span><span class="sxs-lookup"><span data-stu-id="8040b-120">For a list of the properties that must be included as columns in your outgoing queue table, see [Outgoing Queue Tables](outgoing-queue-tables.md).</span></span> 
  
<span data-ttu-id="8040b-121">由于 MAPI 后台处理程序旨在以提交时间升序接受来自邮件存储的邮件，因此，请允许 MAPI 后台处理程序对传出队列表进行排序以匹配此顺序，或建立该表作为默认排序顺序。</span><span class="sxs-lookup"><span data-stu-id="8040b-121">Because the MAPI spooler is designed to accept messages from a message store in ascending order of submission time, either allow the MAPI spooler to sort the outgoing queue table to match this order or establish it as the default sort order.</span></span>
  
<span data-ttu-id="8040b-122">必须支持传出邮件队列表的通知，以确保在队列内容更改时通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="8040b-122">You must support notifications for the outgoing message queue table, ensuring that the MAPI spooler is notified when the contents of the queue change.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8040b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8040b-123">See also</span></span>



[<span data-ttu-id="8040b-124">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="8040b-124">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="8040b-125">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="8040b-125">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

