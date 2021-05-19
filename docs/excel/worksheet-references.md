---
title: 工作表引用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- references [excel 2007]， worksheet，worksheet references [Excel 2007]，external worksheet references [Excel 2007]，active worksheet [Excel 2007]，current worksheet [Excel 2007]，internal worksheet references [Excel 2007]
localization_priority: Normal
ms.assetid: 53406fb8-4ca5-4204-a6ad-b21ca9e6a100
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 2944f73a3144837a4be8aff7c7fed9a8d2158203
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416459"
---
# <a name="worksheet-references"></a><span data-ttu-id="aa4aa-104">工作表引用</span><span class="sxs-lookup"><span data-stu-id="aa4aa-104">Worksheet References</span></span>

 <span data-ttu-id="aa4aa-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aa4aa-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="aa4aa-106">Microsoft Excel 中的引用是引用单元格 数据类型的矩形块 (该矩形块只能是一个单元格) ，在某些情况下，可以是多个不脱节的单元格块。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-106">A reference in Microsoft Excel is a data type that refers to a rectangular block of cells (which can be just one cell), or in some cases, a number of disjoint blocks of cells.</span></span> <span data-ttu-id="aa4aa-107">在内部Excel，对当前工作表上的单元格使用一种引用类型，称为内部引用。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-107">Internally, Excel uses one reference type for cells on the current sheet, known as an internal reference.</span></span> <span data-ttu-id="aa4aa-108">不在当前工作表上的任何单元格都由另一种引用类型（称为外部引用）描述。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-108">Any cell that is not on the current sheet is described by another type of reference known as an external reference.</span></span> <span data-ttu-id="aa4aa-109">有关活动和当前的定义，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-109">See the next section for the definition of active and current.</span></span>
  
## <a name="active-vs-current"></a><span data-ttu-id="aa4aa-110">活动与当前</span><span class="sxs-lookup"><span data-stu-id="aa4aa-110">Active vs. Current</span></span>

<span data-ttu-id="aa4aa-111">在Excel中，术语 active 是指用户正在查看的内容。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-111">In Excel, the term active refers to what the user is viewing.</span></span> <span data-ttu-id="aa4aa-112">活动工作簿和工作表是用户当前正在查看的工作簿和工作表，或者，如果Excel应用程序失去焦点，则查看上次Excel焦点的时间。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-112">The active workbook and worksheet are those that the user is currently looking at, or, if Excel has lost focus to another application, was looking at when Excel last had focus.</span></span> <span data-ttu-id="aa4aa-113">活动工作表始终位于活动工作簿中。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-113">The active sheet is always in the active workbook.</span></span> <span data-ttu-id="aa4aa-114">在活动工作表中选定的一个或多个单元格称为活动单元格。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-114">The one or more cells that are selected in the active sheet are known as the active cells.</span></span> <span data-ttu-id="aa4aa-115">如果嵌入对象具有焦点，则最后选定的单元格仍处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-115">If an embedded object has focus, the last-selected cells are still active.</span></span> 
  
<span data-ttu-id="aa4aa-116">术语"当前"是指Excel重新计算。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-116">The term current refers to what Excel is recalculating.</span></span> <span data-ttu-id="aa4aa-117">当前工作簿和工作表是当前正在重新计算的工作簿和工作表。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-117">The current workbook and worksheet are those that are currently being recalculated.</span></span> <span data-ttu-id="aa4aa-118">当前工作表始终在当前工作簿中。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-118">The current sheet is always in the current workbook.</span></span> <span data-ttu-id="aa4aa-119">重新计算的单元格称为当前单元格，在重新计算数组公式的情况下称为当前单元格。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-119">The cell being recalculated is known as the current cell, or, in the case of an array formula being recalculated, the current cells.</span></span> 
  
<span data-ttu-id="aa4aa-120">需要记住的要点如下：</span><span class="sxs-lookup"><span data-stu-id="aa4aa-120">The important points to remember are as follows:</span></span>
  
- <span data-ttu-id="aa4aa-121">活动工作簿/工作表/单元格通常不是当前工作簿/工作表/单元格，尽管它可以是当前工作簿/工作表/单元格。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-121">The active workbook/worksheet/cell is not generally the current one, although it can be.</span></span>
    
- <span data-ttu-id="aa4aa-122">外接程序函数（无论是在 Visual Basic for Applications (VBA) 模块中，还是 DLL 或 XLL 中）始终从当前工作表上的当前单元格调用，对于多线程重新计算 (MTR) ，始终调用其中一个函数。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-122">An add-in function, whether in a Visual Basic for Applications (VBA) module or a DLL or XLL, is always called from the current cell on the current sheet, or one of them in the case of multithreaded recalculation (MTR).</span></span>
    
