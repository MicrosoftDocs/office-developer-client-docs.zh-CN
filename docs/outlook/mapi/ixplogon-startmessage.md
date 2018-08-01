---
title: IXPLogonStartMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.StartMessage
api_type:
- COM
ms.assetid: 83c349f7-dcac-4268-befe-fb2bc0cd9c50
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3758cf72aa79dbf500138e96872352950fafbd2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776132"
---
# <a name="ixplogonstartmessage"></a><span data-ttu-id="ed686-103">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="ed686-103">IXPLogon::StartMessage</span></span>

  
  
<span data-ttu-id="ed686-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ed686-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ed686-105">启动入站邮件传输提供程序传输到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="ed686-105">Initiates the transfer of an inbound message from the transport provider to the MAPI spooler.</span></span>
  
```cpp
HRESULT StartMessage(
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMsgRef
);
```

## <a name="parameters"></a><span data-ttu-id="ed686-106">参数</span><span class="sxs-lookup"><span data-stu-id="ed686-106">Parameters</span></span>

 <span data-ttu-id="ed686-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ed686-107">_ulFlags_</span></span>
  
> <span data-ttu-id="ed686-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="ed686-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="ed686-109">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="ed686-109">_lpMessage_</span></span>
  
> <span data-ttu-id="ed686-110">[in]指向具有读/写权限，由传输提供程序来访问和处理邮件的邮件对象 （表示入站的邮件） 的指针。</span><span class="sxs-lookup"><span data-stu-id="ed686-110">[in] A pointer to a message object (representing the inbound message) that has read/write permission, which is used by the transport provider to access and manipulate that message.</span></span> <span data-ttu-id="ed686-111">传输提供程序返回从**IXPLogon::StartMessage**调用后，该对象保持有效之前。</span><span class="sxs-lookup"><span data-stu-id="ed686-111">This object remains valid until after the transport provider returns from the call to **IXPLogon::StartMessage**.</span></span>
    
 <span data-ttu-id="ed686-112">_lpulMsgRef_</span><span class="sxs-lookup"><span data-stu-id="ed686-112">_lpulMsgRef_</span></span>
  
> <span data-ttu-id="ed686-113">[输出]指向引用值分配给邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="ed686-113">[out] A pointer to a reference value assigned to the message.</span></span> <span data-ttu-id="ed686-114">将指针返回到传输提供程序之前，MAPI 后台处理程序初始化此值设置为 1。</span><span class="sxs-lookup"><span data-stu-id="ed686-114">The MAPI spooler initializes this value to 1 before it returns the pointer to the transport provider.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ed686-115">返回值</span><span class="sxs-lookup"><span data-stu-id="ed686-115">Return value</span></span>

<span data-ttu-id="ed686-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed686-116">S_OK</span></span> 
  
> <span data-ttu-id="ed686-117">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="ed686-117">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ed686-118">说明</span><span class="sxs-lookup"><span data-stu-id="ed686-118">Remarks</span></span>

