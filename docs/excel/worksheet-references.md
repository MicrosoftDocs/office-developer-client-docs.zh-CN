---
title: 工作表引用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 引用 [excel 2007], 工作表, 工作表引用 [excel 2007], 外部工作表引用 [excel 2007], 活动工作表 [excel 2007], 当前工作表 [excel 2007], 内部工作表引用 [excel 2007]
localization_priority: Normal
ms.assetid: 53406fb8-4ca5-4204-a6ad-b21ca9e6a100
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 2944f73a3144837a4be8aff7c7fed9a8d2158203
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304023"
---
# <a name="worksheet-references"></a><span data-ttu-id="8692b-104">工作表引用</span><span class="sxs-lookup"><span data-stu-id="8692b-104">Worksheet References</span></span>

 <span data-ttu-id="8692b-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8692b-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="8692b-106">Microsoft Excel 中的引用是指矩形单元格块 (可以只是一个单元格) 的数据类型, 或者在某些情况下, 许多不连续的单元格块。</span><span class="sxs-lookup"><span data-stu-id="8692b-106">A reference in Microsoft Excel is a data type that refers to a rectangular block of cells (which can be just one cell), or in some cases, a number of disjoint blocks of cells.</span></span> <span data-ttu-id="8692b-107">在内部, Excel 将对当前工作表上的单元格使用一种引用类型, 称为 "内部引用"。</span><span class="sxs-lookup"><span data-stu-id="8692b-107">Internally, Excel uses one reference type for cells on the current sheet, known as an internal reference.</span></span> <span data-ttu-id="8692b-108">不在当前工作表上的任何单元格由称为外部引用的另一种引用类型进行描述。</span><span class="sxs-lookup"><span data-stu-id="8692b-108">Any cell that is not on the current sheet is described by another type of reference known as an external reference.</span></span> <span data-ttu-id="8692b-109">有关 active 和 current 的定义, 请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="8692b-109">See the next section for the definition of active and current.</span></span>
  
## <a name="active-vs-current"></a><span data-ttu-id="8692b-110">活动与当前</span><span class="sxs-lookup"><span data-stu-id="8692b-110">Active vs. Current</span></span>

<span data-ttu-id="8692b-111">在 Excel 中, 术语 "活动" 表示用户正在查看的内容。</span><span class="sxs-lookup"><span data-stu-id="8692b-111">In Excel, the term active refers to what the user is viewing.</span></span> <span data-ttu-id="8692b-112">当前工作簿和工作表是用户当前正在查看的工作簿和工作表, 或者, 如果 excel 失去焦点到另一个应用程序, 则查看 excel 上次获得焦点的时间。</span><span class="sxs-lookup"><span data-stu-id="8692b-112">The active workbook and worksheet are those that the user is currently looking at, or, if Excel has lost focus to another application, was looking at when Excel last had focus.</span></span> <span data-ttu-id="8692b-113">活动工作表始终在活动工作簿中。</span><span class="sxs-lookup"><span data-stu-id="8692b-113">The active sheet is always in the active workbook.</span></span> <span data-ttu-id="8692b-114">在活动工作表中选择的一个或多个单元格称为活动单元格。</span><span class="sxs-lookup"><span data-stu-id="8692b-114">The one or more cells that are selected in the active sheet are known as the active cells.</span></span> <span data-ttu-id="8692b-115">如果嵌入对象有焦点, 则最后选定的单元格仍处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="8692b-115">If an embedded object has focus, the last-selected cells are still active.</span></span> 
  
<span data-ttu-id="8692b-116">术语 current 指 Excel 要重新计算的内容。</span><span class="sxs-lookup"><span data-stu-id="8692b-116">The term current refers to what Excel is recalculating.</span></span> <span data-ttu-id="8692b-117">当前的工作簿和工作表是当前正在重新计算的工作簿和工作表。</span><span class="sxs-lookup"><span data-stu-id="8692b-117">The current workbook and worksheet are those that are currently being recalculated.</span></span> <span data-ttu-id="8692b-118">当前工作表始终在当前工作簿中。</span><span class="sxs-lookup"><span data-stu-id="8692b-118">The current sheet is always in the current workbook.</span></span> <span data-ttu-id="8692b-119">要重新计算的单元格称为当前单元格, 或者, 如果要重新计算数组公式, 则为当前单元格。</span><span class="sxs-lookup"><span data-stu-id="8692b-119">The cell being recalculated is known as the current cell, or, in the case of an array formula being recalculated, the current cells.</span></span> 
  
<span data-ttu-id="8692b-120">要记住的要点如下:</span><span class="sxs-lookup"><span data-stu-id="8692b-120">The important points to remember are as follows:</span></span>
  
- <span data-ttu-id="8692b-121">当前的工作簿/工作表/单元格通常不是当前工作簿/工作表/单元格, 但也是如此。</span><span class="sxs-lookup"><span data-stu-id="8692b-121">The active workbook/worksheet/cell is not generally the current one, although it can be.</span></span>
    
