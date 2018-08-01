---
title: MAPI 进度对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e446004e-1ef2-4e58-b764-de7b4dcefaf1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3007aeb5ac3810c57ed6fb4a555d5ce22e831768
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776282"
---
# <a name="mapi-progress-objects"></a><span data-ttu-id="4bca5-103">MAPI 进度对象</span><span class="sxs-lookup"><span data-stu-id="4bca5-103">MAPI Progress Objects</span></span>

  
  
<span data-ttu-id="4bca5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4bca5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4bca5-105">使用的方法和进度对象的数据，您可以控制如何标记报告进度。</span><span class="sxs-lookup"><span data-stu-id="4bca5-105">With the methods and data of a progress object, you can control how the indicator reports progress.</span></span> <span data-ttu-id="4bca5-106">客户端或 MAPI 实现进度对象，虽然大部分的负担，确保正确的进度显示属于服务提供商。</span><span class="sxs-lookup"><span data-stu-id="4bca5-106">Although a client or MAPI implements the progress object, most of the burden of ensuring the correctness of the progress display falls on service providers.</span></span> <span data-ttu-id="4bca5-107">您可以通过指定特定的顺序和传递给进度对象方法的参数值保证其准确性。</span><span class="sxs-lookup"><span data-stu-id="4bca5-107">You can guarantee its accuracy by specifying a particular order and value for the parameters that are passed to progress object methods.</span></span>
  
<span data-ttu-id="4bca5-108">以下参数传递给进度对象：</span><span class="sxs-lookup"><span data-stu-id="4bca5-108">The following parameters are passed to progress objects:</span></span>
  
- <span data-ttu-id="4bca5-109">标志，与[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)设置和检索与[IMAPIProgress::GetFlags](imapiprogress-getflags.md)的位掩码。</span><span class="sxs-lookup"><span data-stu-id="4bca5-109">A bitmask of flags, set with [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) and retrieved with [IMAPIProgress::GetFlags](imapiprogress-getflags.md).</span></span>
    
- <span data-ttu-id="4bca5-110">（本地和全局） 的最小值与**SetLimits**设置，并检索与[IMAPIProgress::GetMin](imapiprogress-getmin.md)。</span><span class="sxs-lookup"><span data-stu-id="4bca5-110">A minimum value (local and global), set with **SetLimits** and retrieved with [IMAPIProgress::GetMin](imapiprogress-getmin.md).</span></span>
    
- <span data-ttu-id="4bca5-111">（本地和全局） 的最大值与**SetLimits**设置，并检索与[IMAPIProgress::GetMax](imapiprogress-getmax.md)。</span><span class="sxs-lookup"><span data-stu-id="4bca5-111">A maximum value (local and global), set with **SetLimits** and retrieved with [IMAPIProgress::GetMax](imapiprogress-getmax.md).</span></span>
    
- <span data-ttu-id="4bca5-112">一个值，指示当前操作，传递给[IMAPIProgress::Progress](imapiprogress-progress.md)完成百分比。</span><span class="sxs-lookup"><span data-stu-id="4bca5-112">A value that indicates the current percentage of completion of the operation, passed to [IMAPIProgress::Progress](imapiprogress-progress.md).</span></span>
    
- <span data-ttu-id="4bca5-113">到目前为止已处理，传递给**进度**的对象数的计数。</span><span class="sxs-lookup"><span data-stu-id="4bca5-113">A count of the number of objects that have so far been processed, passed to **Progress**.</span></span>
    
- <span data-ttu-id="4bca5-114">操作，传递给**进度**中所涉及的对象的总数的计数。</span><span class="sxs-lookup"><span data-stu-id="4bca5-114">A count of the total number of objects involved in the operation, passed to **Progress**.</span></span>
    
<span data-ttu-id="4bca5-115">所有服务提供商都开始处理与**IMAPIProgress::GetFlags**到呼叫中以检索存在标志设置其进行显示。</span><span class="sxs-lookup"><span data-stu-id="4bca5-115">All service providers begin their progress display processing with a call to **IMAPIProgress::GetFlags** to retrieve the present flags setting.</span></span> <span data-ttu-id="4bca5-116">目前，可以仅对 MAPI_TOP_LEVEL 设置标志。</span><span class="sxs-lookup"><span data-stu-id="4bca5-116">Currently, the flags can be set only to MAPI_TOP_LEVEL.</span></span> <span data-ttu-id="4bca5-117">客户端和 MAPI 初始化 MAPI_TOP_LEVEL，标志依赖于服务提供商，以将其适当时清除。</span><span class="sxs-lookup"><span data-stu-id="4bca5-117">Clients and MAPI initialize the flag to MAPI_TOP_LEVEL, relying on service providers to clear it when appropriate.</span></span> 
  
