---
title: 工作表引用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 引用 [excel 2007]、 工作表、 工作表引用 [Excel 2007]、 外部工作表引用 [Excel 2007]、 活动工作表 [Excel 2007]、 当前工作表 [Excel 2007]、 内部的工作表引用 [Excel 2007]
localization_priority: Normal
ms.assetid: 53406fb8-4ca5-4204-a6ad-b21ca9e6a100
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: b7089fb891c96be9182189e3a5f30057721cebbc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773835"
---
# <a name="worksheet-references"></a><span data-ttu-id="870b8-104">工作表引用</span><span class="sxs-lookup"><span data-stu-id="870b8-104">Worksheet References</span></span>

 <span data-ttu-id="870b8-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="870b8-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="870b8-106">Microsoft Excel 中的引用是指的矩形块的单元格 （它可能只有一个单元格），或在某些情况下，非连续单元格块大量数据类型。</span><span class="sxs-lookup"><span data-stu-id="870b8-106">A reference in Microsoft Excel is a data type that refers to a rectangular block of cells (which can be just one cell), or in some cases, a number of disjoint blocks of cells.</span></span> <span data-ttu-id="870b8-107">内部，Excel 将使用一个引用类型称为内部引用当前的工作表上的单元格。</span><span class="sxs-lookup"><span data-stu-id="870b8-107">Internally, Excel uses one reference type for cells on the current sheet, known as an internal reference.</span></span> <span data-ttu-id="870b8-108">不在当前工作表的任意单元格被描述另一种称为外部引用的引用。</span><span class="sxs-lookup"><span data-stu-id="870b8-108">Any cell that is not on the current sheet is described by another type of reference known as an external reference.</span></span> <span data-ttu-id="870b8-109">请参阅定义活动和当前的下一节。</span><span class="sxs-lookup"><span data-stu-id="870b8-109">See the next section for the definition of active and current.</span></span>
  
## <a name="active-vs-current"></a><span data-ttu-id="870b8-110">与当前活动</span><span class="sxs-lookup"><span data-stu-id="870b8-110">Active vs. Current</span></span>

<span data-ttu-id="870b8-111">在 Excel 中，用户正在查看指活动的术语。</span><span class="sxs-lookup"><span data-stu-id="870b8-111">In Excel, the term active refers to what the user is viewing.</span></span> <span data-ttu-id="870b8-112">活动工作簿和工作表是那些用户当前看，或已查看 Excel 已丢失焦点移到另一个应用程序，如果 Excel 最后一个具有焦点。</span><span class="sxs-lookup"><span data-stu-id="870b8-112">The active workbook and worksheet are those that the user is currently looking at, or, if Excel has lost focus to another application, was looking at when Excel last had focus.</span></span> <span data-ttu-id="870b8-113">活动工作表始终是活动工作簿中。</span><span class="sxs-lookup"><span data-stu-id="870b8-113">The active sheet is always in the active workbook.</span></span> <span data-ttu-id="870b8-114">活动工作表中所选的一个或多个单元格称为活动单元格。</span><span class="sxs-lookup"><span data-stu-id="870b8-114">The one or more cells that are selected in the active sheet are known as the active cells.</span></span> <span data-ttu-id="870b8-115">嵌入的对象具有焦点，最后一次选定单元格仍处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="870b8-115">If an embedded object has focus, the last-selected cells are still active.</span></span> 
  
<span data-ttu-id="870b8-116">Excel 正在重新计算引用当前的术语。</span><span class="sxs-lookup"><span data-stu-id="870b8-116">The term current refers to what Excel is recalculating.</span></span> <span data-ttu-id="870b8-117">当前工作簿和工作表是那些当前正在重新计算。</span><span class="sxs-lookup"><span data-stu-id="870b8-117">The current workbook and worksheet are those that are currently being recalculated.</span></span> <span data-ttu-id="870b8-118">当前工作表始终是当前工作簿中。</span><span class="sxs-lookup"><span data-stu-id="870b8-118">The current sheet is always in the current workbook.</span></span> <span data-ttu-id="870b8-119">正在重新计算的单元格称为作为当前单元格，或者，对于数组公式重新计算，当前的单元格。</span><span class="sxs-lookup"><span data-stu-id="870b8-119">The cell being recalculated is known as the current cell, or, in the case of an array formula being recalculated, the current cells.</span></span> 
  
<span data-ttu-id="870b8-120">要记住的要点如下所示：</span><span class="sxs-lookup"><span data-stu-id="870b8-120">The important points to remember are as follows:</span></span>
  
- <span data-ttu-id="870b8-121">活动工作簿/工作表/单元格不是通常当前，但它可以是。</span><span class="sxs-lookup"><span data-stu-id="870b8-121">The active workbook/worksheet/cell is not generally the current one, although it can be.</span></span>
    
- <span data-ttu-id="870b8-122">外接程序，无论在 Visual Basic for Applications (VBA) 模块或 DLL 或 XLL，始终从调用函数当前单元格上当前工作表，或对于多线程重新计算 (MTR) 两者之一。</span><span class="sxs-lookup"><span data-stu-id="870b8-122">An add-in function, whether in a Visual Basic for Applications (VBA) module or a DLL or XLL, is always called from the current cell on the current sheet, or one of them in the case of multithreaded recalculation (MTR).</span></span>
    
