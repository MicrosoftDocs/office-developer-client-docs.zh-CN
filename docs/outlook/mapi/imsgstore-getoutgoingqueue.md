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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fe722e8723fdc3868cbbc3188f03e13ef3f466f3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575334"
---
# <a name="imsgstoregetoutgoingqueue"></a><span data-ttu-id="26f49-103">IMsgStore::GetOutgoingQueue</span><span class="sxs-lookup"><span data-stu-id="26f49-103">IMsgStore::GetOutgoingQueue</span></span>

  
  
<span data-ttu-id="26f49-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="26f49-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="26f49-105">提供对传出队列表，具有信息的所有邮件的邮件存储传出队列中的表的访问。</span><span class="sxs-lookup"><span data-stu-id="26f49-105">Provides access to the outgoing queue table, a table that has information about all of the messages in the message store's outgoing queue.</span></span> <span data-ttu-id="26f49-106">只能通过 MAPI 后台处理程序调用此方法。</span><span class="sxs-lookup"><span data-stu-id="26f49-106">This method is called only by the MAPI spooler.</span></span>
  
```cpp
HRESULT GetOutgoingQueue(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="26f49-107">参数</span><span class="sxs-lookup"><span data-stu-id="26f49-107">Parameters</span></span>

 <span data-ttu-id="26f49-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="26f49-108">_ulFlags_</span></span>
  
> <span data-ttu-id="26f49-109">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="26f49-109">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="26f49-110">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="26f49-110">_lppTable_</span></span>
  
> <span data-ttu-id="26f49-111">[输出]指向与传出队列表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="26f49-111">[out] A pointer to a pointer to the outgoing queue table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="26f49-112">返回值</span><span class="sxs-lookup"><span data-stu-id="26f49-112">Return value</span></span>

<span data-ttu-id="26f49-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="26f49-113">S_OK</span></span> 
  
> <span data-ttu-id="26f49-114">已成功返回传出队列表。</span><span class="sxs-lookup"><span data-stu-id="26f49-114">The outgoing queue table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="26f49-115">注解</span><span class="sxs-lookup"><span data-stu-id="26f49-115">Remarks</span></span>

<span data-ttu-id="26f49-116">**IMsgStore::GetOutgoingQueue**方法提供了有权访问表的显示的消息存储队列的传出消息的 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f49-116">The **IMsgStore::GetOutgoingQueue** method provides the MAPI spooler with access to the table that shows the message store's queue of outgoing messages.</span></span> <span data-ttu-id="26f49-117">通常情况下，消息发出传出队列表中调用其[IMessage::SubmitMessage](imessage-submitmessage.md)方法之后。</span><span class="sxs-lookup"><span data-stu-id="26f49-117">Typically, messages are placed in the outgoing queue table after their [IMessage::SubmitMessage](imessage-submitmessage.md) method is called.</span></span> <span data-ttu-id="26f49-118">但是，由于提交的顺序将影响预处理和提交到传输提供程序的顺序，某些被标记为发送的消息可能未显示在传出队列表立即。</span><span class="sxs-lookup"><span data-stu-id="26f49-118">However, because the order of submission affects the order of preprocessing and submission to the transport provider, some messages that have been marked for sending might not appear in the outgoing queue table immediately.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="26f49-119">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="26f49-119">Notes to implementers</span></span>

<span data-ttu-id="26f49-120">必须为传出队列数据表中的列包含的属性的列表，请参阅[传出队列表](outgoing-queue-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="26f49-120">For a list of the properties that must be included as columns in your outgoing queue table, see [Outgoing Queue Tables](outgoing-queue-tables.md).</span></span> 
  
<span data-ttu-id="26f49-121">由于设计 MAPI 后台处理程序是要接受来自提交时间的升序的消息存储的邮件，也允许 MAPI 后台处理程序传出的队列表格，以匹配以下顺序或建立作为默认排序顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="26f49-121">Because the MAPI spooler is designed to accept messages from a message store in ascending order of submission time, either allow the MAPI spooler to sort the outgoing queue table to match this order or establish it as the default sort order.</span></span>
  
<span data-ttu-id="26f49-122">传出消息队列表，必须支持通知确保队列的内容更改时 MAPI 后台处理程序将收到通知。</span><span class="sxs-lookup"><span data-stu-id="26f49-122">You must support notifications for the outgoing message queue table, ensuring that the MAPI spooler is notified when the contents of the queue change.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="26f49-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26f49-123">See also</span></span>



[<span data-ttu-id="26f49-124">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="26f49-124">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="26f49-125">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="26f49-125">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