<span data-ttu-id="4bca5-118">Flags 值设置为 MAPI_TOP_LEVEL 时您正在使用操作中的顶级对象。</span><span class="sxs-lookup"><span data-stu-id="4bca5-118">The flags value is set to MAPI_TOP_LEVEL while you are working with the top-level object in the operation.</span></span> <span data-ttu-id="4bca5-119">顶级对象是由客户端开始操作调用的对象。</span><span class="sxs-lookup"><span data-stu-id="4bca5-119">The top-level object is the object that is called by the client to begin an operation.</span></span> <span data-ttu-id="4bca5-120">在文件夹复制操作，这是要复制的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4bca5-120">In a folder copy operation, this is the folder being copied.</span></span> <span data-ttu-id="4bca5-121">在文件夹删除操作中，这是要删除的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4bca5-121">In a folder delete operation, this is the folder being deleted.</span></span> <span data-ttu-id="4bca5-122">当您进行的呼叫处理较低的 level 对象或子对象，请清除该标志值。</span><span class="sxs-lookup"><span data-stu-id="4bca5-122">When you make a call to process a lower level object, or subobject, clear the flags value.</span></span> <span data-ttu-id="4bca5-123">在文件夹复制操作，子对象是要复制的文件夹中的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="4bca5-123">In a folder copy operation, subobjects are the subfolders that are in the folder being copied.</span></span> 
  
<span data-ttu-id="4bca5-124">MAPI 允许您区分顶级对象，并与 MAPI_TOP_LEVEL 标志的子对象，以便在操作中涉及的所有对象可以使用相同的[IMAPIProgress](imapiprogressiunknown.md)实现以显示进度，从而导致到标记显示顺利的一个正数方向。</span><span class="sxs-lookup"><span data-stu-id="4bca5-124">MAPI allows you to differentiate between top-level objects and subobjects with the MAPI_TOP_LEVEL flag so that all objects involved in an operation can use the same [IMAPIProgress](imapiprogressiunknown.md) implementation to show progress, thereby causing the indicator display to proceed smoothly in a single positive direction.</span></span> <span data-ttu-id="4bca5-125">设置了 MAPI_TOP_LEVEL 标志会影响的后面对进度对象中的其他参数的设置。</span><span class="sxs-lookup"><span data-stu-id="4bca5-125">Whether or not the MAPI_TOP_LEVEL flag is set affects the settings of the other parameters in subsequent calls to the progress object.</span></span> 
  
<span data-ttu-id="4bca5-126">由于可能很重要多级操作的所有级别设置适当的参数值的进度显示，某些服务提供商选择不显示进度的子对象。</span><span class="sxs-lookup"><span data-stu-id="4bca5-126">Because it can be nontrivial to set appropriate parameter values for a progress display at all levels of a multilevel operation, some service providers elect not to show progress for subobjects.</span></span> 
  
 <span data-ttu-id="4bca5-127">**若要避免显示进度的子对象**</span><span class="sxs-lookup"><span data-stu-id="4bca5-127">**To avoid showing progress for subobjects**</span></span>
  
