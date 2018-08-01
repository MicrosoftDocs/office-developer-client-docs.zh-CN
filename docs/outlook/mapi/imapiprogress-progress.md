---
title: IMAPIProgressProgress
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.Progress
api_type:
- COM
ms.assetid: edbf7623-a64e-43b8-8379-e3cde2433d91
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2a003be35fc9c3ef8efc7c66997ee99f6e578f09
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775509"
---
# <a name="imapiprogressprogress"></a><span data-ttu-id="ac7b0-103">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="ac7b0-103">IMAPIProgress::Progress</span></span>

  
  
<span data-ttu-id="ac7b0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ac7b0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ac7b0-105">更新进度指示器进度的显示做出的操作完成。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-105">Updates the progress indicator with a display of the progress as it is made toward completion of the operation.</span></span> 
  
```cpp
HRESULT Progress(
  ULONG ulValue,
  ULONG ulCount,
  ULONG ulTotal
);
```

## <a name="parameters"></a><span data-ttu-id="ac7b0-106">参数</span><span class="sxs-lookup"><span data-stu-id="ac7b0-106">Parameters</span></span>

 <span data-ttu-id="ac7b0-107">_ulValue_</span><span class="sxs-lookup"><span data-stu-id="ac7b0-107">_ulValue_</span></span>
  
