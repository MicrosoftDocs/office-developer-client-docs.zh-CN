---
title: IMsgStoreSetLockState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.SetLockState
api_type:
- COM
ms.assetid: 4b1176ec-4126-43f5-856d-cbab8d622825
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2efee531e277b6295b7d4bc299eefc789a805d34
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571085"
---
# <a name="imsgstoresetlockstate"></a><span data-ttu-id="30da6-103">IMsgStore::SetLockState</span><span class="sxs-lookup"><span data-stu-id="30da6-103">IMsgStore::SetLockState</span></span>

  
  
<span data-ttu-id="30da6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="30da6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="30da6-105">锁定或解除锁定一条消息。</span><span class="sxs-lookup"><span data-stu-id="30da6-105">Locks or unlocks a message.</span></span> <span data-ttu-id="30da6-106">只能通过 MAPI 后台处理程序调用此方法。</span><span class="sxs-lookup"><span data-stu-id="30da6-106">This method is called only by the MAPI spooler.</span></span>
  
```cpp
HRESULT SetLockState(
  LPMESSAGE lpMessage,
  ULONG ulLockState  
);
```

## <a name="parameters"></a><span data-ttu-id="30da6-107">参数</span><span class="sxs-lookup"><span data-stu-id="30da6-107">Parameters</span></span>

 <span data-ttu-id="30da6-108">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="30da6-108">_lpMessage_</span></span>
  
> <span data-ttu-id="30da6-109">[in]指向要锁定或解锁的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="30da6-109">[in] A pointer to the message to lock or unlock.</span></span>
    
 <span data-ttu-id="30da6-110">_ulLockState_</span><span class="sxs-lookup"><span data-stu-id="30da6-110">_ulLockState_</span></span>
  
> <span data-ttu-id="30da6-111">[in]一个值，指示是否应在锁定或解锁邮件。</span><span class="sxs-lookup"><span data-stu-id="30da6-111">[in] A value that indicates whether the message should be locked or unlocked.</span></span> <span data-ttu-id="30da6-112">下列值之一是有效的：</span><span class="sxs-lookup"><span data-stu-id="30da6-112">One of the following values is valid:</span></span>
    
<span data-ttu-id="30da6-113">MSG_LOCKED</span><span class="sxs-lookup"><span data-stu-id="30da6-113">MSG_LOCKED</span></span> 
  
> <span data-ttu-id="30da6-114">邮件应被锁定。</span><span class="sxs-lookup"><span data-stu-id="30da6-114">The message should be locked.</span></span> 
    
<span data-ttu-id="30da6-115">MSG_UNLOCKED</span><span class="sxs-lookup"><span data-stu-id="30da6-115">MSG_UNLOCKED</span></span> 
  
> <span data-ttu-id="30da6-116">邮件应为解除锁定。</span><span class="sxs-lookup"><span data-stu-id="30da6-116">The message should be unlocked.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="30da6-117">返回值</span><span class="sxs-lookup"><span data-stu-id="30da6-117">Return value</span></span>

<span data-ttu-id="30da6-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="30da6-118">S_OK</span></span> 
  
> <span data-ttu-id="30da6-119">成功设置消息的锁定状态。</span><span class="sxs-lookup"><span data-stu-id="30da6-119">The lock state of the message was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="30da6-120">注解</span><span class="sxs-lookup"><span data-stu-id="30da6-120">Remarks</span></span>

<span data-ttu-id="30da6-121">**IMsgStore::SetLockState**方法锁定或解除锁定一条消息。</span><span class="sxs-lookup"><span data-stu-id="30da6-121">The **IMsgStore::SetLockState** method locks or unlocks a message.</span></span> <span data-ttu-id="30da6-122">可以通过 MAPI 后台处理程序调用**SetLockState** ，其发送邮件时。</span><span class="sxs-lookup"><span data-stu-id="30da6-122">**SetLockState** can be called only by the MAPI spooler while it is sending the message.</span></span> 
  
<span data-ttu-id="30da6-123">通常，当 MAPI 后台处理程序调用**SetLockState**锁定一条消息，其锁定只有最早邮件 （即下, 一条消息排队 MAPI 后台处理程序发送的）。</span><span class="sxs-lookup"><span data-stu-id="30da6-123">Usually, when the MAPI spooler calls **SetLockState** to lock a message, it locks only the oldest message (that is, the next message queued for the MAPI spooler to send).</span></span> <span data-ttu-id="30da6-124">如果最早的消息队列中等待暂时不可用的传输提供程序，并在下一步消息队列中的使用不同的传输提供程序，MAPI 后台处理程序可以开始处理更高版本的消息。</span><span class="sxs-lookup"><span data-stu-id="30da6-124">If the oldest message in the queue is waiting for a temporarily unavailable transport provider, and the next message in the queue uses a different transport provider, the MAPI spooler can begin processing the later message.</span></span> <span data-ttu-id="30da6-125">通过使用**SetLockState**锁定邮件开始处理。</span><span class="sxs-lookup"><span data-stu-id="30da6-125">It begins processing by locking that message by using **SetLockState**.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="30da6-126">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="30da6-126">Notes to implementers</span></span>

<span data-ttu-id="30da6-127">MAPI 后台处理程序已与_ulLockState_参数设置为 MSG_LOCKED 调用**SetLockState**后，必须先对[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)方法的调用，以取消消息的传输。</span><span class="sxs-lookup"><span data-stu-id="30da6-127">After the MAPI spooler has called **SetLockState** with the  _ulLockState_ parameter set to MSG_LOCKED, calls to the [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) method to cancel the message's transmission must fail.</span></span> 
  
<span data-ttu-id="30da6-128">调用**SetLockState**实现中的消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以便保存之前收到**SetLockState**呼叫到邮件所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="30da6-128">Call the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method in your **SetLockState** implementation so that any changes that were made to the message before the **SetLockState** call was received are saved.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="30da6-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30da6-129">See also</span></span>



[<span data-ttu-id="30da6-130">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="30da6-130">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)
  
[<span data-ttu-id="30da6-131">IMsgStore::FinishedMsg</span><span class="sxs-lookup"><span data-stu-id="30da6-131">IMsgStore::FinishedMsg</span></span>](imsgstore-finishedmsg.md)
  
[<span data-ttu-id="30da6-132">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="30da6-132">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

