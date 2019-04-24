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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351595"
---
# <a name="ixplogonstartmessage"></a><span data-ttu-id="d05ed-103">IXPLogon::StartMessage</span><span class="sxs-lookup"><span data-stu-id="d05ed-103">IXPLogon::StartMessage</span></span>

  
  
<span data-ttu-id="d05ed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d05ed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d05ed-105">启动从传输提供程序到 MAPI 后台处理程序的入站邮件传输。</span><span class="sxs-lookup"><span data-stu-id="d05ed-105">Initiates the transfer of an inbound message from the transport provider to the MAPI spooler.</span></span>
  
```cpp
HRESULT StartMessage(
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMsgRef
);
```

## <a name="parameters"></a><span data-ttu-id="d05ed-106">参数</span><span class="sxs-lookup"><span data-stu-id="d05ed-106">Parameters</span></span>

 <span data-ttu-id="d05ed-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d05ed-107">_ulFlags_</span></span>
  
> <span data-ttu-id="d05ed-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="d05ed-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="d05ed-109">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="d05ed-109">_lpMessage_</span></span>
  
> <span data-ttu-id="d05ed-110">实时指向具有读/写权限的邮件对象 (表示入站邮件) 的指针, 该对象由传输提供程序用来访问和操作该邮件。</span><span class="sxs-lookup"><span data-stu-id="d05ed-110">[in] A pointer to a message object (representing the inbound message) that has read/write permission, which is used by the transport provider to access and manipulate that message.</span></span> <span data-ttu-id="d05ed-111">此对象一直保持有效, 直到传输提供程序从对**IXPLogon:: StartMessage**的调用返回。</span><span class="sxs-lookup"><span data-stu-id="d05ed-111">This object remains valid until after the transport provider returns from the call to **IXPLogon::StartMessage**.</span></span>
    
 <span data-ttu-id="d05ed-112">_lpulMsgRef_</span><span class="sxs-lookup"><span data-stu-id="d05ed-112">_lpulMsgRef_</span></span>
  
> <span data-ttu-id="d05ed-113">排除指向分配给邮件的引用值的指针。</span><span class="sxs-lookup"><span data-stu-id="d05ed-113">[out] A pointer to a reference value assigned to the message.</span></span> <span data-ttu-id="d05ed-114">MAPI 后台处理程序将此值初始化为 1, 然后再将指针返回到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="d05ed-114">The MAPI spooler initializes this value to 1 before it returns the pointer to the transport provider.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d05ed-115">返回值</span><span class="sxs-lookup"><span data-stu-id="d05ed-115">Return value</span></span>

<span data-ttu-id="d05ed-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d05ed-116">S_OK</span></span> 
  
> <span data-ttu-id="d05ed-117">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="d05ed-117">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d05ed-118">注解</span><span class="sxs-lookup"><span data-stu-id="d05ed-118">Remarks</span></span>

<span data-ttu-id="d05ed-119">MAPI 后台处理程序调用**IXPLogon:: StartMessage**方法, 以启动从传输提供程序到 MAPI 后台处理程序的入站邮件的传输。</span><span class="sxs-lookup"><span data-stu-id="d05ed-119">The MAPI spooler calls the **IXPLogon::StartMessage** method to initiate the transfer of an inbound message from the transport provider to the MAPI spooler.</span></span> <span data-ttu-id="d05ed-120">在传输提供程序开始使用由_lpMessage_指向的邮件之前, 它应在_lpulMsgRef_参数中存储消息引用, 以便可以调用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法, 以供潜在使用。</span><span class="sxs-lookup"><span data-stu-id="d05ed-120">Before the transport provider starts to use the message pointed to by  _lpMessage_, it should store a message reference in the  _lpulMsgRef_ parameter for potential use by a call to the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method.</span></span> 
  
<span data-ttu-id="d05ed-121">在**StartMessage**呼叫过程中, MAPI 后台处理程序将处理在邮件传输过程中打开的对象的方法, 并且还会处理所有附件。</span><span class="sxs-lookup"><span data-stu-id="d05ed-121">During a **StartMessage** call, the MAPI spooler processes methods for objects opened during the transfer of the message, and it also processes any attachments.</span></span> <span data-ttu-id="d05ed-122">此处理可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="d05ed-122">This processing can take a long time.</span></span> <span data-ttu-id="d05ed-123">在此处理过程中, 传输提供程序可以在此处理过程中频繁调用 MAPI 后台处理程序的[IMAPISupport:: SpoolerYield](imapisupport-spooleryield.md)回调函数, 以释放其他系统任务的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="d05ed-123">Transport providers can call the [IMAPISupport::SpoolerYield](imapisupport-spooleryield.md) callback function for the MAPI spooler frequently during this processing to release CPU time for other system tasks.</span></span> 
  
<span data-ttu-id="d05ed-124">收件人表中的传输提供程序为邮件创建的所有收件人必须包含所有必需的寻址属性。</span><span class="sxs-lookup"><span data-stu-id="d05ed-124">All recipients in the recipient table that the transport provider creates for the message must contain all required addressing properties.</span></span> <span data-ttu-id="d05ed-125">如有必要, 提供程序可以构造自定义收件人以代表特定收件人。</span><span class="sxs-lookup"><span data-stu-id="d05ed-125">If necessary, the provider can construct a custom recipient to represent a particular recipient.</span></span> <span data-ttu-id="d05ed-126">但是, 如果提供程序可以生成包含详细信息的收件人条目, 则应执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d05ed-126">However, if the provider can produce a recipient entry that includes more information, it should do so.</span></span> <span data-ttu-id="d05ed-127">例如, 如果传输提供程序具有有关通讯簿提供程序的收件人格式的足够信息, 可以为该格式的收件人生成有效的条目标识符, 则它应生成条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d05ed-127">For example, if a transport provider has enough information about an address book provider's recipient format that it can build a valid entry identifier for a recipient for that format, it should build the entry identifier.</span></span>
  
