---
title: IMessageSubmitMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.SubmitMessage
api_type:
- COM
ms.assetid: 9ce93469-c55d-48d1-9abb-a637716ed4f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28786f483c4d2031c334d7b9697db7c5e627fe93
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437362"
---
# <a name="imessagesubmitmessage"></a><span data-ttu-id="edf8a-103">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="edf8a-103">IMessage::SubmitMessage</span></span>

  
  
<span data-ttu-id="edf8a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="edf8a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="edf8a-105">保存邮件的所有属性, 并将邮件标记为 "已准备好发送"。</span><span class="sxs-lookup"><span data-stu-id="edf8a-105">Saves all of the message's properties and marks the message as ready to be sent.</span></span>
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="edf8a-106">参数</span><span class="sxs-lookup"><span data-stu-id="edf8a-106">Parameters</span></span>

 <span data-ttu-id="edf8a-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="edf8a-107">_ulFlags_</span></span>
  
> <span data-ttu-id="edf8a-108">实时用于控制如何提交邮件的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="edf8a-108">[in] Bitmask of flags used to control how a message is submitted.</span></span> <span data-ttu-id="edf8a-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="edf8a-109">The following flag can be set:</span></span>
    
<span data-ttu-id="edf8a-110">FORCE_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="edf8a-110">FORCE_SUBMIT</span></span> 
  
> <span data-ttu-id="edf8a-111">MAPI 应立即提交邮件。</span><span class="sxs-lookup"><span data-stu-id="edf8a-111">MAPI should submit the message immediately.</span></span> <span data-ttu-id="edf8a-112">此标志当前未在使用中。</span><span class="sxs-lookup"><span data-stu-id="edf8a-112">This flag is not currently in use.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="edf8a-113">返回值</span><span class="sxs-lookup"><span data-stu-id="edf8a-113">Return value</span></span>

<span data-ttu-id="edf8a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="edf8a-114">S_OK</span></span> 
  
> <span data-ttu-id="edf8a-115">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="edf8a-115">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="edf8a-116">MAPI_E_NO_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="edf8a-116">MAPI_E_NO_RECIPIENTS</span></span> 
  
> <span data-ttu-id="edf8a-117">邮件的收件人表为空。</span><span class="sxs-lookup"><span data-stu-id="edf8a-117">The message's recipient table is empty.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="edf8a-118">说明</span><span class="sxs-lookup"><span data-stu-id="edf8a-118">Remarks</span></span>

<span data-ttu-id="edf8a-119">**IMessage:: SubmitMessage**方法将邮件标记为已准备好传输。</span><span class="sxs-lookup"><span data-stu-id="edf8a-119">The **IMessage::SubmitMessage** method marks a message as ready to be transmitted.</span></span> <span data-ttu-id="edf8a-120">MAPI 将邮件按标记为发送的顺序传递给基础邮件系统。</span><span class="sxs-lookup"><span data-stu-id="edf8a-120">MAPI passes messages to the underlying messaging system in the order in which they are marked for sending.</span></span> <span data-ttu-id="edf8a-121">由于此功能, 邮件可能会在邮件存储区中保留一段时间, 然后基础邮件系统才能对其承担责任。</span><span class="sxs-lookup"><span data-stu-id="edf8a-121">Because of this functionality, a message might stay in a message store for some time before the underlying messaging system can take responsibility for it.</span></span> <span data-ttu-id="edf8a-122">目标中的收据顺序位于基础邮件系统的控制中, 并不一定与发送邮件的顺序一致。</span><span class="sxs-lookup"><span data-stu-id="edf8a-122">The order of receipt at the destination is in the underlying messaging system's control and does not necessarily match the order in which messages were sent.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="edf8a-123">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="edf8a-123">Notes to implementers</span></span>

