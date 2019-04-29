---
title: IMessageSetReadFlag
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.SetReadFlag
api_type:
- COM
ms.assetid: 2d02ebf6-bb8b-42bb-9bd0-870dbae9aeb4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 874dba4aa18190792a52e29064155f5afa0ef44d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439868"
---
# <a name="imessagesetreadflag"></a><span data-ttu-id="d4702-103">IMessage::SetReadFlag</span><span class="sxs-lookup"><span data-stu-id="d4702-103">IMessage::SetReadFlag</span></span>

<span data-ttu-id="d4702-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d4702-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d4702-105">设置或清除邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_READ 标记, 并管理阅读报告的发送。</span><span class="sxs-lookup"><span data-stu-id="d4702-105">Sets or clears the MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message and manages the sending of read reports.</span></span>
  
```cpp
HRESULT SetReadFlag(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="d4702-106">参数</span><span class="sxs-lookup"><span data-stu-id="d4702-106">Parameters</span></span>

<span data-ttu-id="d4702-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d4702-107">_ulFlags_</span></span>
  
> <span data-ttu-id="d4702-108">实时标志的位掩码, 用于控制邮件的阅读标志的设置, 即邮件的 MSGFLAG_READ 标记在其**PR_MESSAGE_FLAGS**属性和处理读取报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-108">[in] Bitmask of flags that controls the setting of a message's read flag that is, the message's MSGFLAG_READ flag in its **PR_MESSAGE_FLAGS** property and the processing of read reports.</span></span> <span data-ttu-id="d4702-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="d4702-109">The following flags can be set:</span></span> 
    
  - <span data-ttu-id="d4702-110">CLEAR_READ_FLAG: 应在**PR_MESSAGE_FLAGS**中清除 MSGFLAG_READ 标志, 并且不应发送任何读取报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-110">CLEAR_READ_FLAG: The MSGFLAG_READ flag should be cleared in **PR_MESSAGE_FLAGS** and no read report should be sent.</span></span> 
      
  - <span data-ttu-id="d4702-111">CLEAR_NRN_PENDING: 应在**PR_MESSAGE_FLAGS**中清除 MSGFLAG_NRN_PENDING 标志, 且不应发送不阅读的报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-111">CLEAR_NRN_PENDING: The MSGFLAG_NRN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and a non-read report should not be sent.</span></span> 
      
  - <span data-ttu-id="d4702-112">CLEAR_RN_PENDING: 应在**PR_MESSAGE_FLAGS**中清除 MSGFLAG_RN_PENDING 标志, 并且不应发送任何读取报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-112">CLEAR_RN_PENDING: The MSGFLAG_RN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and no read report should be sent.</span></span> 
      
  - <span data-ttu-id="d4702-113">GENERATE_RECEIPT_ONLY: 应在一个已挂起的情况下发送已读报告, 但在 MSGFLAG_READ 标志的状态中不应进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="d4702-113">GENERATE_RECEIPT_ONLY: A read report should be sent if one is pending, but there should be no change in the state of the MSGFLAG_READ flag.</span></span>
      
  - <span data-ttu-id="d4702-114">MAPI_DEFERRED_ERRORS: 允许**SetReadFlag**成功返回, 可能在操作完成前。</span><span class="sxs-lookup"><span data-stu-id="d4702-114">MAPI_DEFERRED_ERRORS: Allows **SetReadFlag** to return successfully, possibly before the operation has completed.</span></span> 
      
  - <span data-ttu-id="d4702-115">SUPPRESS_RECEIPT: 如果已请求读取报告且此呼叫将邮件的状态从 "未读" 更改为 "已读", 则应取消挂起的读取报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-115">SUPPRESS_RECEIPT: A pending read report should be canceled if a read report had been requested and this call changes the state of the message from unread to read.</span></span> <span data-ttu-id="d4702-116">如果此调用不更改邮件的状态, 则邮件存储提供程序可以忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="d4702-116">If this call does not change the state of the message, the message store provider can ignore this flag.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d4702-117">返回值</span><span class="sxs-lookup"><span data-stu-id="d4702-117">Return value</span></span>

<span data-ttu-id="d4702-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4702-118">S_OK</span></span> 
  
> <span data-ttu-id="d4702-119">已成功设置或清除邮件的读取标志。</span><span class="sxs-lookup"><span data-stu-id="d4702-119">The message's read flag has been successfully set or cleared.</span></span>
    
<span data-ttu-id="d4702-120">MAPI_E_NO_SUPPRESS</span><span class="sxs-lookup"><span data-stu-id="d4702-120">MAPI_E_NO_SUPPRESS</span></span> 
  
> <span data-ttu-id="d4702-121">邮件存储区提供程序不支持禁止显示已读报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-121">The message store provider does not support the suppression of read reports.</span></span>
    
<span data-ttu-id="d4702-122">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="d4702-122">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="d4702-123">在_ulFlags_参数中设置以下标志组合中的一种:</span><span class="sxs-lookup"><span data-stu-id="d4702-123">One of the following combinations of flags is set in the  _ulFlags_ parameter:</span></span> 
    
   - <span data-ttu-id="d4702-124">SUPPRESS_RECEIPT |CLEAR_READ_FLAG</span><span class="sxs-lookup"><span data-stu-id="d4702-124">SUPPRESS_RECEIPT | CLEAR_READ_FLAG</span></span> 
    
   - <span data-ttu-id="d4702-125">SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="d4702-125">SUPPRESS_RECEIPT | CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
   - <span data-ttu-id="d4702-126">CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="d4702-126">CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d4702-127">说明</span><span class="sxs-lookup"><span data-stu-id="d4702-127">Remarks</span></span>

<span data-ttu-id="d4702-128">**IMessage:: SetReadFlag**方法设置或清除**PR_MESSAGE_FLAGS**属性中的邮件的 MSGFLAG_READ 标记, 并调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)以保存该邮件。</span><span class="sxs-lookup"><span data-stu-id="d4702-128">The **IMessage::SetReadFlag** method sets or clears the message's MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** property and calls [IMAPIProp::SaveChanges](imapiprop-savechanges.md) to save the message.</span></span> <span data-ttu-id="d4702-129">设置 MSGFLAG_READ 标志将邮件标记为已阅读, 这并不一定表明预期收件人确实已阅读邮件。</span><span class="sxs-lookup"><span data-stu-id="d4702-129">Setting the MSGFLAG_READ flag marks a message as having been read, which does not necessarily indicate that the intended recipient has actually read the message.</span></span> 
  
<span data-ttu-id="d4702-130">**SetReadFlags**还管理阅读报告的发送。</span><span class="sxs-lookup"><span data-stu-id="d4702-130">**SetReadFlags** also manages the sending of read reports.</span></span> <span data-ttu-id="d4702-131">仅当发件人请求了一个阅读报告时, 才会发送该报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-131">A read report is sent only if the sender has requested one.</span></span> 
  
<span data-ttu-id="d4702-132">无法为以下项更改读取标志:</span><span class="sxs-lookup"><span data-stu-id="d4702-132">The read flag cannot be altered for:</span></span>
  
- <span data-ttu-id="d4702-133">不存在的邮件。</span><span class="sxs-lookup"><span data-stu-id="d4702-133">Messages that do not exist.</span></span>
    
- <span data-ttu-id="d4702-134">已移动到其他位置的邮件。</span><span class="sxs-lookup"><span data-stu-id="d4702-134">Messages that have been moved elsewhere.</span></span>
    
- <span data-ttu-id="d4702-135">以读/写权限打开的邮件。</span><span class="sxs-lookup"><span data-stu-id="d4702-135">Messages that are open with read/write permission.</span></span>
    
- <span data-ttu-id="d4702-136">当前已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="d4702-136">Messages that are currently submitted.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="d4702-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d4702-137">Notes to callers</span></span>

<span data-ttu-id="d4702-138">如果未在_ulFlags_参数中设置任何标志, 则以下规则适用:</span><span class="sxs-lookup"><span data-stu-id="d4702-138">If none of the flags are set in the  _ulFlags_ parameter, the following rules apply:</span></span> 
  
- <span data-ttu-id="d4702-139">如果已设置 MSGFLAG_READ, 则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d4702-139">If MSGFLAG_READ is already set, do nothing.</span></span>
    
- <span data-ttu-id="d4702-140">如果未设置 MSGFLAG_READ, 则设置它并发送任何挂起的读取报告 (如果设置了**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性)。</span><span class="sxs-lookup"><span data-stu-id="d4702-140">If MSGFLAG_READ is not set, set it and send any pending read reports if the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property is set.</span></span>
    
<span data-ttu-id="d4702-141">如果同时设置了 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志, 则应清除 PR_READ_RECEIPT_REQUESTED 位, 如果设置, 则不应发送读取报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-141">If both the SUPPRESS_RECEIPT and GENERATE_RECEIPT_ONLY flags are set, the PR_READ_RECEIPT_REQUESTED bit, if set, should be cleared and a read report should not be sent.</span></span>
  
<span data-ttu-id="d4702-142">设置 SUPPRESS_RECEIPT 标志时:</span><span class="sxs-lookup"><span data-stu-id="d4702-142">When the SUPPRESS_RECEIPT flag is set:</span></span>
  
- <span data-ttu-id="d4702-143">如果已设置 MSGFLAG_READ, 则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d4702-143">If MSGFLAG_READ is already set, do nothing.</span></span> 
    
- <span data-ttu-id="d4702-144">如果未设置 MSGFLAG_READ, 请将其设置并取消任何待执行的已读报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-144">If MSGFLAG_READ is not set, set it and cancel any pending read reports.</span></span>
    
<span data-ttu-id="d4702-145">设置 CLEAR_READ_FLAG 标志后, 清除每个邮件的**PR_MESSAGE_FLAGS**属性中的 MSGFLAG_READ 标记, 而不发送任何已读报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-145">When the CLEAR_READ_FLAG flag is set, clear the MSGFLAG_READ flag in each message's **PR_MESSAGE_FLAGS** property and do not send any read reports.</span></span> 
  
<span data-ttu-id="d4702-146">设置 GENERATE_RECEIPT_ONLY 标志后, 发送任何挂起的读取报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-146">When the GENERATE_RECEIPT_ONLY flag is set, send any pending read reports.</span></span> <span data-ttu-id="d4702-147">请勿设置或清除 MSGFLAG_READ。</span><span class="sxs-lookup"><span data-stu-id="d4702-147">Do not set or clear MSGFLAG_READ.</span></span>
  
<span data-ttu-id="d4702-148">如果设置了 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志, 则将 PR_READ_RECEIPT_REQUESTED 属性设置为 FALSE, 如果设置了该属性, 但不发送已读报告。</span><span class="sxs-lookup"><span data-stu-id="d4702-148">When both the SUPPRESS_RECEIPT and GENERATE_RECEIPT_ONLY flags are set, set the PR_READ_RECEIPT_REQUESTED property to FALSE if it is set and do not send a read report.</span></span>
  
<span data-ttu-id="d4702-149">您可以通过在特定条件下禁止生成阅读报告来优化报告行为。</span><span class="sxs-lookup"><span data-stu-id="d4702-149">You can optimize report behavior by suppressing the generation of read reports under certain conditions.</span></span> <span data-ttu-id="d4702-150">但是, 如果您不支持禁止显示报告和客户端调用**SetReadFlag**并设置 SUPPRESS_RECEIPT 标志, 则返回 MAPI_E_NO_SUPPRESS。</span><span class="sxs-lookup"><span data-stu-id="d4702-150">However, if you do not support the suppression of reports and a client calls **SetReadFlag** with the SUPPRESS_RECEIPT flag set, return MAPI_E_NO_SUPPRESS.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="d4702-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="d4702-151">MFCMAPI reference</span></span>

<span data-ttu-id="d4702-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d4702-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d4702-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="d4702-153">**File**</span></span>|<span data-ttu-id="d4702-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="d4702-154">**Function**</span></span>|<span data-ttu-id="d4702-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="d4702-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4702-156">FolderDlg</span><span class="sxs-lookup"><span data-stu-id="d4702-156">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="d4702-157">CFolderDlg:: OnSetReadFlag</span><span class="sxs-lookup"><span data-stu-id="d4702-157">CFolderDlg::OnSetReadFlag</span></span>  <br/> |<span data-ttu-id="d4702-158">MFCMAPI 使用**IMessage:: SetReadFlag**方法来设置所选邮件上的读取标志。</span><span class="sxs-lookup"><span data-stu-id="d4702-158">MFCMAPI uses the **IMessage::SetReadFlag** method to set read flags on selected messages.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d4702-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4702-159">See also</span></span>

- [<span data-ttu-id="d4702-160">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="d4702-160">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)  
- [<span data-ttu-id="d4702-161">IMAPIFolder::SetReadFlags</span><span class="sxs-lookup"><span data-stu-id="d4702-161">IMAPIFolder::SetReadFlags</span></span>](imapifolder-setreadflags.md)  
- [<span data-ttu-id="d4702-162">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="d4702-162">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)  
- [<span data-ttu-id="d4702-163">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="d4702-163">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md) 
- [<span data-ttu-id="d4702-164">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="d4702-164">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md) 
- [<span data-ttu-id="d4702-165">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d4702-165">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)
- [<span data-ttu-id="d4702-166">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d4702-166">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

