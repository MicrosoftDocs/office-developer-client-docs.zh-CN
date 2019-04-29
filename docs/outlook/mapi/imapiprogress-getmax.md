---
title: IMAPIProgressGetMax
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.GetMax
api_type:
- COM
ms.assetid: 88a910ed-b55a-4e5b-a43d-eb3ea795a70e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 64b6235151c7700a24992bc1d4394553a53c0464
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436200"
---
# <a name="imapiprogressgetmax"></a><span data-ttu-id="c3177-103">IMAPIProgress::GetMax</span><span class="sxs-lookup"><span data-stu-id="c3177-103">IMAPIProgress::GetMax</span></span>

  
  
<span data-ttu-id="c3177-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c3177-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c3177-105">返回显示其进度信息的操作中的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="c3177-105">Returns the maximum number of items in the operation for which progress information is displayed.</span></span>
  
```cpp
HRESULT GetMax(
  ULONG FAR * lpulMax
);
```

## <a name="parameters"></a><span data-ttu-id="c3177-106">参数</span><span class="sxs-lookup"><span data-stu-id="c3177-106">Parameters</span></span>

 <span data-ttu-id="c3177-107">_lpulMax_</span><span class="sxs-lookup"><span data-stu-id="c3177-107">_lpulMax_</span></span>
  
> <span data-ttu-id="c3177-108">排除一个指针, 指向操作中的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="c3177-108">[out] A pointer to the maximum number of items in the operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c3177-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c3177-109">Return value</span></span>

<span data-ttu-id="c3177-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3177-110">S_OK</span></span> 
  
> <span data-ttu-id="c3177-111">已检索到操作中的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="c3177-111">The maximum number of items in the operation has been retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c3177-112">说明</span><span class="sxs-lookup"><span data-stu-id="c3177-112">Remarks</span></span>

<span data-ttu-id="c3177-113">最大值表示以数字形式的运算的结束。</span><span class="sxs-lookup"><span data-stu-id="c3177-113">The maximum value represents the end of the operation in numeric form.</span></span> <span data-ttu-id="c3177-114">该值可以是全局最大值，用于表示整个进度显示的范围，也可以是本地值，用于仅表示显示的一部分。</span><span class="sxs-lookup"><span data-stu-id="c3177-114">The value can be a global maximum value, used to represent the scope of the entire progress display, or a local value, used to represent only a part of the display.</span></span> 
  
<span data-ttu-id="c3177-115">标记设置的值影响进度对象是否理解为本地或全局的最大值。</span><span class="sxs-lookup"><span data-stu-id="c3177-115">The value of the flag setting affects whether the progress object understands the maximum value to be local or global.</span></span> <span data-ttu-id="c3177-116">设置 MAPI_TOP_LEVEL 标志后, 最大值将被视为全局值, 用于计算整个操作的进度。</span><span class="sxs-lookup"><span data-stu-id="c3177-116">When the MAPI_TOP_LEVEL flag is set, the maximum value is considered to be global and is used to calculate progress for the entire operation.</span></span> <span data-ttu-id="c3177-117">如果未设置 MAPI_TOP_LEVEL, 则将最大值视为本地, 并且提供程序在内部使用它来显示较低级别子集的进度。</span><span class="sxs-lookup"><span data-stu-id="c3177-117">When MAPI_TOP_LEVEL is not set, the maximum value is considered to be local, and providers use it internally to display progress for lower level subobjects.</span></span> <span data-ttu-id="c3177-118">进度对象仅保存本地最大值, 以通过**GetMax**调用将其返回给提供程序。</span><span class="sxs-lookup"><span data-stu-id="c3177-118">Progress objects save the local maximum value only to return it to a provider through a **GetMax** call.</span></span> 
  
<span data-ttu-id="c3177-119">有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="c3177-119">For more information about how and when to make calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="c3177-120">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="c3177-120">Notes to implementers</span></span>

<span data-ttu-id="c3177-121">将最大值初始化为1000。</span><span class="sxs-lookup"><span data-stu-id="c3177-121">Initialize the maximum value to 1000.</span></span> <span data-ttu-id="c3177-122">服务提供程序可以通过调用 [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) 方法重置此值。</span><span class="sxs-lookup"><span data-stu-id="c3177-122">Service providers can reset this value by calling the [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method.</span></span> <span data-ttu-id="c3177-123">有关如何实现**GetMax**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息, 请参阅[实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="c3177-123">For more information about how to implement **GetMax** and the other [IMAPIProgress](imapiprogressiunknown.md) methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c3177-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c3177-124">MFCMAPI reference</span></span>

<span data-ttu-id="c3177-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c3177-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c3177-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="c3177-126">**File**</span></span>|<span data-ttu-id="c3177-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="c3177-127">**Function**</span></span>|<span data-ttu-id="c3177-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="c3177-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3177-129">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="c3177-129">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="c3177-130">CMAPIProgress:: GetMax</span><span class="sxs-lookup"><span data-stu-id="c3177-130">CMAPIProgress::GetMax</span></span>  <br/> |<span data-ttu-id="c3177-131">MFCMAPI 使用**IMAPIProgress:: GetMax**方法获取进度对象的最大值。</span><span class="sxs-lookup"><span data-stu-id="c3177-131">MFCMAPI uses the **IMAPIProgress::GetMax** method to get the maximum value for the progress object.</span></span> <span data-ttu-id="c3177-132">返回 1000, 除非以前使用**IMAPIProgress:: SetLimits**方法设置了限制。</span><span class="sxs-lookup"><span data-stu-id="c3177-132">Returns 1000 unless limits have previously been set with the **IMAPIProgress::SetLimits** method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c3177-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3177-133">See also</span></span>



[<span data-ttu-id="c3177-134">IMAPIProgress::GetMin</span><span class="sxs-lookup"><span data-stu-id="c3177-134">IMAPIProgress::GetMin</span></span>](imapiprogress-getmin.md)
  
[<span data-ttu-id="c3177-135">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="c3177-135">IMAPIProgress::Progress</span></span>](imapiprogress-progress.md)
  
[<span data-ttu-id="c3177-136">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="c3177-136">IMAPIProgress::SetLimits</span></span>](imapiprogress-setlimits.md)
  
[<span data-ttu-id="c3177-137">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c3177-137">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="c3177-138">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c3177-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="c3177-139">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="c3177-139">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="c3177-140">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="c3177-140">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

