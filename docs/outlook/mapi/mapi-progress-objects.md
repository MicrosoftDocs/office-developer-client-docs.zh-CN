---
title: MAPI Progress 对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e446004e-1ef2-4e58-b764-de7b4dcefaf1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 73d905028f8f62ad8cbb9da9b1ad61b8cab1065e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422024"
---
# <a name="mapi-progress-objects"></a><span data-ttu-id="0837f-103">MAPI Progress 对象</span><span class="sxs-lookup"><span data-stu-id="0837f-103">MAPI Progress Objects</span></span>

  
  
<span data-ttu-id="0837f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0837f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0837f-105">使用进度对象的方法和数据，可以控制指示器报告进度的方式。</span><span class="sxs-lookup"><span data-stu-id="0837f-105">With the methods and data of a progress object, you can control how the indicator reports progress.</span></span> <span data-ttu-id="0837f-106">虽然客户端或 MAPI 实现了进度对象，但确保进度显示正确无误的多数负担都由服务提供商承担。</span><span class="sxs-lookup"><span data-stu-id="0837f-106">Although a client or MAPI implements the progress object, most of the burden of ensuring the correctness of the progress display falls on service providers.</span></span> <span data-ttu-id="0837f-107">通过为传递给 progress 对象方法的参数指定特定顺序和值，可以保证其准确性。</span><span class="sxs-lookup"><span data-stu-id="0837f-107">You can guarantee its accuracy by specifying a particular order and value for the parameters that are passed to progress object methods.</span></span>
  
<span data-ttu-id="0837f-108">以下参数将传递给 progress 对象：</span><span class="sxs-lookup"><span data-stu-id="0837f-108">The following parameters are passed to progress objects:</span></span>
  
- <span data-ttu-id="0837f-109">标志的位掩码，使用 [IMAPIProgress：：SetLimits](imapiprogress-setlimits.md) 设置，使用 [IMAPIProgress：：GetFlags 检索](imapiprogress-getflags.md)。</span><span class="sxs-lookup"><span data-stu-id="0837f-109">A bitmask of flags, set with [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) and retrieved with [IMAPIProgress::GetFlags](imapiprogress-getflags.md).</span></span>
    
- <span data-ttu-id="0837f-110">本地和全局 (的最小值) **SetLimits** 设置，然后使用 [IMAPIProgress：：GetMin 检索](imapiprogress-getmin.md)。</span><span class="sxs-lookup"><span data-stu-id="0837f-110">A minimum value (local and global), set with **SetLimits** and retrieved with [IMAPIProgress::GetMin](imapiprogress-getmin.md).</span></span>
    
- <span data-ttu-id="0837f-111">本地和全局 (的最大值) **SetLimits** 设置，然后使用 [IMAPIProgress：：GetMax 检索](imapiprogress-getmax.md)。</span><span class="sxs-lookup"><span data-stu-id="0837f-111">A maximum value (local and global), set with **SetLimits** and retrieved with [IMAPIProgress::GetMax](imapiprogress-getmax.md).</span></span>
    
