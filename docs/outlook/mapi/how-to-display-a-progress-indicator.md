---
title: 显示进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 20f5ad5a-b700-4fb5-9658-f71da5a06a12
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7b0ce0ab75ffdce045ccde5bf6ea8a7da046f463
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408024"
---
# <a name="display-a-progress-indicator"></a><span data-ttu-id="7662c-103">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="7662c-103">Display a progress indicator</span></span>
 
<span data-ttu-id="7662c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7662c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7662c-105">若要显示进度指示器，请调用 [IMAPIProgress：：GetFlags](imapiprogress-getflags.md) 以检索当前标志设置。</span><span class="sxs-lookup"><span data-stu-id="7662c-105">To display a progress indicator, call [IMAPIProgress::GetFlags](imapiprogress-getflags.md) to retrieve the current flags setting.</span></span> 
  
<span data-ttu-id="7662c-106">如果MAPI_TOP_LEVEL，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7662c-106">If the MAPI_TOP_LEVEL flag is set, complete the following steps:</span></span>
  
1. <span data-ttu-id="7662c-107">将变量设置为等于操作中要处理的项目总数。</span><span class="sxs-lookup"><span data-stu-id="7662c-107">Set a variable equal to the total number of items to process in the operation.</span></span> <span data-ttu-id="7662c-108">例如，如果要复制文件夹的内容，则此值将等于文件夹中子文件夹的数量以及邮件数。</span><span class="sxs-lookup"><span data-stu-id="7662c-108">For example, if you are copying the contents of a folder, this value will be equal to the number of the subfolders in the folder plus the number of messages.</span></span> 
    
2. <span data-ttu-id="7662c-109">将变量设置为等于 1000 除以项目数。</span><span class="sxs-lookup"><span data-stu-id="7662c-109">Set a variable equal to 1000 divided by the number of items.</span></span> 
    
3. <span data-ttu-id="7662c-110">如果要显示子对象的进度，请调用进度对象的 [IMAPIProgress：：SetLimits](imapiprogress-setlimits.md) 方法，并传递以下三个参数的值：</span><span class="sxs-lookup"><span data-stu-id="7662c-110">If you are showing progress for subobjects, call the progress object's [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method and pass the following values for the three parameters:</span></span> 
    
   - <span data-ttu-id="7662c-111">将  _lpulMin_ 参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="7662c-111">Set the  _lpulMin_ parameter to 0.</span></span> 
    
   - <span data-ttu-id="7662c-112">将  _lpulMax_ 参数设置为 1000。</span><span class="sxs-lookup"><span data-stu-id="7662c-112">Set the  _lpulMax_ parameter to 1000.</span></span> 
    
   - <span data-ttu-id="7662c-113">将  _lpulFlags_ 参数设置为 MAPI_TOP_LEVEL。</span><span class="sxs-lookup"><span data-stu-id="7662c-113">Set the  _lpulFlags_ parameter to MAPI_TOP_LEVEL.</span></span> 
    
