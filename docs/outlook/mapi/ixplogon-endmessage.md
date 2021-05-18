---
title: IXPLogonEndMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.EndMessage
api_type:
- COM
ms.assetid: bb29e6a0-7a92-46eb-bbeb-6f2df6ac6d21
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 03eccfe27c6f93e42ee01a34fbf5df766c145cf1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414156"
---
# <a name="ixplogonendmessage"></a><span data-ttu-id="75f35-103">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="75f35-103">IXPLogon::EndMessage</span></span>

  
  
<span data-ttu-id="75f35-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="75f35-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="75f35-105">通知传输提供程序 MAPI 后台处理程序已完成对出站邮件的处理。</span><span class="sxs-lookup"><span data-stu-id="75f35-105">Informs the transport provider that the MAPI spooler completed its processing on an outbound message.</span></span>
  
```cpp
HRESULT EndMessage(
  ULONG ulMsgRef,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="75f35-106">参数</span><span class="sxs-lookup"><span data-stu-id="75f35-106">Parameters</span></span>

 <span data-ttu-id="75f35-107">_ulMsgRef_</span><span class="sxs-lookup"><span data-stu-id="75f35-107">_ulMsgRef_</span></span>
  
> <span data-ttu-id="75f35-108">[in]在之前对 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md) 方法的调用中获取的特定于邮件的引用值。</span><span class="sxs-lookup"><span data-stu-id="75f35-108">[in] A message-specific reference value that was obtained in an earlier call to the [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) method.</span></span> 
    
 <span data-ttu-id="75f35-109">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="75f35-109">_lpulFlags_</span></span>
  
> <span data-ttu-id="75f35-110">[out]指示 MAPI 后台处理程序应该对消息执行哪些操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="75f35-110">[out] A bitmask of flags that indicates to the MAPI spooler what it should do with the message.</span></span> <span data-ttu-id="75f35-111">如果未设置标志，则邮件已发送。</span><span class="sxs-lookup"><span data-stu-id="75f35-111">If no flags are set, the message has been sent.</span></span> <span data-ttu-id="75f35-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="75f35-112">The following flags can be set:</span></span>
    
<span data-ttu-id="75f35-113">END_DONT_RESEND</span><span class="sxs-lookup"><span data-stu-id="75f35-113">END_DONT_RESEND</span></span> 
  
> <span data-ttu-id="75f35-114">传输提供程序目前包含其需要有关此邮件的所有信息。</span><span class="sxs-lookup"><span data-stu-id="75f35-114">The transport provider has all the information it needs about this message for now.</span></span> <span data-ttu-id="75f35-115">当传输提供程序需要更多信息或发送消息时，它将通过调用具有 NOTIFY_SENTDEFERRED 标志的 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法并传递邮件的条目标识符来通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="75f35-115">When the transport provider requires more information or when it has sent the message, it notifies the MAPI spooler by calling the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method with the NOTIFY_SENTDEFERRED flag and by passing the message's entry identifier.</span></span> 
    
<span data-ttu-id="75f35-116">END_RESEND_LATER</span><span class="sxs-lookup"><span data-stu-id="75f35-116">END_RESEND_LATER</span></span> 
  
> <span data-ttu-id="75f35-117">由于非错误条件的原因，传输提供程序当前不发送邮件。</span><span class="sxs-lookup"><span data-stu-id="75f35-117">The transport provider is not sending the message at the current time for reasons that are not error conditions.</span></span> <span data-ttu-id="75f35-118">稍后应再次调用传输提供程序以发送邮件。</span><span class="sxs-lookup"><span data-stu-id="75f35-118">The transport provider should be called again later to send the message.</span></span>
    
<span data-ttu-id="75f35-119">END_RESEND_NOW</span><span class="sxs-lookup"><span data-stu-id="75f35-119">END_RESEND_NOW</span></span> 
  
> <span data-ttu-id="75f35-120">传输提供程序需要重新启动 [在 IMessage：：SubmitMessage](imessage-submitmessage.md) 方法调用中传递给它的邮件。</span><span class="sxs-lookup"><span data-stu-id="75f35-120">The transport provider needs to restart the message passed to it in an [IMessage::SubmitMessage](imessage-submitmessage.md) method call.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="75f35-121">返回值</span><span class="sxs-lookup"><span data-stu-id="75f35-121">Return value</span></span>

<span data-ttu-id="75f35-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="75f35-122">S_OK</span></span> 
  
> <span data-ttu-id="75f35-123">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="75f35-123">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="75f35-124">备注</span><span class="sxs-lookup"><span data-stu-id="75f35-124">Remarks</span></span>

<span data-ttu-id="75f35-125">MAPI 后台处理程序在完成提供扩展传递或非传递信息所涉及的处理后调用 **IXPLogon：：EndMessage** 方法。</span><span class="sxs-lookup"><span data-stu-id="75f35-125">The MAPI spooler calls the **IXPLogon::EndMessage** method after it completes the processing involved in providing extended delivery or nondelivery information.</span></span> 
  
<span data-ttu-id="75f35-126">一旦此调用返回  _，ulMsgRef_ 参数中的值将不再对此消息有效。</span><span class="sxs-lookup"><span data-stu-id="75f35-126">Once this call returns, the value in the  _ulMsgRef_ parameter is no longer valid for this message.</span></span> <span data-ttu-id="75f35-127">传输提供程序可以在将来的邮件上重用相同的值。</span><span class="sxs-lookup"><span data-stu-id="75f35-127">The transport provider can reuse the same value on a future message.</span></span> 
  
<span data-ttu-id="75f35-128">传输提供程序在传输邮件期间打开的所有对象都应在 **EndMessage** 调用返回之前释放，MAPI 后台处理程序传递给传输提供程序的邮件对象除外。</span><span class="sxs-lookup"><span data-stu-id="75f35-128">All objects that the transport provider opens during the transfer of a message should be released before the **EndMessage** call returns, with the exception of the message object that the MAPI spooler passes to the transport provider.</span></span> <span data-ttu-id="75f35-129">MAPI 后台处理程序传递的消息对象在 **EndMessage** 调用后无效。</span><span class="sxs-lookup"><span data-stu-id="75f35-129">The message object passed by the MAPI spooler is invalid after the **EndMessage** call.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="75f35-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75f35-130">See also</span></span>



[<span data-ttu-id="75f35-131">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="75f35-131">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="75f35-132">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="75f35-132">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="75f35-133">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="75f35-133">IXPLogon::SubmitMessage</span></span>](ixplogon-submitmessage.md)
  
[<span data-ttu-id="75f35-134">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="75f35-134">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

