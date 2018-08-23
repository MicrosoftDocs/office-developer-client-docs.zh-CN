---
title: IMAPIProgressSetLimits
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.SetLimits
api_type:
- COM
ms.assetid: 63c9e316-ee53-4065-8154-449639643ff7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 010f69b70324d4280a34d2fe06d670e07d922d86
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586772"
---
# <a name="imapiprogresssetlimits"></a><span data-ttu-id="54353-103">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="54353-103">IMAPIProgress::SetLimits</span></span>

  
  
<span data-ttu-id="54353-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="54353-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="54353-105">设置项的数目的上限和下限限制中操作，并且控制操作的进度信息的计算方式的标志。</span><span class="sxs-lookup"><span data-stu-id="54353-105">Sets the lower and upper limits for the number of items in the operation, and the flags that control how progress information is calculated for the operation.</span></span>
  
```cpp
HRESULT SetLimits(
  LPULONG lpulMin,
  LPULONG lpulMax,
  LPULONG lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="54353-106">参数</span><span class="sxs-lookup"><span data-stu-id="54353-106">Parameters</span></span>

 <span data-ttu-id="54353-107">_lpulMin_</span><span class="sxs-lookup"><span data-stu-id="54353-107">_lpulMin_</span></span>
  
> <span data-ttu-id="54353-108">[in]指向包含操作中的项目的下限变量的指针。</span><span class="sxs-lookup"><span data-stu-id="54353-108">[in] A pointer to a variable that contains the lower limit of items in the operation.</span></span>
    
 <span data-ttu-id="54353-109">_lpulMax_</span><span class="sxs-lookup"><span data-stu-id="54353-109">_lpulMax_</span></span>
  
> <span data-ttu-id="54353-110">[in]指向包含操作中的项目的上限变量的指针。</span><span class="sxs-lookup"><span data-stu-id="54353-110">[in] A pointer to a variable that contains the upper limit of items in the operation.</span></span>
    
 <span data-ttu-id="54353-111">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="54353-111">_lpulFlags_</span></span>
  
> <span data-ttu-id="54353-112">[in]位掩码的标志控制级别的操作的进度信息的计算公式的。</span><span class="sxs-lookup"><span data-stu-id="54353-112">[in] A bitmask of flags that controls the level of operation on which progress information is calculated.</span></span> <span data-ttu-id="54353-113">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="54353-113">The following flag can be set:</span></span>
    
<span data-ttu-id="54353-114">MAPI_TOP_LEVEL</span><span class="sxs-lookup"><span data-stu-id="54353-114">MAPI_TOP_LEVEL</span></span> 
  
> <span data-ttu-id="54353-115">[IMAPIProgress::Progress](imapiprogress-progress.md)方法的_ulCount_和_ulTotal_参数，指示当前处理的项目和的项，分别增量操作的进度中使用的值。</span><span class="sxs-lookup"><span data-stu-id="54353-115">Uses the values in the [IMAPIProgress::Progress](imapiprogress-progress.md) method's  _ulCount_ and  _ulTotal_ parameters, which indicate the currently processed item and the total items, respectively, to increment progress on the operation.</span></span> <span data-ttu-id="54353-116">当此标志设置时，必须设置全局上限和下限限制的值。</span><span class="sxs-lookup"><span data-stu-id="54353-116">When this flag is set, the values of the global lower and upper limits have to be set.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="54353-117">返回值</span><span class="sxs-lookup"><span data-stu-id="54353-117">Return value</span></span>

<span data-ttu-id="54353-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="54353-118">S_OK</span></span> 
  
> <span data-ttu-id="54353-119">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="54353-119">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="54353-120">注解</span><span class="sxs-lookup"><span data-stu-id="54353-120">Remarks</span></span>

<span data-ttu-id="54353-121">服务提供商调用**IMAPIProgress::SetLimits**方法来设置或清除 MAPI_TOP_LEVEL 标志并设置本地和全局最小和最大值。</span><span class="sxs-lookup"><span data-stu-id="54353-121">Service providers call the **IMAPIProgress::SetLimits** method to set or clear the MAPI_TOP_LEVEL flag and to set local and global minimum and maximum values.</span></span> <span data-ttu-id="54353-122">是否正在进行对象了解最小和最大值为本地域或全局设置会影响标志的值。</span><span class="sxs-lookup"><span data-stu-id="54353-122">The value of the flag setting affects whether the progress object understands the minimum and maximum values to be local or global.</span></span> <span data-ttu-id="54353-123">当设置 MAPI_TOP_LEVEL 标志时，这些值将被视为全局并用于计算整个操作的进度。</span><span class="sxs-lookup"><span data-stu-id="54353-123">When the MAPI_TOP_LEVEL flag is set, these values are considered global and are used to calculate progress for the entire operation.</span></span> <span data-ttu-id="54353-124">进度对象初始化为 1 的全局最小值和全局最大值为 1000年。</span><span class="sxs-lookup"><span data-stu-id="54353-124">Progress objects initialize the global minimum value to 1 and the global maximum value to 1000.</span></span> 
  
<span data-ttu-id="54353-125">当不设置 MAPI_TOP_LEVEL 时，最小和最大值被视为本地，并提供程序使用其内部显示正在进行较低级别的子对象。</span><span class="sxs-lookup"><span data-stu-id="54353-125">When MAPI_TOP_LEVEL is not set, the minimum and maximum values are considered local, and providers use them internally to display progress for lower level subobjects.</span></span> <span data-ttu-id="54353-126">仅，以便他们可以返回到提供程序的[IMAPIProgress::GetMin](imapiprogress-getmin.md)和[IMAPIProgress::GetMax](imapiprogress-getmax.md)方法调用时，进度对象保存本地的最小和最大值。</span><span class="sxs-lookup"><span data-stu-id="54353-126">Progress objects save the local minimum and maximum values only so that they can be returned to providers when the [IMAPIProgress::GetMin](imapiprogress-getmin.md) and [IMAPIProgress::GetMax](imapiprogress-getmax.md) methods are called.</span></span> 
  
<span data-ttu-id="54353-127">有关如何实施**SetLimits**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="54353-127">For more information about how to implement **SetLimits** and the other [IMAPIProgress](imapiprogressiunknown.md) methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
<span data-ttu-id="54353-128">有关详细了解如何以及何时调用进度对象，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="54353-128">For more information about how and when to make calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="54353-129">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="54353-129">MFCMAPI reference</span></span>

<span data-ttu-id="54353-130">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="54353-130">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="54353-131">**文件**</span><span class="sxs-lookup"><span data-stu-id="54353-131">**File**</span></span>|<span data-ttu-id="54353-132">**函数**</span><span class="sxs-lookup"><span data-stu-id="54353-132">**Function**</span></span>|<span data-ttu-id="54353-133">**Comment**</span><span class="sxs-lookup"><span data-stu-id="54353-133">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54353-134">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="54353-134">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="54353-135">CMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="54353-135">CMAPIProgress::SetLimits</span></span>  <br/> |<span data-ttu-id="54353-136">MFCMAPI 使用**IMAPIProgress::SetLimits**方法设置的最大和最小限制和进度对象的标志。</span><span class="sxs-lookup"><span data-stu-id="54353-136">MFCMAPI uses the **IMAPIProgress::SetLimits** method to set the maximum and minimum limits and flags for the progress object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="54353-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54353-137">See also</span></span>



[<span data-ttu-id="54353-138">IMAPIProgress::GetMax</span><span class="sxs-lookup"><span data-stu-id="54353-138">IMAPIProgress::GetMax</span></span>](imapiprogress-getmax.md)
  
[<span data-ttu-id="54353-139">IMAPIProgress::GetMin</span><span class="sxs-lookup"><span data-stu-id="54353-139">IMAPIProgress::GetMin</span></span>](imapiprogress-getmin.md)
  
[<span data-ttu-id="54353-140">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="54353-140">IMAPIProgress::Progress</span></span>](imapiprogress-progress.md)
  
[<span data-ttu-id="54353-141">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="54353-141">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="54353-142">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="54353-142">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="54353-143">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="54353-143">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="54353-144">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="54353-144">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