- <span data-ttu-id="0837f-112">一个值，指示操作的当前完成百分比，传递给 [IMAPIProgress：:P rogress](imapiprogress-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="0837f-112">A value that indicates the current percentage of completion of the operation, passed to [IMAPIProgress::Progress](imapiprogress-progress.md).</span></span>
    
- <span data-ttu-id="0837f-113">到目前为止已处理的对象数的计数，传递给 **Progress**。</span><span class="sxs-lookup"><span data-stu-id="0837f-113">A count of the number of objects that have so far been processed, passed to **Progress**.</span></span>
    
- <span data-ttu-id="0837f-114">操作中涉及的对象总数，传递给 Progress **。**</span><span class="sxs-lookup"><span data-stu-id="0837f-114">A count of the total number of objects involved in the operation, passed to **Progress**.</span></span>
    
<span data-ttu-id="0837f-115">所有服务提供商都通过调用 **IMAPIProgress：：GetFlags** 以检索当前标志设置开始其进度显示处理。</span><span class="sxs-lookup"><span data-stu-id="0837f-115">All service providers begin their progress display processing with a call to **IMAPIProgress::GetFlags** to retrieve the present flags setting.</span></span> <span data-ttu-id="0837f-116">目前，只能将标志设置为 MAPI_TOP_LEVEL。</span><span class="sxs-lookup"><span data-stu-id="0837f-116">Currently, the flags can be set only to MAPI_TOP_LEVEL.</span></span> <span data-ttu-id="0837f-117">客户端和 MAPI 将标志初始化为MAPI_TOP_LEVEL，并依赖服务提供商在适当的时候清除它。</span><span class="sxs-lookup"><span data-stu-id="0837f-117">Clients and MAPI initialize the flag to MAPI_TOP_LEVEL, relying on service providers to clear it when appropriate.</span></span> 
  
<span data-ttu-id="0837f-118">标志值设置为 MAPI_TOP_LEVEL处理操作中的顶级对象时。</span><span class="sxs-lookup"><span data-stu-id="0837f-118">The flags value is set to MAPI_TOP_LEVEL while you are working with the top-level object in the operation.</span></span> <span data-ttu-id="0837f-119">顶级对象是由客户端调用以开始操作的对象。</span><span class="sxs-lookup"><span data-stu-id="0837f-119">The top-level object is the object that is called by the client to begin an operation.</span></span> <span data-ttu-id="0837f-120">在文件夹复制操作中，这是要复制的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0837f-120">In a folder copy operation, this is the folder being copied.</span></span> <span data-ttu-id="0837f-121">在文件夹删除操作中，这是要删除的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0837f-121">In a folder delete operation, this is the folder being deleted.</span></span> <span data-ttu-id="0837f-122">调用处理较低级别对象或子对象时，请清除 flags 值。</span><span class="sxs-lookup"><span data-stu-id="0837f-122">When you make a call to process a lower level object, or subobject, clear the flags value.</span></span> <span data-ttu-id="0837f-123">在文件夹复制操作中，子对象是正在复制的文件夹中的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="0837f-123">In a folder copy operation, subobjects are the subfolders that are in the folder being copied.</span></span> 
  
<span data-ttu-id="0837f-124">MAPI 允许您区分顶级对象和具有 MAPI_TOP_LEVEL 标志的子对象，以便操作中涉及的所有对象可以使用同一 [IMAPIProgress](imapiprogressiunknown.md) 实现来显示进度，从而使指示器显示在单个正方向上平稳进行。</span><span class="sxs-lookup"><span data-stu-id="0837f-124">MAPI allows you to differentiate between top-level objects and subobjects with the MAPI_TOP_LEVEL flag so that all objects involved in an operation can use the same [IMAPIProgress](imapiprogressiunknown.md) implementation to show progress, thereby causing the indicator display to proceed smoothly in a single positive direction.</span></span> <span data-ttu-id="0837f-125">是否设置MAPI_TOP_LEVEL标记会影响后续调用进度对象时其他参数的设置。</span><span class="sxs-lookup"><span data-stu-id="0837f-125">Whether or not the MAPI_TOP_LEVEL flag is set affects the settings of the other parameters in subsequent calls to the progress object.</span></span> 
  
<span data-ttu-id="0837f-126">由于在多级操作的所有级别为进度显示设置适当的参数值是非特有的，因此一些服务提供商选择不显示子对象的进度。</span><span class="sxs-lookup"><span data-stu-id="0837f-126">Because it can be nontrivial to set appropriate parameter values for a progress display at all levels of a multilevel operation, some service providers elect not to show progress for subobjects.</span></span> 
  
 <span data-ttu-id="0837f-127">**避免显示子对象的进度**</span><span class="sxs-lookup"><span data-stu-id="0837f-127">**To avoid showing progress for subobjects**</span></span>
  
- <span data-ttu-id="0837f-128">在调用中为  _lpProgress_ 参数传递 NULL 以处理子对象。</span><span class="sxs-lookup"><span data-stu-id="0837f-128">Pass NULL for the  _lpProgress_ parameter in the call to process a subobject.</span></span> <span data-ttu-id="0837f-129">例如，如果要复制文件夹，则这是对子文件夹 [的 IMAPIFolder：：CopyFolder](imapifolder-copyfolder.md) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="0837f-129">For example, if you are copying folders, this is the call to a subfolder's [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md) method.</span></span> 
    
- <span data-ttu-id="0837f-130">编写特殊代码以确定如何解释  _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="0837f-130">Write special code to determine how to interpret the  _lpProgress_ parameter.</span></span> <span data-ttu-id="0837f-131">因为 _lpProgress_ 参数的 NULL 值还意味着客户端应该使用 MAPI 实现显示进度，所以需要特殊代码来确定何时忽略 _lpProgress_ 参数以及何时调用 [IMAPISupport：:D oProgressDialog。](imapisupport-doprogressdialog.md)</span><span class="sxs-lookup"><span data-stu-id="0837f-131">Because a NULL value for the  _lpProgress_ parameter can also mean that the client should display progress by using the MAPI implementation, special code is necessary to determine when to ignore the  _lpProgress_ parameter and when to call [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md).</span></span>
    
<span data-ttu-id="0837f-132">调用 **IMAPIProgress：：SetLimits** 设置或清除 MAPI_TOP_LEVEL 标志，并设置本地和全局最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="0837f-132">Call **IMAPIProgress::SetLimits** to set or clear the MAPI_TOP_LEVEL flag and to set local and global minimum and maximum values.</span></span> <span data-ttu-id="0837f-133">标志设置的值会影响进度对象是了解最小值还是最大值是本地值还是全局值。</span><span class="sxs-lookup"><span data-stu-id="0837f-133">The value of the flags setting affects whether the progress object understands the minimum and maximum values to be local or global.</span></span> <span data-ttu-id="0837f-134">设置 MAPI_TOP_LEVEL 标志时，这些值被视为全局值，用于计算整个操作的进度。</span><span class="sxs-lookup"><span data-stu-id="0837f-134">When the MAPI_TOP_LEVEL flag is set, these values are considered global and are used to calculate progress for the entire operation.</span></span> <span data-ttu-id="0837f-135">Progress 对象将全局最小值初始化为 0，将全局最大值初始化为 1000。</span><span class="sxs-lookup"><span data-stu-id="0837f-135">Progress objects initialize the global minimum value to 0 and the global maximum value to 1000.</span></span> 
  
<span data-ttu-id="0837f-136">未MAPI_TOP_LEVEL时，最小值和最大值被视为本地值，供提供程序在内部用于显示较低级别的子对象的进度。</span><span class="sxs-lookup"><span data-stu-id="0837f-136">When MAPI_TOP_LEVEL is not set, the minimum and maximum values are considered local and are used internally by providers to display progress for lower level subobjects.</span></span> <span data-ttu-id="0837f-137">Progress 对象仅保存本地最小值和最大值，以便它们可以在 **调用 GetMin** 和 **GetMax** 时返回到提供程序。</span><span class="sxs-lookup"><span data-stu-id="0837f-137">Progress objects save the local minimum and maximum values only so that they can be returned to providers when **GetMin** and **GetMax** are called.</span></span> 
  
<span data-ttu-id="0837f-138">值、对象计数和对象总数参数是 **IMAPIProgress：:P rogress 方法** 的输入。</span><span class="sxs-lookup"><span data-stu-id="0837f-138">The value, object count, and object total parameters are input to the **IMAPIProgress::Progress** method.</span></span> <span data-ttu-id="0837f-139">value 参数是一个指示进度百分比的数值。</span><span class="sxs-lookup"><span data-stu-id="0837f-139">The value parameter, a number that indicates the percentage of progress, is required.</span></span> <span data-ttu-id="0837f-140">如果MAPI_TOP_LEVEL，则还可以传递对象计数和对象总数。</span><span class="sxs-lookup"><span data-stu-id="0837f-140">If the MAPI_TOP_LEVEL flag is set, you can also pass an object count and an object total.</span></span> <span data-ttu-id="0837f-141">某些客户端使用这些值显示一个短语，例如"5 个项目已完成，10 个项目已完成"以及进度指示器。</span><span class="sxs-lookup"><span data-stu-id="0837f-141">Some clients use these values to display a phrase such as "5 items completed out of 10" with the progress indicator.</span></span> <span data-ttu-id="0837f-142">可以严格按照百分比或百分比以及已处理项目数（从要处理的项目总数中）报告操作进度。</span><span class="sxs-lookup"><span data-stu-id="0837f-142">Progress on an operation can be reported strictly as a percentage or as a percentage and in terms of the number of items that have been processed out of the total to be processed.</span></span> <span data-ttu-id="0837f-143">例如，如果您是邮件存储提供程序，并且正在执行复制 10 个文件夹的复制操作，则进度指示器可以通过显示短语（如"1/10"、"2/10"、"3 of 10"等）来向用户提供其他信息，直到操作完成。</span><span class="sxs-lookup"><span data-stu-id="0837f-143">For example, if you are a message store provider and you are performing a copy operation that is copying 10 folders, the progress indicator can supply the user with additional information by displaying a phrase such as "1 of 10", "2 of 10", "3 of 10", and so on until the operation is complete.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0837f-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0837f-144">See also</span></span>



[<span data-ttu-id="0837f-145">MAPI 进度指示器</span><span class="sxs-lookup"><span data-stu-id="0837f-145">MAPI Progress Indicators</span></span>](mapi-progress-indicators.md)

