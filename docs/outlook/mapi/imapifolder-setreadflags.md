---
title: IMAPIFolderSetReadFlags
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.SetReadFlags
api_type:
- COM
ms.assetid: 95a40c8a-0a8b-46c7-a07a-cbc6a7de8a3c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 88185efea344844016547d0844277de6e0d661db
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578316"
---
# <a name="imapifoldersetreadflags"></a><span data-ttu-id="79af4-103">IMAPIFolder::SetReadFlags</span><span class="sxs-lookup"><span data-stu-id="79af4-103">IMAPIFolder::SetReadFlags</span></span>

<span data-ttu-id="79af4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79af4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79af4-105">设置或清除 MSGFLAG_READ 标志中的一个或多个文件夹的邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性并管理阅读报告的发送。</span><span class="sxs-lookup"><span data-stu-id="79af4-105">Sets or clears the MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of one or more of the folder's messages, and manages the sending of read reports.</span></span> 
  
```cpp
HRESULT SetReadFlags(
  LPENTRYLIST lpMsgList,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="79af4-106">参数</span><span class="sxs-lookup"><span data-stu-id="79af4-106">Parameters</span></span>

<span data-ttu-id="79af4-107">_lpMsgList_</span><span class="sxs-lookup"><span data-stu-id="79af4-107">_lpMsgList_</span></span>
  
> <span data-ttu-id="79af4-108">[in]一个指向[ENTRYLIST](entrylist.md)结构标识的邮件或阅读标志设置或清除的邮件的数组。</span><span class="sxs-lookup"><span data-stu-id="79af4-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that identify the message or messages that have read flags to set or clear.</span></span> <span data-ttu-id="79af4-109">如果_lpMsgList_设置为 NULL，读取的所有文件夹的邮件被设置或清除标志。</span><span class="sxs-lookup"><span data-stu-id="79af4-109">If  _lpMsgList_ is set to NULL, the read flags for all the folder's messages are set or cleared.</span></span> 
    
<span data-ttu-id="79af4-110">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="79af4-110">_ulUIParam_</span></span>
  
> <span data-ttu-id="79af4-111">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="79af4-111">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="79af4-112">除非 MESSAGE_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="79af4-112">The  _ulUIParam_ parameter is ignored unless the MESSAGE_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
<span data-ttu-id="79af4-113">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="79af4-113">_lpProgress_</span></span>
  
> <span data-ttu-id="79af4-114">[in]指向显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="79af4-114">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="79af4-115">如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 的实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="79af4-115">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using MAPI's implementation.</span></span> <span data-ttu-id="79af4-116">除非_ulFlags_中设置了 MESSAGE_DIALOG 标志，则将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="79af4-116">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in  _ulFlags_.</span></span>
    
<span data-ttu-id="79af4-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="79af4-117">_ulFlags_</span></span>
  
> <span data-ttu-id="79af4-118">[in]邮件阅读标记的设置和处理控件的标志的位掩码阅读报告。</span><span class="sxs-lookup"><span data-stu-id="79af4-118">[in] A bitmask of flags that controls the setting of a message's read flag and the processing of read reports.</span></span> <span data-ttu-id="79af4-119">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="79af4-119">The following flags can be set:</span></span>
    
  - <span data-ttu-id="79af4-120">CLEAR_READ_FLAG： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_READ 标志和不应发送读取的报表。</span><span class="sxs-lookup"><span data-stu-id="79af4-120">CLEAR_READ_FLAG: The MSGFLAG_READ flag should be cleared in **PR_MESSAGE_FLAGS** and a read report should not be sent.</span></span> 
        
  - <span data-ttu-id="79af4-121">CLEAR_NRN_PENDING： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_NRN_PENDING 标志，不应发送未读的报告。</span><span class="sxs-lookup"><span data-stu-id="79af4-121">CLEAR_NRN_PENDING: The MSGFLAG_NRN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and an unread report should not be sent.</span></span> 
        
  - <span data-ttu-id="79af4-122">CLEAR_RN_PENDING： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_RN_PENDING 标志和不应发送读取的报表。</span><span class="sxs-lookup"><span data-stu-id="79af4-122">CLEAR_RN_PENDING: The MSGFLAG_RN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and a read report should not be sent.</span></span> 
        
  - <span data-ttu-id="79af4-123">GENERATE_RECEIPT_ONLY： 应发送读取的报表，如果一个处于挂起状态，但不应 MSGFLAG_READ 标志的状态发生任何变化。</span><span class="sxs-lookup"><span data-stu-id="79af4-123">GENERATE_RECEIPT_ONLY: A read report should be sent if one is pending, but there should be no change in the state of the MSGFLAG_READ flag.</span></span>
        
  - <span data-ttu-id="79af4-124">MAPI_DEFERRED_ERRORS： 允许**SetReadFlags**返回成功，原因可能是完成此操作之前。</span><span class="sxs-lookup"><span data-stu-id="79af4-124">MAPI_DEFERRED_ERRORS: Allows **SetReadFlags** to return successfully, possibly before the operation has completed.</span></span> 
        
  - <span data-ttu-id="79af4-125">MESSAGE_DIALOG： 显示进度指示器时需执行的操作。</span><span class="sxs-lookup"><span data-stu-id="79af4-125">MESSAGE_DIALOG: Displays a progress indicator while the operation proceeds.</span></span>
    
  - <span data-ttu-id="79af4-126">SUPPRESS_RECEIPT： 应取消挂起的阅读的报告，如果阅读的报告已被请求，并且此呼叫将从未读读取更改邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="79af4-126">SUPPRESS_RECEIPT: A pending read report should be canceled if a read report had been requested and this call changes the state of the message from unread to read.</span></span> <span data-ttu-id="79af4-127">如果此呼叫不会更改邮件的状态，消息存储提供程序可以忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="79af4-127">If this call does not change the state of the message, the message store provider can ignore this flag.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="79af4-128">返回值</span><span class="sxs-lookup"><span data-stu-id="79af4-128">Return values</span></span>

<span data-ttu-id="79af4-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="79af4-129">S_OK</span></span> 
  
> <span data-ttu-id="79af4-130">对指定的邮件或消息读取标志成功设置或清除。</span><span class="sxs-lookup"><span data-stu-id="79af4-130">The read flag for the specified message or messages was successfully set or cleared.</span></span>
    
<span data-ttu-id="79af4-131">MAPI_E_NO_SUPPRESS</span><span class="sxs-lookup"><span data-stu-id="79af4-131">MAPI_E_NO_SUPPRESS</span></span> 
  
> <span data-ttu-id="79af4-132">消息存储提供程序不支持阅读报告的禁止显示。</span><span class="sxs-lookup"><span data-stu-id="79af4-132">The message store provider does not support the suppression of read reports.</span></span>
    
<span data-ttu-id="79af4-133">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="79af4-133">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="79af4-134">_UlFlags_参数中设置以下不兼容的标志组合之一：</span><span class="sxs-lookup"><span data-stu-id="79af4-134">One of the following incompatible combinations of flags is set in the  _ulFlags_ parameter:</span></span> 
    
   - <span data-ttu-id="79af4-135">SUPPRESS_RECEIPT |CLEAR_READ_FLAG</span><span class="sxs-lookup"><span data-stu-id="79af4-135">SUPPRESS_RECEIPT | CLEAR_READ_FLAG</span></span> 
    
   - <span data-ttu-id="79af4-136">SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="79af4-136">SUPPRESS_RECEIPT | CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
   - <span data-ttu-id="79af4-137">CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="79af4-137">CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
<span data-ttu-id="79af4-138">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="79af4-138">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="79af4-139">调用成功，但不是所有的邮件已成功处理。</span><span class="sxs-lookup"><span data-stu-id="79af4-139">The call succeeded, but not all of the messages were successfully processed.</span></span> <span data-ttu-id="79af4-140">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="79af4-140">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="79af4-141">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="79af4-141">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="79af4-142">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="79af4-142">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="79af4-143">注解</span><span class="sxs-lookup"><span data-stu-id="79af4-143">Remarks</span></span>

<span data-ttu-id="79af4-144">**IMAPIFolder::SetReadFlags**方法设置或清除 MSGFLAG_READ 标志的一个或多个文件夹的邮件的**PR_MESSAGE_FLAGS**属性中。</span><span class="sxs-lookup"><span data-stu-id="79af4-144">The **IMAPIFolder::SetReadFlags** method sets or clears the MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** property of one or more of the folder's messages.</span></span> <span data-ttu-id="79af4-145">设置 MSGFLAG_READ 标志将邮件标记为已读，不一定表示预期接收人已实际阅读消息。</span><span class="sxs-lookup"><span data-stu-id="79af4-145">Setting the MSGFLAG_READ flag marks a message as read, which does not necessarily indicate that the intended recipient has actually read the message.</span></span> 
  
<span data-ttu-id="79af4-146">**SetReadFlags**还管理阅读报告的发送。</span><span class="sxs-lookup"><span data-stu-id="79af4-146">**SetReadFlags** also manages the sending of read reports.</span></span> 
  
<span data-ttu-id="79af4-147">读取标志不能更改以下：</span><span class="sxs-lookup"><span data-stu-id="79af4-147">The read flag cannot be changed for the following:</span></span>
  
- <span data-ttu-id="79af4-148">不存在的邮件。</span><span class="sxs-lookup"><span data-stu-id="79af4-148">Messages that do not exist.</span></span>
    
- <span data-ttu-id="79af4-149">邮件已移动至其他位置。</span><span class="sxs-lookup"><span data-stu-id="79af4-149">Messages that have been moved elsewhere.</span></span>
    
- <span data-ttu-id="79af4-150">打开具有读/写权限的邮件。</span><span class="sxs-lookup"><span data-stu-id="79af4-150">Messages that are open with read/write permission.</span></span>
    
- <span data-ttu-id="79af4-151">当前提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="79af4-151">Messages that are currently submitted.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="79af4-152">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="79af4-152">Notes to implementers</span></span>

<span data-ttu-id="79af4-153">您可以决定不支持的读取的报表和禁止阅读的报告的请求发送。</span><span class="sxs-lookup"><span data-stu-id="79af4-153">You can decide not to support the sending of read reports and the request to suppress read reports.</span></span> <span data-ttu-id="79af4-154">若要避免消除读取的报表，返回 MAPI_E_NO_SUPPRESS **SetReadFlags**调用与 SUPPRESS_RECEIPT _ulFlags_参数中设置时。</span><span class="sxs-lookup"><span data-stu-id="79af4-154">To avoid suppressing a read report, return MAPI_E_NO_SUPPRESS when **SetReadFlags** is called with SUPPRESS_RECEIPT set in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="79af4-155">当_lpMsgList_参数指向多个邮件时，执行操作完全尽可能每条消息。</span><span class="sxs-lookup"><span data-stu-id="79af4-155">When the  _lpMsgList_ parameter points to more than one message, perform the operation as completely as possible for each message.</span></span> <span data-ttu-id="79af4-156">不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。</span><span class="sxs-lookup"><span data-stu-id="79af4-156">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span> 
  
<span data-ttu-id="79af4-157">如果无标志设置_ulFlags_参数中，下列规则适用：</span><span class="sxs-lookup"><span data-stu-id="79af4-157">If none of the flags are set in the  _ulFlags_ parameter, the following rules apply:</span></span> 
  
- <span data-ttu-id="79af4-158">如果已设置 MSGFLAG_READ，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="79af4-158">If MSGFLAG_READ is already set, do nothing.</span></span>
    
- <span data-ttu-id="79af4-159">如果未设置 MSGFLAG_READ，立即设置，并发送任何挂起的阅读报告如果**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性设置。</span><span class="sxs-lookup"><span data-stu-id="79af4-159">If MSGFLAG_READ is not set, set it immediately and send any pending read reports if the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property is set.</span></span>
    
<span data-ttu-id="79af4-160">当 SUPPRESS_RECEIPT 标志设置时，下列规则适用：</span><span class="sxs-lookup"><span data-stu-id="79af4-160">When the SUPPRESS_RECEIPT flag is set, the following rules apply:</span></span>
  
- <span data-ttu-id="79af4-161">如果已设置 MSGFLAG_READ，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="79af4-161">If MSGFLAG_READ is already set, do nothing.</span></span> 
    
- <span data-ttu-id="79af4-162">如果未设置 MSGFLAG_READ，将其设置和取消任何挂起的阅读报告。</span><span class="sxs-lookup"><span data-stu-id="79af4-162">If MSGFLAG_READ is not set, set it and cancel any pending read reports.</span></span>
    
<span data-ttu-id="79af4-163">当设置 CLEAR_READ_FLAG 标志时，清除 MSGFLAG_READ 标志每条消息**PR_MESSAGE_FLAGS**属性中的并不发送任何阅读的报告。</span><span class="sxs-lookup"><span data-stu-id="79af4-163">When the CLEAR_READ_FLAG flag is set, clear the MSGFLAG_READ flag in each message's **PR_MESSAGE_FLAGS** property and do not send any read reports.</span></span> 
  
<span data-ttu-id="79af4-164">当设置 GENERATE_RECEIPT_ONLY 标志时，发送任何挂起的阅读的报告。</span><span class="sxs-lookup"><span data-stu-id="79af4-164">When the GENERATE_RECEIPT_ONLY flag is set, send any pending read reports.</span></span> <span data-ttu-id="79af4-165">执行操作未设置或清除 MSGFLAG_READ。</span><span class="sxs-lookup"><span data-stu-id="79af4-165">Do not set or clear MSGFLAG_READ.</span></span>
  
<span data-ttu-id="79af4-166">时设置的 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志， **PR_READ_RECEIPT_REQUESTED**如果设置为 false，则其设置，但不发送读取的报表。</span><span class="sxs-lookup"><span data-stu-id="79af4-166">When both the SUPPRESS_RECEIPT and GENERATE_RECEIPT_ONLY flags are set, set **PR_READ_RECEIPT_REQUESTED** to FALSE if it is set and do not send a read report.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="79af4-167">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="79af4-167">Notes to callers</span></span>

<span data-ttu-id="79af4-168">希望在下列情况下的这些返回值。</span><span class="sxs-lookup"><span data-stu-id="79af4-168">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="79af4-169">**条件**</span><span class="sxs-lookup"><span data-stu-id="79af4-169">**Condition**</span></span>|<span data-ttu-id="79af4-170">**返回值**</span><span class="sxs-lookup"><span data-stu-id="79af4-170">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="79af4-171">**SetReadFlags**已成功处理每条消息。</span><span class="sxs-lookup"><span data-stu-id="79af4-171">**SetReadFlags** has successfully processed every message.</span></span>  <br/> |<span data-ttu-id="79af4-172">S_OK</span><span class="sxs-lookup"><span data-stu-id="79af4-172">S_OK</span></span>  <br/> |
|<span data-ttu-id="79af4-173">**SetReadFlags**未能成功处理每条消息。</span><span class="sxs-lookup"><span data-stu-id="79af4-173">**SetReadFlags** was unable to successfully process every message.</span></span>  <br/> |<span data-ttu-id="79af4-174">MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="79af4-174">MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND</span></span>  <br/> |
|<span data-ttu-id="79af4-175">**SetReadFlags**无法完成。</span><span class="sxs-lookup"><span data-stu-id="79af4-175">**SetReadFlags** was unable to complete.</span></span>  <br/> |<span data-ttu-id="79af4-176">除 MAPI_E_NOT_FOUND 任何错误值</span><span class="sxs-lookup"><span data-stu-id="79af4-176">Any error value except MAPI_E_NOT_FOUND</span></span>  <br/> |
   
<span data-ttu-id="79af4-177">无法完成**SetReadFlags**时，不假定任何工作已完成。</span><span class="sxs-lookup"><span data-stu-id="79af4-177">When **SetReadFlags** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="79af4-178">**SetReadFlags**可能已经能够设置或在遇到错误之前的一个或多个邮件清除 MSGFLAG_READ 标志。</span><span class="sxs-lookup"><span data-stu-id="79af4-178">**SetReadFlags** might have been able to set or clear the MSGFLAG_READ flag for one or more of the messages before encountering the error.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="79af4-179">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="79af4-179">MFCMAPI reference</span></span>

<span data-ttu-id="79af4-180">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="79af4-180">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="79af4-181">**文件**</span><span class="sxs-lookup"><span data-stu-id="79af4-181">**File**</span></span>|<span data-ttu-id="79af4-182">**函数**</span><span class="sxs-lookup"><span data-stu-id="79af4-182">**Function**</span></span>|<span data-ttu-id="79af4-183">**Comment**</span><span class="sxs-lookup"><span data-stu-id="79af4-183">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79af4-184">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="79af4-184">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="79af4-185">CFolderDlg::OnSetReadFlag</span><span class="sxs-lookup"><span data-stu-id="79af4-185">CFolderDlg::OnSetReadFlag</span></span>  <br/> |<span data-ttu-id="79af4-186">MFCMAPI 使用**IMAPIFolder::SetReadFlags**方法将读取的状态手动设置对指定的邮件。</span><span class="sxs-lookup"><span data-stu-id="79af4-186">MFCMAPI uses the **IMAPIFolder::SetReadFlags** method to manually set the read status on the specified messages.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="79af4-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79af4-187">See also</span></span>

- [<span data-ttu-id="79af4-188">ENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="79af4-188">ENTRYLIST</span></span>](entrylist.md) 
- [<span data-ttu-id="79af4-189">IMessage::SetReadFlag</span><span class="sxs-lookup"><span data-stu-id="79af4-189">IMessage::SetReadFlag</span></span>](imessage-setreadflag.md)  
- [<span data-ttu-id="79af4-190">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="79af4-190">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)  
- [<span data-ttu-id="79af4-191">PidTagReadReceiptRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="79af4-191">PidTagReadReceiptRequested Canonical Property</span></span>](pidtagreadreceiptrequested-canonical-property.md)  
- [<span data-ttu-id="79af4-192">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="79af4-192">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
- [<span data-ttu-id="79af4-193">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="79af4-193">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)  
- [<span data-ttu-id="79af4-194">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="79af4-194">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

