---
title: 'ReplaceCopyCells Cell (Change Shape Behavior Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f36aefd-da49-47ea-9b90-2fa1a2298849
description: 指示 ShapeSheet 中的单元格列表，这些单元格在形状替换操作过程中从旧形状复制到替换形状。
ms.openlocfilehash: f2a7908a623c861d0284821b2d8ae5fc71690685
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409340"
---
# <a name="replacecopycells-cell-change-shape-behavior-section"></a><span data-ttu-id="f2e0c-103">ReplaceCopyCells Cell (Change Shape Behavior Section) </span><span class="sxs-lookup"><span data-stu-id="f2e0c-103">ReplaceCopyCells Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="f2e0c-104">指示 ShapeSheet 中的单元格列表，这些单元格在形状替换操作过程中从旧形状复制到替换形状。</span><span class="sxs-lookup"><span data-stu-id="f2e0c-104">Indicates a list of cells in the ShapeSheet that are copied from an old shape to the replacement shape during a shape replacement operation.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="f2e0c-105">备注</span><span class="sxs-lookup"><span data-stu-id="f2e0c-105">Remarks</span></span>

<span data-ttu-id="f2e0c-106">替换的主形状必须在 **ReplaceCopyCells** 单元格中包含 **DEPENDSON** 函数调用，其中函数的每个参数都是对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="f2e0c-106">The master shape of the replacement must contain a **DEPENDSON** function call in the **ReplaceCopyCells** cell, where each argument in the function is a reference to a cell.</span></span> <span data-ttu-id="f2e0c-107">这些单元格从旧形状复制到由形状替换操作产生的形状，而不管它们在 ShapeSheet 中在哪里。</span><span class="sxs-lookup"><span data-stu-id="f2e0c-107">Those cells are copied from the old shape to the shape that results from a shape replacement operation, regardless of where they are in the ShapeSheet.</span></span> 
  
<span data-ttu-id="f2e0c-108">引用其他单元格的值和/或公式将复制到生成的形状。</span><span class="sxs-lookup"><span data-stu-id="f2e0c-108">Values and/or formulas that reference other cells are copied to the resulting shape.</span></span> <span data-ttu-id="f2e0c-109">如果生成的形状没有引用的单元格，则复制的单元格仅包含值。</span><span class="sxs-lookup"><span data-stu-id="f2e0c-109">If the resulting shape does not have the referenced cell, the copied cell contains the value only.</span></span> 
  
<span data-ttu-id="f2e0c-110">**ReplaceCopyCells** 单元格中的引用会覆盖在"保护"部分以及 **ReplaceLockFormat、ReplaceLockShapeData** 和 **ReplaceLockText** 单元格中定义的单元格上设置的保护。 </span><span class="sxs-lookup"><span data-stu-id="f2e0c-110">References in the **ReplaceCopyCells** cell override protection set on cells as defined in the **Protection** section and the **ReplaceLockFormat**, **ReplaceLockShapeData**, and **ReplaceLockText** cells.</span></span> 
  
<span data-ttu-id="f2e0c-111">若要从另一个公式、Cell 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **ReplaceCopyCells** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f2e0c-111">To get a reference to the **ReplaceCopyCells** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f2e0c-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f2e0c-112">Cell name:</span></span>  <br/> | <span data-ttu-id="f2e0c-113">ReplaceCopyCells</span><span class="sxs-lookup"><span data-stu-id="f2e0c-113">ReplaceCopyCells</span></span>  <br/> |
   
<span data-ttu-id="f2e0c-114">若要从程序按索引获取 **对 ReplaceCopyCells** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f2e0c-114">To get a reference to the **ReplaceCopyCells** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f2e0c-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f2e0c-115">Section index:</span></span>  <br/> |<span data-ttu-id="f2e0c-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f2e0c-116">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="f2e0c-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="f2e0c-117">Row index:</span></span>  <br/> |<span data-ttu-id="f2e0c-118">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="f2e0c-118">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="f2e0c-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f2e0c-119">Cell index:</span></span>  <br/> |<span data-ttu-id="f2e0c-120">**visReplaceCopyCells**</span><span class="sxs-lookup"><span data-stu-id="f2e0c-120">**visReplaceCopyCells**</span></span> <br/> |
   

