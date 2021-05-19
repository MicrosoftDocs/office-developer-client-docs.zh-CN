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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 00273d5572fa0c12a9501a1620db11ea087fd5d1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427603"
---
# <a name="ixplogonstartmessage"></a><span data-ttu-id="89c4d-103">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="89c4d-103">IXPLogon::StartMessage</span></span>

  
  
<span data-ttu-id="89c4d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="89c4d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="89c4d-105">启动将入站邮件从传输提供程序转移到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="89c4d-105">Initiates the transfer of an inbound message from the transport provider to the MAPI spooler.</span></span>
  
```cpp
HRESULT StartMessage(
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMsgRef
);
```

## <a name="parameters"></a><span data-ttu-id="89c4d-106">参数</span><span class="sxs-lookup"><span data-stu-id="89c4d-106">Parameters</span></span>

 <span data-ttu-id="89c4d-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="89c4d-107">_ulFlags_</span></span>
  
> <span data-ttu-id="89c4d-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="89c4d-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="89c4d-109">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="89c4d-109">_lpMessage_</span></span>
  
> <span data-ttu-id="89c4d-110">[in]一个指向邮件 (表示具有读/写) 的入站邮件的指针，传输提供程序使用该对象访问和操作该邮件。</span><span class="sxs-lookup"><span data-stu-id="89c4d-110">[in] A pointer to a message object (representing the inbound message) that has read/write permission, which is used by the transport provider to access and manipulate that message.</span></span> <span data-ttu-id="89c4d-111">在传输提供程序从对 **IXPLogon：：StartMessage** 的调用中返回之前，此对象一直有效。</span><span class="sxs-lookup"><span data-stu-id="89c4d-111">This object remains valid until after the transport provider returns from the call to **IXPLogon::StartMessage**.</span></span>
    
 <span data-ttu-id="89c4d-112">_lpulMsgRef_</span><span class="sxs-lookup"><span data-stu-id="89c4d-112">_lpulMsgRef_</span></span>
  
> <span data-ttu-id="89c4d-113">[out]指向分配给邮件的引用值的指针。</span><span class="sxs-lookup"><span data-stu-id="89c4d-113">[out] A pointer to a reference value assigned to the message.</span></span> <span data-ttu-id="89c4d-114">MAPI 后台处理程序在返回指向传输提供程序的指针之前将此值初始化为 1。</span><span class="sxs-lookup"><span data-stu-id="89c4d-114">The MAPI spooler initializes this value to 1 before it returns the pointer to the transport provider.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="89c4d-115">返回值</span><span class="sxs-lookup"><span data-stu-id="89c4d-115">Return value</span></span>

<span data-ttu-id="89c4d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="89c4d-116">S_OK</span></span> 
  
> <span data-ttu-id="89c4d-117">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="89c4d-117">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="89c4d-118">备注</span><span class="sxs-lookup"><span data-stu-id="89c4d-118">Remarks</span></span>

<span data-ttu-id="89c4d-119">MAPI 后台处理程序调用 **IXPLogon：：StartMessage** 方法以启动将入站邮件从传输提供程序转移到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="89c4d-119">The MAPI spooler calls the **IXPLogon::StartMessage** method to initiate the transfer of an inbound message from the transport provider to the MAPI spooler.</span></span> <span data-ttu-id="89c4d-120">在传输提供程序开始使用  _lpMessage_ 指向的邮件之前，它应在  _lpulMsgRef_ 参数中存储邮件引用，以通过调用 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) 方法来可能使用它。</span><span class="sxs-lookup"><span data-stu-id="89c4d-120">Before the transport provider starts to use the message pointed to by  _lpMessage_, it should store a message reference in the  _lpulMsgRef_ parameter for potential use by a call to the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method.</span></span> 
  
<span data-ttu-id="89c4d-121">在 **StartMessage** 调用期间，MAPI 后台处理程序处理在邮件传输期间打开的对象的方法，并且还会处理任何附件。</span><span class="sxs-lookup"><span data-stu-id="89c4d-121">During a **StartMessage** call, the MAPI spooler processes methods for objects opened during the transfer of the message, and it also processes any attachments.</span></span> <span data-ttu-id="89c4d-122">此处理可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="89c4d-122">This processing can take a long time.</span></span> <span data-ttu-id="89c4d-123">传输提供程序可以在此处理过程中经常调用 MAPI 后台处理程序的 [IMAPISupport：：SpoolerYield](imapisupport-spooleryield.md) 回调函数，以释放其他系统任务的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="89c4d-123">Transport providers can call the [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) callback function for the MAPI spooler frequently during this processing to release CPU time for other system tasks.</span></span> 
  
<span data-ttu-id="89c4d-124">传输提供程序为邮件创建的收件人表中的所有收件人都必须包含所有必需的寻址属性。</span><span class="sxs-lookup"><span data-stu-id="89c4d-124">All recipients in the recipient table that the transport provider creates for the message must contain all required addressing properties.</span></span> <span data-ttu-id="89c4d-125">如有必要，提供程序可以构造一个自定义收件人来表示特定收件人。</span><span class="sxs-lookup"><span data-stu-id="89c4d-125">If necessary, the provider can construct a custom recipient to represent a particular recipient.</span></span> <span data-ttu-id="89c4d-126">但是，如果提供程序可以生成包含详细信息的收件人条目，则应该这样做。</span><span class="sxs-lookup"><span data-stu-id="89c4d-126">However, if the provider can produce a recipient entry that includes more information, it should do so.</span></span> <span data-ttu-id="89c4d-127">例如，如果传输提供程序具有有关通讯簿提供程序的收件人格式的足够信息，可以针对该格式为收件人生成有效的条目标识符，则应该构建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="89c4d-127">For example, if a transport provider has enough information about an address book provider's recipient format that it can build a valid entry identifier for a recipient for that format, it should build the entry identifier.</span></span>
  
