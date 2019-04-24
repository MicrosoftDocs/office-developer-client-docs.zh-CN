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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270299"
---
# <a name="imapiprogressprogress"></a><span data-ttu-id="e6dba-103">IMAPIProgress::Progress</span><span class="sxs-lookup"><span data-stu-id="e6dba-103">IMAPIProgress::Progress</span></span>

  
  
<span data-ttu-id="e6dba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6dba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6dba-105">将进度指示器更新为在完成操作时显示进度。</span><span class="sxs-lookup"><span data-stu-id="e6dba-105">Updates the progress indicator with a display of the progress as it is made toward completion of the operation.</span></span> 
  
```cpp
HRESULT Progress(
  ULONG ulValue,
  ULONG ulCount,
  ULONG ulTotal
);
```

## <a name="parameters"></a><span data-ttu-id="e6dba-106">参数</span><span class="sxs-lookup"><span data-stu-id="e6dba-106">Parameters</span></span>

 <span data-ttu-id="e6dba-107">_ulValue_</span><span class="sxs-lookup"><span data-stu-id="e6dba-107">_ulValue_</span></span>
  
> <span data-ttu-id="e6dba-108">实时一个数字, 表示当前的进度级别 (从_ulCount_和_ulTotal_参数计算, 或从[IMAPIProgress:: SetLimits](imapiprogress-setlimits.md)方法的_lpulMin_和_lpulMax_参数中计算) 在全局下限和全局上限。</span><span class="sxs-lookup"><span data-stu-id="e6dba-108">[in] A number that indicates the current level of progress (calculated from the  _ulCount_ and  _ulTotal_ parameters or from the  _lpulMin_ and  _lpulMax_ parameters of the [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method) between the global lower limit and the global upper limit.</span></span> 
    
 <span data-ttu-id="e6dba-109">_ulCount_</span><span class="sxs-lookup"><span data-stu-id="e6dba-109">_ulCount_</span></span>
  
> <span data-ttu-id="e6dba-110">实时一个指示当前处理的项相对于总数的数字。</span><span class="sxs-lookup"><span data-stu-id="e6dba-110">[in] A number that indicates the currently processed item relative to the total.</span></span>
    
 <span data-ttu-id="e6dba-111">_ulTotal_</span><span class="sxs-lookup"><span data-stu-id="e6dba-111">_ulTotal_</span></span>
  
> <span data-ttu-id="e6dba-112">实时操作过程中要处理的项目总数。</span><span class="sxs-lookup"><span data-stu-id="e6dba-112">[in] The total number of items to be processed during the operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e6dba-113">返回值</span><span class="sxs-lookup"><span data-stu-id="e6dba-113">Return value</span></span>

<span data-ttu-id="e6dba-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6dba-114">S_OK</span></span> 
  
> <span data-ttu-id="e6dba-115">已成功更新进度指示器。</span><span class="sxs-lookup"><span data-stu-id="e6dba-115">The progress indicator was successfully updated.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="e6dba-116">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="e6dba-116">Notes to implementers</span></span>

<span data-ttu-id="e6dba-117">只有在操作完成时, _ulValue_参数才等于全局最小值, 且仅在操作完成时为全局最大值。</span><span class="sxs-lookup"><span data-stu-id="e6dba-117">The  _ulValue_ parameter will be equal to the global minimum value only at the start of the operation and to the global maximum value only at the completion of the operation.</span></span> 
  
<span data-ttu-id="e6dba-118">使用_ulCount_和_ulTotal_参数 (如果可用) 显示可选的消息, 如 "5 个项目已完成10个"。</span><span class="sxs-lookup"><span data-stu-id="e6dba-118">Use the  _ulCount_ and  _ulTotal_ parameters, if available, to display an optional message such as "5 items completed out of 10."</span></span> <span data-ttu-id="e6dba-119">如果_ulCount_和_ulTotal_设置为 0, 则决定是否以可视方式更改进度指示器。</span><span class="sxs-lookup"><span data-stu-id="e6dba-119">If  _ulCount_ and  _ulTotal_ are set to 0, decide whether to visually change the progress indicator.</span></span> <span data-ttu-id="e6dba-120">某些服务提供程序将这些参数设置为 0, 以指示它们正在处理其进度受监视的子对象相对于父对象。</span><span class="sxs-lookup"><span data-stu-id="e6dba-120">Some service providers set these parameters to 0 to indicate that they are processing a subobject whose progress is monitored relative to a parent object.</span></span> <span data-ttu-id="e6dba-121">在这种情况下, 仅在父对象报告进度时更改显示是有意义的。</span><span class="sxs-lookup"><span data-stu-id="e6dba-121">In this situation, it makes sense to change the display only when the parent object reports progress.</span></span> <span data-ttu-id="e6dba-122">某些服务提供程序每次都为这些参数传递0。</span><span class="sxs-lookup"><span data-stu-id="e6dba-122">Some service providers pass 0 for these parameters every time.</span></span> 
  
<span data-ttu-id="e6dba-123">有关如何实施**进度**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息, 请参阅[实现进度指示器](implementing-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="e6dba-123">For more information about how to implement **Progress** and the other [IMAPIProgress](imapiprogressiunknown.md) methods, see [Implementing a Progress Indicator](implementing-a-progress-indicator.md).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="e6dba-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e6dba-124">Notes to callers</span></span>

<span data-ttu-id="e6dba-125">不是 IMAPIProgress 的所有三个参数都是必需的 **::P rogress** 。</span><span class="sxs-lookup"><span data-stu-id="e6dba-125">Not all three of the parameters to **IMAPIProgress::Progress** are required.</span></span> <span data-ttu-id="e6dba-126">唯一必需的参数是_ulValue_(一个指示进度百分比的数字)。</span><span class="sxs-lookup"><span data-stu-id="e6dba-126">The only parameter that is required is  _ulValue_, a number that indicates the percentage of progress.</span></span> <span data-ttu-id="e6dba-127">如果设置了 MAPI_TOP_LEVEL 标志, 则还可以传递对象数和对象总数。</span><span class="sxs-lookup"><span data-stu-id="e6dba-127">If the MAPI_TOP_LEVEL flag is set, you can also pass an object count and an object total.</span></span> <span data-ttu-id="e6dba-128">某些实现使用这些值来显示一个短语, 如 "5 个项目已完成10个" (带有进度指示器)。</span><span class="sxs-lookup"><span data-stu-id="e6dba-128">Some implementations use these values to display a phrase such as "5 items completed out of 10" with the progress indicator.</span></span> 
  
<span data-ttu-id="e6dba-129">如果要复制单个文件夹中的所有邮件, 请将_ulTotal_设置为要复制的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="e6dba-129">If you are copying all messages in a single folder, set  _ulTotal_ to the total number of messages being copied.</span></span> <span data-ttu-id="e6dba-130">如果要复制文件夹, 请将_ulTotal_设置为该文件夹中的子文件夹数。</span><span class="sxs-lookup"><span data-stu-id="e6dba-130">If you are copying a folder, set  _ulTotal_ to the number of subfolders in the folder.</span></span> <span data-ttu-id="e6dba-131">如果要复制的文件夹不包含子文件夹且仅包含邮件, 则将_ulTotal_设置为1。</span><span class="sxs-lookup"><span data-stu-id="e6dba-131">If the folder to be copied contains no subfolders and only messages, set  _ulTotal_ to 1.</span></span> 
  
<span data-ttu-id="e6dba-132">有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="e6dba-132">For more information about how and when to make calls to a progress object, see [Display a Progress Indicator](how-to-display-a-progress-indicator.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e6dba-133">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="e6dba-133">MFCMAPI reference</span></span>

<span data-ttu-id="e6dba-134">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e6dba-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e6dba-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="e6dba-135">**File**</span></span>|<span data-ttu-id="e6dba-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="e6dba-136">**Function**</span></span>|<span data-ttu-id="e6dba-137">**备注**</span><span class="sxs-lookup"><span data-stu-id="e6dba-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6dba-138">MAPIProgress.cpp</span><span class="sxs-lookup"><span data-stu-id="e6dba-138">MAPIProgress.cpp</span></span>  <br/> |<span data-ttu-id="e6dba-139">CMAPIProgress::P rogress</span><span class="sxs-lookup"><span data-stu-id="e6dba-139">CMAPIProgress::Progress</span></span>  <br/> |<span data-ttu-id="e6dba-140">MFCMAPI 使用**IMAPIProgress::P rogress**方法更新 MFCMAPI 状态栏, 该状态栏的当前进度百分比, 从_uValue_计算, 以及当前的最大值和最小值。</span><span class="sxs-lookup"><span data-stu-id="e6dba-140">MFCMAPI uses the **IMAPIProgress::Progress** method to update the MFCMAPI status bar with the current percentage of progress, calculated from  _uValue_ and the current maximum and minimum values.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e6dba-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6dba-141">See also</span></span>



[<span data-ttu-id="e6dba-142">IMAPIProgress::SetLimits</span><span class="sxs-lookup"><span data-stu-id="e6dba-142">IMAPIProgress::SetLimits</span></span>](imapiprogress-setlimits.md)
  
[<span data-ttu-id="e6dba-143">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e6dba-143">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)


[<span data-ttu-id="e6dba-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e6dba-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="e6dba-145">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="e6dba-145">Display a Progress Indicator</span></span>](how-to-display-a-progress-indicator.md)
  
[<span data-ttu-id="e6dba-146">实现进度指示器</span><span class="sxs-lookup"><span data-stu-id="e6dba-146">Implementing a Progress Indicator</span></span>](implementing-a-progress-indicator.md)

