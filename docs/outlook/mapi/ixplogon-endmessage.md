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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7f81a0c3c9a9ad0a9bcef5c5685aa5b343237f19
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776114"
---
# <a name="ixplogonendmessage"></a><span data-ttu-id="af6ed-103">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="af6ed-103">IXPLogon::EndMessage</span></span>

  
  
<span data-ttu-id="af6ed-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="af6ed-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="af6ed-105">通知传输提供程序 MAPI 后台处理程序完成对出站邮件及其处理。</span><span class="sxs-lookup"><span data-stu-id="af6ed-105">Informs the transport provider that the MAPI spooler completed its processing on an outbound message.</span></span>
  
```cpp
HRESULT EndMessage(
  ULONG ulMsgRef,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="af6ed-106">参数</span><span class="sxs-lookup"><span data-stu-id="af6ed-106">Parameters</span></span>

 <span data-ttu-id="af6ed-107">_ulMsgRef_</span><span class="sxs-lookup"><span data-stu-id="af6ed-107">_ulMsgRef_</span></span>
  
> <span data-ttu-id="af6ed-108">[in]在以前的[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法调用中获得一个特定的消息参考值。</span><span class="sxs-lookup"><span data-stu-id="af6ed-108">[in] A message-specific reference value that was obtained in an earlier call to the [IXPLogon::SubmitMessage](ixplogon-submitmessage.md) method.</span></span> 
    
 <span data-ttu-id="af6ed-109">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="af6ed-109">_lpulFlags_</span></span>
  
> <span data-ttu-id="af6ed-110">[输出]位掩码的标志，指示 MAPI 后台处理程序向它应为邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="af6ed-110">[out] A bitmask of flags that indicates to the MAPI spooler what it should do with the message.</span></span> <span data-ttu-id="af6ed-111">如果未设置标志，已发送邮件。</span><span class="sxs-lookup"><span data-stu-id="af6ed-111">If no flags are set, the message has been sent.</span></span> <span data-ttu-id="af6ed-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="af6ed-112">The following flags can be set:</span></span>
    
<span data-ttu-id="af6ed-113">END_DONT_RESEND</span><span class="sxs-lookup"><span data-stu-id="af6ed-113">END_DONT_RESEND</span></span> 
  
> <span data-ttu-id="af6ed-114">传输提供程序具有现在需要有关此消息的所有信息。</span><span class="sxs-lookup"><span data-stu-id="af6ed-114">The transport provider has all the information it needs about this message for now.</span></span> <span data-ttu-id="af6ed-115">传输提供程序要求的详细信息时，或者它已发送邮件时，它会通知 MAPI 后台处理程序，通过调用带 NOTIFY_SENTDEFERRED 标志的[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法和传递消息的项标识符。</span><span class="sxs-lookup"><span data-stu-id="af6ed-115">When the transport provider requires more information or when it has sent the message, it notifies the MAPI spooler by calling the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method with the NOTIFY_SENTDEFERRED flag and by passing the message's entry identifier.</span></span> 
    
<span data-ttu-id="af6ed-116">END_RESEND_LATER</span><span class="sxs-lookup"><span data-stu-id="af6ed-116">END_RESEND_LATER</span></span> 
  
> <span data-ttu-id="af6ed-117">传输提供程序不条件时发生错误的原因的当前时间在不发送邮件。</span><span class="sxs-lookup"><span data-stu-id="af6ed-117">The transport provider is not sending the message at the current time for reasons that are not error conditions.</span></span> <span data-ttu-id="af6ed-118">传输提供程序应调用再次更高版本来发送邮件。</span><span class="sxs-lookup"><span data-stu-id="af6ed-118">The transport provider should be called again later to send the message.</span></span>
    
<span data-ttu-id="af6ed-119">END_RESEND_NOW</span><span class="sxs-lookup"><span data-stu-id="af6ed-119">END_RESEND_NOW</span></span> 
  
> <span data-ttu-id="af6ed-120">传输提供程序需要重新启动[IMessage::SubmitMessage](imessage-submitmessage.md)方法调用中传递给它的消息。</span><span class="sxs-lookup"><span data-stu-id="af6ed-120">The transport provider needs to restart the message passed to it in an [IMessage::SubmitMessage](imessage-submitmessage.md) method call.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="af6ed-121">返回值</span><span class="sxs-lookup"><span data-stu-id="af6ed-121">Return value</span></span>

<span data-ttu-id="af6ed-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="af6ed-122">S_OK</span></span> 
  
> <span data-ttu-id="af6ed-123">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="af6ed-123">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="af6ed-124">说明</span><span class="sxs-lookup"><span data-stu-id="af6ed-124">Remarks</span></span>

<span data-ttu-id="af6ed-125">完成处理参与提供扩展的传递或原件信息后，MAPI 后台处理程序调用**IXPLogon::EndMessage**方法。</span><span class="sxs-lookup"><span data-stu-id="af6ed-125">The MAPI spooler calls the **IXPLogon::EndMessage** method after it completes the processing involved in providing extended delivery or nondelivery information.</span></span> 
  
<span data-ttu-id="af6ed-126">一旦返回此呼叫，将不再有效此消息的_ulMsgRef_参数中的值。</span><span class="sxs-lookup"><span data-stu-id="af6ed-126">Once this call returns, the value in the  _ulMsgRef_ parameter is no longer valid for this message.</span></span> <span data-ttu-id="af6ed-127">传输提供程序可以重用将来的消息的相同值。</span><span class="sxs-lookup"><span data-stu-id="af6ed-127">The transport provider can reuse the same value on a future message.</span></span> 
  
<span data-ttu-id="af6ed-128">**EndMessage**呼叫返回，除外 MAPI 后台处理程序将传递到传输提供程序的消息对象之前，应释放的邮件传输过程中打开传输提供程序的所有对象。</span><span class="sxs-lookup"><span data-stu-id="af6ed-128">All objects that the transport provider opens during the transfer of a message should be released before the **EndMessage** call returns, with the exception of the message object that the MAPI spooler passes to the transport provider.</span></span> <span data-ttu-id="af6ed-129">Message 对象传递的 MAPI 后台处理程序无效**EndMessage**调用后。</span><span class="sxs-lookup"><span data-stu-id="af6ed-129">The message object passed by the MAPI spooler is invalid after the **EndMessage** call.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="af6ed-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af6ed-130">See also</span></span>



[<span data-ttu-id="af6ed-131">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="af6ed-131">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="af6ed-132">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="af6ed-132">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="af6ed-133">IXPLogon::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="af6ed-133">IXPLogon::SubmitMessage</span></span>](ixplogon-submitmessage.md)
  
[<span data-ttu-id="af6ed-134">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="af6ed-134">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

