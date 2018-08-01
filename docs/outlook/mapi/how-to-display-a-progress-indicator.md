---
title: 显示进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 20f5ad5a-b700-4fb5-9658-f71da5a06a12
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3c4c553a000dab233eb208c1222cc427c97b1e70
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775097"
---
# <a name="display-a-progress-indicator"></a><span data-ttu-id="f262c-103">显示进度指示器</span><span class="sxs-lookup"><span data-stu-id="f262c-103">Display a progress indicator</span></span>
 
<span data-ttu-id="f262c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f262c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f262c-105">若要显示进度指示器，请调用[IMAPIProgress::GetFlags](imapiprogress-getflags.md)检索设置的当前标志。</span><span class="sxs-lookup"><span data-stu-id="f262c-105">To display a progress indicator, call [IMAPIProgress::GetFlags](imapiprogress-getflags.md) to retrieve the current flags setting.</span></span> 
  
<span data-ttu-id="f262c-106">如果设置了 MAPI_TOP_LEVEL 标志，完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f262c-106">If the MAPI_TOP_LEVEL flag is set, complete the following steps:</span></span>
  
1. <span data-ttu-id="f262c-107">将变量等于设置为要处理操作中的项的总数。</span><span class="sxs-lookup"><span data-stu-id="f262c-107">Set a variable equal to the total number of items to process in the operation.</span></span> <span data-ttu-id="f262c-108">例如，如果要复制的文件夹的内容，此值将等于的文件夹中的子文件夹数加上的消息数。</span><span class="sxs-lookup"><span data-stu-id="f262c-108">For example, if you are copying the contents of a folder, this value will be equal to the number of the subfolders in the folder plus the number of messages.</span></span> 
    
2. <span data-ttu-id="f262c-109">将变量等于设置为 1000 的项目数的比率。</span><span class="sxs-lookup"><span data-stu-id="f262c-109">Set a variable equal to 1000 divided by the number of items.</span></span> 
    
