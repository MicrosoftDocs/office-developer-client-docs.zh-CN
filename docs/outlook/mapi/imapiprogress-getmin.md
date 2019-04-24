---
title: IMAPIProgressGetMin
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.GetMin
api_type:
- COM
ms.assetid: caceddf1-0f7c-47b5-97bf-17ffe3440a6c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cd31f8ac713c21053db7ef461220a360ebeec74
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331680"
---
# <a name="imapiprogressgetmin"></a><span data-ttu-id="bc9d3-103">IMAPIProgress::GetMin</span><span class="sxs-lookup"><span data-stu-id="bc9d3-103">IMAPIProgress::GetMin</span></span>

  
  
<span data-ttu-id="bc9d3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc9d3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc9d3-105">在显示其进度信息的 [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) 方法中返回最小值。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-105">Returns the minimum value in the [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method for which progress information is displayed.</span></span> 
  
```cpp
HRESULT GetMin(
  ULONG FAR * lpulMin
);
```

## <a name="parameters"></a><span data-ttu-id="bc9d3-106">参数</span><span class="sxs-lookup"><span data-stu-id="bc9d3-106">Parameters</span></span>

 <span data-ttu-id="bc9d3-107">_lpulMin_</span><span class="sxs-lookup"><span data-stu-id="bc9d3-107">_lpulMin_</span></span>
  
> <span data-ttu-id="bc9d3-108">[out] 指向操作中项数目最小值的指针。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-108">[out] A pointer to the minimum number of items in the operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bc9d3-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bc9d3-109">Return value</span></span>

<span data-ttu-id="bc9d3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc9d3-110">S_OK</span></span> 
  
> <span data-ttu-id="bc9d3-111">已检索到操作中项数目最小值。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-111">The minimum number of items in the operation has been retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bc9d3-112">备注</span><span class="sxs-lookup"><span data-stu-id="bc9d3-112">Remarks</span></span>

<span data-ttu-id="bc9d3-113">最小值表示在数值窗体中操作的开始。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-113">The minimum value represents the start of the operation in numeric form.</span></span> <span data-ttu-id="bc9d3-114">该值可以是全局最大值，用于表示整个进度显示的范围，也可以是本地值，用于仅表示显示的一部分。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-114">The value can be a global maximum value, used to represent the scope of the entire progress display, or a local value, used to represent only a part of the display.</span></span> 
  
<span data-ttu-id="bc9d3-115">标记设置的值会影响进度对象是将最小值理解为本地最小值还是全局最小值。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-115">The value of the flag setting affects whether the progress object understands the minimum value to be local or global.</span></span> <span data-ttu-id="bc9d3-116">设置 MAPI_TOP_LEVEL 标记时，将最小值视为全局最小值，用于计算整个操作的进度。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-116">When the MAPI_TOP_LEVEL flag is set, the minimum value is considered to be global and is used to calculate progress for the entire operation.</span></span> <span data-ttu-id="bc9d3-117">如果未设置 MAPI_TOP_LEVEL，则将最小值视为本地最小值，并且提供程序在内部使用它来显示较低级别子对象的进度。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-117">When MAPI_TOP_LEVEL is not set, the minimum value is considered local, and providers use it internally to display progress for lower level subobjects.</span></span> <span data-ttu-id="bc9d3-118">进度对象仅保存本地最小值，以通过 **GetMin** 调用将其返回给提供程序。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-118">Progress objects save the local minimum value only to return it to a provider through a **GetMin** call.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="bc9d3-119">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="bc9d3-119">Notes to implementers</span></span>

<span data-ttu-id="bc9d3-120">将最小值初始化为 1。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-120">Initialize the minimum value to 1.</span></span> <span data-ttu-id="bc9d3-121">服务提供程序可以通过调用 **IMAPIProgress::SetLimits** 方法重置此值。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-121">Service providers can reset this value by calling the **IMAPIProgress::SetLimits** method.</span></span> <span data-ttu-id="bc9d3-122">有关如何实现 **GetMin** 和其他 [IMAPIProgress](imapiprogressiunknown.md) 方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-122">For more information about how to implement **GetMin** and the other [IMAPIProgress](imapiprogressiunknown.md) methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
<span data-ttu-id="bc9d3-123">有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-123">For more information about how and when to make calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="bc9d3-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="bc9d3-124">MFCMAPI reference</span></span>

<span data-ttu-id="bc9d3-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="bc9d3-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="bc9d3-126">**File**</span></span>|<span data-ttu-id="bc9d3-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="bc9d3-127">**Function**</span></span>|<span data-ttu-id="bc9d3-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="bc9d3-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bc9d3-129">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="bc9d3-129">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="bc9d3-130">CMAPIProgress::GetMin</span><span class="sxs-lookup"><span data-stu-id="bc9d3-130">CMAPIProgress::GetMin</span></span>  <br/> |<span data-ttu-id="bc9d3-131">MFCMAPI 使用 **IMAPIProgress::GetMin** 方法获取进度指示器的最小值。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-131">MFCMAPI uses the **IMAPIProgress::GetMin** method to get the minimum value for the progress indicator.</span></span> <span data-ttu-id="bc9d3-132">除非之前通过调用 **IMAPIProgress::SetLimits** 方法设置了限制，否则返回 1。</span><span class="sxs-lookup"><span data-stu-id="bc9d3-132">Returns 1 unless limits have been previously set by calling the **IMAPIProgress::SetLimits** method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bc9d3-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc9d3-133">See also</span></span>



[<span data-ttu-id="bc9d3-134">IMAPIProgress::GetMax</span><span class="sxs-lookup"><span data-stu-id="bc9d3-134">IMAPIProgress::GetMax</span></span>](imapiprogress-getmax.md)
  
[<span data-ttu-id="bc9d3-135">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="bc9d3-135">IMAPIProgress::Progress</span></span>](imapiprogress-progress.md)
  
[<span data-ttu-id="bc9d3-136">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="bc9d3-136">IMAPIProgress::SetLimits</span></span>](imapiprogress-setlimits.md)
  
[<span data-ttu-id="bc9d3-137">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bc9d3-137">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="bc9d3-138">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="bc9d3-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="bc9d3-139">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="bc9d3-139">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="bc9d3-140">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="bc9d3-140">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

