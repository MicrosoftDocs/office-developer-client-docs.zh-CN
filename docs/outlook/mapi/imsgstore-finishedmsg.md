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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348760"
---
# <a name="imsgstorefinishedmsg"></a><span data-ttu-id="fc29b-103">IMsgStore::FinishedMsg</span><span class="sxs-lookup"><span data-stu-id="fc29b-103">IMsgStore::FinishedMsg</span></span>

  
  
<span data-ttu-id="fc29b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fc29b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fc29b-105">使邮件存储提供程序能够对已发送的邮件执行处理。</span><span class="sxs-lookup"><span data-stu-id="fc29b-105">Enables the message store provider to perform processing on a sent message.</span></span> <span data-ttu-id="fc29b-106">此方法仅由 MAPI 后台处理程序调用。</span><span class="sxs-lookup"><span data-stu-id="fc29b-106">This method is called only by the MAPI spooler.</span></span>
  
```cpp
HRESULT FinishedMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="fc29b-107">参数</span><span class="sxs-lookup"><span data-stu-id="fc29b-107">Parameters</span></span>

 <span data-ttu-id="fc29b-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fc29b-108">_ulFlags_</span></span>
  
> <span data-ttu-id="fc29b-109">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="fc29b-109">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="fc29b-110">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="fc29b-110">_cbEntryID_</span></span>
  
> <span data-ttu-id="fc29b-111">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="fc29b-111">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="fc29b-112">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="fc29b-112">_lpEntryID_</span></span>
  
> <span data-ttu-id="fc29b-113">实时指向要处理的邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="fc29b-113">[in] A pointer to the entry identifier of the message to be processed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fc29b-114">返回值</span><span class="sxs-lookup"><span data-stu-id="fc29b-114">Return value</span></span>

<span data-ttu-id="fc29b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc29b-115">S_OK</span></span> 
  
> <span data-ttu-id="fc29b-116">对已发送邮件的处理已成功。</span><span class="sxs-lookup"><span data-stu-id="fc29b-116">Processing on the sent message was successful.</span></span>
    
<span data-ttu-id="fc29b-117">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="fc29b-117">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="fc29b-118">邮件存储区提供程序不支持发送的邮件处理。</span><span class="sxs-lookup"><span data-stu-id="fc29b-118">The message store provider does not support sent message processing.</span></span> <span data-ttu-id="fc29b-119">如果调用方不是 MAPI 后台处理程序, 将返回此错误值。</span><span class="sxs-lookup"><span data-stu-id="fc29b-119">This error value is returned if the caller is not the MAPI spooler.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fc29b-120">注解</span><span class="sxs-lookup"><span data-stu-id="fc29b-120">Remarks</span></span>

<span data-ttu-id="fc29b-121">**IMsgStore:: FinishedMsg**方法对已发送的邮件执行处理。</span><span class="sxs-lookup"><span data-stu-id="fc29b-121">The **IMsgStore::FinishedMsg** method performs processing on a sent message.</span></span> <span data-ttu-id="fc29b-122">此处理可能涉及删除邮件、将邮件移动到其他文件夹或两种操作。</span><span class="sxs-lookup"><span data-stu-id="fc29b-122">This processing can involve deleting the message, moving it to a different folder, or both actions.</span></span> <span data-ttu-id="fc29b-123">处理的类型取决于是否设置了**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 和**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="fc29b-123">The type of processing depends on whether the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) and **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) properties are set.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="fc29b-124">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="fc29b-124">Notes to implementers</span></span>

<span data-ttu-id="fc29b-125">在**FinishedMsg**的实现中, 解锁_lpEntryID_标识的邮件并执行相应的处理。</span><span class="sxs-lookup"><span data-stu-id="fc29b-125">In your implementation of **FinishedMsg**, unlock the message identified by  _lpEntryID_ and perform the appropriate processing.</span></span> <span data-ttu-id="fc29b-126">目标邮件将始终处于锁定状态;MAPI 后台处理程序从不将未锁定邮件的条目标识符传递给**FinishedMsg**。</span><span class="sxs-lookup"><span data-stu-id="fc29b-126">The target message will always be locked; the MAPI spooler never passes the entry identifier for an unlocked message to **FinishedMsg**.</span></span>
  
<span data-ttu-id="fc29b-127">**PR_DELETE_AFTER_SUBMIT**或**PR_SENTMAIL_ENTRYID**的设置可能既不是已设置的, 也可能是一个或另一个设置。</span><span class="sxs-lookup"><span data-stu-id="fc29b-127">It is possible that neither **PR_DELETE_AFTER_SUBMIT** or **PR_SENTMAIL_ENTRYID** is set, both are set, or one or the other is set.</span></span> <span data-ttu-id="fc29b-128">下表描述了应基于设置执行的操作:</span><span class="sxs-lookup"><span data-stu-id="fc29b-128">The following table describes the action you should take based on the settings:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fc29b-129">如果两个属性都不设置:</span><span class="sxs-lookup"><span data-stu-id="fc29b-129">If neither property is set:</span></span>  <br/> |<span data-ttu-id="fc29b-130">将邮件保留在发送邮件的文件夹中 (通常为 "发件箱")。</span><span class="sxs-lookup"><span data-stu-id="fc29b-130">Leave the message in the folder from which it was sent (typically the Outbox).</span></span>  <br/> |
|<span data-ttu-id="fc29b-131">如果同时设置这两个属性:</span><span class="sxs-lookup"><span data-stu-id="fc29b-131">If both properties are set:</span></span>  <br/> |<span data-ttu-id="fc29b-132">如果需要, 将邮件移至指定的文件夹, 然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="fc29b-132">Move the message to the indicated folder, if desired, and then delete it.</span></span>  <br/> |
|<span data-ttu-id="fc29b-133">如果设置了 PR_SENTMAIL_ENTRYID:</span><span class="sxs-lookup"><span data-stu-id="fc29b-133">If PR_SENTMAIL_ENTRYID is set:</span></span>  <br/> |<span data-ttu-id="fc29b-134">将邮件移动到指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fc29b-134">Move the message to the indicated folder.</span></span>  <br/> |
|<span data-ttu-id="fc29b-135">如果设置了 PR_DELETE_AFTER_SUBMIT:</span><span class="sxs-lookup"><span data-stu-id="fc29b-135">If PR_DELETE_AFTER_SUBMIT is set:</span></span>  <br/> |<span data-ttu-id="fc29b-136">删除邮件。</span><span class="sxs-lookup"><span data-stu-id="fc29b-136">Delete the message.</span></span>  <br/> |
   
<span data-ttu-id="fc29b-137">采取任何适合的操作后, 请调用[IMAPISupport::D osentmail](imapisupport-dosentmail.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fc29b-137">After you have taken whatever action is appropriate, call the [IMAPISupport::DoSentMail](imapisupport-dosentmail.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fc29b-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc29b-138">See also</span></span>



[<span data-ttu-id="fc29b-139">IMAPISupport::DoSentMail</span><span class="sxs-lookup"><span data-stu-id="fc29b-139">IMAPISupport::DoSentMail</span></span>](imapisupport-dosentmail.md)
  
[<span data-ttu-id="fc29b-140">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fc29b-140">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

