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
ms.openlocfilehash: 0810ed7ce20bba95c4286e6e042065c0c2d1a802
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421464"
---
# <a name="imapiprogresssetlimits"></a><span data-ttu-id="a6030-103">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="a6030-103">IMAPIProgress::SetLimits</span></span>

  
  
<span data-ttu-id="a6030-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a6030-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a6030-105">设置操作中项数的下限和上限，以及控制如何计算操作进度信息的标志。</span><span class="sxs-lookup"><span data-stu-id="a6030-105">Sets the lower and upper limits for the number of items in the operation, and the flags that control how progress information is calculated for the operation.</span></span>
  
```cpp
HRESULT SetLimits(
  LPULONG lpulMin,
  LPULONG lpulMax,
  LPULONG lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="a6030-106">参数</span><span class="sxs-lookup"><span data-stu-id="a6030-106">Parameters</span></span>

 <span data-ttu-id="a6030-107">_lpulMin_</span><span class="sxs-lookup"><span data-stu-id="a6030-107">_lpulMin_</span></span>
  
> <span data-ttu-id="a6030-108">[in]指向包含操作中项下限的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="a6030-108">[in] A pointer to a variable that contains the lower limit of items in the operation.</span></span>
    
 <span data-ttu-id="a6030-109">_lpulMax_</span><span class="sxs-lookup"><span data-stu-id="a6030-109">_lpulMax_</span></span>
  
> <span data-ttu-id="a6030-110">[in]指向包含操作中项目的上限的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="a6030-110">[in] A pointer to a variable that contains the upper limit of items in the operation.</span></span>
    
 <span data-ttu-id="a6030-111">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="a6030-111">_lpulFlags_</span></span>
  
> <span data-ttu-id="a6030-112">[in]控制计算进度信息的操作级别的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="a6030-112">[in] A bitmask of flags that controls the level of operation on which progress information is calculated.</span></span> <span data-ttu-id="a6030-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a6030-113">The following flag can be set:</span></span>
    
<span data-ttu-id="a6030-114">MAPI_TOP_LEVEL</span><span class="sxs-lookup"><span data-stu-id="a6030-114">MAPI_TOP_LEVEL</span></span> 
  
> <span data-ttu-id="a6030-115">使用 [IMAPIProgress：:P rogress](imapiprogress-progress.md) 方法的  _ulCount_ 和  _ulTotal_ 参数中的值，分别指示当前处理的项和总项数，以递增操作的进度。</span><span class="sxs-lookup"><span data-stu-id="a6030-115">Uses the values in the [IMAPIProgress::Progress](imapiprogress-progress.md) method's  _ulCount_ and  _ulTotal_ parameters, which indicate the currently processed item and the total items, respectively, to increment progress on the operation.</span></span> <span data-ttu-id="a6030-116">设置此标志时，必须设置全局下限和上限的值。</span><span class="sxs-lookup"><span data-stu-id="a6030-116">When this flag is set, the values of the global lower and upper limits have to be set.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a6030-117">返回值</span><span class="sxs-lookup"><span data-stu-id="a6030-117">Return value</span></span>

<span data-ttu-id="a6030-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6030-118">S_OK</span></span> 
  
> <span data-ttu-id="a6030-119">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="a6030-119">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a6030-120">备注</span><span class="sxs-lookup"><span data-stu-id="a6030-120">Remarks</span></span>

<span data-ttu-id="a6030-121">服务提供商调用 **IMAPIProgress：：SetLimits** 方法来设置或清除 MAPI_TOP_LEVEL 标志，并设置本地和全局最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="a6030-121">Service providers call the **IMAPIProgress::SetLimits** method to set or clear the MAPI_TOP_LEVEL flag and to set local and global minimum and maximum values.</span></span> <span data-ttu-id="a6030-122">标志设置的值会影响进度对象是了解最小值还是最大值是本地值还是全局值。</span><span class="sxs-lookup"><span data-stu-id="a6030-122">The value of the flag setting affects whether the progress object understands the minimum and maximum values to be local or global.</span></span> <span data-ttu-id="a6030-123">设置 MAPI_TOP_LEVEL 标志时，这些值被视为全局值，用于计算整个操作的进度。</span><span class="sxs-lookup"><span data-stu-id="a6030-123">When the MAPI_TOP_LEVEL flag is set, these values are considered global and are used to calculate progress for the entire operation.</span></span> <span data-ttu-id="a6030-124">Progress 对象将全局最小值初始化为 1，将全局最大值初始化为 1000。</span><span class="sxs-lookup"><span data-stu-id="a6030-124">Progress objects initialize the global minimum value to 1 and the global maximum value to 1000.</span></span> 
  
<span data-ttu-id="a6030-125">未MAPI_TOP_LEVEL时，最小值和最大值被视为本地值，提供程序在内部使用它们来显示较低级别的子对象的进度。</span><span class="sxs-lookup"><span data-stu-id="a6030-125">When MAPI_TOP_LEVEL is not set, the minimum and maximum values are considered local, and providers use them internally to display progress for lower level subobjects.</span></span> <span data-ttu-id="a6030-126">Progress 对象仅保存本地最小值和最大值，以便它们可以在 [调用 IMAPIProgress：：GetMin](imapiprogress-getmin.md) 和 [IMAPIProgress：：GetMax](imapiprogress-getmax.md) 方法时返回到提供程序。</span><span class="sxs-lookup"><span data-stu-id="a6030-126">Progress objects save the local minimum and maximum values only so that they can be returned to providers when the [IMAPIProgress::GetMin](imapiprogress-getmin.md) and [IMAPIProgress::GetMax](imapiprogress-getmax.md) methods are called.</span></span> 
  
<span data-ttu-id="a6030-127">若要详细了解如何实现 **SetLimits 和其他** [IMAPIProgress](imapiprogressiunknown.md) 方法，请参阅 [实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="a6030-127">For more information about how to implement **SetLimits** and the other [IMAPIProgress](imapiprogressiunknown.md) methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
<span data-ttu-id="a6030-128">有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="a6030-128">For more information about how and when to make calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a6030-129">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a6030-129">MFCMAPI reference</span></span>

<span data-ttu-id="a6030-130">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a6030-130">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a6030-131">**文件**</span><span class="sxs-lookup"><span data-stu-id="a6030-131">**File**</span></span>|<span data-ttu-id="a6030-132">**函数**</span><span class="sxs-lookup"><span data-stu-id="a6030-132">**Function**</span></span>|<span data-ttu-id="a6030-133">**备注**</span><span class="sxs-lookup"><span data-stu-id="a6030-133">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6030-134">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="a6030-134">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="a6030-135">CMAPIProgress：：SetLimits</span><span class="sxs-lookup"><span data-stu-id="a6030-135">CMAPIProgress::SetLimits</span></span>  <br/> |<span data-ttu-id="a6030-136">MFCMAPI 使用 **IMAPIProgress：：SetLimits** 方法来设置进度对象的最大和最小限制和标志。</span><span class="sxs-lookup"><span data-stu-id="a6030-136">MFCMAPI uses the **IMAPIProgress::SetLimits** method to set the maximum and minimum limits and flags for the progress object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a6030-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6030-137">See also</span></span>



[<span data-ttu-id="a6030-138">IMAPIProgress::GetMax</span><span class="sxs-lookup"><span data-stu-id="a6030-138">IMAPIProgress::GetMax</span></span>](imapiprogress-getmax.md)
  
[<span data-ttu-id="a6030-139">IMAPIProgress::GetMin</span><span class="sxs-lookup"><span data-stu-id="a6030-139">IMAPIProgress::GetMin</span></span>](imapiprogress-getmin.md)
  
[<span data-ttu-id="a6030-140">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="a6030-140">IMAPIProgress::Progress</span></span>](imapiprogress-progress.md)
  
[<span data-ttu-id="a6030-141">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a6030-141">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="a6030-142">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a6030-142">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="a6030-143">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="a6030-143">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="a6030-144">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="a6030-144">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