<span data-ttu-id="aa4aa-123">许多Excel，这些函数提供有关工作簿中单元格、单元格区域或工作表的信息，以区分活动工作簿、工作表或单元格以及当前工作簿、工作表或单元格。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-123">Many Excel functions that provide information about a cell, a range of cells, or a sheet in a workbook distinguish between the active workbook, sheet, or cell and the current workbook, sheet, or cell.</span></span> <span data-ttu-id="aa4aa-124">此差异反映在用于描述对单元格块的引用的数据类型中，如下一节所述。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-124">This difference is reflected in the data types used to describe references to blocks of cells, as described in the following section.</span></span>
  
## <a name="internal-and-external-worksheet-references"></a><span data-ttu-id="aa4aa-125">内部和外部工作表引用</span><span class="sxs-lookup"><span data-stu-id="aa4aa-125">Internal and External Worksheet References</span></span>

<span data-ttu-id="aa4aa-126">内部和外部引用之间的主要区别在于，外部引用引用数据包含工作表的 ID 以及引用哪些单元格的说明。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-126">The key difference between internal and external references is that the external reference data type contains an ID for the worksheet and also a description of which cells are referred to.</span></span> <span data-ttu-id="aa4aa-127">内部引用不包含对工作表的引用-它是隐式的，即工作表是当前工作表。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-127">An internal reference contains no reference to the sheet—it is implicit that the sheet is the current sheet.</span></span> 
  
<span data-ttu-id="aa4aa-128">许多 C API 函数返回引用或接受引用参数。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-128">Many C API functions return references or take reference arguments.</span></span> <span data-ttu-id="aa4aa-129">任何采用引用参数的 C API 函数都接受内部或外部引用 **，xlSheetNm** 函数除外，该函数需要外部引用。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-129">Any C API function that takes reference arguments accepts either internal or external references, except the **xlSheetNm** function, which requires an external reference.</span></span> <span data-ttu-id="aa4aa-130">某些函数仅返回内部或外部引用。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-130">Some functions only return either internal or external references.</span></span> <span data-ttu-id="aa4aa-131">例如，C API 函数 [xlfCaller](xlfcaller.md) 根据定义返回对当前工作表上调用单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-131">For example, the C API function [xlfCaller](xlfcaller.md) returns a reference to the calling cells, by definition, on the current sheet.</span></span> <span data-ttu-id="aa4aa-132">返回的引用始终是内部引用，尽管该函数可以返回非引用类型，其中函数不是从工作表单元格调用的。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-132">The returned reference is always an internal reference, although the function can return non-reference types where the function is not called from a worksheet cell.</span></span> <span data-ttu-id="aa4aa-133">C API 函数 [xlSheetId](xlsheetid.md) 始终返回外部数据库类型中包含的引用数据 ID。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-133">The C API function [xlSheetId](xlsheetid.md) always returns the ID of a worksheet contained within an external reference data type.</span></span> 
  
<span data-ttu-id="aa4aa-134">内部和外部引用类型之间的另一个关键区别是，外部引用引用数据可以描述同一工作表上多个不脱节的单元格块。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-134">The other key difference between the internal and external reference types is that the external reference data type can describe multiple disjoint blocks of cells on the same sheet.</span></span> <span data-ttu-id="aa4aa-135">内部引用只能描述当前工作表上的单个块。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-135">Internal references can describe only a single block on the current sheet.</span></span> <span data-ttu-id="aa4aa-136">脱节引用可以传递给任何采用 range 参数的函数。</span><span class="sxs-lookup"><span data-stu-id="aa4aa-136">Disjoint references can be passed to any function that takes a range argument.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aa4aa-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa4aa-137">See also</span></span>



[<span data-ttu-id="aa4aa-138">Excel 编程概念</span><span class="sxs-lookup"><span data-stu-id="aa4aa-138">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
  
[<span data-ttu-id="aa4aa-139">求值名称和其他工作表公式表达式</span><span class="sxs-lookup"><span data-stu-id="aa4aa-139">Evaluating Names and Other Worksheet Formula Expressions</span></span>](evaluating-names-and-other-worksheet-formula-expressions.md)
  
[<span data-ttu-id="aa4aa-140">Excel 工作表和表达式计算</span><span class="sxs-lookup"><span data-stu-id="aa4aa-140">Excel Worksheet and Expression Evaluation</span></span>](excel-worksheet-and-expression-evaluation.md)

