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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341767"
---
# <a name="imapisupportstatusrecips"></a><span data-ttu-id="ca29c-103">IMAPISupport::StatusRecips</span><span class="sxs-lookup"><span data-stu-id="ca29c-103">IMAPISupport::StatusRecips</span></span>

  
  
<span data-ttu-id="ca29c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca29c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca29c-105">生成传递和 nondelivery 报告。</span><span class="sxs-lookup"><span data-stu-id="ca29c-105">Generates delivery and nondelivery reports.</span></span>
  
```cpp
HRESULT StatusRecips(
LPMESSAGE lpMessage,
LPADRLIST lpRecipList
);
```

## <a name="parameters"></a><span data-ttu-id="ca29c-106">参数</span><span class="sxs-lookup"><span data-stu-id="ca29c-106">Parameters</span></span>

 <span data-ttu-id="ca29c-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="ca29c-107">_lpMessage_</span></span>
  
> <span data-ttu-id="ca29c-108">实时指向应为其生成报告的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="ca29c-108">[in] A pointer to the message for which the report should be generated.</span></span>
    
 <span data-ttu-id="ca29c-109">_lpRecipList_</span><span class="sxs-lookup"><span data-stu-id="ca29c-109">_lpRecipList_</span></span>
  
> <span data-ttu-id="ca29c-110">实时一个指向[ADRLIST](adrlist.md)结构的指针, 该结构描述_lpMessage_指向的邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="ca29c-110">[in] A pointer to an [ADRLIST](adrlist.md) structure that describes the recipients of the message pointed to by  _lpMessage_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ca29c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ca29c-111">Return value</span></span>

<span data-ttu-id="ca29c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca29c-112">S_OK</span></span> 
  
> <span data-ttu-id="ca29c-113">已成功生成报告。</span><span class="sxs-lookup"><span data-stu-id="ca29c-113">The report was successfully generated.</span></span>
    
<span data-ttu-id="ca29c-114">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="ca29c-114">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="ca29c-115">呼叫全部成功, 但此类型的收件人没有收件人选项。</span><span class="sxs-lookup"><span data-stu-id="ca29c-115">The call succeeded overall, but there are no recipient options for this type of recipient.</span></span> <span data-ttu-id="ca29c-116">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="ca29c-116">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="ca29c-117">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="ca29c-117">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="ca29c-118">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="ca29c-118">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ca29c-119">注解</span><span class="sxs-lookup"><span data-stu-id="ca29c-119">Remarks</span></span>

<span data-ttu-id="ca29c-120">为传输提供程序支持对象实现了**IMAPISupport:: StatusRecips**方法。</span><span class="sxs-lookup"><span data-stu-id="ca29c-120">The **IMAPISupport::StatusRecips** method is implemented for transport provider support objects.</span></span> <span data-ttu-id="ca29c-121">传输提供程序调用**StatusRecips**以请求 MAPI 向一组或多封邮件的一个或多个收件人发送传递或 nondelivery 报告。</span><span class="sxs-lookup"><span data-stu-id="ca29c-121">Transport providers call **StatusRecips** to request that MAPI send a delivery or nondelivery report to a set of one or more of the recipients of a message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="ca29c-122">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ca29c-122">Notes to callers</span></span>

<span data-ttu-id="ca29c-123">在邮件处理过程中, 可以多次调用**StatusRecips** 。</span><span class="sxs-lookup"><span data-stu-id="ca29c-123">You can call **StatusRecips** multiple times during the processing of a message.</span></span> <span data-ttu-id="ca29c-124">但是, 如果您为打开的邮件调用**StatusRecips** , 则最好收集邮件收件人的所有传递和 nondelivery 信息, 并为该收件人列表调用**StatusRecips** 。</span><span class="sxs-lookup"><span data-stu-id="ca29c-124">However, if you call **StatusRecips** for an open message, do your best to collect all delivery and nondelivery information for the message recipients and call **StatusRecips** for that recipient list.</span></span> <span data-ttu-id="ca29c-125">单点集合非常重要, 因为对一个收件人的多个**StatusRecips**调用可能会导致发送多个相同的报告。</span><span class="sxs-lookup"><span data-stu-id="ca29c-125">A single point of collection is important, because multiple **StatusRecips** calls for one recipient can result in multiple identical reports being sent.</span></span> 
  
<span data-ttu-id="ca29c-126">与_lpRecipList_参数指示的**ADRLIST**结构中的邮件传递或 nondelivery 相关的存储属性。</span><span class="sxs-lookup"><span data-stu-id="ca29c-126">Store properties that relate to message delivery or nondelivery in the **ADRLIST** structure indicated by the  _lpRecipList_ parameter.</span></span> <span data-ttu-id="ca29c-127">有关送达报告和 nondelivery 报告的必需属性和可选属性的完整列表, 请参阅[必需的报告邮件属性](required-report-message-properties.md)和[可选的报告邮件属性](optional-report-message-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="ca29c-127">For a complete list of required and optional properties for delivery reports and nondelivery reports, see [Required Report Message Properties](required-report-message-properties.md) and [Optional Report Message Properties](optional-report-message-properties.md).</span></span> 
  
<span data-ttu-id="ca29c-128">使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIAllocateMore](mapiallocatemore.md)函数为_lpRecipList_中的**ADRLIST**结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="ca29c-128">Allocate memory for the **ADRLIST** structure in  _lpRecipList_ by using the [MAPIAllocateBuffer](mapiallocatebuffer.md) and [MAPIAllocateMore](mapiallocatemore.md) functions.</span></span> <span data-ttu-id="ca29c-129">MAPI 仅在**StatusRecips**成功时调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 从而释放内存。</span><span class="sxs-lookup"><span data-stu-id="ca29c-129">MAPI releases the memory by calling the [MAPIFreeBuffer](mapifreebuffer.md) function only if **StatusRecips** succeeds.</span></span> 
  
<span data-ttu-id="ca29c-130">有关传递和 nondelivery 报告的概述, 请参阅[MAPI 报告邮件](mapi-report-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="ca29c-130">For an overview of delivery and nondelivery reports, see [MAPI Report Messages](mapi-report-messages.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ca29c-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca29c-131">See also</span></span>



[<span data-ttu-id="ca29c-132">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="ca29c-132">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="ca29c-133">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="ca29c-133">IMAPISupport::Address</span></span>](imapisupport-address.md)
  
[<span data-ttu-id="ca29c-134">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="ca29c-134">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
  
[<span data-ttu-id="ca29c-135">IXPLogon::EndMessage</span><span class="sxs-lookup"><span data-stu-id="ca29c-135">IXPLogon::EndMessage</span></span>](ixplogon-endmessage.md)
  
[<span data-ttu-id="ca29c-136">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="ca29c-136">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="ca29c-137">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="ca29c-137">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="ca29c-138">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="ca29c-138">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="ca29c-139">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ca29c-139">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

