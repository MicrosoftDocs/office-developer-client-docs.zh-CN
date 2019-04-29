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
ms.openlocfilehash: 1486730dfa2d76bf8e97439213851b195504962f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414380"
---
# <a name="imsgstoreabortsubmit"></a><span data-ttu-id="3b2bd-103">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="3b2bd-103">IMsgStore::AbortSubmit</span></span>

  
  
<span data-ttu-id="3b2bd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b2bd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3b2bd-105">尝试从传出队列中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-105">Attempts to remove a message from the outgoing queue.</span></span>
  
```cpp
AbortSubmit(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="3b2bd-106">参数</span><span class="sxs-lookup"><span data-stu-id="3b2bd-106">Parameters</span></span>

 <span data-ttu-id="3b2bd-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="3b2bd-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="3b2bd-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="3b2bd-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="3b2bd-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="3b2bd-110">实时指向要从传出队列中删除的邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-110">[in] A pointer to the entry identifier of the message to remove from the outgoing queue.</span></span> 
    
 <span data-ttu-id="3b2bd-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3b2bd-111">_ulFlags_</span></span>
  
> <span data-ttu-id="3b2bd-112">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-112">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3b2bd-113">返回值</span><span class="sxs-lookup"><span data-stu-id="3b2bd-113">Return value</span></span>

<span data-ttu-id="3b2bd-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b2bd-114">S_OK</span></span> 
  
> <span data-ttu-id="3b2bd-115">邮件已成功从传出队列中删除。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-115">The message was successfully removed from the outgoing queue.</span></span>
    
<span data-ttu-id="3b2bd-116">MAPI_E_NOT_IN_QUEUE</span><span class="sxs-lookup"><span data-stu-id="3b2bd-116">MAPI_E_NOT_IN_QUEUE</span></span> 
  
> <span data-ttu-id="3b2bd-117">由_lpEntryID_标识的邮件不再位于邮件存储区的传出队列中, 通常是因为它已被发送。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-117">The message identified by  _lpEntryID_ is no longer in the message store's outgoing queue, typically because it has already been sent.</span></span> 
    
<span data-ttu-id="3b2bd-118">MAPI_E_UNABLE_TO_ABORT</span><span class="sxs-lookup"><span data-stu-id="3b2bd-118">MAPI_E_UNABLE_TO_ABORT</span></span> 
  
> <span data-ttu-id="3b2bd-119">由_lpEntryID_标识的邮件被 MAPI 后台处理程序锁定, 无法中止该操作。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-119">The message identified by  _lpEntryID_ is locked by the MAPI spooler, and the operation cannot be aborted.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="3b2bd-120">说明</span><span class="sxs-lookup"><span data-stu-id="3b2bd-120">Remarks</span></span>

<span data-ttu-id="3b2bd-121">**IMsgStore:: AbortSubmit**方法尝试从邮件存储区的传出队列中删除已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-121">The **IMsgStore::AbortSubmit** method attempts to remove a submitted message from the message store's outgoing queue.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3b2bd-122">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3b2bd-122">Notes to callers</span></span>

<span data-ttu-id="3b2bd-123">提交邮件后, 通过调用**AbortSubmit**来中止提交操作是可对邮件执行的唯一操作。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-123">After a message is submitted, aborting the submission by calling **AbortSubmit** is the only action that can be performed on the message.</span></span> <span data-ttu-id="3b2bd-124">不希望**AbortSubmit**总是成功。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-124">Do not expect **AbortSubmit** to always succeed.</span></span> <span data-ttu-id="3b2bd-125">根据基础邮件系统的实现方式, 可能无法取消邮件的发送。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-125">Depending on how the underlying messaging system is implemented, it might not be possible to cancel the sending of the message.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3b2bd-126">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="3b2bd-126">MFCMAPI reference</span></span>

<span data-ttu-id="3b2bd-127">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-127">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3b2bd-128">**文件**</span><span class="sxs-lookup"><span data-stu-id="3b2bd-128">**File**</span></span>|<span data-ttu-id="3b2bd-129">**函数**</span><span class="sxs-lookup"><span data-stu-id="3b2bd-129">**Function**</span></span>|<span data-ttu-id="3b2bd-130">**备注**</span><span class="sxs-lookup"><span data-stu-id="3b2bd-130">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b2bd-131">FolderDlg</span><span class="sxs-lookup"><span data-stu-id="3b2bd-131">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="3b2bd-132">CFolderDlg:: OnAbortSubmit</span><span class="sxs-lookup"><span data-stu-id="3b2bd-132">CFolderDlg::OnAbortSubmit</span></span>  <br/> |<span data-ttu-id="3b2bd-133">MFCMAPI 使用**IMsgStore:: AbortSubmit**方法中止所选邮件的提交。</span><span class="sxs-lookup"><span data-stu-id="3b2bd-133">MFCMAPI uses the **IMsgStore::AbortSubmit** method to abort the submission of the selected message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3b2bd-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b2bd-134">See also</span></span>



[<span data-ttu-id="3b2bd-135">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="3b2bd-135">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="3b2bd-136">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="3b2bd-136">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="3b2bd-137">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="3b2bd-137">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

