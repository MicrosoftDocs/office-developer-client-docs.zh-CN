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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ab92aee6a8254a16c48352e371b711932bbe7427
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775505"
---
# <a name="imapiprogressgetmin"></a><span data-ttu-id="87704-103">IMAPIProgress::GetMin</span><span class="sxs-lookup"><span data-stu-id="87704-103">IMAPIProgress::GetMin</span></span>

  
  
<span data-ttu-id="87704-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="87704-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="87704-105">对于的进度的信息将显示在[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法中返回的最小值。</span><span class="sxs-lookup"><span data-stu-id="87704-105">Returns the minimum value in the [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method for which progress information is displayed.</span></span> 
  
```cpp
HRESULT GetMin(
  ULONG FAR * lpulMin
);
```

## <a name="parameters"></a><span data-ttu-id="87704-106">参数</span><span class="sxs-lookup"><span data-stu-id="87704-106">Parameters</span></span>

 <span data-ttu-id="87704-107">_lpulMin_</span><span class="sxs-lookup"><span data-stu-id="87704-107">_lpulMin_</span></span>
  
> <span data-ttu-id="87704-108">[输出]一个指向操作中的项的最小数目。</span><span class="sxs-lookup"><span data-stu-id="87704-108">[out] A pointer to the minimum number of items in the operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="87704-109">返回值</span><span class="sxs-lookup"><span data-stu-id="87704-109">Return value</span></span>

<span data-ttu-id="87704-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="87704-110">S_OK</span></span> 
  
> <span data-ttu-id="87704-111">已检索的最小操作中的项目数。</span><span class="sxs-lookup"><span data-stu-id="87704-111">The minimum number of items in the operation has been retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="87704-112">备注</span><span class="sxs-lookup"><span data-stu-id="87704-112">Remarks</span></span>

<span data-ttu-id="87704-113">最小值表示数字形式操作的开始。</span><span class="sxs-lookup"><span data-stu-id="87704-113">The minimum value represents the start of the operation in numeric form.</span></span> <span data-ttu-id="87704-114">值可以是全局的最大值，用于表示显示整个进度的范围或本地值，用于表示仅显示的一部分。</span><span class="sxs-lookup"><span data-stu-id="87704-114">The value can be a global maximum value, used to represent the scope of the entire progress display, or a local value, used to represent only a part of the display.</span></span> 
  
<span data-ttu-id="87704-115">是否正在进行对象能够理解的最小值为本地域或全局设置会影响标志的值。</span><span class="sxs-lookup"><span data-stu-id="87704-115">The value of the flag setting affects whether the progress object understands the minimum value to be local or global.</span></span> <span data-ttu-id="87704-116">当设置 MAPI_TOP_LEVEL 标志时，最小值被视为全局和用于计算整个操作的进度。</span><span class="sxs-lookup"><span data-stu-id="87704-116">When the MAPI_TOP_LEVEL flag is set, the minimum value is considered to be global and is used to calculate progress for the entire operation.</span></span> <span data-ttu-id="87704-117">时未设置 MAPI_TOP_LEVEL，最小值被视为本地，并提供程序将其内部来显示较低级别的子对象的进度。</span><span class="sxs-lookup"><span data-stu-id="87704-117">When MAPI_TOP_LEVEL is not set, the minimum value is considered local, and providers use it internally to display progress for lower level subobjects.</span></span> <span data-ttu-id="87704-118">进度对象保存仅使它返回到通过**GetMin**呼叫提供程序的本地最小值。</span><span class="sxs-lookup"><span data-stu-id="87704-118">Progress objects save the local minimum value only to return it to a provider through a **GetMin** call.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="87704-119">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="87704-119">Notes to implementers</span></span>

<span data-ttu-id="87704-120">初始化的最小值为 1。</span><span class="sxs-lookup"><span data-stu-id="87704-120">Initialize the minimum value to 1.</span></span> <span data-ttu-id="87704-121">服务提供商可以通过调用**IMAPIProgress::SetLimits**方法重置此值。</span><span class="sxs-lookup"><span data-stu-id="87704-121">Service providers can reset this value by calling the **IMAPIProgress::SetLimits** method.</span></span> <span data-ttu-id="87704-122">有关如何实施**GetMin**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="87704-122">For more information about how to implement **GetMin** and the other [IMAPIProgress](imapiprogressiunknown.md) methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
<span data-ttu-id="87704-123">有关详细了解如何以及何时调用进度对象，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="87704-123">For more information about how and when to make calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="87704-124">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="87704-124">MFCMAPI reference</span></span>

<span data-ttu-id="87704-125">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="87704-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="87704-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="87704-126">**File**</span></span>|<span data-ttu-id="87704-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="87704-127">**Function**</span></span>|<span data-ttu-id="87704-128">**Comment**</span><span class="sxs-lookup"><span data-stu-id="87704-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="87704-129">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="87704-129">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="87704-130">CMAPIProgress::GetMin</span><span class="sxs-lookup"><span data-stu-id="87704-130">CMAPIProgress::GetMin</span></span>  <br/> |<span data-ttu-id="87704-131">MFCMAPI 使用**IMAPIProgress::GetMin**方法获取进度指示器的最小值。</span><span class="sxs-lookup"><span data-stu-id="87704-131">MFCMAPI uses the **IMAPIProgress::GetMin** method to get the minimum value for the progress indicator.</span></span> <span data-ttu-id="87704-132">除非限制先前已设置通过调用**IMAPIProgress::SetLimits**方法会返回 1。</span><span class="sxs-lookup"><span data-stu-id="87704-132">Returns 1 unless limits have been previously set by calling the **IMAPIProgress::SetLimits** method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="87704-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87704-133">See also</span></span>



[<span data-ttu-id="87704-134">IMAPIProgress::GetMax</span><span class="sxs-lookup"><span data-stu-id="87704-134">IMAPIProgress::GetMax</span></span>](imapiprogress-getmax.md)
  
[<span data-ttu-id="87704-135">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="87704-135">IMAPIProgress::Progress</span></span>](imapiprogress-progress.md)
  
[<span data-ttu-id="87704-136">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="87704-136">IMAPIProgress::SetLimits</span></span>](imapiprogress-setlimits.md)
  
[<span data-ttu-id="87704-137">IMAPIProgress: IUnknown</span><span class="sxs-lookup"><span data-stu-id="87704-137">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="87704-138">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="87704-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="87704-139">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="87704-139">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="87704-140">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="87704-140">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