4. <span data-ttu-id="7662c-114">对于要处理的每个对象，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7662c-114">For each object to be processed, complete the following steps:</span></span>
    
   1. <span data-ttu-id="7662c-115">调用 **IMAPIProgress：：SetLimits** 并传递以下三个参数的值：</span><span class="sxs-lookup"><span data-stu-id="7662c-115">Call **IMAPIProgress::SetLimits** and pass the following values for the three parameters:</span></span> 
      
     - <span data-ttu-id="7662c-116">将  _lpulMin_ 参数设置为步骤 2 乘以当前项减 1 中设置的变量。</span><span class="sxs-lookup"><span data-stu-id="7662c-116">Set the  _lpulMin_ parameter to the variable set in step 2 multiplied by the current item minus 1.</span></span> 
      
     - <span data-ttu-id="7662c-117">将  _lpulMax_ 参数设置为步骤 2 中与当前对象相乘的变量集。</span><span class="sxs-lookup"><span data-stu-id="7662c-117">Set the  _lpulMax_ parameter to the variable set in step 2 multiplied by the current object.</span></span> 
      
     - <span data-ttu-id="7662c-118">将  _lpulFlags_ 参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="7662c-118">Set the  _lpulFlags_ parameter to 0.</span></span> 
      
   2. <span data-ttu-id="7662c-119">对此对象执行应执行的任何处理。</span><span class="sxs-lookup"><span data-stu-id="7662c-119">Perform whatever processing should be done on this object.</span></span> <span data-ttu-id="7662c-120">如果这是一个子对象，并且您希望显示子对象上的进度，则向该方法传递指向  _lpProgress_ 参数中 progress 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="7662c-120">If this is a subobject and you want to display progress on subobjects, pass a pointer to the progress object in the  _lpProgress_ parameter to the method.</span></span> 
      
   3. <span data-ttu-id="7662c-121">调用 [IMAPIProgress：:P rogress](imapiprogress-progress.md) 并传递以下三个参数的值：</span><span class="sxs-lookup"><span data-stu-id="7662c-121">Call [IMAPIProgress::Progress](imapiprogress-progress.md) and pass the following values for the three parameters:</span></span> 
      
     - <span data-ttu-id="7662c-122">将  _ulValue_ 参数设置为步骤 2 中与当前对象相乘的变量集。</span><span class="sxs-lookup"><span data-stu-id="7662c-122">Set the  _ulValue_ parameter to the variable set in step 2 multiplied by the current object.</span></span> 
      
     - <span data-ttu-id="7662c-123">将  _ulCount_ 参数设置为当前对象。</span><span class="sxs-lookup"><span data-stu-id="7662c-123">Set the  _ulCount_ parameter to the current object.</span></span> 
      
     - <span data-ttu-id="7662c-124">将  _ulTotal_ 参数设置为步骤 1 中设置的变量（对象总数）。</span><span class="sxs-lookup"><span data-stu-id="7662c-124">Set the  _ulTotal_ parameter to the variable set in step 1, the total number of objects.</span></span> 
    
<span data-ttu-id="7662c-125">如果未MAPI_TOP_LEVEL，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7662c-125">If the MAPI_TOP_LEVEL flag is not set, complete the following steps:</span></span>
  
1. <span data-ttu-id="7662c-126">调用进度对象的 [IMAPIProgress：：GetMin](imapiprogress-getmin.md) 方法来检索显示器的最小值。</span><span class="sxs-lookup"><span data-stu-id="7662c-126">Call the progress object's [IMAPIProgress::GetMin](imapiprogress-getmin.md) method to retrieve the minimum value for the display.</span></span> 
    
2. <span data-ttu-id="7662c-127">调用 [IMAPIProgress：：GetMax](imapiprogress-getmax.md) 以检索显示器的最大值。</span><span class="sxs-lookup"><span data-stu-id="7662c-127">Call [IMAPIProgress::GetMax](imapiprogress-getmax.md) to retrieve the maximum value for the display.</span></span> 
    
3. <span data-ttu-id="7662c-128">设置一个等于要处理的对象总数的变量。</span><span class="sxs-lookup"><span data-stu-id="7662c-128">Set a variable equal to the total number of objects to be processed.</span></span> 
    
4. <span data-ttu-id="7662c-129">将变量设置为等于最大值减去最小值后除以对象总数的结果。</span><span class="sxs-lookup"><span data-stu-id="7662c-129">Set a variable equal to the result of subtracting the minimum value from the maximum value and then dividing by the total number of objects.</span></span>
    
