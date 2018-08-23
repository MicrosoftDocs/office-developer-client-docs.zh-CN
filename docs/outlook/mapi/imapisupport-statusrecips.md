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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cda629cf78d3f7915b64c130867ed4f8ebbd6f8d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563840"
---
# <a name="imapisupportstatusrecips"></a><span data-ttu-id="7f87e-103">IMAPISupport::StatusRecips</span><span class="sxs-lookup"><span data-stu-id="7f87e-103">IMAPISupport::StatusRecips</span></span>

  
  
<span data-ttu-id="7f87e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7f87e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7f87e-105">生成送达和原件报告。</span><span class="sxs-lookup"><span data-stu-id="7f87e-105">Generates delivery and nondelivery reports.</span></span>
  
```cpp
HRESULT StatusRecips(
LPMESSAGE lpMessage,
LPADRLIST lpRecipList
);
```

## <a name="parameters"></a><span data-ttu-id="7f87e-106">参数</span><span class="sxs-lookup"><span data-stu-id="7f87e-106">Parameters</span></span>

 <span data-ttu-id="7f87e-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="7f87e-107">_lpMessage_</span></span>
  
> <span data-ttu-id="7f87e-108">[in]一个指向应为其生成报告的邮件。</span><span class="sxs-lookup"><span data-stu-id="7f87e-108">[in] A pointer to the message for which the report should be generated.</span></span>
    
 <span data-ttu-id="7f87e-109">_lpRecipList_</span><span class="sxs-lookup"><span data-stu-id="7f87e-109">_lpRecipList_</span></span>
  
> <span data-ttu-id="7f87e-110">[in]由_lpMessage_指向指向介绍邮件的收件人[ADRLIST](adrlist.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="7f87e-110">[in] A pointer to an [ADRLIST](adrlist.md) structure that describes the recipients of the message pointed to by  _lpMessage_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7f87e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7f87e-111">Return value</span></span>

<span data-ttu-id="7f87e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f87e-112">S_OK</span></span> 
  
> <span data-ttu-id="7f87e-113">成功生成报告。</span><span class="sxs-lookup"><span data-stu-id="7f87e-113">The report was successfully generated.</span></span>
    
<span data-ttu-id="7f87e-114">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="7f87e-114">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="7f87e-115">调用成功总体上讲，但没有这种类型的收件人的收件人的选项。</span><span class="sxs-lookup"><span data-stu-id="7f87e-115">The call succeeded overall, but there are no recipient options for this type of recipient.</span></span> <span data-ttu-id="7f87e-116">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="7f87e-116">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="7f87e-117">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="7f87e-117">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="7f87e-118">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="7f87e-118">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7f87e-119">注解</span><span class="sxs-lookup"><span data-stu-id="7f87e-119">Remarks</span></span>

<span data-ttu-id="7f87e-120">对于传输提供程序支持对象实现**IMAPISupport::StatusRecips**方法。</span><span class="sxs-lookup"><span data-stu-id="7f87e-120">The **IMAPISupport::StatusRecips** method is implemented for transport provider support objects.</span></span> <span data-ttu-id="7f87e-121">传输提供程序调用**StatusRecips**请求的 MAPI 发送到一组一个或多个收件人的邮件的传递或原件报表。</span><span class="sxs-lookup"><span data-stu-id="7f87e-121">Transport providers call **StatusRecips** to request that MAPI send a delivery or nondelivery report to a set of one or more of the recipients of a message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="7f87e-122">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7f87e-122">Notes to callers</span></span>

<span data-ttu-id="7f87e-123">您可以一条消息处理过程中调用**StatusRecips**多次。</span><span class="sxs-lookup"><span data-stu-id="7f87e-123">You can call **StatusRecips** multiple times during the processing of a message.</span></span> <span data-ttu-id="7f87e-124">但是，如果您调用**StatusRecips**打开邮件时，进行收集信息传递和原件所有邮件的收件人，并对该收件人列表调用**StatusRecips**您最佳。</span><span class="sxs-lookup"><span data-stu-id="7f87e-124">However, if you call **StatusRecips** for an open message, do your best to collect all delivery and nondelivery information for the message recipients and call **StatusRecips** for that recipient list.</span></span> <span data-ttu-id="7f87e-125">因为有一个收件人的多个**StatusRecips**呼叫会发送的多个相同的报告，很重要，单点的集合。</span><span class="sxs-lookup"><span data-stu-id="7f87e-125">A single point of collection is important, because multiple **StatusRecips** calls for one recipient can result in multiple identical reports being sent.</span></span> 
  
<span data-ttu-id="7f87e-126">存储与邮件传递或原件_lpRecipList_参数指示**ADRLIST**结构中的相关的属性。</span><span class="sxs-lookup"><span data-stu-id="7f87e-126">Store properties that relate to message delivery or nondelivery in the **ADRLIST** structure indicated by the  _lpRecipList_ parameter.</span></span> <span data-ttu-id="7f87e-127">送达报告和未送达报告的必需的和可选属性的完整列表，请参阅[所需的报表消息属性](required-report-message-properties.md)和[可选的报表消息属性](optional-report-message-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7f87e-127">For a complete list of required and optional properties for delivery reports and nondelivery reports, see [Required Report Message Properties](required-report-message-properties.md) and [Optional Report Message Properties](optional-report-message-properties.md).</span></span> 
  
<span data-ttu-id="7f87e-128">使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIAllocateMore](mapiallocatemore.md)函数为_lpRecipList_的**ADRLIST**结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="7f87e-128">Allocate memory for the **ADRLIST** structure in  _lpRecipList_ by using the [MAPIAllocateBuffer](mapiallocatebuffer.md) and [MAPIAllocateMore](mapiallocatemore.md) functions.</span></span> <span data-ttu-id="7f87e-129">MAPI 通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数，仅当**StatusRecips**成功释放内存。</span><span class="sxs-lookup"><span data-stu-id="7f87e-129">MAPI releases the memory by calling the [MAPIFreeBuffer](mapifreebuffer.md) function only if **StatusRecips** succeeds.</span></span> 
  
<span data-ttu-id="7f87e-130">送达和原件报告的概述，请参阅[MAPI 报告消息](mapi-report-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="7f87e-130">For an overview of delivery and nondelivery reports, see [MAPI Report Messages](mapi-report-messages.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7f87e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f87e-131">See also</span></span>



[<span data-ttu-id="7f87e-132">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="7f87e-132">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="7f87e-133">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="7f87e-133">IMAPISupport::Address</span></span>](imapisupport-address.md)
  
[<span data-ttu-id="7f87e-134">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="7f87e-134">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="7f87e-135">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="7f87e-135">IXPLogon::EndMessage</span></span>](ixplogon-endmessage.md)
  
[<span data-ttu-id="7f87e-136">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="7f87e-136">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="7f87e-137">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="7f87e-137">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="7f87e-138">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="7f87e-138">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="7f87e-139">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7f87e-139">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