<span data-ttu-id="870b8-123">提供有关单元格、 单元格区域或工作簿中的工作表信息的许多 Excel 函数区分活动工作簿、 工作表，或单元格和当前工作簿、 工作表或单元格。</span><span class="sxs-lookup"><span data-stu-id="870b8-123">Many Excel functions that provide information about a cell, a range of cells, or a sheet in a workbook distinguish between the active workbook, sheet, or cell and the current workbook, sheet, or cell.</span></span> <span data-ttu-id="870b8-124">这种差异会反映在用来描述引用单元格，块中下一节所述的数据类型。</span><span class="sxs-lookup"><span data-stu-id="870b8-124">This difference is reflected in the data types used to describe references to blocks of cells, as described in the following section.</span></span>
  
## <a name="internal-and-external-worksheet-references"></a><span data-ttu-id="870b8-125">内部和外部工作表引用</span><span class="sxs-lookup"><span data-stu-id="870b8-125">Internal and External Worksheet References</span></span>

<span data-ttu-id="870b8-126">内部和外部引用之间的主要区别是外部引用数据类型包含工作表以及说明的单元格的引用的 ID。</span><span class="sxs-lookup"><span data-stu-id="870b8-126">The key difference between internal and external references is that the external reference data type contains an ID for the worksheet and also a description of which cells are referred to.</span></span> <span data-ttu-id="870b8-127">内部参考包含对工作表不引用 — 它是隐式工作表是当前工作表。</span><span class="sxs-lookup"><span data-stu-id="870b8-127">An internal reference contains no reference to the sheet—it is implicit that the sheet is the current sheet.</span></span> 
  
<span data-ttu-id="870b8-128">许多 C API 函数返回引用或带引用参数。</span><span class="sxs-lookup"><span data-stu-id="870b8-128">Many C API functions return references or take reference arguments.</span></span> <span data-ttu-id="870b8-129">考虑引用参数任何 C API 函数接受内部或外部的引用，除**xlSheetNm**函数，这需要外部引用。</span><span class="sxs-lookup"><span data-stu-id="870b8-129">Any C API function that takes reference arguments accepts either internal or external references, except the **xlSheetNm** function, which requires an external reference.</span></span> <span data-ttu-id="870b8-130">某些功能仅返回内部或外部的引用。</span><span class="sxs-lookup"><span data-stu-id="870b8-130">Some functions only return either internal or external references.</span></span> <span data-ttu-id="870b8-131">例如，C API 函数[xlfCaller](xlfcaller.md)返回引用调用单元格中，根据定义，当前工作表上。</span><span class="sxs-lookup"><span data-stu-id="870b8-131">For example, the C API function [xlfCaller](xlfcaller.md) returns a reference to the calling cells, by definition, on the current sheet.</span></span> <span data-ttu-id="870b8-132">返回的引用始终是内部的引用，但该函数可以返回非引用类型，函数将不调用从工作表单元格。</span><span class="sxs-lookup"><span data-stu-id="870b8-132">The returned reference is always an internal reference, although the function can return non-reference types where the function is not called from a worksheet cell.</span></span> <span data-ttu-id="870b8-133">C API 函数[xlSheetId](xlsheetid.md)始终返回外部引用数据类型中包含的工作表的 ID。</span><span class="sxs-lookup"><span data-stu-id="870b8-133">The C API function [xlSheetId](xlsheetid.md) always returns the ID of a worksheet contained within an external reference data type.</span></span> 
  
<span data-ttu-id="870b8-134">其他关键区别之间的内部和外部引用类型是外部引用数据类型可以描述在同一工作表上的多个非连续单元格块。</span><span class="sxs-lookup"><span data-stu-id="870b8-134">The other key difference between the internal and external reference types is that the external reference data type can describe multiple disjoint blocks of cells on the same sheet.</span></span> <span data-ttu-id="870b8-135">内部引用可以在当前工作表上描述单个块。</span><span class="sxs-lookup"><span data-stu-id="870b8-135">Internal references can describe only a single block on the current sheet.</span></span> <span data-ttu-id="870b8-136">可以采用范围参数任何函数传递脱节的引用。</span><span class="sxs-lookup"><span data-stu-id="870b8-136">Disjoint references can be passed to any function that takes a range argument.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="870b8-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="870b8-137">See also</span></span>



[<span data-ttu-id="870b8-138">Excel Programming Concepts</span><span class="sxs-lookup"><span data-stu-id="870b8-138">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
  
[<span data-ttu-id="870b8-139">Evaluating Names and Other Worksheet Formula Expressions</span><span class="sxs-lookup"><span data-stu-id="870b8-139">Evaluating Names and Other Worksheet Formula Expressions</span></span>](evaluating-names-and-other-worksheet-formula-expressions.md)
  
[<span data-ttu-id="870b8-140">Excel 工作表和表达式评估</span><span class="sxs-lookup"><span data-stu-id="870b8-140">Excel Worksheet and Expression Evaluation</span></span>](excel-worksheet-and-expression-evaluation.md)