<span data-ttu-id="d05ed-128">如果收到任何 nontransmittable 属性, 则传输提供程序不应将其存储在新邮件中。</span><span class="sxs-lookup"><span data-stu-id="d05ed-128">If any nontransmittable properties are received, the transport provider should not store them in the new message.</span></span> <span data-ttu-id="d05ed-129">但是, 传输提供程序应将其收到的所有传输属性存储在新邮件中。</span><span class="sxs-lookup"><span data-stu-id="d05ed-129">However, the transport provider should store all transmittable properties it receives in the new message.</span></span>
  
<span data-ttu-id="d05ed-130">如果传入邮件是传递报告或 nondelivery 报告, 并且传输提供程序无法使用[IMAPISupport:: StatusRecips](imapisupport-statusrecips.md)方法来生成来自原始邮件的报告, 则提供程序将自行在中填充邮件相应的属性。</span><span class="sxs-lookup"><span data-stu-id="d05ed-130">If the incoming message is a delivery report or a nondelivery report and the transport provider is unable to use the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method to generate the report from the original message, the provider should itself populate the message with the appropriate properties.</span></span> <span data-ttu-id="d05ed-131">但是, 传输提供程序无法设置邮件的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d05ed-131">However, the transport provider cannot set the message's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="d05ed-132">若要在处理后将传入邮件保存在相应的 MAPI 邮件存储库中, 传输提供程序将调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d05ed-132">To save the incoming message in the appropriate MAPI message store after processing, the transport provider calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="d05ed-133">如果传输提供程序没有任何要传递给 MAPI 后台处理程序的邮件, 它可以通过从**StartMessage**调用返回, 而无需调用**SaveChanges**, 从而停止传入的邮件。</span><span class="sxs-lookup"><span data-stu-id="d05ed-133">If the transport provider does not have any messages to pass to the MAPI spooler, it can stop the incoming message by returning from the **StartMessage** call without calling **SaveChanges**.</span></span>
  
<span data-ttu-id="d05ed-134">传输提供程序在**StartMessage**呼叫过程中打开的所有对象都应在返回之前释放。</span><span class="sxs-lookup"><span data-stu-id="d05ed-134">All objects that the transport provider opens during a **StartMessage** call should be released before returning.</span></span> <span data-ttu-id="d05ed-135">但是, 提供程序不应释放 MAPI 假脱机程序最初在_lpMessage_参数中传递的邮件对象。</span><span class="sxs-lookup"><span data-stu-id="d05ed-135">However, the provider should not release the message object that the MAPI spooler originally passed in the  _lpMessage_ parameter.</span></span> 
  
<span data-ttu-id="d05ed-136">如果**StartMessage**返回错误, 则会在不保存更改的情况下释放进程中的邮件, 并且该邮件将丢失。</span><span class="sxs-lookup"><span data-stu-id="d05ed-136">If **StartMessage** returns an error, the message in process is released without having changes saved and is lost.</span></span> <span data-ttu-id="d05ed-137">在这种情况下, 传输提供程序应通过调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法传递 NOTIFY_CRITICAL_ERROR 标志并调用[IXPLogon::P oll](ixplogon-poll.md)方法, 以通知 MAPI 后台处理程序存在严重的错误情况。</span><span class="sxs-lookup"><span data-stu-id="d05ed-137">In this case, the transport provider should pass the NOTIFY_CRITICAL_ERROR flag with a call to the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method and call the [IXPLogon::Poll](ixplogon-poll.md) method to notify the MAPI spooler that it is in a severe error condition.</span></span> 
  
<span data-ttu-id="d05ed-138">有关详细信息, 请参阅[与 MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)。</span><span class="sxs-lookup"><span data-stu-id="d05ed-138">For more information, see [Interacting with the MAPI Spooler](interacting-with-the-mapi-spooler.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d05ed-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d05ed-139">See also</span></span>



[<span data-ttu-id="d05ed-140">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="d05ed-140">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="d05ed-141">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="d05ed-141">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="d05ed-142">IMAPISupport::SpoolerYield</span><span class="sxs-lookup"><span data-stu-id="d05ed-142">IMAPISupport::SpoolerYield</span></span>](imapisupport-spooleryield.md)
  
[<span data-ttu-id="d05ed-143">IMAPISupport::StatusRecips</span><span class="sxs-lookup"><span data-stu-id="d05ed-143">IMAPISupport::StatusRecips</span></span>](imapisupport-statusrecips.md)
  
[<span data-ttu-id="d05ed-144">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="d05ed-144">IMessage::GetRecipientTable</span></span>](imessage-getrecipienttable.md)
  
[<span data-ttu-id="d05ed-145">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="d05ed-145">IXPLogon::Poll</span></span>](ixplogon-poll.md)
  
[<span data-ttu-id="d05ed-146">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="d05ed-146">IXPLogon::TransportNotify</span></span>](ixplogon-transportnotify.md)
  
[<span data-ttu-id="d05ed-147">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d05ed-147">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