<span data-ttu-id="edf8a-124">调用邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以保存它, 然后检查邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="edf8a-124">Call the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save it and then check the message's **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="edf8a-125">如果设置了 MSGFLAG_RESEND 标志, 则调用[IMAPISupport::P reparesubmit](imapisupport-preparesubmit.md)。</span><span class="sxs-lookup"><span data-stu-id="edf8a-125">If the MSGFLAG_RESEND flag is set, call [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md).</span></span> <span data-ttu-id="edf8a-126">**PrepareSubmit**更新重发邮件中所有收件人的收件人类型和**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="edf8a-126">**PrepareSubmit** updates the recipient type and **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property for all of the recipients in the resend message.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="edf8a-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="edf8a-127">Notes to callers</span></span>

<span data-ttu-id="edf8a-128">当**SubmitMessage**返回时, 指向邮件及其关联的子消息、文件夹、附件、流、表格等的所有指针都将不再有效。</span><span class="sxs-lookup"><span data-stu-id="edf8a-128">When **SubmitMessage** returns, all pointers to the message and its associated subobjects messages, folders, attachments, streams, tables, and so on are no longer valid.</span></span> <span data-ttu-id="edf8a-129">MAPI 不允许对这些指针执行任何进一步的操作, 但调用其**IUnknown:: Release**方法除外。</span><span class="sxs-lookup"><span data-stu-id="edf8a-129">MAPI does not permit any further operations on these pointers, except for calling their **IUnknown::Release** methods.</span></span> <span data-ttu-id="edf8a-130">MAPI 的设计方式是, 在调用**SubmitMessage**后, 您应释放邮件和所有关联的子类型。</span><span class="sxs-lookup"><span data-stu-id="edf8a-130">MAPI is designed such that after **SubmitMessage** is called, you should release the message and all associated subobjects.</span></span> <span data-ttu-id="edf8a-131">但是, 如果**SubmitMessage**返回一个指示缺少或无效信息的错误值, 则邮件仍处于打开状态, 并且指针仍然有效。</span><span class="sxs-lookup"><span data-stu-id="edf8a-131">However, if **SubmitMessage** returns an error value indicating missing or invalid information, the message remains open and the pointers remain valid.</span></span> 
  
<span data-ttu-id="edf8a-132">若要取消发送操作, 请先获取并存储指向邮件的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的指针, 然后再提交邮件。</span><span class="sxs-lookup"><span data-stu-id="edf8a-132">To cancel a send operation, get and store a pointer to the message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property before the message is submitted.</span></span> <span data-ttu-id="edf8a-133">由于在提交邮件后邮件的条目标识符无效, 因此必须先保存它, 然后才能调用**SubmitMessage**。</span><span class="sxs-lookup"><span data-stu-id="edf8a-133">Because a message's entry identifier is invalidated after the message has been submitted, it is necessary to save it before calling **SubmitMessage**.</span></span> <span data-ttu-id="edf8a-134">若要取消发送, 请将_lpEntryId_参数指向此条目标识符, 并调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)。</span><span class="sxs-lookup"><span data-stu-id="edf8a-134">To cancel the send, point the  _lpEntryId_ parameter to this entry identifier and call [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="edf8a-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="edf8a-135">MFCMAPI reference</span></span>

<span data-ttu-id="edf8a-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="edf8a-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="edf8a-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="edf8a-137">**File**</span></span>|<span data-ttu-id="edf8a-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="edf8a-138">**Function**</span></span>|<span data-ttu-id="edf8a-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="edf8a-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="edf8a-140">FolderDlg</span><span class="sxs-lookup"><span data-stu-id="edf8a-140">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="edf8a-141">**CFolderDlg:: OnSubmitMessage**</span><span class="sxs-lookup"><span data-stu-id="edf8a-141">**CFolderDlg::OnSubmitMessage**</span></span> <br/> |<span data-ttu-id="edf8a-142">MFCMAPI 使用**IMessage:: SubmitMessage**方法提交选定的邮件。</span><span class="sxs-lookup"><span data-stu-id="edf8a-142">MFCMAPI uses the **IMessage::SubmitMessage** method to submit the selected message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="edf8a-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edf8a-143">See also</span></span>



[<span data-ttu-id="edf8a-144">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="edf8a-144">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)
  
[<span data-ttu-id="edf8a-145">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="edf8a-145">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)


[<span data-ttu-id="edf8a-146">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="edf8a-146">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