3. <span data-ttu-id="f262c-110">如果显示进度的子对象时，调用进度对象的[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法并传递的三个参数的下列值：</span><span class="sxs-lookup"><span data-stu-id="f262c-110">If you are showing progress for subobjects, call the progress object's [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) method and pass the following values for the three parameters:</span></span> 
    
   - <span data-ttu-id="f262c-111">_LpulMin_参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="f262c-111">Set the  _lpulMin_ parameter to 0.</span></span> 
    
   - <span data-ttu-id="f262c-112">将_lpulMax_参数设置为 1000年。</span><span class="sxs-lookup"><span data-stu-id="f262c-112">Set the  _lpulMax_ parameter to 1000.</span></span> 
    
   - <span data-ttu-id="f262c-113">_LpulFlags_参数设置为 MAPI_TOP_LEVEL。</span><span class="sxs-lookup"><span data-stu-id="f262c-113">Set the  _lpulFlags_ parameter to MAPI_TOP_LEVEL.</span></span> 
    
4. <span data-ttu-id="f262c-114">对于处理每个对象，完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f262c-114">For each object to be processed, complete the following steps:</span></span>
    
   1. <span data-ttu-id="f262c-115">调用**IMAPIProgress::SetLimits**并传递的三个参数的下列值：</span><span class="sxs-lookup"><span data-stu-id="f262c-115">Call **IMAPIProgress::SetLimits** and pass the following values for the three parameters:</span></span> 
      
     - <span data-ttu-id="f262c-116">_LpulMin_参数设置为在步骤 2 乘以减 1 之间的当前项目中设置的变量。</span><span class="sxs-lookup"><span data-stu-id="f262c-116">Set the  _lpulMin_ parameter to the variable set in step 2 multiplied by the current item minus 1.</span></span> 
      
     - <span data-ttu-id="f262c-117">_LpulMax_参数设置为设置在步骤 2 乘以当前对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f262c-117">Set the  _lpulMax_ parameter to the variable set in step 2 multiplied by the current object.</span></span> 
      
     - <span data-ttu-id="f262c-118">_LpulFlags_参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="f262c-118">Set the  _lpulFlags_ parameter to 0.</span></span> 
      
   2. <span data-ttu-id="f262c-119">执行此对象应的任何处理。</span><span class="sxs-lookup"><span data-stu-id="f262c-119">Perform whatever processing should be done on this object.</span></span> <span data-ttu-id="f262c-120">如果这是子对象和您想要在子对象上显示进度，请将指针传递给方法_lpProgress_参数中的进度对象。</span><span class="sxs-lookup"><span data-stu-id="f262c-120">If this is a subobject and you want to display progress on subobjects, pass a pointer to the progress object in the  _lpProgress_ parameter to the method.</span></span> 
      
   3. <span data-ttu-id="f262c-121">调用[IMAPIProgress::Progress](imapiprogress-progress.md)并传递的三个参数的下列值：</span><span class="sxs-lookup"><span data-stu-id="f262c-121">Call [IMAPIProgress::Progress](imapiprogress-progress.md) and pass the following values for the three parameters:</span></span> 
      
     - <span data-ttu-id="f262c-122">_UlValue_参数设置为设置在步骤 2 乘以当前对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f262c-122">Set the  _ulValue_ parameter to the variable set in step 2 multiplied by the current object.</span></span> 
      
     - <span data-ttu-id="f262c-123">_UlCount_参数设置为当前对象。</span><span class="sxs-lookup"><span data-stu-id="f262c-123">Set the  _ulCount_ parameter to the current object.</span></span> 
      
     - <span data-ttu-id="f262c-124">_UlTotal_参数设置为在步骤 1，对象总数中设置的变量。</span><span class="sxs-lookup"><span data-stu-id="f262c-124">Set the  _ulTotal_ parameter to the variable set in step 1, the total number of objects.</span></span> 
    
<span data-ttu-id="f262c-125">如果未设置 MAPI_TOP_LEVEL 标志，完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f262c-125">If the MAPI_TOP_LEVEL flag is not set, complete the following steps:</span></span>
  
1. <span data-ttu-id="f262c-126">调用进度对象的[IMAPIProgress::GetMin](imapiprogress-getmin.md)方法来检索显示的最小值。</span><span class="sxs-lookup"><span data-stu-id="f262c-126">Call the progress object's [IMAPIProgress::GetMin](imapiprogress-getmin.md) method to retrieve the minimum value for the display.</span></span> 
    
2. <span data-ttu-id="f262c-127">调用[IMAPIProgress::GetMax](imapiprogress-getmax.md)检索显示的最大值。</span><span class="sxs-lookup"><span data-stu-id="f262c-127">Call [IMAPIProgress::GetMax](imapiprogress-getmax.md) to retrieve the maximum value for the display.</span></span> 
    
3. <span data-ttu-id="f262c-128">将变量等于设置为要处理的对象的总数。</span><span class="sxs-lookup"><span data-stu-id="f262c-128">Set a variable equal to the total number of objects to be processed.</span></span> 
    
4. <span data-ttu-id="f262c-129">设置变量等于为减去的最大值的最小值，然后除以对象总数的结果。</span><span class="sxs-lookup"><span data-stu-id="f262c-129">Set a variable equal to the result of subtracting the minimum value from the maximum value and then dividing by the total number of objects.</span></span>
    
5. <span data-ttu-id="f262c-130">对于处理每个对象，完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f262c-130">For each object to be processed, complete the following steps:</span></span>
    
   1. <span data-ttu-id="f262c-131">如果您的提供商显示进度的子对象，调用**IMAPIProgress::SetLimits**并传递的三个参数的下列值：</span><span class="sxs-lookup"><span data-stu-id="f262c-131">If your provider is showing progress for subobjects, call **IMAPIProgress::SetLimits** and pass the following values for the three parameters:</span></span> 
      
     - <span data-ttu-id="f262c-132">_LpulMin_参数设置为最小值再加上当前项值减 1 的第 4 步中设置的变量。</span><span class="sxs-lookup"><span data-stu-id="f262c-132">Set the  _lpulMin_ parameter to the minimum value plus the current item minus 1 multiplied by the variable set in step 4.</span></span> 
      
     - <span data-ttu-id="f262c-133">_LpulMax_参数设置为最小值再加上当前单位乘以第 4 步中设置的变量。</span><span class="sxs-lookup"><span data-stu-id="f262c-133">Set the  _lpulMax_ parameter to the minimum value plus the current unit multiplied by the variable set in step 4.</span></span> 
      
     - <span data-ttu-id="f262c-134">_LpulFlags_参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="f262c-134">Set the  _lpulFlags_ parameter to 0.</span></span> 
      
   2. <span data-ttu-id="f262c-135">执行此对象应的任何处理。</span><span class="sxs-lookup"><span data-stu-id="f262c-135">Perform whatever processing should be done on this object.</span></span> <span data-ttu-id="f262c-136">如果对象是子对象和您的提供商显示进度的子对象，请将指针传递给方法_lpProgress_参数中的进度对象。</span><span class="sxs-lookup"><span data-stu-id="f262c-136">If the object is a subobject, and your provider displays progress for subobjects, pass a pointer to the progress object in the  _lpProgress_ parameter to the method.</span></span> 
      
   3. <span data-ttu-id="f262c-137">调用[IMAPIProgress::Progress](imapiprogress-progress.md)并传递的三个参数的下列值：</span><span class="sxs-lookup"><span data-stu-id="f262c-137">Call [IMAPIProgress::Progress](imapiprogress-progress.md) and pass the following values for the three parameters:</span></span> 
      
     - <span data-ttu-id="f262c-138">_UlValue_参数设置为设置在步骤 2 乘以当前对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f262c-138">Set the  _ulValue_ parameter to variable set in step 2 multiplied by the current object.</span></span> 
      
     - <span data-ttu-id="f262c-139">_UlCount_参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="f262c-139">Set the  _ulCount_ parameter to 0.</span></span> 
      
     - <span data-ttu-id="f262c-140">_UlTotal_参数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="f262c-140">Set the  _ulTotal_ parameter to 0.</span></span> 
    
<span data-ttu-id="f262c-141">下面的代码示例说明了显示所有级别将包含五个子文件夹的文件夹的内容复制操作的进度所需的逻辑。</span><span class="sxs-lookup"><span data-stu-id="f262c-141">The following code example illustrates the logic required to show progress at all levels of an operation that copies the contents of a folder that contains five subfolders.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="f262c-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f262c-142">See also</span></span>

- [<span data-ttu-id="f262c-143">MAPI 进度指示器</span><span class="sxs-lookup"><span data-stu-id="f262c-143">MAPI Progress Indicators</span></span>](mapi-progress-indicators.md)

