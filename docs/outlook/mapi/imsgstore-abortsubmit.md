---
title: IMsgStoreAbortSubmit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.AbortSubmit
api_type:
- COM
ms.assetid: 9be6b88e-2510-4b82-8b35-5f20a0f99fc0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e2871f5804cda172328fbd3ebdc43f860de939ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775876"
---
# <a name="imsgstoreabortsubmit"></a><span data-ttu-id="614e5-103">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="614e5-103">IMsgStore::AbortSubmit</span></span>

  
  
<span data-ttu-id="614e5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="614e5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="614e5-105">尝试从传出队列中删除一条消息。</span><span class="sxs-lookup"><span data-stu-id="614e5-105">Attempts to remove a message from the outgoing queue.</span></span>
  
```cpp
AbortSubmit(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="614e5-106">参数</span><span class="sxs-lookup"><span data-stu-id="614e5-106">Parameters</span></span>

 <span data-ttu-id="614e5-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="614e5-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="614e5-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="614e5-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="614e5-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="614e5-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="614e5-110">[in]指向要从传出队列中移除的消息的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="614e5-110">[in] A pointer to the entry identifier of the message to remove from the outgoing queue.</span></span> 
    
 <span data-ttu-id="614e5-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="614e5-111">_ulFlags_</span></span>
  
> <span data-ttu-id="614e5-112">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="614e5-112">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="614e5-113">返回值</span><span class="sxs-lookup"><span data-stu-id="614e5-113">Return value</span></span>

<span data-ttu-id="614e5-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="614e5-114">S_OK</span></span> 
  
> <span data-ttu-id="614e5-115">邮件已成功删除传出队列中。</span><span class="sxs-lookup"><span data-stu-id="614e5-115">The message was successfully removed from the outgoing queue.</span></span>
    
<span data-ttu-id="614e5-116">MAPI_E_NOT_IN_QUEUE</span><span class="sxs-lookup"><span data-stu-id="614e5-116">MAPI_E_NOT_IN_QUEUE</span></span> 
  
> <span data-ttu-id="614e5-117">由_lpEntryID_标识邮件不再在传出队列中的消息存储，通常是因为已发送。</span><span class="sxs-lookup"><span data-stu-id="614e5-117">The message identified by  _lpEntryID_ is no longer in the message store's outgoing queue, typically because it has already been sent.</span></span> 
    
<span data-ttu-id="614e5-118">MAPI_E_UNABLE_TO_ABORT</span><span class="sxs-lookup"><span data-stu-id="614e5-118">MAPI_E_UNABLE_TO_ABORT</span></span> 
  
> <span data-ttu-id="614e5-119">由_lpEntryID_标识邮件已被锁定通过 MAPI 后台处理程序，且不能中止操作。</span><span class="sxs-lookup"><span data-stu-id="614e5-119">The message identified by  _lpEntryID_ is locked by the MAPI spooler, and the operation cannot be aborted.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="614e5-120">说明</span><span class="sxs-lookup"><span data-stu-id="614e5-120">Remarks</span></span>

<span data-ttu-id="614e5-121">**IMsgStore::AbortSubmit**方法尝试删除的消息存储传出队列中的已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="614e5-121">The **IMsgStore::AbortSubmit** method attempts to remove a submitted message from the message store's outgoing queue.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="614e5-122">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="614e5-122">Notes to callers</span></span>

<span data-ttu-id="614e5-123">邮件提交后，通过调用**AbortSubmit**中止提交是唯一可以对邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="614e5-123">After a message is submitted, aborting the submission by calling **AbortSubmit** is the only action that can be performed on the message.</span></span> <span data-ttu-id="614e5-124">不希望**AbortSubmit**总是成功。</span><span class="sxs-lookup"><span data-stu-id="614e5-124">Do not expect **AbortSubmit** to always succeed.</span></span> <span data-ttu-id="614e5-125">根据实现基础邮件系统的方式，它可能不是邮件的可以取消发送。</span><span class="sxs-lookup"><span data-stu-id="614e5-125">Depending on how the underlying messaging system is implemented, it might not be possible to cancel the sending of the message.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="614e5-126">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="614e5-126">MFCMAPI reference</span></span>

<span data-ttu-id="614e5-127">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="614e5-127">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="614e5-128">**文件**</span><span class="sxs-lookup"><span data-stu-id="614e5-128">**File**</span></span>|<span data-ttu-id="614e5-129">**函数**</span><span class="sxs-lookup"><span data-stu-id="614e5-129">**Function**</span></span>|<span data-ttu-id="614e5-130">**Comment**</span><span class="sxs-lookup"><span data-stu-id="614e5-130">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="614e5-131">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="614e5-131">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="614e5-132">CFolderDlg::OnAbortSubmit</span><span class="sxs-lookup"><span data-stu-id="614e5-132">CFolderDlg::OnAbortSubmit</span></span>  <br/> |<span data-ttu-id="614e5-133">MFCMAPI 使用**IMsgStore::AbortSubmit**方法中止的所选消息提交。</span><span class="sxs-lookup"><span data-stu-id="614e5-133">MFCMAPI uses the **IMsgStore::AbortSubmit** method to abort the submission of the selected message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="614e5-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="614e5-134">See also</span></span>



[<span data-ttu-id="614e5-135">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="614e5-135">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="614e5-136">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="614e5-136">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="614e5-137">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="614e5-137">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