> <span data-ttu-id="ac7b0-108">[in]一个数字，指示之间全局 （计算的_ulCount_和_ulTotal_参数从或[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法的_lpulMin_和_lpulMax_参数） 的进度的当前级别下限和全局上限。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-108">[in] A number that indicates the current level of progress (calculated from the  _ulCount_ and  _ulTotal_ parameters or from the  _lpulMin_ and  _lpulMax_ parameters of the [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method) between the global lower limit and the global upper limit.</span></span> 
    
 <span data-ttu-id="ac7b0-109">_ulCount_</span><span class="sxs-lookup"><span data-stu-id="ac7b0-109">_ulCount_</span></span>
  
> <span data-ttu-id="ac7b0-110">[in]一个数字，表示相对于总当前处理的项目。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-110">[in] A number that indicates the currently processed item relative to the total.</span></span>
    
 <span data-ttu-id="ac7b0-111">_ulTotal_</span><span class="sxs-lookup"><span data-stu-id="ac7b0-111">_ulTotal_</span></span>
  
> <span data-ttu-id="ac7b0-112">[in]在操作过程中处理的项目总数。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-112">[in] The total number of items to be processed during the operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ac7b0-113">返回值</span><span class="sxs-lookup"><span data-stu-id="ac7b0-113">Return value</span></span>

<span data-ttu-id="ac7b0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac7b0-114">S_OK</span></span> 
  
> <span data-ttu-id="ac7b0-115">已成功更新进度指示器。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-115">The progress indicator was successfully updated.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="ac7b0-116">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="ac7b0-116">Notes to implementers</span></span>

<span data-ttu-id="ac7b0-117">_UlValue_参数将只操作的开头的全局最小值到和仅在完成该操作的全局最大值相等。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-117">The  _ulValue_ parameter will be equal to the global minimum value only at the start of the operation and to the global maximum value only at the completion of the operation.</span></span> 
  
<span data-ttu-id="ac7b0-118">使用的_ulCount_和_ulTotal_参数，如果可用，以显示可选消息，例如"5 项目完成 10。"</span><span class="sxs-lookup"><span data-stu-id="ac7b0-118">Use the  _ulCount_ and  _ulTotal_ parameters, if available, to display an optional message such as "5 items completed out of 10."</span></span> <span data-ttu-id="ac7b0-119">如果_ulCount_和_ulTotal_都设为 0，决定是否以可视方式更改进度指示器。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-119">If  _ulCount_ and  _ulTotal_ are set to 0, decide whether to visually change the progress indicator.</span></span> <span data-ttu-id="ac7b0-120">某些服务提供商将这些参数设置为 0，以指示它们处理相对于父对象监视其进度的子对象。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-120">Some service providers set these parameters to 0 to indicate that they are processing a subobject whose progress is monitored relative to a parent object.</span></span> <span data-ttu-id="ac7b0-121">在此情况下，有意义的父对象报告进度时仅显示更改。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-121">In this situation, it makes sense to change the display only when the parent object reports progress.</span></span> <span data-ttu-id="ac7b0-122">某些服务提供商传递为这些参数的 0 每次。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-122">Some service providers pass 0 for these parameters every time.</span></span> 
  
<span data-ttu-id="ac7b0-123">有关如何实施**进度**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-123">For more information about how to implement **Progress** and the other [IMAPIProgress](imapiprogressiunknown.md) methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="ac7b0-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ac7b0-124">Notes to callers</span></span>

<span data-ttu-id="ac7b0-125">并非所有三个向**IMAPIProgress::Progress**参数都是必需的。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-125">Not all three of the parameters to **IMAPIProgress::Progress** are required.</span></span> <span data-ttu-id="ac7b0-126">所需的唯一参数是_ulValue_，一个数字，指示正在进行的百分比。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-126">The only parameter that is required is  _ulValue_, a number that indicates the percentage of progress.</span></span> <span data-ttu-id="ac7b0-127">如果设置了 MAPI_TOP_LEVEL 标志，您还可以传递对象计数和对象的汇总。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-127">If the MAPI_TOP_LEVEL flag is set, you can also pass an object count and an object total.</span></span> <span data-ttu-id="ac7b0-128">某些实现使用这些值来显示进度指示器的短语，例如"5 项目完成 10"。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-128">Some implementations use these values to display a phrase such as "5 items completed out of 10" with the progress indicator.</span></span> 
  
<span data-ttu-id="ac7b0-129">如果要将所有邮件都复制到一个文件夹中，设置_ulTotal_为复制的消息的总数。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-129">If you are copying all messages in a single folder, set  _ulTotal_ to the total number of messages being copied.</span></span> <span data-ttu-id="ac7b0-130">如果要复制的文件夹，设置_ulTotal_到文件夹中的子文件夹数。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-130">If you are copying a folder, set  _ulTotal_ to the number of subfolders in the folder.</span></span> <span data-ttu-id="ac7b0-131">如果要复制的文件夹中包含没有子文件夹和仅邮件，设置为 1 _ulTotal_ 。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-131">If the folder to be copied contains no subfolders and only messages, set  _ulTotal_ to 1.</span></span> 
  
<span data-ttu-id="ac7b0-132">有关详细了解如何以及何时调用进度对象，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-132">For more information about how and when to make calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ac7b0-133">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="ac7b0-133">MFCMAPI reference</span></span>

<span data-ttu-id="ac7b0-134">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ac7b0-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="ac7b0-135">**File**</span></span>|<span data-ttu-id="ac7b0-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="ac7b0-136">**Function**</span></span>|<span data-ttu-id="ac7b0-137">**Comment**</span><span class="sxs-lookup"><span data-stu-id="ac7b0-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac7b0-138">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="ac7b0-138">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="ac7b0-139">CMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="ac7b0-139">CMAPIProgress::Progress</span></span>  <br/> |<span data-ttu-id="ac7b0-140">MFCMAPI 使用**IMAPIProgress::Progress**方法使用当前的进度，从_uValue_和当前的最大和最小值计算百分比更新 MFCMAPI 状态栏。</span><span class="sxs-lookup"><span data-stu-id="ac7b0-140">MFCMAPI uses the **IMAPIProgress::Progress** method to update the MFCMAPI status bar with the current percentage of progress, calculated from  _uValue_ and the current maximum and minimum values.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ac7b0-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac7b0-141">See also</span></span>



[<span data-ttu-id="ac7b0-142">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="ac7b0-142">IMAPIProgress::SetLimits</span></span>](imapiprogress-setlimits.md)
  
[<span data-ttu-id="ac7b0-143">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ac7b0-143">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="ac7b0-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ac7b0-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="ac7b0-145">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="ac7b0-145">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="ac7b0-146">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="ac7b0-146">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