- <span data-ttu-id="8692b-122">加载项函数 (无论是在 Visual Basic for Applications (VBA) 模块中还是在 DLL 或 XLL 中) 总是从当前工作表上的当前单元格调用, 或者是在多线程重新计算 (MTR) 的情况下调用其中的一个。</span><span class="sxs-lookup"><span data-stu-id="8692b-122">An add-in function, whether in a Visual Basic for Applications (VBA) module or a DLL or XLL, is always called from the current cell on the current sheet, or one of them in the case of multithreaded recalculation (MTR).</span></span>
    
<span data-ttu-id="8692b-123">许多 Excel 函数, 提供有关单元格、单元格区域或工作簿中的工作表的信息区分活动工作簿、工作表或单元格与当前工作簿、工作表或单元格。</span><span class="sxs-lookup"><span data-stu-id="8692b-123">Many Excel functions that provide information about a cell, a range of cells, or a sheet in a workbook distinguish between the active workbook, sheet, or cell and the current workbook, sheet, or cell.</span></span> <span data-ttu-id="8692b-124">此差异反映在用于描述对单元格块的引用的数据类型中, 如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="8692b-124">This difference is reflected in the data types used to describe references to blocks of cells, as described in the following section.</span></span>
  
## <a name="internal-and-external-worksheet-references"></a><span data-ttu-id="8692b-125">内部和外部工作表引用</span><span class="sxs-lookup"><span data-stu-id="8692b-125">Internal and External Worksheet References</span></span>

<span data-ttu-id="8692b-126">内部引用和外部引用的主要区别是外部引用数据类型包含工作表的 ID, 也是对单元格所引用的说明。</span><span class="sxs-lookup"><span data-stu-id="8692b-126">The key difference between internal and external references is that the external reference data type contains an ID for the worksheet and also a description of which cells are referred to.</span></span> <span data-ttu-id="8692b-127">内部引用不包含对工作表的引用—它是隐式的工作表是当前工作表。</span><span class="sxs-lookup"><span data-stu-id="8692b-127">An internal reference contains no reference to the sheet—it is implicit that the sheet is the current sheet.</span></span> 
  
<span data-ttu-id="8692b-128">许多 C API 函数返回引用或获取引用参数。</span><span class="sxs-lookup"><span data-stu-id="8692b-128">Many C API functions return references or take reference arguments.</span></span> <span data-ttu-id="8692b-129">任何采用引用参数的 C API 函数都可接受内部引用或外部引用, 但**xlSheetNm**函数除外, 它需要外部引用。</span><span class="sxs-lookup"><span data-stu-id="8692b-129">Any C API function that takes reference arguments accepts either internal or external references, except the **xlSheetNm** function, which requires an external reference.</span></span> <span data-ttu-id="8692b-130">某些函数仅返回内部或外部引用。</span><span class="sxs-lookup"><span data-stu-id="8692b-130">Some functions only return either internal or external references.</span></span> <span data-ttu-id="8692b-131">例如, C API 函数[xlfCaller](xlfcaller.md)按定义返回对当前工作表上的调用单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="8692b-131">For example, the C API function [xlfCaller](xlfcaller.md) returns a reference to the calling cells, by definition, on the current sheet.</span></span> <span data-ttu-id="8692b-132">返回的引用始终是内部引用, 尽管函数可以返回不是从工作表单元格中调用函数的非引用类型。</span><span class="sxs-lookup"><span data-stu-id="8692b-132">The returned reference is always an internal reference, although the function can return non-reference types where the function is not called from a worksheet cell.</span></span> <span data-ttu-id="8692b-133">C API 函数[xlSheetId](xlsheetid.md)始终返回包含在外部引用数据类型中的工作表的 ID。</span><span class="sxs-lookup"><span data-stu-id="8692b-133">The C API function [xlSheetId](xlsheetid.md) always returns the ID of a worksheet contained within an external reference data type.</span></span> 
  
<span data-ttu-id="8692b-134">内部和外部引用类型之间的其他关键区别在于外部引用数据类型可以在同一工作表上描述多个脱节的单元格块。</span><span class="sxs-lookup"><span data-stu-id="8692b-134">The other key difference between the internal and external reference types is that the external reference data type can describe multiple disjoint blocks of cells on the same sheet.</span></span> <span data-ttu-id="8692b-135">内部引用只能描述当前工作表上的一个块。</span><span class="sxs-lookup"><span data-stu-id="8692b-135">Internal references can describe only a single block on the current sheet.</span></span> <span data-ttu-id="8692b-136">不连续引用可传递给采用 range 参数的任何函数。</span><span class="sxs-lookup"><span data-stu-id="8692b-136">Disjoint references can be passed to any function that takes a range argument.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8692b-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8692b-137">See also</span></span>



[<span data-ttu-id="8692b-138">Excel 编程概念</span><span class="sxs-lookup"><span data-stu-id="8692b-138">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
  
[<span data-ttu-id="8692b-139">评估名称和其他工作表公式表达式</span><span class="sxs-lookup"><span data-stu-id="8692b-139">Evaluating Names and Other Worksheet Formula Expressions</span></span>](evaluating-names-and-other-worksheet-formula-expressions.md)
  
[<span data-ttu-id="8692b-140">Excel 工作表和表达式计算</span><span class="sxs-lookup"><span data-stu-id="8692b-140">Excel Worksheet and Expression Evaluation</span></span>](excel-worksheet-and-expression-evaluation.md)

