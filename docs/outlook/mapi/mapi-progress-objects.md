---
title: MAPI 进度对象
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
# <a name="mapi-progress-objects"></a><span data-ttu-id="44f86-103">MAPI 进度对象</span><span class="sxs-lookup"><span data-stu-id="44f86-103">MAPI Progress Objects</span></span>

  
  
<span data-ttu-id="44f86-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="44f86-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="44f86-105">使用进度对象的方法和数据, 可以控制指示器报告进度的方式。</span><span class="sxs-lookup"><span data-stu-id="44f86-105">With the methods and data of a progress object, you can control how the indicator reports progress.</span></span> <span data-ttu-id="44f86-106">虽然客户端或 MAPI 实现了进度对象, 但确保进度显示正确的大部分负担在服务提供商上。</span><span class="sxs-lookup"><span data-stu-id="44f86-106">Although a client or MAPI implements the progress object, most of the burden of ensuring the correctness of the progress display falls on service providers.</span></span> <span data-ttu-id="44f86-107">您可以通过为传递给进度对象方法的参数指定特定的顺序和值来保证其准确性。</span><span class="sxs-lookup"><span data-stu-id="44f86-107">You can guarantee its accuracy by specifying a particular order and value for the parameters that are passed to progress object methods.</span></span>
  
<span data-ttu-id="44f86-108">将以下参数传递给进度对象:</span><span class="sxs-lookup"><span data-stu-id="44f86-108">The following parameters are passed to progress objects:</span></span>
  
- <span data-ttu-id="44f86-109">使用[IMAPIProgress:: SetLimits](imapiprogress-setlimits.md)设置的标志的位掩码, 并使用[IMAPIProgress:: GetFlags](imapiprogress-getflags.md)进行检索。</span><span class="sxs-lookup"><span data-stu-id="44f86-109">A bitmask of flags, set with [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) and retrieved with [IMAPIProgress::GetFlags](imapiprogress-getflags.md).</span></span>
    
- <span data-ttu-id="44f86-110">使用**SetLimits**设置的最小值 (本地和全局), 使用[IMAPIProgress:: GetMin](imapiprogress-getmin.md)进行检索。</span><span class="sxs-lookup"><span data-stu-id="44f86-110">A minimum value (local and global), set with **SetLimits** and retrieved with [IMAPIProgress::GetMin](imapiprogress-getmin.md).</span></span>
    
- <span data-ttu-id="44f86-111">使用**SetLimits**设置的最大值 (本地和全局), 使用[IMAPIProgress:: GetMax](imapiprogress-getmax.md)进行检索。</span><span class="sxs-lookup"><span data-stu-id="44f86-111">A maximum value (local and global), set with **SetLimits** and retrieved with [IMAPIProgress::GetMax](imapiprogress-getmax.md).</span></span>
    
