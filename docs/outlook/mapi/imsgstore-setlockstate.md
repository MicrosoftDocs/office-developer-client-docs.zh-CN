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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9eeede2a430f5186daf429dd6ed59f312ae334be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348746"
---
# <a name="imsgstoresetlockstate"></a><span data-ttu-id="245d2-103">IMsgStore::SetLockState</span><span class="sxs-lookup"><span data-stu-id="245d2-103">IMsgStore::SetLockState</span></span>

  
  
<span data-ttu-id="245d2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="245d2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="245d2-105">锁定或解除锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="245d2-105">Locks or unlocks a message.</span></span> <span data-ttu-id="245d2-106">此方法仅由 MAPI 后台处理程序调用。</span><span class="sxs-lookup"><span data-stu-id="245d2-106">This method is called only by the MAPI spooler.</span></span>
  
```cpp
HRESULT SetLockState(
  LPMESSAGE lpMessage,
  ULONG ulLockState  
);
```

## <a name="parameters"></a><span data-ttu-id="245d2-107">参数</span><span class="sxs-lookup"><span data-stu-id="245d2-107">Parameters</span></span>

 <span data-ttu-id="245d2-108">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="245d2-108">_lpMessage_</span></span>
  
> <span data-ttu-id="245d2-109">实时指向要锁定或解锁的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="245d2-109">[in] A pointer to the message to lock or unlock.</span></span>
    
 <span data-ttu-id="245d2-110">_ulLockState_</span><span class="sxs-lookup"><span data-stu-id="245d2-110">_ulLockState_</span></span>
  
> <span data-ttu-id="245d2-111">实时一个值, 指示是否应锁定或解除锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="245d2-111">[in] A value that indicates whether the message should be locked or unlocked.</span></span> <span data-ttu-id="245d2-112">以下值之一是有效的:</span><span class="sxs-lookup"><span data-stu-id="245d2-112">One of the following values is valid:</span></span>
    
<span data-ttu-id="245d2-113">MSG_LOCKED</span><span class="sxs-lookup"><span data-stu-id="245d2-113">MSG_LOCKED</span></span> 
  
> <span data-ttu-id="245d2-114">应锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="245d2-114">The message should be locked.</span></span> 
    
<span data-ttu-id="245d2-115">MSG_UNLOCKED</span><span class="sxs-lookup"><span data-stu-id="245d2-115">MSG_UNLOCKED</span></span> 
  
> <span data-ttu-id="245d2-116">应解锁邮件。</span><span class="sxs-lookup"><span data-stu-id="245d2-116">The message should be unlocked.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="245d2-117">返回值</span><span class="sxs-lookup"><span data-stu-id="245d2-117">Return value</span></span>

<span data-ttu-id="245d2-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="245d2-118">S_OK</span></span> 
  
> <span data-ttu-id="245d2-119">已成功设置邮件的锁定状态。</span><span class="sxs-lookup"><span data-stu-id="245d2-119">The lock state of the message was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="245d2-120">注解</span><span class="sxs-lookup"><span data-stu-id="245d2-120">Remarks</span></span>

<span data-ttu-id="245d2-121">**IMsgStore:: SetLockState**方法锁定或解除锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="245d2-121">The **IMsgStore::SetLockState** method locks or unlocks a message.</span></span> <span data-ttu-id="245d2-122">在发送邮件时, **SetLockState**只能由 MAPI 后台处理程序调用。</span><span class="sxs-lookup"><span data-stu-id="245d2-122">**SetLockState** can be called only by the MAPI spooler while it is sending the message.</span></span> 
  
<span data-ttu-id="245d2-123">通常情况下, 当 MAPI 后台处理程序调用**SetLockState**以锁定邮件时, 它将仅锁定最旧的邮件 (即, 在排队等待 MAPI 后台处理程序发送的下一封邮件)。</span><span class="sxs-lookup"><span data-stu-id="245d2-123">Usually, when the MAPI spooler calls **SetLockState** to lock a message, it locks only the oldest message (that is, the next message queued for the MAPI spooler to send).</span></span> <span data-ttu-id="245d2-124">如果队列中的最旧邮件等待暂时不可用的传输提供程序, 并且队列中的下一封邮件使用不同的传输提供程序, 则 MAPI 后台处理程序可以开始处理后续邮件。</span><span class="sxs-lookup"><span data-stu-id="245d2-124">If the oldest message in the queue is waiting for a temporarily unavailable transport provider, and the next message in the queue uses a different transport provider, the MAPI spooler can begin processing the later message.</span></span> <span data-ttu-id="245d2-125">它通过使用**SetLockState**锁定邮件来开始处理。</span><span class="sxs-lookup"><span data-stu-id="245d2-125">It begins processing by locking that message by using **SetLockState**.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="245d2-126">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="245d2-126">Notes to implementers</span></span>

<span data-ttu-id="245d2-127">MAPI 后台处理程序在将_ulLockState_参数设置为 MSG_LOCKED 的情况下调用**SetLockState**后, 调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)方法以取消邮件的传输必须失败。</span><span class="sxs-lookup"><span data-stu-id="245d2-127">After the MAPI spooler has called **SetLockState** with the  _ulLockState_ parameter set to MSG_LOCKED, calls to the [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) method to cancel the message's transmission must fail.</span></span> 
  
<span data-ttu-id="245d2-128">在**SetLockState**实现中调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法, 以便在收到**SetLockState**调用之前对邮件所做的任何更改都将被保存。</span><span class="sxs-lookup"><span data-stu-id="245d2-128">Call the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method in your **SetLockState** implementation so that any changes that were made to the message before the **SetLockState** call was received are saved.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="245d2-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="245d2-129">See also</span></span>



[<span data-ttu-id="245d2-130">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="245d2-130">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)
  
[<span data-ttu-id="245d2-131">IMsgStore::FinishedMsg</span><span class="sxs-lookup"><span data-stu-id="245d2-131">IMsgStore::FinishedMsg</span></span>](imsgstore-finishedmsg.md)
  
[<span data-ttu-id="245d2-132">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="245d2-132">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

