---
title: IMAPISupportStatusRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.StatusRecips
api_type:
- COM
ms.assetid: 9c34538e-5ba4-47c8-8002-85afa9d6c067
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 39d8786bf558ade4599d69e0a764f87fe60d99f3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408766"
---
# <a name="imapisupportstatusrecips"></a><span data-ttu-id="4579d-103">IMAPISupport::StatusRecips</span><span class="sxs-lookup"><span data-stu-id="4579d-103">IMAPISupport::StatusRecips</span></span>

  
  
<span data-ttu-id="4579d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4579d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4579d-105">生成送达和未送达报告。</span><span class="sxs-lookup"><span data-stu-id="4579d-105">Generates delivery and nondelivery reports.</span></span>
  
```cpp
HRESULT StatusRecips(
LPMESSAGE lpMessage,
LPADRLIST lpRecipList
);
```

## <a name="parameters"></a><span data-ttu-id="4579d-106">参数</span><span class="sxs-lookup"><span data-stu-id="4579d-106">Parameters</span></span>

 <span data-ttu-id="4579d-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="4579d-107">_lpMessage_</span></span>
  
> <span data-ttu-id="4579d-108">[in]指向应生成报告的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="4579d-108">[in] A pointer to the message for which the report should be generated.</span></span>
    
 <span data-ttu-id="4579d-109">_lpRecipList_</span><span class="sxs-lookup"><span data-stu-id="4579d-109">_lpRecipList_</span></span>
  
> <span data-ttu-id="4579d-110">[in]指向 [ADRLIST](adrlist.md) 结构的指针，该结构描述  _lpMessage 指向的邮件的收件人_。</span><span class="sxs-lookup"><span data-stu-id="4579d-110">[in] A pointer to an [ADRLIST](adrlist.md) structure that describes the recipients of the message pointed to by  _lpMessage_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4579d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4579d-111">Return value</span></span>

<span data-ttu-id="4579d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4579d-112">S_OK</span></span> 
  
> <span data-ttu-id="4579d-113">报告已成功生成。</span><span class="sxs-lookup"><span data-stu-id="4579d-113">The report was successfully generated.</span></span>
    
<span data-ttu-id="4579d-114">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="4579d-114">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="4579d-115">呼叫整体成功，但此类型的收件人没有收件人选项。</span><span class="sxs-lookup"><span data-stu-id="4579d-115">The call succeeded overall, but there are no recipient options for this type of recipient.</span></span> <span data-ttu-id="4579d-116">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="4579d-116">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="4579d-117">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="4579d-117">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="4579d-118">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="4579d-118">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4579d-119">备注</span><span class="sxs-lookup"><span data-stu-id="4579d-119">Remarks</span></span>

<span data-ttu-id="4579d-120">**IMAPISupport：：StatusRecips** 方法为传输提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="4579d-120">The **IMAPISupport::StatusRecips** method is implemented for transport provider support objects.</span></span> <span data-ttu-id="4579d-121">传输提供程序调用 **StatusRecips** 以请求 MAPI 将传递或非送达报告发送给一组邮件的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="4579d-121">Transport providers call **StatusRecips** to request that MAPI send a delivery or nondelivery report to a set of one or more of the recipients of a message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="4579d-122">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="4579d-122">Notes to callers</span></span>

<span data-ttu-id="4579d-123">在处理邮件 **期间，可以多次调用 StatusRecips。**</span><span class="sxs-lookup"><span data-stu-id="4579d-123">You can call **StatusRecips** multiple times during the processing of a message.</span></span> <span data-ttu-id="4579d-124">但是，如果为打开的邮件调用 **StatusRecips，** 请尽力收集邮件收件人的所有传递和未送达信息，并呼叫该收件人列表的 **StatusRecips。**</span><span class="sxs-lookup"><span data-stu-id="4579d-124">However, if you call **StatusRecips** for an open message, do your best to collect all delivery and nondelivery information for the message recipients and call **StatusRecips** for that recipient list.</span></span> <span data-ttu-id="4579d-125">一个集合点很重要，因为对一个收件人的多个 **StatusRecips** 调用可能会导致发送多个相同的报告。</span><span class="sxs-lookup"><span data-stu-id="4579d-125">A single point of collection is important, because multiple **StatusRecips** calls for one recipient can result in multiple identical reports being sent.</span></span> 
  
<span data-ttu-id="4579d-126">将与邮件传递或非送达相关的属性存储在 _由 lpRecipList_ 参数指示的 **ADRLIST** 结构中。</span><span class="sxs-lookup"><span data-stu-id="4579d-126">Store properties that relate to message delivery or nondelivery in the **ADRLIST** structure indicated by the  _lpRecipList_ parameter.</span></span> <span data-ttu-id="4579d-127">有关送达报告和未送达报告的必需属性和可选属性的完整列表，请参阅 Required Report [Message Properties](required-report-message-properties.md)和[Optional Report Message Properties。](optional-report-message-properties.md)</span><span class="sxs-lookup"><span data-stu-id="4579d-127">For a complete list of required and optional properties for delivery reports and nondelivery reports, see [Required Report Message Properties](required-report-message-properties.md) and [Optional Report Message Properties](optional-report-message-properties.md).</span></span> 
  
<span data-ttu-id="4579d-128">使用 [MAPIAllocateBuffer](mapiallocatebuffer.md)和 [MAPIAllocateMore](mapiallocatemore.md)函数为 _lpRecipList_ 中的 **ADRLIST** 结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="4579d-128">Allocate memory for the **ADRLIST** structure in  _lpRecipList_ by using the [MAPIAllocateBuffer](mapiallocatebuffer.md) and [MAPIAllocateMore](mapiallocatemore.md) functions.</span></span> <span data-ttu-id="4579d-129">MAPI 仅在 **StatusRecips** 成功时通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放内存。</span><span class="sxs-lookup"><span data-stu-id="4579d-129">MAPI releases the memory by calling the [MAPIFreeBuffer](mapifreebuffer.md) function only if **StatusRecips** succeeds.</span></span> 
  
<span data-ttu-id="4579d-130">有关送达和未送达报告的概述，请参阅 [MAPI Report Messages](mapi-report-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="4579d-130">For an overview of delivery and nondelivery reports, see [MAPI Report Messages](mapi-report-messages.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4579d-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4579d-131">See also</span></span>



[<span data-ttu-id="4579d-132">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="4579d-132">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="4579d-133">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="4579d-133">IMAPISupport::Address</span></span>](imapisupport-address.md)
  
[<span data-ttu-id="4579d-134">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="4579d-134">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="4579d-135">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="4579d-135">IXPLogon::EndMessage</span></span>](ixplogon-endmessage.md)
  
[<span data-ttu-id="4579d-136">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="4579d-136">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="4579d-137">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="4579d-137">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="4579d-138">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="4579d-138">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="4579d-139">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4579d-139">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