- <span data-ttu-id="44f86-112">一个值, 该值指示传递给 IMAPIProgress 的当前完成的操作百分比[::P rogress](imapiprogress-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="44f86-112">A value that indicates the current percentage of completion of the operation, passed to [IMAPIProgress::Progress](imapiprogress-progress.md).</span></span>
    
- <span data-ttu-id="44f86-113">已传递到**进度**的已处理的对象数的计数。</span><span class="sxs-lookup"><span data-stu-id="44f86-113">A count of the number of objects that have so far been processed, passed to **Progress**.</span></span>
    
- <span data-ttu-id="44f86-114">传递给**进度**的操作中涉及的对象总数的计数。</span><span class="sxs-lookup"><span data-stu-id="44f86-114">A count of the total number of objects involved in the operation, passed to **Progress**.</span></span>
    
<span data-ttu-id="44f86-115">所有服务提供程序都通过调用**IMAPIProgress:: GetFlags**检索显示的标志设置来开始处理其进度显示处理。</span><span class="sxs-lookup"><span data-stu-id="44f86-115">All service providers begin their progress display processing with a call to **IMAPIProgress::GetFlags** to retrieve the present flags setting.</span></span> <span data-ttu-id="44f86-116">目前, 只能将标志设置为 MAPI_TOP_LEVEL。</span><span class="sxs-lookup"><span data-stu-id="44f86-116">Currently, the flags can be set only to MAPI_TOP_LEVEL.</span></span> <span data-ttu-id="44f86-117">客户端和 MAPI 将标志初始化为 MAPI_TOP_LEVEL, 并依赖服务提供程序在适当的时候将其清除。</span><span class="sxs-lookup"><span data-stu-id="44f86-117">Clients and MAPI initialize the flag to MAPI_TOP_LEVEL, relying on service providers to clear it when appropriate.</span></span> 
  
<span data-ttu-id="44f86-118">在处理操作中的顶级对象时, flags 值设置为 MAPI_TOP_LEVEL。</span><span class="sxs-lookup"><span data-stu-id="44f86-118">The flags value is set to MAPI_TOP_LEVEL while you are working with the top-level object in the operation.</span></span> <span data-ttu-id="44f86-119">顶级对象是由客户端调用以开始操作的对象。</span><span class="sxs-lookup"><span data-stu-id="44f86-119">The top-level object is the object that is called by the client to begin an operation.</span></span> <span data-ttu-id="44f86-120">在文件夹复制操作中, 这是要复制的文件夹。</span><span class="sxs-lookup"><span data-stu-id="44f86-120">In a folder copy operation, this is the folder being copied.</span></span> <span data-ttu-id="44f86-121">在文件夹删除操作中, 这是要删除的文件夹。</span><span class="sxs-lookup"><span data-stu-id="44f86-121">In a folder delete operation, this is the folder being deleted.</span></span> <span data-ttu-id="44f86-122">当您调用处理较低级别对象 (或子对象) 时, 请清除 flags 值。</span><span class="sxs-lookup"><span data-stu-id="44f86-122">When you make a call to process a lower level object, or subobject, clear the flags value.</span></span> <span data-ttu-id="44f86-123">在文件夹复制操作中, 子文件夹是要复制的文件夹中的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="44f86-123">In a folder copy operation, subobjects are the subfolders that are in the folder being copied.</span></span> 
  
<span data-ttu-id="44f86-124">MAPI 允许您区分顶级对象和子对象与 MAPI_TOP_LEVEL 标志, 以便操作中涉及的所有对象都可以使用相同的[IMAPIProgress](imapiprogressiunknown.md)实现来显示进度, 从而导致指示器显示在一个积极方向上顺利进行。</span><span class="sxs-lookup"><span data-stu-id="44f86-124">MAPI allows you to differentiate between top-level objects and subobjects with the MAPI_TOP_LEVEL flag so that all objects involved in an operation can use the same [IMAPIProgress](imapiprogressiunknown.md) implementation to show progress, thereby causing the indicator display to proceed smoothly in a single positive direction.</span></span> <span data-ttu-id="44f86-125">无论 MAPI_TOP_LEVEL 标志是否设置会影响对进度对象的后续调用中的其他参数的设置。</span><span class="sxs-lookup"><span data-stu-id="44f86-125">Whether or not the MAPI_TOP_LEVEL flag is set affects the settings of the other parameters in subsequent calls to the progress object.</span></span> 
  
<span data-ttu-id="44f86-126">由于可以将其设置为 nontrivial, 以便为多级操作的所有级别上的进度显示设置适当的参数值, 因此一些服务提供程序选择不显示子数据的进度。</span><span class="sxs-lookup"><span data-stu-id="44f86-126">Because it can be nontrivial to set appropriate parameter values for a progress display at all levels of a multilevel operation, some service providers elect not to show progress for subobjects.</span></span> 
  
 <span data-ttu-id="44f86-127">**避免显示子进程的进度**</span><span class="sxs-lookup"><span data-stu-id="44f86-127">**To avoid showing progress for subobjects**</span></span>
  
- <span data-ttu-id="44f86-128">在调用中为处理子过程的_lpProgress_参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="44f86-128">Pass NULL for the  _lpProgress_ parameter in the call to process a subobject.</span></span> <span data-ttu-id="44f86-129">例如, 如果要复制文件夹, 这就是对子文件夹的[IMAPIFolder:: CopyFolder](imapifolder-copyfolder.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="44f86-129">For example, if you are copying folders, this is the call to a subfolder's [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md) method.</span></span> 
    
- <span data-ttu-id="44f86-130">编写特殊代码以确定如何解释_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="44f86-130">Write special code to determine how to interpret the  _lpProgress_ parameter.</span></span> <span data-ttu-id="44f86-131">由于_lpProgress_参数的 NULL 值也可能意味着客户端应使用 MAPI 实现来显示进度, 因此需要特殊代码来确定何时忽略_lpProgress_参数以及何时调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)。</span><span class="sxs-lookup"><span data-stu-id="44f86-131">Because a NULL value for the  _lpProgress_ parameter can also mean that the client should display progress by using the MAPI implementation, special code is necessary to determine when to ignore the  _lpProgress_ parameter and when to call [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md).</span></span>
    
<span data-ttu-id="44f86-132">调用**IMAPIProgress:: SetLimits**以设置或清除 MAPI_TOP_LEVEL 标志并设置本地和全局最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="44f86-132">Call **IMAPIProgress::SetLimits** to set or clear the MAPI_TOP_LEVEL flag and to set local and global minimum and maximum values.</span></span> <span data-ttu-id="44f86-133">flags 设置的值会影响进度对象是否理解为本地或全局的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="44f86-133">The value of the flags setting affects whether the progress object understands the minimum and maximum values to be local or global.</span></span> <span data-ttu-id="44f86-134">设置 MAPI_TOP_LEVEL 标志后, 这些值被视为全局值, 用于计算整个操作的进度。</span><span class="sxs-lookup"><span data-stu-id="44f86-134">When the MAPI_TOP_LEVEL flag is set, these values are considered global and are used to calculate progress for the entire operation.</span></span> <span data-ttu-id="44f86-135">进度对象将全局最小值初始化为 0, 将全局最大值初始化为1000。</span><span class="sxs-lookup"><span data-stu-id="44f86-135">Progress objects initialize the global minimum value to 0 and the global maximum value to 1000.</span></span> 
  
<span data-ttu-id="44f86-136">如果未设置 MAPI_TOP_LEVEL, 最小值和最大值将被视为本地值, 并由提供程序在内部使用, 以显示较低级别的子数据的进度。</span><span class="sxs-lookup"><span data-stu-id="44f86-136">When MAPI_TOP_LEVEL is not set, the minimum and maximum values are considered local and are used internally by providers to display progress for lower level subobjects.</span></span> <span data-ttu-id="44f86-137">进度对象仅保存本地最小值和最大值, 以便在**GetMin**和**GetMax**调用时可以将其返回到提供程序。</span><span class="sxs-lookup"><span data-stu-id="44f86-137">Progress objects save the local minimum and maximum values only so that they can be returned to providers when **GetMin** and **GetMax** are called.</span></span> 
  
<span data-ttu-id="44f86-138">值、对象数和对象总计参数是**IMAPIProgress::P rogress**方法的输入。</span><span class="sxs-lookup"><span data-stu-id="44f86-138">The value, object count, and object total parameters are input to the **IMAPIProgress::Progress** method.</span></span> <span data-ttu-id="44f86-139">value 参数 (一个指示进度百分比的数字) 是必需的。</span><span class="sxs-lookup"><span data-stu-id="44f86-139">The value parameter, a number that indicates the percentage of progress, is required.</span></span> <span data-ttu-id="44f86-140">如果设置了 MAPI_TOP_LEVEL 标志, 则还可以传递对象数和对象总数。</span><span class="sxs-lookup"><span data-stu-id="44f86-140">If the MAPI_TOP_LEVEL flag is set, you can also pass an object count and an object total.</span></span> <span data-ttu-id="44f86-141">有些客户端使用这些值来显示一个短语, 如 "5 个项目已完成10个" (带有进度指示器)。</span><span class="sxs-lookup"><span data-stu-id="44f86-141">Some clients use these values to display a phrase such as "5 items completed out of 10" with the progress indicator.</span></span> <span data-ttu-id="44f86-142">可以严格将操作的进度报告为百分比, 也可以根据处理的待处理的项目数的百分比形式报告。</span><span class="sxs-lookup"><span data-stu-id="44f86-142">Progress on an operation can be reported strictly as a percentage or as a percentage and in terms of the number of items that have been processed out of the total to be processed.</span></span> <span data-ttu-id="44f86-143">例如, 如果您是一封邮件存储提供程序, 并且正在执行复制10个文件夹的复制操作, 则通过显示一个短语 (如 "1 个, 共10个"、"2 of 10"、"3 of 10"), 进度指示器可以为用户提供其他信息。等, 直到操作完成。</span><span class="sxs-lookup"><span data-stu-id="44f86-143">For example, if you are a message store provider and you are performing a copy operation that is copying 10 folders, the progress indicator can supply the user with additional information by displaying a phrase such as "1 of 10", "2 of 10", "3 of 10", and so on until the operation is complete.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="44f86-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44f86-144">See also</span></span>



[<span data-ttu-id="44f86-145">MAPI 进度指示器</span><span class="sxs-lookup"><span data-stu-id="44f86-145">MAPI Progress Indicators</span></span>](mapi-progress-indicators.md)

