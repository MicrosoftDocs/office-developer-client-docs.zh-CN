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
ms.openlocfilehash: 15504ecc88188ed7bc4eed0e64b1871dbc6a5e8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406911"
---
# <a name="imapifoldersetreadflags"></a><span data-ttu-id="cda2d-103">IMAPIFolder::SetReadFlags</span><span class="sxs-lookup"><span data-stu-id="cda2d-103">IMAPIFolder::SetReadFlags</span></span>

<span data-ttu-id="cda2d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cda2d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cda2d-105">设置或清除文件夹的一个或多个邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_READ 标志，并管理读取报表的发送。</span><span class="sxs-lookup"><span data-stu-id="cda2d-105">Sets or clears the MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of one or more of the folder's messages, and manages the sending of read reports.</span></span> 
  
```cpp
HRESULT SetReadFlags(
  LPENTRYLIST lpMsgList,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="cda2d-106">参数</span><span class="sxs-lookup"><span data-stu-id="cda2d-106">Parameters</span></span>

<span data-ttu-id="cda2d-107">_lpMsgList_</span><span class="sxs-lookup"><span data-stu-id="cda2d-107">_lpMsgList_</span></span>
  
> <span data-ttu-id="cda2d-108">[in]指向 [ENTRYLIST](entrylist.md) 结构的数组的指针，该数组标识要设置或清除的读取标志的邮件。</span><span class="sxs-lookup"><span data-stu-id="cda2d-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that identify the message or messages that have read flags to set or clear.</span></span> <span data-ttu-id="cda2d-109">如果  _lpMsgList_ 设置为 NULL，则设置或清除文件夹的所有邮件的读取标志。</span><span class="sxs-lookup"><span data-stu-id="cda2d-109">If  _lpMsgList_ is set to NULL, the read flags for all the folder's messages are set or cleared.</span></span> 
    
<span data-ttu-id="cda2d-110">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="cda2d-110">_ulUIParam_</span></span>
  
> <span data-ttu-id="cda2d-111">[in]进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="cda2d-111">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="cda2d-112">除非  _在 ulFlags_ 参数中设置了 MESSAGE_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。</span><span class="sxs-lookup"><span data-stu-id="cda2d-112">The  _ulUIParam_ parameter is ignored unless the MESSAGE_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
<span data-ttu-id="cda2d-113">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="cda2d-113">_lpProgress_</span></span>
  
> <span data-ttu-id="cda2d-114">[in]指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="cda2d-114">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="cda2d-115">如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 的实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="cda2d-115">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using MAPI's implementation.</span></span> <span data-ttu-id="cda2d-116">除非在 _ulFlags_ 中设置了 MESSAGE_DIALOG 标志，否则将忽略 _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="cda2d-116">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in  _ulFlags_.</span></span>
    
<span data-ttu-id="cda2d-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cda2d-117">_ulFlags_</span></span>
  
> <span data-ttu-id="cda2d-118">[in]控制邮件的读取标志设置和读取报告处理的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="cda2d-118">[in] A bitmask of flags that controls the setting of a message's read flag and the processing of read reports.</span></span> <span data-ttu-id="cda2d-119">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="cda2d-119">The following flags can be set:</span></span>
    
  - <span data-ttu-id="cda2d-120">CLEAR_READ_FLAG：MSGFLAG_READ中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送阅读报告。</span><span class="sxs-lookup"><span data-stu-id="cda2d-120">CLEAR_READ_FLAG: The MSGFLAG_READ flag should be cleared in **PR_MESSAGE_FLAGS** and a read report should not be sent.</span></span> 
        
  - <span data-ttu-id="cda2d-121">CLEAR_NRN_PENDING：MSGFLAG_NRN_PENDING中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送未读报告。</span><span class="sxs-lookup"><span data-stu-id="cda2d-121">CLEAR_NRN_PENDING: The MSGFLAG_NRN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and an unread report should not be sent.</span></span> 
        
  - <span data-ttu-id="cda2d-122">CLEAR_RN_PENDING：MSGFLAG_RN_PENDING中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送阅读报告。</span><span class="sxs-lookup"><span data-stu-id="cda2d-122">CLEAR_RN_PENDING: The MSGFLAG_RN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and a read report should not be sent.</span></span> 
        
  - <span data-ttu-id="cda2d-123">GENERATE_RECEIPT_ONLY：如果一个已读报告挂起，则应该发送一个已读报告，但该读取报告MSGFLAG_READ状态。</span><span class="sxs-lookup"><span data-stu-id="cda2d-123">GENERATE_RECEIPT_ONLY: A read report should be sent if one is pending, but there should be no change in the state of the MSGFLAG_READ flag.</span></span>
        
  - <span data-ttu-id="cda2d-124">MAPI_DEFERRED_ERRORS：允许在操作完成之前成功返回 **SetReadFlags。**</span><span class="sxs-lookup"><span data-stu-id="cda2d-124">MAPI_DEFERRED_ERRORS: Allows **SetReadFlags** to return successfully, possibly before the operation has completed.</span></span> 
        
  - <span data-ttu-id="cda2d-125">MESSAGE_DIALOG：在操作进行时显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="cda2d-125">MESSAGE_DIALOG: Displays a progress indicator while the operation proceeds.</span></span>
    
  - <span data-ttu-id="cda2d-126">SUPPRESS_RECEIPT：如果已请求读取报告，并且此调用将邮件的状态从"未读"改为"已读"，应取消挂起的阅读报告。</span><span class="sxs-lookup"><span data-stu-id="cda2d-126">SUPPRESS_RECEIPT: A pending read report should be canceled if a read report had been requested and this call changes the state of the message from unread to read.</span></span> <span data-ttu-id="cda2d-127">如果此调用不更改邮件的状态，则邮件存储提供程序可以忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="cda2d-127">If this call does not change the state of the message, the message store provider can ignore this flag.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="cda2d-128">返回值</span><span class="sxs-lookup"><span data-stu-id="cda2d-128">Return values</span></span>

<span data-ttu-id="cda2d-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="cda2d-129">S_OK</span></span> 
  
> <span data-ttu-id="cda2d-130">已成功设置或清除指定邮件的读取标志。</span><span class="sxs-lookup"><span data-stu-id="cda2d-130">The read flag for the specified message or messages was successfully set or cleared.</span></span>
    
<span data-ttu-id="cda2d-131">MAPI_E_NO_SUPPRESS</span><span class="sxs-lookup"><span data-stu-id="cda2d-131">MAPI_E_NO_SUPPRESS</span></span> 
  
> <span data-ttu-id="cda2d-132">邮件存储提供程序不支持禁止读取报告。</span><span class="sxs-lookup"><span data-stu-id="cda2d-132">The message store provider does not support the suppression of read reports.</span></span>
    
<span data-ttu-id="cda2d-133">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="cda2d-133">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="cda2d-134">在  _ulFlags_ 参数中设置以下不兼容的标志组合之一：</span><span class="sxs-lookup"><span data-stu-id="cda2d-134">One of the following incompatible combinations of flags is set in the  _ulFlags_ parameter:</span></span> 
    
   - <span data-ttu-id="cda2d-135">SUPPRESS_RECEIPT |CLEAR_READ_FLAG</span><span class="sxs-lookup"><span data-stu-id="cda2d-135">SUPPRESS_RECEIPT | CLEAR_READ_FLAG</span></span> 
    
   - <span data-ttu-id="cda2d-136">SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="cda2d-136">SUPPRESS_RECEIPT | CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
   - <span data-ttu-id="cda2d-137">CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="cda2d-137">CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
<span data-ttu-id="cda2d-138">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="cda2d-138">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="cda2d-139">调用成功，但并非所有邮件都已成功处理。</span><span class="sxs-lookup"><span data-stu-id="cda2d-139">The call succeeded, but not all of the messages were successfully processed.</span></span> <span data-ttu-id="cda2d-140">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="cda2d-140">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="cda2d-141">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="cda2d-141">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="cda2d-142">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="cda2d-142">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cda2d-143">备注</span><span class="sxs-lookup"><span data-stu-id="cda2d-143">Remarks</span></span>

<span data-ttu-id="cda2d-144">**IMAPIFolder：：SetReadFlags** 方法设置或清除文件夹的一个或多个邮件的 PR_MESSAGE_FLAGS 属性中的 **MSGFLAG_READ** 标志。</span><span class="sxs-lookup"><span data-stu-id="cda2d-144">The **IMAPIFolder::SetReadFlags** method sets or clears the MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** property of one or more of the folder's messages.</span></span> <span data-ttu-id="cda2d-145">设置MSGFLAG_READ标记将邮件标记为已读，这不一定表示目标收件人实际上已阅读该邮件。</span><span class="sxs-lookup"><span data-stu-id="cda2d-145">Setting the MSGFLAG_READ flag marks a message as read, which does not necessarily indicate that the intended recipient has actually read the message.</span></span> 
  
<span data-ttu-id="cda2d-146">**SetReadFlags** 还管理读取报表的发送。</span><span class="sxs-lookup"><span data-stu-id="cda2d-146">**SetReadFlags** also manages the sending of read reports.</span></span> 
  
<span data-ttu-id="cda2d-147">不能为以下项更改读取标志：</span><span class="sxs-lookup"><span data-stu-id="cda2d-147">The read flag cannot be changed for the following:</span></span>
  
- <span data-ttu-id="cda2d-148">不存在的邮件。</span><span class="sxs-lookup"><span data-stu-id="cda2d-148">Messages that do not exist.</span></span>
    
- <span data-ttu-id="cda2d-149">已移动到其他位置的邮件。</span><span class="sxs-lookup"><span data-stu-id="cda2d-149">Messages that have been moved elsewhere.</span></span>
    
- <span data-ttu-id="cda2d-150">具有读/写权限打开的邮件。</span><span class="sxs-lookup"><span data-stu-id="cda2d-150">Messages that are open with read/write permission.</span></span>
    
- <span data-ttu-id="cda2d-151">当前提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="cda2d-151">Messages that are currently submitted.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="cda2d-152">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="cda2d-152">Notes to implementers</span></span>

<span data-ttu-id="cda2d-153">您可以决定不支持发送阅读报告和禁止显示阅读报告的请求。</span><span class="sxs-lookup"><span data-stu-id="cda2d-153">You can decide not to support the sending of read reports and the request to suppress read reports.</span></span> <span data-ttu-id="cda2d-154">为了避免隐藏读取报表，当调用 **setReadFlags** MAPI_E_NO_SUPPRESS  _ulFlags_ 参数中设置SUPPRESS_RECEIPT返回一个返回值。</span><span class="sxs-lookup"><span data-stu-id="cda2d-154">To avoid suppressing a read report, return MAPI_E_NO_SUPPRESS when **SetReadFlags** is called with SUPPRESS_RECEIPT set in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="cda2d-155">当  _lpMsgList_ 参数指向多个邮件时，请尽可能完全地执行每封邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="cda2d-155">When the  _lpMsgList_ parameter points to more than one message, perform the operation as completely as possible for each message.</span></span> <span data-ttu-id="cda2d-156">除非发生超出你的控制范围（如内存不足、磁盘空间不足或邮件存储损坏）发生的故障，否则不要提前停止操作。</span><span class="sxs-lookup"><span data-stu-id="cda2d-156">Do not stop the operation prematurely unless a failure occurs that is beyond your control, such as running out of memory, running out of disk space, or corruption in the message store.</span></span> 
  
<span data-ttu-id="cda2d-157">如果在  _ulFlags_ 参数中未设置任何标志，则以下规则适用：</span><span class="sxs-lookup"><span data-stu-id="cda2d-157">If none of the flags are set in the  _ulFlags_ parameter, the following rules apply:</span></span> 
  
- <span data-ttu-id="cda2d-158">如果MSGFLAG_READ，则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="cda2d-158">If MSGFLAG_READ is already set, do nothing.</span></span>
    
- <span data-ttu-id="cda2d-159">如果未MSGFLAG_READ，则立即设置它，如果设置了 PR_READ_RECEIPT_REQUESTED ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 发送任何挂起的已读报告。 </span><span class="sxs-lookup"><span data-stu-id="cda2d-159">If MSGFLAG_READ is not set, set it immediately and send any pending read reports if the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property is set.</span></span>
    
<span data-ttu-id="cda2d-160">设置 SUPPRESS_RECEIPT 标志时，以下规则适用：</span><span class="sxs-lookup"><span data-stu-id="cda2d-160">When the SUPPRESS_RECEIPT flag is set, the following rules apply:</span></span>
  
- <span data-ttu-id="cda2d-161">如果MSGFLAG_READ，则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="cda2d-161">If MSGFLAG_READ is already set, do nothing.</span></span> 
    
- <span data-ttu-id="cda2d-162">如果未MSGFLAG_READ，请设置它并取消任何挂起的已读报告。</span><span class="sxs-lookup"><span data-stu-id="cda2d-162">If MSGFLAG_READ is not set, set it and cancel any pending read reports.</span></span>
    
<span data-ttu-id="cda2d-163">设置 CLEAR_READ_FLAG 标记时，清除MSGFLAG_READ属性中的 PR_MESSAGE_FLAGS 标记，不要发送任何已读报告。</span><span class="sxs-lookup"><span data-stu-id="cda2d-163">When the CLEAR_READ_FLAG flag is set, clear the MSGFLAG_READ flag in each message's **PR_MESSAGE_FLAGS** property and do not send any read reports.</span></span> 
  
<span data-ttu-id="cda2d-164">设置GENERATE_RECEIPT_ONLY时，发送任何挂起的已读报告。</span><span class="sxs-lookup"><span data-stu-id="cda2d-164">When the GENERATE_RECEIPT_ONLY flag is set, send any pending read reports.</span></span> <span data-ttu-id="cda2d-165">不要设置或清除MSGFLAG_READ。</span><span class="sxs-lookup"><span data-stu-id="cda2d-165">Do not set or clear MSGFLAG_READ.</span></span>
  
<span data-ttu-id="cda2d-166">当设置 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志时，PR_READ_RECEIPT_REQUESTED设置为 FALSE，并且不要发送读取报告。</span><span class="sxs-lookup"><span data-stu-id="cda2d-166">When both the SUPPRESS_RECEIPT and GENERATE_RECEIPT_ONLY flags are set, set **PR_READ_RECEIPT_REQUESTED** to FALSE if it is set and do not send a read report.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="cda2d-167">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="cda2d-167">Notes to callers</span></span>

<span data-ttu-id="cda2d-168">预计以下情况下会返回这些值。</span><span class="sxs-lookup"><span data-stu-id="cda2d-168">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="cda2d-169">**Condition**</span><span class="sxs-lookup"><span data-stu-id="cda2d-169">**Condition**</span></span>|<span data-ttu-id="cda2d-170">**返回值**</span><span class="sxs-lookup"><span data-stu-id="cda2d-170">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cda2d-171">**SetReadFlags** 已成功处理每封邮件。</span><span class="sxs-lookup"><span data-stu-id="cda2d-171">**SetReadFlags** has successfully processed every message.</span></span>  <br/> |<span data-ttu-id="cda2d-172">S_OK</span><span class="sxs-lookup"><span data-stu-id="cda2d-172">S_OK</span></span>  <br/> |
|<span data-ttu-id="cda2d-173">**SetReadFlags** 无法成功处理每封邮件。</span><span class="sxs-lookup"><span data-stu-id="cda2d-173">**SetReadFlags** was unable to successfully process every message.</span></span>  <br/> |<span data-ttu-id="cda2d-174">MAPI_W_PARTIAL_COMPLETION 或 MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="cda2d-174">MAPI_W_PARTIAL_COMPLETION or MAPI_E_NOT_FOUND</span></span>  <br/> |
|<span data-ttu-id="cda2d-175">**SetReadFlags** 无法完成。</span><span class="sxs-lookup"><span data-stu-id="cda2d-175">**SetReadFlags** was unable to complete.</span></span>  <br/> |<span data-ttu-id="cda2d-176">任何错误值（MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="cda2d-176">Any error value except MAPI_E_NOT_FOUND</span></span>  <br/> |
   
<span data-ttu-id="cda2d-177">当 **SetReadFlags** 无法完成时，不要假定未完成任何工作。</span><span class="sxs-lookup"><span data-stu-id="cda2d-177">When **SetReadFlags** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="cda2d-178">**SetReadFlags** 可能能够在遇到错误之前为一个或多个邮件设置或清除 MSGFLAG_READ 标志。</span><span class="sxs-lookup"><span data-stu-id="cda2d-178">**SetReadFlags** might have been able to set or clear the MSGFLAG_READ flag for one or more of the messages before encountering the error.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="cda2d-179">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="cda2d-179">MFCMAPI reference</span></span>

<span data-ttu-id="cda2d-180">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="cda2d-180">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="cda2d-181">**文件**</span><span class="sxs-lookup"><span data-stu-id="cda2d-181">**File**</span></span>|<span data-ttu-id="cda2d-182">**函数**</span><span class="sxs-lookup"><span data-stu-id="cda2d-182">**Function**</span></span>|<span data-ttu-id="cda2d-183">**备注**</span><span class="sxs-lookup"><span data-stu-id="cda2d-183">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cda2d-184">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="cda2d-184">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="cda2d-185">CFolderDlg：：OnSetReadFlag</span><span class="sxs-lookup"><span data-stu-id="cda2d-185">CFolderDlg::OnSetReadFlag</span></span>  <br/> |<span data-ttu-id="cda2d-186">MFCMAPI 使用 **IMAPIFolder：：SetReadFlags** 方法手动设置指定邮件的读取状态。</span><span class="sxs-lookup"><span data-stu-id="cda2d-186">MFCMAPI uses the **IMAPIFolder::SetReadFlags** method to manually set the read status on the specified messages.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cda2d-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cda2d-187">See also</span></span>

- [<span data-ttu-id="cda2d-188">ENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="cda2d-188">ENTRYLIST</span></span>](entrylist.md) 
- [<span data-ttu-id="cda2d-189">IMessage::SetReadFlag</span><span class="sxs-lookup"><span data-stu-id="cda2d-189">IMessage::SetReadFlag</span></span>](imessage-setreadflag.md)  
- [<span data-ttu-id="cda2d-190">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="cda2d-190">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)  
- [<span data-ttu-id="cda2d-191">PidTagReadReceiptRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="cda2d-191">PidTagReadReceiptRequested Canonical Property</span></span>](pidtagreadreceiptrequested-canonical-property.md)  
- [<span data-ttu-id="cda2d-192">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="cda2d-192">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
- [<span data-ttu-id="cda2d-193">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="cda2d-193">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)  
- [<span data-ttu-id="cda2d-194">使用宏处理错误</span><span class="sxs-lookup"><span data-stu-id="cda2d-194">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