<span data-ttu-id="ed686-119">MAPI 后台处理程序调用**IXPLogon::StartMessage**方法来启动入站邮件传输提供程序传输到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="ed686-119">The MAPI spooler calls the **IXPLogon::StartMessage** method to initiate the transfer of an inbound message from the transport provider to the MAPI spooler.</span></span> <span data-ttu-id="ed686-120">传输提供程序开始使用所指的_lpMessage_消息之前，它应通过[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法调用潜在用于_lpulMsgRef_参数中存储消息引用。</span><span class="sxs-lookup"><span data-stu-id="ed686-120">Before the transport provider starts to use the message pointed to by  _lpMessage_, it should store a message reference in the  _lpulMsgRef_ parameter for potential use by a call to the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method.</span></span> 
  
<span data-ttu-id="ed686-121">**StartMessage**调用，过程中 MAPI 后台处理程序处理的邮件传输过程中打开的对象的方法，它还处理任何附件。</span><span class="sxs-lookup"><span data-stu-id="ed686-121">During a **StartMessage** call, the MAPI spooler processes methods for objects opened during the transfer of the message, and it also processes any attachments.</span></span> <span data-ttu-id="ed686-122">此处理花费很长时间。</span><span class="sxs-lookup"><span data-stu-id="ed686-122">This processing can take a long time.</span></span> <span data-ttu-id="ed686-123">传输提供程序可以[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)回调函数的 MAPI 后台处理程序经常在过程中调用此处理发布的其他系统任务的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="ed686-123">Transport providers can call the [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) callback function for the MAPI spooler frequently during this processing to release CPU time for other system tasks.</span></span> 
  
<span data-ttu-id="ed686-124">收件人的邮件传输提供程序创建的表中的所有收件人都必须都包含所有必需的寻址属性。</span><span class="sxs-lookup"><span data-stu-id="ed686-124">All recipients in the recipient table that the transport provider creates for the message must contain all required addressing properties.</span></span> <span data-ttu-id="ed686-125">如有必要，提供程序可以构造一个自定义的收件人，表示特定收件人。</span><span class="sxs-lookup"><span data-stu-id="ed686-125">If necessary, the provider can construct a custom recipient to represent a particular recipient.</span></span> <span data-ttu-id="ed686-126">但是，如果提供程序可能会产生的收件人的条目，其中包含的详细信息，它应这样做。</span><span class="sxs-lookup"><span data-stu-id="ed686-126">However, if the provider can produce a recipient entry that includes more information, it should do so.</span></span> <span data-ttu-id="ed686-127">例如，如果传输提供程序具有足够的信息有关通讯簿提供程序的收件人的格式，它可以为该格式收件人生成的有效条目标识符，它应生成的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ed686-127">For example, if a transport provider has enough information about an address book provider's recipient format that it can build a valid entry identifier for a recipient for that format, it should build the entry identifier.</span></span>
  
<span data-ttu-id="ed686-128">如果收到任何 nontransmittable 属性，则传输提供程序不应存储它们在新邮件。</span><span class="sxs-lookup"><span data-stu-id="ed686-128">If any nontransmittable properties are received, the transport provider should not store them in the new message.</span></span> <span data-ttu-id="ed686-129">但是，传输提供程序应将存储在新邮件中收到的所有可传送属性。</span><span class="sxs-lookup"><span data-stu-id="ed686-129">However, the transport provider should store all transmittable properties it receives in the new message.</span></span>
  
<span data-ttu-id="ed686-130">如果传入邮件送达报告或原件报表及传输提供程序无法[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法用于从原始邮件生成报告，提供程序本身也应该填充邮件相应的属性。</span><span class="sxs-lookup"><span data-stu-id="ed686-130">If the incoming message is a delivery report or a nondelivery report and the transport provider is unable to use the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method to generate the report from the original message, the provider should itself populate the message with the appropriate properties.</span></span> <span data-ttu-id="ed686-131">但是，传输提供程序无法设置消息的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ed686-131">However, the transport provider cannot set the message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="ed686-132">若要保存传入消息中的相应的 MAPI 邮件存储区进行处理之后，传输提供程序，请调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ed686-132">To save the incoming message in the appropriate MAPI message store after processing, the transport provider calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="ed686-133">如果传输提供程序没有任何邮件传递到 MAPI 后台处理程序，它可以通过从**StartMessage**调用返回而无需调用**SaveChanges**停止传入消息。</span><span class="sxs-lookup"><span data-stu-id="ed686-133">If the transport provider does not have any messages to pass to the MAPI spooler, it can stop the incoming message by returning from the **StartMessage** call without calling **SaveChanges**.</span></span>
  
<span data-ttu-id="ed686-134">返回之前，应释放传输提供程序打开**StartMessage**在呼叫过程中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="ed686-134">All objects that the transport provider opens during a **StartMessage** call should be released before returning.</span></span> <span data-ttu-id="ed686-135">但是，提供程序不应释放 MAPI 后台处理程序最初在_lpMessage_参数中传递的消息对象。</span><span class="sxs-lookup"><span data-stu-id="ed686-135">However, the provider should not release the message object that the MAPI spooler originally passed in the  _lpMessage_ parameter.</span></span> 
  
<span data-ttu-id="ed686-136">如果**StartMessage**返回一个错误，过程中的消息不必更改保存年和都将丢失。</span><span class="sxs-lookup"><span data-stu-id="ed686-136">If **StartMessage** returns an error, the message in process is released without having changes saved and is lost.</span></span> <span data-ttu-id="ed686-137">在这种情况下，传输提供程序应传递给[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法的调用 NOTIFY_CRITICAL_ERROR 标志，并调用[IXPLogon::Poll](ixplogon-poll.md)方法以通知处于严重错误条件 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="ed686-137">In this case, the transport provider should pass the NOTIFY_CRITICAL_ERROR flag with a call to the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method and call the [IXPLogon::Poll](ixplogon-poll.md) method to notify the MAPI spooler that it is in a severe error condition.</span></span> 
  
<span data-ttu-id="ed686-138">有关详细信息，请参阅[与 MAPI 后台处理程序的交互](interacting-with-the-mapi-spooler.md)。</span><span class="sxs-lookup"><span data-stu-id="ed686-138">For more information, see [Interacting with the MAPI Spooler](interacting-with-the-mapi-spooler.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ed686-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed686-139">See also</span></span>



[<span data-ttu-id="ed686-140">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="ed686-140">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="ed686-141">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="ed686-141">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="ed686-142">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="ed686-142">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md)
  
[<span data-ttu-id="ed686-143">IMAPISupport::StatusRecips</span><span class="sxs-lookup"><span data-stu-id="ed686-143">IMAPISupport::StatusRecips</span></span>](imapisupport-statusrecips.md)
  
[<span data-ttu-id="ed686-144">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="ed686-144">IMessage::GetRecipientTable</span></span>](imessage-getrecipienttable.md)
  
[<span data-ttu-id="ed686-145">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="ed686-145">IXPLogon::Poll</span></span>](ixplogon-poll.md)
  
[<span data-ttu-id="ed686-146">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="ed686-146">IXPLogon::TransportNotify</span></span>](ixplogon-transportnotify.md)
  
[<span data-ttu-id="ed686-147">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ed686-147">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