<span data-ttu-id="89c4d-128">如果收到任何不可传输的属性，则传输提供程序不应将它们存储在新邮件中。</span><span class="sxs-lookup"><span data-stu-id="89c4d-128">If any nontransmittable properties are received, the transport provider should not store them in the new message.</span></span> <span data-ttu-id="89c4d-129">但是，传输提供程序应在新邮件中存储其接收的所有可传输属性。</span><span class="sxs-lookup"><span data-stu-id="89c4d-129">However, the transport provider should store all transmittable properties it receives in the new message.</span></span>
  
<span data-ttu-id="89c4d-130">如果传入的邮件是送达报告或未送达报告，并且传输提供程序无法使用 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法从原始邮件生成报告，则提供程序本身应该使用适当的属性填充邮件。</span><span class="sxs-lookup"><span data-stu-id="89c4d-130">If the incoming message is a delivery report or a nondelivery report and the transport provider is unable to use the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method to generate the report from the original message, the provider should itself populate the message with the appropriate properties.</span></span> <span data-ttu-id="89c4d-131">但是，传输提供程序无法将邮件的 PR_ENTRYID ( [PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="89c4d-131">However, the transport provider cannot set the message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="89c4d-132">若要在处理后将传入邮件保存在相应的 MAPI 邮件存储中，传输提供程序会调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="89c4d-132">To save the incoming message in the appropriate MAPI message store after processing, the transport provider calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="89c4d-133">如果传输提供程序没有任何要传递到 MAPI 后台处理程序的邮件，则可以通过不调用 **SaveChanges** 从 **StartMessage** 调用返回来停止传入邮件。</span><span class="sxs-lookup"><span data-stu-id="89c4d-133">If the transport provider does not have any messages to pass to the MAPI spooler, it can stop the incoming message by returning from the **StartMessage** call without calling **SaveChanges**.</span></span>
  
<span data-ttu-id="89c4d-134">传输提供程序在 **StartMessage** 调用期间打开的所有对象都应在返回之前释放。</span><span class="sxs-lookup"><span data-stu-id="89c4d-134">All objects that the transport provider opens during a **StartMessage** call should be released before returning.</span></span> <span data-ttu-id="89c4d-135">但是，提供程序不应释放 MAPI 后台处理程序最初在  _lpMessage_ 参数中传递的消息对象。</span><span class="sxs-lookup"><span data-stu-id="89c4d-135">However, the provider should not release the message object that the MAPI spooler originally passed in the  _lpMessage_ parameter.</span></span> 
  
<span data-ttu-id="89c4d-136">如果 **StartMessage** 返回错误，则过程中的消息在未保存更改的情况下释放并丢失。</span><span class="sxs-lookup"><span data-stu-id="89c4d-136">If **StartMessage** returns an error, the message in process is released without having changes saved and is lost.</span></span> <span data-ttu-id="89c4d-137">在这种情况下，传输提供程序应该通过调用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法传递 NOTIFY_CRITICAL_ERROR 标志，并调用 [IXPLogon：:P oll](ixplogon-poll.md) 方法以通知 MAPI 后台处理程序它受到严重错误情况。</span><span class="sxs-lookup"><span data-stu-id="89c4d-137">In this case, the transport provider should pass the NOTIFY_CRITICAL_ERROR flag with a call to the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method and call the [IXPLogon::Poll](ixplogon-poll.md) method to notify the MAPI spooler that it is in a severe error condition.</span></span> 
  
<span data-ttu-id="89c4d-138">有关详细信息，请参阅与 [MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)。</span><span class="sxs-lookup"><span data-stu-id="89c4d-138">For more information, see [Interacting with the MAPI Spooler](interacting-with-the-mapi-spooler.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="89c4d-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89c4d-139">See also</span></span>



[<span data-ttu-id="89c4d-140">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="89c4d-140">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="89c4d-141">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="89c4d-141">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="89c4d-142">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="89c4d-142">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md)
  
[<span data-ttu-id="89c4d-143">IMAPISupport::StatusRecips</span><span class="sxs-lookup"><span data-stu-id="89c4d-143">IMAPISupport::StatusRecips</span></span>](imapisupport-statusrecips.md)
  
[<span data-ttu-id="89c4d-144">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="89c4d-144">IMessage::GetRecipientTable</span></span>](imessage-getrecipienttable.md)
  
[<span data-ttu-id="89c4d-145">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="89c4d-145">IXPLogon::Poll</span></span>](ixplogon-poll.md)
  
[<span data-ttu-id="89c4d-146">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="89c4d-146">IXPLogon::TransportNotify</span></span>](ixplogon-transportnotify.md)
  
[<span data-ttu-id="89c4d-147">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="89c4d-147">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

