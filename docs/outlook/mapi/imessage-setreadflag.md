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
# <a name="imessagesetreadflag"></a><span data-ttu-id="c38a5-103">IMessage::SetReadFlag</span><span class="sxs-lookup"><span data-stu-id="c38a5-103">IMessage::SetReadFlag</span></span>

<span data-ttu-id="c38a5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c38a5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c38a5-105">设置或清除 MSGFLAG_READ [PidTagMessageFlags PR_MESSAGE_FLAGS (PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的"已读"标志，并管理已读报表的发送。 </span><span class="sxs-lookup"><span data-stu-id="c38a5-105">Sets or clears the MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message and manages the sending of read reports.</span></span>
  
```cpp
HRESULT SetReadFlag(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="c38a5-106">参数</span><span class="sxs-lookup"><span data-stu-id="c38a5-106">Parameters</span></span>

<span data-ttu-id="c38a5-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c38a5-107">_ulFlags_</span></span>
  
> <span data-ttu-id="c38a5-108">[in]控制邮件的读取标志设置的位掩码，即邮件的 MSGFLAG_READ 标志在其 **PR_MESSAGE_FLAGS** 属性中和读取报告处理。</span><span class="sxs-lookup"><span data-stu-id="c38a5-108">[in] Bitmask of flags that controls the setting of a message's read flag that is, the message's MSGFLAG_READ flag in its **PR_MESSAGE_FLAGS** property and the processing of read reports.</span></span> <span data-ttu-id="c38a5-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="c38a5-109">The following flags can be set:</span></span> 
    
  - <span data-ttu-id="c38a5-110">CLEAR_READ_FLAG：MSGFLAG_READ中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送任何读取报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-110">CLEAR_READ_FLAG: The MSGFLAG_READ flag should be cleared in **PR_MESSAGE_FLAGS** and no read report should be sent.</span></span> 
      
  - <span data-ttu-id="c38a5-111">CLEAR_NRN_PENDING：MSGFLAG_NRN_PENDING中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送未读报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-111">CLEAR_NRN_PENDING: The MSGFLAG_NRN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and a non-read report should not be sent.</span></span> 
      
  - <span data-ttu-id="c38a5-112">CLEAR_RN_PENDING：MSGFLAG_RN_PENDING中应清除 **PR_MESSAGE_FLAGS，并且** 不应发送任何读取报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-112">CLEAR_RN_PENDING: The MSGFLAG_RN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and no read report should be sent.</span></span> 
      
  - <span data-ttu-id="c38a5-113">GENERATE_RECEIPT_ONLY：如果一个已读报告挂起，则应该发送一个已读报告，但该读取报告MSGFLAG_READ状态。</span><span class="sxs-lookup"><span data-stu-id="c38a5-113">GENERATE_RECEIPT_ONLY: A read report should be sent if one is pending, but there should be no change in the state of the MSGFLAG_READ flag.</span></span>
      
  - <span data-ttu-id="c38a5-114">MAPI_DEFERRED_ERRORS：允许在操作完成之前成功返回 **SetReadFlag。**</span><span class="sxs-lookup"><span data-stu-id="c38a5-114">MAPI_DEFERRED_ERRORS: Allows **SetReadFlag** to return successfully, possibly before the operation has completed.</span></span> 
      
  - <span data-ttu-id="c38a5-115">SUPPRESS_RECEIPT：如果已请求读取报告，并且此调用将邮件的状态从"未读"改为"已读"，应取消挂起的阅读报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-115">SUPPRESS_RECEIPT: A pending read report should be canceled if a read report had been requested and this call changes the state of the message from unread to read.</span></span> <span data-ttu-id="c38a5-116">如果此调用不更改邮件的状态，则邮件存储提供程序可以忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="c38a5-116">If this call does not change the state of the message, the message store provider can ignore this flag.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c38a5-117">返回值</span><span class="sxs-lookup"><span data-stu-id="c38a5-117">Return value</span></span>

<span data-ttu-id="c38a5-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c38a5-118">S_OK</span></span> 
  
> <span data-ttu-id="c38a5-119">已成功设置或清除邮件的读取标志。</span><span class="sxs-lookup"><span data-stu-id="c38a5-119">The message's read flag has been successfully set or cleared.</span></span>
    
<span data-ttu-id="c38a5-120">MAPI_E_NO_SUPPRESS</span><span class="sxs-lookup"><span data-stu-id="c38a5-120">MAPI_E_NO_SUPPRESS</span></span> 
  
> <span data-ttu-id="c38a5-121">邮件存储提供程序不支持禁止读取报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-121">The message store provider does not support the suppression of read reports.</span></span>
    
<span data-ttu-id="c38a5-122">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="c38a5-122">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="c38a5-123">在  _ulFlags_ 参数中设置以下标志组合之一：</span><span class="sxs-lookup"><span data-stu-id="c38a5-123">One of the following combinations of flags is set in the  _ulFlags_ parameter:</span></span> 
    
   - <span data-ttu-id="c38a5-124">SUPPRESS_RECEIPT |CLEAR_READ_FLAG</span><span class="sxs-lookup"><span data-stu-id="c38a5-124">SUPPRESS_RECEIPT | CLEAR_READ_FLAG</span></span> 
    
   - <span data-ttu-id="c38a5-125">SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="c38a5-125">SUPPRESS_RECEIPT | CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
   - <span data-ttu-id="c38a5-126">CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="c38a5-126">CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c38a5-127">备注</span><span class="sxs-lookup"><span data-stu-id="c38a5-127">Remarks</span></span>

<span data-ttu-id="c38a5-128">**IMessage：：SetReadFlag** 方法设置或清除 PR_MESSAGE_FLAGS 属性中的邮件 MSGFLAG_READ 标志 **，** 并调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)以保存邮件。</span><span class="sxs-lookup"><span data-stu-id="c38a5-128">The **IMessage::SetReadFlag** method sets or clears the message's MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** property and calls [IMAPIProp::SaveChanges](imapiprop-savechanges.md) to save the message.</span></span> <span data-ttu-id="c38a5-129">设置MSGFLAG_READ标记将邮件标记为已阅读，这不一定表示目标收件人实际上已阅读该邮件。</span><span class="sxs-lookup"><span data-stu-id="c38a5-129">Setting the MSGFLAG_READ flag marks a message as having been read, which does not necessarily indicate that the intended recipient has actually read the message.</span></span> 
  
<span data-ttu-id="c38a5-130">**SetReadFlags** 还管理读取报表的发送。</span><span class="sxs-lookup"><span data-stu-id="c38a5-130">**SetReadFlags** also manages the sending of read reports.</span></span> <span data-ttu-id="c38a5-131">仅在发件人已请求一份阅读报告时发送。</span><span class="sxs-lookup"><span data-stu-id="c38a5-131">A read report is sent only if the sender has requested one.</span></span> 
  
<span data-ttu-id="c38a5-132">不能为以下项目更改读取标志：</span><span class="sxs-lookup"><span data-stu-id="c38a5-132">The read flag cannot be altered for:</span></span>
  
- <span data-ttu-id="c38a5-133">不存在的邮件。</span><span class="sxs-lookup"><span data-stu-id="c38a5-133">Messages that do not exist.</span></span>
    
- <span data-ttu-id="c38a5-134">已移动到其他位置的邮件。</span><span class="sxs-lookup"><span data-stu-id="c38a5-134">Messages that have been moved elsewhere.</span></span>
    
- <span data-ttu-id="c38a5-135">具有读/写权限打开的邮件。</span><span class="sxs-lookup"><span data-stu-id="c38a5-135">Messages that are open with read/write permission.</span></span>
    
- <span data-ttu-id="c38a5-136">当前提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="c38a5-136">Messages that are currently submitted.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="c38a5-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c38a5-137">Notes to callers</span></span>

<span data-ttu-id="c38a5-138">如果在  _ulFlags_ 参数中未设置任何标志，则以下规则适用：</span><span class="sxs-lookup"><span data-stu-id="c38a5-138">If none of the flags are set in the  _ulFlags_ parameter, the following rules apply:</span></span> 
  
- <span data-ttu-id="c38a5-139">如果MSGFLAG_READ，则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c38a5-139">If MSGFLAG_READ is already set, do nothing.</span></span>
    
- <span data-ttu-id="c38a5-140">如果未MSGFLAG_READ，请设置此属性，如果设置了 **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 发送任何挂起的已读报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-140">If MSGFLAG_READ is not set, set it and send any pending read reports if the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property is set.</span></span>
    
<span data-ttu-id="c38a5-141">如果设置了 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志，PR_READ_RECEIPT_REQUESTED位（如果已设置）并且不应发送读取报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-141">If both the SUPPRESS_RECEIPT and GENERATE_RECEIPT_ONLY flags are set, the PR_READ_RECEIPT_REQUESTED bit, if set, should be cleared and a read report should not be sent.</span></span>
  
<span data-ttu-id="c38a5-142">设置SUPPRESS_RECEIPT标记时：</span><span class="sxs-lookup"><span data-stu-id="c38a5-142">When the SUPPRESS_RECEIPT flag is set:</span></span>
  
- <span data-ttu-id="c38a5-143">如果MSGFLAG_READ，则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c38a5-143">If MSGFLAG_READ is already set, do nothing.</span></span> 
    
- <span data-ttu-id="c38a5-144">如果未MSGFLAG_READ，请设置它并取消任何挂起的已读报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-144">If MSGFLAG_READ is not set, set it and cancel any pending read reports.</span></span>
    
<span data-ttu-id="c38a5-145">设置 CLEAR_READ_FLAG 标记时，清除MSGFLAG_READ属性中的 PR_MESSAGE_FLAGS 标记，不要发送任何已读报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-145">When the CLEAR_READ_FLAG flag is set, clear the MSGFLAG_READ flag in each message's **PR_MESSAGE_FLAGS** property and do not send any read reports.</span></span> 
  
<span data-ttu-id="c38a5-146">设置GENERATE_RECEIPT_ONLY时，发送任何挂起的已读报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-146">When the GENERATE_RECEIPT_ONLY flag is set, send any pending read reports.</span></span> <span data-ttu-id="c38a5-147">不要设置或清除MSGFLAG_READ。</span><span class="sxs-lookup"><span data-stu-id="c38a5-147">Do not set or clear MSGFLAG_READ.</span></span>
  
<span data-ttu-id="c38a5-148">设置 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志时，PR_READ_RECEIPT_REQUESTED属性设置为 FALSE（如果已设置）并且不发送读取报告。</span><span class="sxs-lookup"><span data-stu-id="c38a5-148">When both the SUPPRESS_RECEIPT and GENERATE_RECEIPT_ONLY flags are set, set the PR_READ_RECEIPT_REQUESTED property to FALSE if it is set and do not send a read report.</span></span>
  
<span data-ttu-id="c38a5-149">您可以通过禁止在特定条件下生成读取报告来优化报告行为。</span><span class="sxs-lookup"><span data-stu-id="c38a5-149">You can optimize report behavior by suppressing the generation of read reports under certain conditions.</span></span> <span data-ttu-id="c38a5-150">但是，如果您不支持抑制报告，并且客户端调用 **SetReadFlag** 时设置了 SUPPRESS_RECEIPT，则返回 MAPI_E_NO_SUPPRESS。</span><span class="sxs-lookup"><span data-stu-id="c38a5-150">However, if you do not support the suppression of reports and a client calls **SetReadFlag** with the SUPPRESS_RECEIPT flag set, return MAPI_E_NO_SUPPRESS.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c38a5-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c38a5-151">MFCMAPI reference</span></span>

<span data-ttu-id="c38a5-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c38a5-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c38a5-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="c38a5-153">**File**</span></span>|<span data-ttu-id="c38a5-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="c38a5-154">**Function**</span></span>|<span data-ttu-id="c38a5-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="c38a5-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c38a5-156">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="c38a5-156">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="c38a5-157">CFolderDlg：：OnSetReadFlag</span><span class="sxs-lookup"><span data-stu-id="c38a5-157">CFolderDlg::OnSetReadFlag</span></span>  <br/> |<span data-ttu-id="c38a5-158">MFCMAPI 使用 **IMessage：：SetReadFlag** 方法在所选邮件上设置读取标志。</span><span class="sxs-lookup"><span data-stu-id="c38a5-158">MFCMAPI uses the **IMessage::SetReadFlag** method to set read flags on selected messages.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c38a5-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c38a5-159">See also</span></span>

- [<span data-ttu-id="c38a5-160">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="c38a5-160">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)  
- [<span data-ttu-id="c38a5-161">IMAPIFolder::SetReadFlags</span><span class="sxs-lookup"><span data-stu-id="c38a5-161">IMAPIFolder::SetReadFlags</span></span>](imapifolder-setreadflags.md)  
- [<span data-ttu-id="c38a5-162">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="c38a5-162">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)  
- [<span data-ttu-id="c38a5-163">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="c38a5-163">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md) 
- [<span data-ttu-id="c38a5-164">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="c38a5-164">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md) 
- [<span data-ttu-id="c38a5-165">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c38a5-165">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)
- [<span data-ttu-id="c38a5-166">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c38a5-166">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

