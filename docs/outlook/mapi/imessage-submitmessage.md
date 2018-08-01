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
ms.openlocfilehash: 1d325c67c836e727d8285bd2dceecf88bf68327c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775769"
---
# <a name="imessagesubmitmessage"></a><span data-ttu-id="01b59-103">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="01b59-103">IMessage::SubmitMessage</span></span>

  
  
<span data-ttu-id="01b59-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="01b59-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="01b59-105">保存所有消息的属性，并将邮件标记为已准备好发送。</span><span class="sxs-lookup"><span data-stu-id="01b59-105">Saves all of the message's properties and marks the message as ready to be sent.</span></span>
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="01b59-106">参数</span><span class="sxs-lookup"><span data-stu-id="01b59-106">Parameters</span></span>

 <span data-ttu-id="01b59-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="01b59-107">_ulFlags_</span></span>
  
> <span data-ttu-id="01b59-108">[in]用于控制一条消息的提交方式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="01b59-108">[in] Bitmask of flags used to control how a message is submitted.</span></span> <span data-ttu-id="01b59-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="01b59-109">The following flag can be set:</span></span>
    
<span data-ttu-id="01b59-110">FORCE_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="01b59-110">FORCE_SUBMIT</span></span> 
  
> <span data-ttu-id="01b59-111">MAPI 应立即提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="01b59-111">MAPI should submit the message immediately.</span></span> <span data-ttu-id="01b59-112">此标志不当前正在使用中。</span><span class="sxs-lookup"><span data-stu-id="01b59-112">This flag is not currently in use.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="01b59-113">返回值</span><span class="sxs-lookup"><span data-stu-id="01b59-113">Return value</span></span>

<span data-ttu-id="01b59-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="01b59-114">S_OK</span></span> 
  
> <span data-ttu-id="01b59-115">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="01b59-115">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="01b59-116">MAPI_E_NO_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="01b59-116">MAPI_E_NO_RECIPIENTS</span></span> 
  
> <span data-ttu-id="01b59-117">邮件的收件人表为空。</span><span class="sxs-lookup"><span data-stu-id="01b59-117">The message's recipient table is empty.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="01b59-118">说明</span><span class="sxs-lookup"><span data-stu-id="01b59-118">Remarks</span></span>

<span data-ttu-id="01b59-119">**IMessage::SubmitMessage**方法将邮件标记为已准备好进行传输。</span><span class="sxs-lookup"><span data-stu-id="01b59-119">The **IMessage::SubmitMessage** method marks a message as ready to be transmitted.</span></span> <span data-ttu-id="01b59-120">MAPI 将消息传递给基础邮件系统发送的标记的顺序。</span><span class="sxs-lookup"><span data-stu-id="01b59-120">MAPI passes messages to the underlying messaging system in the order in which they are marked for sending.</span></span> <span data-ttu-id="01b59-121">由于此功能，一条消息可能消息存储区中保持之前基础消息系统可以负责为它一些时间。</span><span class="sxs-lookup"><span data-stu-id="01b59-121">Because of this functionality, a message might stay in a message store for some time before the underlying messaging system can take responsibility for it.</span></span> <span data-ttu-id="01b59-122">在目标接收的顺序处于基础邮件系统的控件，并且不一定匹配已发送邮件的顺序。</span><span class="sxs-lookup"><span data-stu-id="01b59-122">The order of receipt at the destination is in the underlying messaging system's control and does not necessarily match the order in which messages were sent.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="01b59-123">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="01b59-123">Notes to implementers</span></span>

<span data-ttu-id="01b59-124">调用消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法以将其保存，然后检查消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="01b59-124">Call the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save it and then check the message's **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="01b59-125">如果设置了 MSGFLAG_RESEND 标志，调用[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md)。</span><span class="sxs-lookup"><span data-stu-id="01b59-125">If the MSGFLAG_RESEND flag is set, call [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md).</span></span> <span data-ttu-id="01b59-126">**PrepareSubmit**更新中重新发送邮件的收件人的所有收件人类型和**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="01b59-126">**PrepareSubmit** updates the recipient type and **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property for all of the recipients in the resend message.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="01b59-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="01b59-127">Notes to callers</span></span>

<span data-ttu-id="01b59-128">**SubmitMessage**返回时，所有指向邮件，并与其关联的子对象的邮件，将不再有效文件夹、 附件、 流、 表和等等。</span><span class="sxs-lookup"><span data-stu-id="01b59-128">When **SubmitMessage** returns, all pointers to the message and its associated subobjects messages, folders, attachments, streams, tables, and so on are no longer valid.</span></span> <span data-ttu-id="01b59-129">MAPI 不允许任何进一步的操作对这些指针，调用其**IUnknown::Release**方法除外。</span><span class="sxs-lookup"><span data-stu-id="01b59-129">MAPI does not permit any further operations on these pointers, except for calling their **IUnknown::Release** methods.</span></span> <span data-ttu-id="01b59-130">MAPI 旨在以便调用**SubmitMessage**后，您应释放消息和所有关联的子对象。</span><span class="sxs-lookup"><span data-stu-id="01b59-130">MAPI is designed such that after **SubmitMessage** is called, you should release the message and all associated subobjects.</span></span> <span data-ttu-id="01b59-131">但是，如果**SubmitMessage**返回错误值，该值指示缺失或无效的信息，邮件保持打开状态，指针保持有效。</span><span class="sxs-lookup"><span data-stu-id="01b59-131">However, if **SubmitMessage** returns an error value indicating missing or invalid information, the message remains open and the pointers remain valid.</span></span> 
  
<span data-ttu-id="01b59-132">若要取消发送操作，获取并提交邮件之前存储指向消息的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="01b59-132">To cancel a send operation, get and store a pointer to the message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property before the message is submitted.</span></span> <span data-ttu-id="01b59-133">因为消息的项标识符将失效提交邮件后，很有必要，以将其保存在调用**SubmitMessage**之前。</span><span class="sxs-lookup"><span data-stu-id="01b59-133">Because a message's entry identifier is invalidated after the message has been submitted, it is necessary to save it before calling **SubmitMessage**.</span></span> <span data-ttu-id="01b59-134">若要取消发送， _lpEntryId_参数指向此条目标识符，并调用[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)。</span><span class="sxs-lookup"><span data-stu-id="01b59-134">To cancel the send, point the  _lpEntryId_ parameter to this entry identifier and call [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="01b59-135">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="01b59-135">MFCMAPI reference</span></span>

<span data-ttu-id="01b59-136">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="01b59-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="01b59-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="01b59-137">**File**</span></span>|<span data-ttu-id="01b59-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="01b59-138">**Function**</span></span>|<span data-ttu-id="01b59-139">**Comment**</span><span class="sxs-lookup"><span data-stu-id="01b59-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="01b59-140">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="01b59-140">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="01b59-141">**CFolderDlg::OnSubmitMessage**</span><span class="sxs-lookup"><span data-stu-id="01b59-141">**CFolderDlg::OnSubmitMessage**</span></span> <br/> |<span data-ttu-id="01b59-142">MFCMAPI 使用**IMessage::SubmitMessage**方法提交所选的消息。</span><span class="sxs-lookup"><span data-stu-id="01b59-142">MFCMAPI uses the **IMessage::SubmitMessage** method to submit the selected message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="01b59-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01b59-143">See also</span></span>



[<span data-ttu-id="01b59-144">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="01b59-144">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)
  
[<span data-ttu-id="01b59-145">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="01b59-145">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)


[<span data-ttu-id="01b59-146">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="01b59-146">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

