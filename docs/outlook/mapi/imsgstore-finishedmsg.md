---
title: IMsgStoreFinishedMsg
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.FinishedMsg
api_type:
- COM
ms.assetid: c32493fa-aa42-485b-9ea4-f93b835906df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e7d7ba91791258eca93a2b8bedf95cf121062c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427085"
---
# <a name="imsgstorefinishedmsg"></a><span data-ttu-id="2d52f-103">IMsgStore::FinishedMsg</span><span class="sxs-lookup"><span data-stu-id="2d52f-103">IMsgStore::FinishedMsg</span></span>

  
  
<span data-ttu-id="2d52f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2d52f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2d52f-105">使邮件存储提供程序能够对已发送的邮件执行处理。</span><span class="sxs-lookup"><span data-stu-id="2d52f-105">Enables the message store provider to perform processing on a sent message.</span></span> <span data-ttu-id="2d52f-106">此方法仅由 MAPI 后台处理程序调用。</span><span class="sxs-lookup"><span data-stu-id="2d52f-106">This method is called only by the MAPI spooler.</span></span>
  
```cpp
HRESULT FinishedMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="2d52f-107">参数</span><span class="sxs-lookup"><span data-stu-id="2d52f-107">Parameters</span></span>

 <span data-ttu-id="2d52f-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2d52f-108">_ulFlags_</span></span>
  
> <span data-ttu-id="2d52f-109">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="2d52f-109">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="2d52f-110">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="2d52f-110">_cbEntryID_</span></span>
  
> <span data-ttu-id="2d52f-111">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="2d52f-111">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="2d52f-112">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="2d52f-112">_lpEntryID_</span></span>
  
> <span data-ttu-id="2d52f-113">[in]指向要处理的邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="2d52f-113">[in] A pointer to the entry identifier of the message to be processed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2d52f-114">返回值</span><span class="sxs-lookup"><span data-stu-id="2d52f-114">Return value</span></span>

<span data-ttu-id="2d52f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d52f-115">S_OK</span></span> 
  
> <span data-ttu-id="2d52f-116">已成功处理已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="2d52f-116">Processing on the sent message was successful.</span></span>
    
<span data-ttu-id="2d52f-117">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2d52f-117">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="2d52f-118">邮件存储提供程序不支持已发送的邮件处理。</span><span class="sxs-lookup"><span data-stu-id="2d52f-118">The message store provider does not support sent message processing.</span></span> <span data-ttu-id="2d52f-119">如果调用方不是 MAPI 后台处理程序，则返回此错误值。</span><span class="sxs-lookup"><span data-stu-id="2d52f-119">This error value is returned if the caller is not the MAPI spooler.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2d52f-120">备注</span><span class="sxs-lookup"><span data-stu-id="2d52f-120">Remarks</span></span>

<span data-ttu-id="2d52f-121">**IMsgStore：：FinishedMsg** 方法对已发送的邮件执行处理。</span><span class="sxs-lookup"><span data-stu-id="2d52f-121">The **IMsgStore::FinishedMsg** method performs processing on a sent message.</span></span> <span data-ttu-id="2d52f-122">此处理过程可能涉及删除邮件、将其移动到其他文件夹或执行这两项操作。</span><span class="sxs-lookup"><span data-stu-id="2d52f-122">This processing can involve deleting the message, moving it to a different folder, or both actions.</span></span> <span data-ttu-id="2d52f-123">处理类型取决于是否设置 **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 和 **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2d52f-123">The type of processing depends on whether the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) and **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) properties are set.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2d52f-124">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="2d52f-124">Notes to implementers</span></span>

<span data-ttu-id="2d52f-125">在 **FinishedMsg 的** 实现中，解锁由  _lpEntryID_ 标识的邮件并执行相应的处理。</span><span class="sxs-lookup"><span data-stu-id="2d52f-125">In your implementation of **FinishedMsg**, unlock the message identified by  _lpEntryID_ and perform the appropriate processing.</span></span> <span data-ttu-id="2d52f-126">目标邮件将始终被锁定;MAPI 后台处理程序从不将未锁定邮件的条目标识符传递给 **FinishedMsg**。</span><span class="sxs-lookup"><span data-stu-id="2d52f-126">The target message will always be locked; the MAPI spooler never passes the entry identifier for an unlocked message to **FinishedMsg**.</span></span>
  
<span data-ttu-id="2d52f-127">两者 **可能PR_DELETE_AFTER_SUBMIT** 或PR_SENTMAIL_ENTRYID设置，或设置其中一个或另一个。</span><span class="sxs-lookup"><span data-stu-id="2d52f-127">It is possible that neither **PR_DELETE_AFTER_SUBMIT** or **PR_SENTMAIL_ENTRYID** is set, both are set, or one or the other is set.</span></span> <span data-ttu-id="2d52f-128">下表介绍了基于设置应执行的操作：</span><span class="sxs-lookup"><span data-stu-id="2d52f-128">The following table describes the action you should take based on the settings:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2d52f-129">如果两个属性都未设置：</span><span class="sxs-lookup"><span data-stu-id="2d52f-129">If neither property is set:</span></span>  <br/> |<span data-ttu-id="2d52f-130">将邮件留在从其中发送邮件的文件夹中 (通常是发件箱) 。</span><span class="sxs-lookup"><span data-stu-id="2d52f-130">Leave the message in the folder from which it was sent (typically the Outbox).</span></span>  <br/> |
|<span data-ttu-id="2d52f-131">如果同时设置了这两个属性：</span><span class="sxs-lookup"><span data-stu-id="2d52f-131">If both properties are set:</span></span>  <br/> |<span data-ttu-id="2d52f-132">如果需要，将邮件移动到指示的文件夹，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="2d52f-132">Move the message to the indicated folder, if desired, and then delete it.</span></span>  <br/> |
|<span data-ttu-id="2d52f-133">如果PR_SENTMAIL_ENTRYID设置：</span><span class="sxs-lookup"><span data-stu-id="2d52f-133">If PR_SENTMAIL_ENTRYID is set:</span></span>  <br/> |<span data-ttu-id="2d52f-134">将邮件移动到指示的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2d52f-134">Move the message to the indicated folder.</span></span>  <br/> |
|<span data-ttu-id="2d52f-135">如果PR_DELETE_AFTER_SUBMIT设置：</span><span class="sxs-lookup"><span data-stu-id="2d52f-135">If PR_DELETE_AFTER_SUBMIT is set:</span></span>  <br/> |<span data-ttu-id="2d52f-136">删除邮件。</span><span class="sxs-lookup"><span data-stu-id="2d52f-136">Delete the message.</span></span>  <br/> |
   
<span data-ttu-id="2d52f-137">执行任何适当的操作后，调用 [IMAPISupport：:D oSentMail](imapisupport-dosentmail.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="2d52f-137">After you have taken whatever action is appropriate, call the [IMAPISupport::DoSentMail](imapisupport-dosentmail.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2d52f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d52f-138">See also</span></span>



[<span data-ttu-id="2d52f-139">IMAPISupport::DoSentMail</span><span class="sxs-lookup"><span data-stu-id="2d52f-139">IMAPISupport::DoSentMail</span></span>](imapisupport-dosentmail.md)
  
[<span data-ttu-id="2d52f-140">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="2d52f-140">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