5. <span data-ttu-id="7662c-130">对于要处理的每个对象，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7662c-130">For each object to be processed, complete the following steps:</span></span>
    
   1. <span data-ttu-id="7662c-131">如果提供程序显示子对象的进度，请调用 **IMAPIProgress：：SetLimits** 并传递以下三个参数的值：</span><span class="sxs-lookup"><span data-stu-id="7662c-131">If your provider is showing progress for subobjects, call **IMAPIProgress::SetLimits** and pass the following values for the three parameters:</span></span> 
      
     - <span data-ttu-id="7662c-132">将  _lpulMin_ 参数设置为最小值加上当前项减去 1 乘以步骤 4 中设置的变量。</span><span class="sxs-lookup"><span data-stu-id="7662c-132">Set the  _lpulMin_ parameter to the minimum value plus the current item minus 1 multiplied by the variable set in step 4.</span></span> 
      
     - <span data-ttu-id="7662c-133">将  _lpulMax_ 参数设置为最小值加上当前单位乘以步骤 4 中设置的变量。</span><span class="sxs-lookup"><span data-stu-id="7662c-133">Set the  _lpulMax_ parameter to the minimum value plus the current unit multiplied by the variable set in step 4.</span></span> 
      
     - <span data-ttu-id="7662c-134">将  _lpulFlags_ 参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="7662c-134">Set the  _lpulFlags_ parameter to 0.</span></span> 
      
   2. <span data-ttu-id="7662c-135">对此对象执行应执行的任何处理。</span><span class="sxs-lookup"><span data-stu-id="7662c-135">Perform whatever processing should be done on this object.</span></span> <span data-ttu-id="7662c-136">如果对象是子对象，并且您的提供程序显示子对象的进度，则向该方法传递指向  _lpProgress_ 参数中 progress 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="7662c-136">If the object is a subobject, and your provider displays progress for subobjects, pass a pointer to the progress object in the  _lpProgress_ parameter to the method.</span></span> 
      
   3. <span data-ttu-id="7662c-137">调用 [IMAPIProgress：:P rogress](imapiprogress-progress.md) 并传递以下三个参数的值：</span><span class="sxs-lookup"><span data-stu-id="7662c-137">Call [IMAPIProgress::Progress](imapiprogress-progress.md) and pass the following values for the three parameters:</span></span> 
      
     - <span data-ttu-id="7662c-138">将  _ulValue_ 参数设置为步骤 2 中与当前对象相乘的变量集。</span><span class="sxs-lookup"><span data-stu-id="7662c-138">Set the  _ulValue_ parameter to variable set in step 2 multiplied by the current object.</span></span> 
      
     - <span data-ttu-id="7662c-139">将  _ulCount 参数_ 设置为 0。</span><span class="sxs-lookup"><span data-stu-id="7662c-139">Set the  _ulCount_ parameter to 0.</span></span> 
      
     - <span data-ttu-id="7662c-140">将  _ulTotal_ 参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="7662c-140">Set the  _ulTotal_ parameter to 0.</span></span> 
    
<span data-ttu-id="7662c-141">以下代码示例演示了在复制包含五个子文件夹的文件夹的内容的操作的所有级别显示进度所需的逻辑。</span><span class="sxs-lookup"><span data-stu-id="7662c-141">The following code example illustrates the logic required to show progress at all levels of an operation that copies the contents of a folder that contains five subfolders.</span></span> 
  
```cpp
lpProgress->GetFlags (lpulFlags);
ulFlags = *lpulFlags;
/* The folder in charge of the display. It contains 5 subfolders. */
if (ulFlags & MAPI_TOP_LEVEL)
{
    ulItems = 5                         // 5 subfolders in this folder
    ulScale = (ulMax / ulItems)         // 200 because ulMax = 1000
    lpProgress->SetLimits(0, ulMax, MAPI_TOP_LEVEL)
    for (i = 1; i <= ulItems; i++)      // for each subfolder to copy
    {
        lpProgress->SetLimits( (i - 1) * ulScale, i * ulScale, 0)
        CopyOneFolder(lpFolder(i), lpProgress)
        lpProgress->Progress( i * ulScale, i, ulItems)
    }
}
else
/* One of the subfolders to be copied. It contains 3 messages. */
{
    lpProgress->GetMin(&ulMin);
    lpProgress->GetMax(&ulMax);
    ulItems = 3;
    ulDelta = (ulMax - ulMin) / ulItems;
    for (i = 1; i <= ulItems; i++)
    {
        lpProgress->SetLimits(ulMin + (i - 1) * ulDelta,
                              ulMin + i * ulDelta, 0)
        CopyOneFolder(lpFolder(i), lpProgress)
        /* Pass 0 for ulCount and ulTotal because this is not the */
        /* top-level display, and that information is unavailable  */
        lpProgress->Progress( i * ulDelta, 0, 0)
    }
}
 
```

## <a name="see-also"></a><span data-ttu-id="7662c-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7662c-142">See also</span></span>

- [<span data-ttu-id="7662c-143">MAPI 进度指示器</span><span class="sxs-lookup"><span data-stu-id="7662c-143">MAPI Progress Indicators</span></span>](mapi-progress-indicators.md)

