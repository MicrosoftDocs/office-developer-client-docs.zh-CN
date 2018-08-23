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
ms.openlocfilehash: 40815f1df597a8fb1fd8adef3dcc09323e946d30
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592960"
---
# <a name="imessagesetreadflag"></a><span data-ttu-id="27d70-103">IMessage::SetReadFlag</span><span class="sxs-lookup"><span data-stu-id="27d70-103">IMessage::SetReadFlag</span></span>

<span data-ttu-id="27d70-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27d70-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27d70-105">设置或清除 MSGFLAG_READ 标志邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中并管理阅读报告的发送。</span><span class="sxs-lookup"><span data-stu-id="27d70-105">Sets or clears the MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the message and manages the sending of read reports.</span></span>
  
```cpp
HRESULT SetReadFlag(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="27d70-106">参数</span><span class="sxs-lookup"><span data-stu-id="27d70-106">Parameters</span></span>

<span data-ttu-id="27d70-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="27d70-107">_ulFlags_</span></span>
  
> <span data-ttu-id="27d70-108">[in]控制的消息的读取设置的标志位掩码，即标记其**PR_MESSAGE_FLAGS**属性和处理阅读报告中的邮件的 MSGFLAG_READ 标志。</span><span class="sxs-lookup"><span data-stu-id="27d70-108">[in] Bitmask of flags that controls the setting of a message's read flag that is, the message's MSGFLAG_READ flag in its **PR_MESSAGE_FLAGS** property and the processing of read reports.</span></span> <span data-ttu-id="27d70-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="27d70-109">The following flags can be set:</span></span> 
    
  - <span data-ttu-id="27d70-110">CLEAR_READ_FLAG： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_READ 标志，但应发送未读取的报告。</span><span class="sxs-lookup"><span data-stu-id="27d70-110">CLEAR_READ_FLAG: The MSGFLAG_READ flag should be cleared in **PR_MESSAGE_FLAGS** and no read report should be sent.</span></span> 
      
  - <span data-ttu-id="27d70-111">CLEAR_NRN_PENDING： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_NRN_PENDING 标志，不应发送未读报告。</span><span class="sxs-lookup"><span data-stu-id="27d70-111">CLEAR_NRN_PENDING: The MSGFLAG_NRN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and a non-read report should not be sent.</span></span> 
      
  - <span data-ttu-id="27d70-112">CLEAR_RN_PENDING： 应**PR_MESSAGE_FLAGS**中清除 MSGFLAG_RN_PENDING 标志，但应发送未读取的报告。</span><span class="sxs-lookup"><span data-stu-id="27d70-112">CLEAR_RN_PENDING: The MSGFLAG_RN_PENDING flag should be cleared in **PR_MESSAGE_FLAGS** and no read report should be sent.</span></span> 
      
  - <span data-ttu-id="27d70-113">GENERATE_RECEIPT_ONLY： 应发送读取的报表，如果一个处于挂起状态，但不应 MSGFLAG_READ 标志的状态发生任何变化。</span><span class="sxs-lookup"><span data-stu-id="27d70-113">GENERATE_RECEIPT_ONLY: A read report should be sent if one is pending, but there should be no change in the state of the MSGFLAG_READ flag.</span></span>
      
  - <span data-ttu-id="27d70-114">MAPI_DEFERRED_ERRORS： 允许**SetReadFlag**返回成功，原因可能是完成此操作之前。</span><span class="sxs-lookup"><span data-stu-id="27d70-114">MAPI_DEFERRED_ERRORS: Allows **SetReadFlag** to return successfully, possibly before the operation has completed.</span></span> 
      
  - <span data-ttu-id="27d70-115">SUPPRESS_RECEIPT： 应取消挂起的阅读的报告，如果阅读的报告已被请求，并且此呼叫将从未读读取更改邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="27d70-115">SUPPRESS_RECEIPT: A pending read report should be canceled if a read report had been requested and this call changes the state of the message from unread to read.</span></span> <span data-ttu-id="27d70-116">如果此呼叫不会更改邮件的状态，消息存储提供程序可以忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="27d70-116">If this call does not change the state of the message, the message store provider can ignore this flag.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="27d70-117">返回值</span><span class="sxs-lookup"><span data-stu-id="27d70-117">Return value</span></span>

<span data-ttu-id="27d70-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="27d70-118">S_OK</span></span> 
  
> <span data-ttu-id="27d70-119">已成功设置或清除邮件的阅读的标志。</span><span class="sxs-lookup"><span data-stu-id="27d70-119">The message's read flag has been successfully set or cleared.</span></span>
    
<span data-ttu-id="27d70-120">MAPI_E_NO_SUPPRESS</span><span class="sxs-lookup"><span data-stu-id="27d70-120">MAPI_E_NO_SUPPRESS</span></span> 
  
> <span data-ttu-id="27d70-121">消息存储提供程序不支持阅读报告的禁止显示。</span><span class="sxs-lookup"><span data-stu-id="27d70-121">The message store provider does not support the suppression of read reports.</span></span>
    
<span data-ttu-id="27d70-122">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="27d70-122">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="27d70-123">_UlFlags_参数中设置以下标志的组合之一：</span><span class="sxs-lookup"><span data-stu-id="27d70-123">One of the following combinations of flags is set in the  _ulFlags_ parameter:</span></span> 
    
   - <span data-ttu-id="27d70-124">SUPPRESS_RECEIPT |CLEAR_READ_FLAG</span><span class="sxs-lookup"><span data-stu-id="27d70-124">SUPPRESS_RECEIPT | CLEAR_READ_FLAG</span></span> 
    
   - <span data-ttu-id="27d70-125">SUPPRESS_RECEIPT |CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="27d70-125">SUPPRESS_RECEIPT | CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
   - <span data-ttu-id="27d70-126">CLEAR_READ_FLAG |GENERATE_RECEIPT_ONLY</span><span class="sxs-lookup"><span data-stu-id="27d70-126">CLEAR_READ_FLAG | GENERATE_RECEIPT_ONLY</span></span>
    
## <a name="remarks"></a><span data-ttu-id="27d70-127">注解</span><span class="sxs-lookup"><span data-stu-id="27d70-127">Remarks</span></span>

<span data-ttu-id="27d70-128">**IMessage::SetReadFlag**方法设置或清除**PR_MESSAGE_FLAGS**属性和呼叫[IMAPIProp::SaveChanges](imapiprop-savechanges.md)保存邮件中的消息的 MSGFLAG_READ 标志。</span><span class="sxs-lookup"><span data-stu-id="27d70-128">The **IMessage::SetReadFlag** method sets or clears the message's MSGFLAG_READ flag in the **PR_MESSAGE_FLAGS** property and calls [IMAPIProp::SaveChanges](imapiprop-savechanges.md) to save the message.</span></span> <span data-ttu-id="27d70-129">设置 MSGFLAG_READ 标志将邮件标记为已读，其中不一定表示预期接收人已实际阅读消息。</span><span class="sxs-lookup"><span data-stu-id="27d70-129">Setting the MSGFLAG_READ flag marks a message as having been read, which does not necessarily indicate that the intended recipient has actually read the message.</span></span> 
  
<span data-ttu-id="27d70-130">**SetReadFlags**还管理阅读报告的发送。</span><span class="sxs-lookup"><span data-stu-id="27d70-130">**SetReadFlags** also manages the sending of read reports.</span></span> <span data-ttu-id="27d70-131">仅当发件人已请求一个发送读取的报表。</span><span class="sxs-lookup"><span data-stu-id="27d70-131">A read report is sent only if the sender has requested one.</span></span> 
  
<span data-ttu-id="27d70-132">读取标志不能更改为：</span><span class="sxs-lookup"><span data-stu-id="27d70-132">The read flag cannot be altered for:</span></span>
  
- <span data-ttu-id="27d70-133">不存在的邮件。</span><span class="sxs-lookup"><span data-stu-id="27d70-133">Messages that do not exist.</span></span>
    
- <span data-ttu-id="27d70-134">邮件已移动至其他位置。</span><span class="sxs-lookup"><span data-stu-id="27d70-134">Messages that have been moved elsewhere.</span></span>
    
- <span data-ttu-id="27d70-135">打开具有读/写权限的邮件。</span><span class="sxs-lookup"><span data-stu-id="27d70-135">Messages that are open with read/write permission.</span></span>
    
- <span data-ttu-id="27d70-136">当前提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="27d70-136">Messages that are currently submitted.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="27d70-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="27d70-137">Notes to callers</span></span>

<span data-ttu-id="27d70-138">如果无标志设置_ulFlags_参数中，下列规则适用：</span><span class="sxs-lookup"><span data-stu-id="27d70-138">If none of the flags are set in the  _ulFlags_ parameter, the following rules apply:</span></span> 
  
- <span data-ttu-id="27d70-139">如果已设置 MSGFLAG_READ，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="27d70-139">If MSGFLAG_READ is already set, do nothing.</span></span>
    
- <span data-ttu-id="27d70-140">如果未设置 MSGFLAG_READ，将其设置，并发送任何挂起的阅读报告如果**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性设置。</span><span class="sxs-lookup"><span data-stu-id="27d70-140">If MSGFLAG_READ is not set, set it and send any pending read reports if the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property is set.</span></span>
    
<span data-ttu-id="27d70-141">如果设置 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志，PR_READ_RECEIPT_REQUESTED 位，如果设置，应该被清除，不应发送读取的报表。</span><span class="sxs-lookup"><span data-stu-id="27d70-141">If both the SUPPRESS_RECEIPT and GENERATE_RECEIPT_ONLY flags are set, the PR_READ_RECEIPT_REQUESTED bit, if set, should be cleared and a read report should not be sent.</span></span>
  
<span data-ttu-id="27d70-142">当 SUPPRESS_RECEIPT 标志设置：</span><span class="sxs-lookup"><span data-stu-id="27d70-142">When the SUPPRESS_RECEIPT flag is set:</span></span>
  
- <span data-ttu-id="27d70-143">如果已设置 MSGFLAG_READ，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="27d70-143">If MSGFLAG_READ is already set, do nothing.</span></span> 
    
- <span data-ttu-id="27d70-144">如果未设置 MSGFLAG_READ，将其设置和取消任何挂起的阅读报告。</span><span class="sxs-lookup"><span data-stu-id="27d70-144">If MSGFLAG_READ is not set, set it and cancel any pending read reports.</span></span>
    
<span data-ttu-id="27d70-145">当设置 CLEAR_READ_FLAG 标志时，清除 MSGFLAG_READ 标志每条消息**PR_MESSAGE_FLAGS**属性中的并不发送任何阅读的报告。</span><span class="sxs-lookup"><span data-stu-id="27d70-145">When the CLEAR_READ_FLAG flag is set, clear the MSGFLAG_READ flag in each message's **PR_MESSAGE_FLAGS** property and do not send any read reports.</span></span> 
  
<span data-ttu-id="27d70-146">当设置 GENERATE_RECEIPT_ONLY 标志时，发送任何挂起的阅读的报告。</span><span class="sxs-lookup"><span data-stu-id="27d70-146">When the GENERATE_RECEIPT_ONLY flag is set, send any pending read reports.</span></span> <span data-ttu-id="27d70-147">执行操作未设置或清除 MSGFLAG_READ。</span><span class="sxs-lookup"><span data-stu-id="27d70-147">Do not set or clear MSGFLAG_READ.</span></span>
  
<span data-ttu-id="27d70-148">时设置的 SUPPRESS_RECEIPT 和 GENERATE_RECEIPT_ONLY 标志，PR_READ_RECEIPT_REQUESTED 属性设置为 FALSE 如果设置，但不发送读取的报表。</span><span class="sxs-lookup"><span data-stu-id="27d70-148">When both the SUPPRESS_RECEIPT and GENERATE_RECEIPT_ONLY flags are set, set the PR_READ_RECEIPT_REQUESTED property to FALSE if it is set and do not send a read report.</span></span>
  
<span data-ttu-id="27d70-149">您可以通过消除在某些情况下的阅读报告的生成优化报表行为。</span><span class="sxs-lookup"><span data-stu-id="27d70-149">You can optimize report behavior by suppressing the generation of read reports under certain conditions.</span></span> <span data-ttu-id="27d70-150">但是，如果您不支持报告的禁止显示设置了 SUPPRESS_RECEIPT 标志在客户端调用**SetReadFlag** ，返回 MAPI_E_NO_SUPPRESS。</span><span class="sxs-lookup"><span data-stu-id="27d70-150">However, if you do not support the suppression of reports and a client calls **SetReadFlag** with the SUPPRESS_RECEIPT flag set, return MAPI_E_NO_SUPPRESS.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="27d70-151">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="27d70-151">MFCMAPI reference</span></span>

<span data-ttu-id="27d70-152">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="27d70-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="27d70-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="27d70-153">**File**</span></span>|<span data-ttu-id="27d70-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="27d70-154">**Function**</span></span>|<span data-ttu-id="27d70-155">**Comment**</span><span class="sxs-lookup"><span data-stu-id="27d70-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="27d70-156">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="27d70-156">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="27d70-157">CFolderDlg::OnSetReadFlag</span><span class="sxs-lookup"><span data-stu-id="27d70-157">CFolderDlg::OnSetReadFlag</span></span>  <br/> |<span data-ttu-id="27d70-158">MFCMAPI 使用**IMessage::SetReadFlag**方法对所选邮件设置只读的标志。</span><span class="sxs-lookup"><span data-stu-id="27d70-158">MFCMAPI uses the **IMessage::SetReadFlag** method to set read flags on selected messages.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="27d70-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27d70-159">See also</span></span>

- [<span data-ttu-id="27d70-160">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="27d70-160">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)  
- [<span data-ttu-id="27d70-161">IMAPIFolder::SetReadFlags</span><span class="sxs-lookup"><span data-stu-id="27d70-161">IMAPIFolder::SetReadFlags</span></span>](imapifolder-setreadflags.md)  
- [<span data-ttu-id="27d70-162">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="27d70-162">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)  
- [<span data-ttu-id="27d70-163">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="27d70-163">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md) 
- [<span data-ttu-id="27d70-164">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="27d70-164">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md) 
- [<span data-ttu-id="27d70-165">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="27d70-165">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)
- [<span data-ttu-id="27d70-166">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="27d70-166">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