- <span data-ttu-id="4bca5-128">呼叫处理子对象中的_lpProgress_参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="4bca5-128">Pass NULL for the  _lpProgress_ parameter in the call to process a subobject.</span></span> <span data-ttu-id="4bca5-129">例如，如果要复制的文件夹，这是对的子文件夹[IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="4bca5-129">For example, if you are copying folders, this is the call to a subfolder's [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md) method.</span></span> 
    
- <span data-ttu-id="4bca5-130">编写特殊代码以确定如何解释_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="4bca5-130">Write special code to determine how to interpret the  _lpProgress_ parameter.</span></span> <span data-ttu-id="4bca5-131">因为_lpProgress_参数的 NULL 值还意味着在客户端，应使用 MAPI 实现显示进度，都需要以确定何时忽略_lpProgress_参数以及何时调用[特殊代码IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)。</span><span class="sxs-lookup"><span data-stu-id="4bca5-131">Because a NULL value for the  _lpProgress_ parameter can also mean that the client should display progress by using the MAPI implementation, special code is necessary to determine when to ignore the  _lpProgress_ parameter and when to call [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md).</span></span>
    
<span data-ttu-id="4bca5-132">调用**IMAPIProgress::SetLimits**设置或清除 MAPI_TOP_LEVEL 标志并设置本地和全局最小和最大值。</span><span class="sxs-lookup"><span data-stu-id="4bca5-132">Call **IMAPIProgress::SetLimits** to set or clear the MAPI_TOP_LEVEL flag and to set local and global minimum and maximum values.</span></span> <span data-ttu-id="4bca5-133">是否设置会影响 flags 的值的进度对象可识别为本地域或全局的最小和最大值。</span><span class="sxs-lookup"><span data-stu-id="4bca5-133">The value of the flags setting affects whether the progress object understands the minimum and maximum values to be local or global.</span></span> <span data-ttu-id="4bca5-134">当设置 MAPI_TOP_LEVEL 标志时，这些值将被视为全局并用于计算整个操作的进度。</span><span class="sxs-lookup"><span data-stu-id="4bca5-134">When the MAPI_TOP_LEVEL flag is set, these values are considered global and are used to calculate progress for the entire operation.</span></span> <span data-ttu-id="4bca5-135">进度对象初始化为 0 的全局最小值和全局最大值为 1000年。</span><span class="sxs-lookup"><span data-stu-id="4bca5-135">Progress objects initialize the global minimum value to 0 and the global maximum value to 1000.</span></span> 
  
<span data-ttu-id="4bca5-136">当不设置 MAPI_TOP_LEVEL 时，最小和最大值将被视为本地并用于内部由提供商提供显示正在进行较低级别的子对象。</span><span class="sxs-lookup"><span data-stu-id="4bca5-136">When MAPI_TOP_LEVEL is not set, the minimum and maximum values are considered local and are used internally by providers to display progress for lower level subobjects.</span></span> <span data-ttu-id="4bca5-137">进度对象仅，以便他们可以返回到提供程序时调用**GetMin**和**GetMax**保存本地的最小和最大值。</span><span class="sxs-lookup"><span data-stu-id="4bca5-137">Progress objects save the local minimum and maximum values only so that they can be returned to providers when **GetMin** and **GetMax** are called.</span></span> 
  
<span data-ttu-id="4bca5-138">值对象计数和对象总参数是输入**IMAPIProgress::Progress**方法。</span><span class="sxs-lookup"><span data-stu-id="4bca5-138">The value, object count, and object total parameters are input to the **IMAPIProgress::Progress** method.</span></span> <span data-ttu-id="4bca5-139">需要 value 参数，一个数字，指示的进度，百分比。</span><span class="sxs-lookup"><span data-stu-id="4bca5-139">The value parameter, a number that indicates the percentage of progress, is required.</span></span> <span data-ttu-id="4bca5-140">如果设置了 MAPI_TOP_LEVEL 标志，您还可以传递对象计数和对象的汇总。</span><span class="sxs-lookup"><span data-stu-id="4bca5-140">If the MAPI_TOP_LEVEL flag is set, you can also pass an object count and an object total.</span></span> <span data-ttu-id="4bca5-141">某些客户端使用这些值显示进度指示器的短语，例如"5 项目完成 10"。</span><span class="sxs-lookup"><span data-stu-id="4bca5-141">Some clients use these values to display a phrase such as "5 items completed out of 10" with the progress indicator.</span></span> <span data-ttu-id="4bca5-142">以百分比形式或百分比和已处理的总处理出的项目数方面可以严格报告上操作的进度。</span><span class="sxs-lookup"><span data-stu-id="4bca5-142">Progress on an operation can be reported strictly as a percentage or as a percentage and in terms of the number of items that have been processed out of the total to be processed.</span></span> <span data-ttu-id="4bca5-143">例如，如果您是消息存储提供程序，并且您执行复制 10 文件夹复制操作，进度指示器可以提供的其他信息的用户通过显示"10 的 1"、"为 10 2"、"3 为 10"等的短语操作完成之前，依此类推。</span><span class="sxs-lookup"><span data-stu-id="4bca5-143">For example, if you are a message store provider and you are performing a copy operation that is copying 10 folders, the progress indicator can supply the user with additional information by displaying a phrase such as "1 of 10", "2 of 10", "3 of 10", and so on until the operation is complete.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4bca5-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bca5-144">See also</span></span>



[<span data-ttu-id="4bca5-145">MAPI 进度指示器</span><span class="sxs-lookup"><span data-stu-id="4bca5-145">MAPI Progress Indicators</span></span>](mapi-progress-indicators.md)

