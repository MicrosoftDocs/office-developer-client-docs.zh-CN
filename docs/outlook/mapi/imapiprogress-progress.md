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
ms.openlocfilehash: 3cf639286a504b9edb600214d13dbe50710e76a9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435493"
---
# <a name="imapiprogressprogress"></a><span data-ttu-id="d2661-103">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="d2661-103">IMAPIProgress::Progress</span></span>

  
  
<span data-ttu-id="d2661-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d2661-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d2661-105">更新进度指示器，并显示在操作完成时的进度。</span><span class="sxs-lookup"><span data-stu-id="d2661-105">Updates the progress indicator with a display of the progress as it is made toward completion of the operation.</span></span> 
  
```cpp
HRESULT Progress(
  ULONG ulValue,
  ULONG ulCount,
  ULONG ulTotal
);
```

## <a name="parameters"></a><span data-ttu-id="d2661-106">参数</span><span class="sxs-lookup"><span data-stu-id="d2661-106">Parameters</span></span>

 <span data-ttu-id="d2661-107">_ulValue_</span><span class="sxs-lookup"><span data-stu-id="d2661-107">_ulValue_</span></span>
  
> <span data-ttu-id="d2661-108">[in]一个数字，指示当前进度级别 (从 _ulCount_ 和 _ulTotal_ 参数计算，或者从 [IMAPIProgress：：SetLimits](imapiprogress-setlimits.md)方法的 _lpulMin_ 和 _lpulMax_ 参数计算) 在全局下限和全局上限之间计算。</span><span class="sxs-lookup"><span data-stu-id="d2661-108">[in] A number that indicates the current level of progress (calculated from the  _ulCount_ and  _ulTotal_ parameters or from the  _lpulMin_ and  _lpulMax_ parameters of the [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method) between the global lower limit and the global upper limit.</span></span> 
    
 <span data-ttu-id="d2661-109">_ulCount_</span><span class="sxs-lookup"><span data-stu-id="d2661-109">_ulCount_</span></span>
  
> <span data-ttu-id="d2661-110">[in]一个数字，指示当前处理的项目相对于总数。</span><span class="sxs-lookup"><span data-stu-id="d2661-110">[in] A number that indicates the currently processed item relative to the total.</span></span>
    
 <span data-ttu-id="d2661-111">_ulTotal_</span><span class="sxs-lookup"><span data-stu-id="d2661-111">_ulTotal_</span></span>
  
> <span data-ttu-id="d2661-112">[in]操作过程中要处理的项目总数。</span><span class="sxs-lookup"><span data-stu-id="d2661-112">[in] The total number of items to be processed during the operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d2661-113">返回值</span><span class="sxs-lookup"><span data-stu-id="d2661-113">Return value</span></span>

<span data-ttu-id="d2661-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2661-114">S_OK</span></span> 
  
> <span data-ttu-id="d2661-115">进度指示器已成功更新。</span><span class="sxs-lookup"><span data-stu-id="d2661-115">The progress indicator was successfully updated.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="d2661-116">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="d2661-116">Notes to implementers</span></span>

<span data-ttu-id="d2661-117">_ulValue_ 参数仅在操作开始时等于全局最小值，并且仅在操作完成时等于全局最大值。</span><span class="sxs-lookup"><span data-stu-id="d2661-117">The  _ulValue_ parameter will be equal to the global minimum value only at the start of the operation and to the global maximum value only at the completion of the operation.</span></span> 
  
<span data-ttu-id="d2661-118">使用  _ulCount_ 和  _ulTotal_ 参数（如果可用）显示可选消息，例如"5 个项目已完成，其中 10 项已完成"。</span><span class="sxs-lookup"><span data-stu-id="d2661-118">Use the  _ulCount_ and  _ulTotal_ parameters, if available, to display an optional message such as "5 items completed out of 10."</span></span> <span data-ttu-id="d2661-119">如果  _ulCount_ 和  _ulTotal_ 设置为 0，请决定是否直观地更改进度指示器。</span><span class="sxs-lookup"><span data-stu-id="d2661-119">If  _ulCount_ and  _ulTotal_ are set to 0, decide whether to visually change the progress indicator.</span></span> <span data-ttu-id="d2661-120">某些服务提供商将这些参数设置为 0，以指示它们正在处理其进度相对于父对象监视的子对象。</span><span class="sxs-lookup"><span data-stu-id="d2661-120">Some service providers set these parameters to 0 to indicate that they are processing a subobject whose progress is monitored relative to a parent object.</span></span> <span data-ttu-id="d2661-121">在这种情况下，仅在父对象报告进度时更改显示是有意义的。</span><span class="sxs-lookup"><span data-stu-id="d2661-121">In this situation, it makes sense to change the display only when the parent object reports progress.</span></span> <span data-ttu-id="d2661-122">某些服务提供商每次为这些参数传递 0。</span><span class="sxs-lookup"><span data-stu-id="d2661-122">Some service providers pass 0 for these parameters every time.</span></span> 
  
<span data-ttu-id="d2661-123">若要详细了解如何实现 **进度和其他** [IMAPIProgress](imapiprogressiunknown.md) 方法，请参阅 [实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="d2661-123">For more information about how to implement **Progress** and the other [IMAPIProgress](imapiprogressiunknown.md) methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="d2661-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d2661-124">Notes to callers</span></span>

<span data-ttu-id="d2661-125">**IMAPIProgress：:P参数并非全部** 是必需的。</span><span class="sxs-lookup"><span data-stu-id="d2661-125">Not all three of the parameters to **IMAPIProgress::Progress** are required.</span></span> <span data-ttu-id="d2661-126">唯一需要的参数是  _ulValue，_ 一个数字，指示进度百分比。</span><span class="sxs-lookup"><span data-stu-id="d2661-126">The only parameter that is required is  _ulValue_, a number that indicates the percentage of progress.</span></span> <span data-ttu-id="d2661-127">如果MAPI_TOP_LEVEL，则还可以传递对象计数和对象总数。</span><span class="sxs-lookup"><span data-stu-id="d2661-127">If the MAPI_TOP_LEVEL flag is set, you can also pass an object count and an object total.</span></span> <span data-ttu-id="d2661-128">某些实现使用这些值来显示一个短语，如"5 个项目已完成，其中 10 个项目"具有进度指示器。</span><span class="sxs-lookup"><span data-stu-id="d2661-128">Some implementations use these values to display a phrase such as "5 items completed out of 10" with the progress indicator.</span></span> 
  
<span data-ttu-id="d2661-129">如果要复制单个文件夹中的所有邮件，将  _ulTotal_ 设置为要复制的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="d2661-129">If you are copying all messages in a single folder, set  _ulTotal_ to the total number of messages being copied.</span></span> <span data-ttu-id="d2661-130">如果要复制文件夹，将  _ulTotal_ 设置为文件夹中子文件夹的数量。</span><span class="sxs-lookup"><span data-stu-id="d2661-130">If you are copying a folder, set  _ulTotal_ to the number of subfolders in the folder.</span></span> <span data-ttu-id="d2661-131">如果要复制的文件夹不包含子文件夹和仅邮件，则将  _ulTotal_ 设置为 1。</span><span class="sxs-lookup"><span data-stu-id="d2661-131">If the folder to be copied contains no subfolders and only messages, set  _ulTotal_ to 1.</span></span> 
  
<span data-ttu-id="d2661-132">有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="d2661-132">For more information about how and when to make calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="d2661-133">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="d2661-133">MFCMAPI reference</span></span>

<span data-ttu-id="d2661-134">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d2661-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d2661-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="d2661-135">**File**</span></span>|<span data-ttu-id="d2661-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="d2661-136">**Function**</span></span>|<span data-ttu-id="d2661-137">**备注**</span><span class="sxs-lookup"><span data-stu-id="d2661-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d2661-138">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="d2661-138">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="d2661-139">CMAPIProgress：:P rogress</span><span class="sxs-lookup"><span data-stu-id="d2661-139">CMAPIProgress::Progress</span></span>  <br/> |<span data-ttu-id="d2661-140">MFCMAPI 使用 **IMAPIProgress：:P rogress** 方法使用当前进度百分比更新 MFCMAPI 状态栏，该进度百分比是根据  _uValue_ 以及当前最大值和最小值计算的。</span><span class="sxs-lookup"><span data-stu-id="d2661-140">MFCMAPI uses the **IMAPIProgress::Progress** method to update the MFCMAPI status bar with the current percentage of progress, calculated from  _uValue_ and the current maximum and minimum values.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d2661-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2661-141">See also</span></span>



[<span data-ttu-id="d2661-142">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="d2661-142">IMAPIProgress::SetLimits</span></span>](imapiprogress-setlimits.md)
  
[<span data-ttu-id="d2661-143">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d2661-143">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="d2661-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d2661-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="d2661-145">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="d2661-145">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="d2661-146">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="d2661-146">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

