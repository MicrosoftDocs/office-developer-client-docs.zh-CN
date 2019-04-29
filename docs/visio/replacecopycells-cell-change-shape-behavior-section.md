---
title: ReplaceCopyCells 单元格 ("更改形状行为" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f36aefd-da49-47ea-9b90-2fa1a2298849
description: 指示在形状替换操作过程中从一个旧形状复制到替换形状的 ShapeSheet 中的单元格列表。
ms.openlocfilehash: f2a7908a623c861d0284821b2d8ae5fc71690685
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409340"
---
# <a name="replacecopycells-cell-change-shape-behavior-section"></a><span data-ttu-id="9b5ee-103">ReplaceCopyCells 单元格 ("更改形状行为" 部分)</span><span class="sxs-lookup"><span data-stu-id="9b5ee-103">ReplaceCopyCells Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="9b5ee-104">指示在形状替换操作过程中从一个旧形状复制到替换形状的 ShapeSheet 中的单元格列表。</span><span class="sxs-lookup"><span data-stu-id="9b5ee-104">Indicates a list of cells in the ShapeSheet that are copied from an old shape to the replacement shape during a shape replacement operation.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="9b5ee-105">说明</span><span class="sxs-lookup"><span data-stu-id="9b5ee-105">Remarks</span></span>

<span data-ttu-id="9b5ee-106">替换的主控形状必须包含**ReplaceCopyCells**单元格中的**DEPENDSON**函数调用, 其中函数中的每个参数都是对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="9b5ee-106">The master shape of the replacement must contain a **DEPENDSON** function call in the **ReplaceCopyCells** cell, where each argument in the function is a reference to a cell.</span></span> <span data-ttu-id="9b5ee-107">将这些单元格从旧形状复制到形状替换操作产生的形状, 而不考虑它们在 ShapeSheet 中的位置。</span><span class="sxs-lookup"><span data-stu-id="9b5ee-107">Those cells are copied from the old shape to the shape that results from a shape replacement operation, regardless of where they are in the ShapeSheet.</span></span> 
  
<span data-ttu-id="9b5ee-108">引用其他单元格的值和/或公式将复制到生成的形状中。</span><span class="sxs-lookup"><span data-stu-id="9b5ee-108">Values and/or formulas that reference other cells are copied to the resulting shape.</span></span> <span data-ttu-id="9b5ee-109">如果生成的形状没有被引用的单元格, 则复制的单元格只包含值。</span><span class="sxs-lookup"><span data-stu-id="9b5ee-109">If the resulting shape does not have the referenced cell, the copied cell contains the value only.</span></span> 
  
<span data-ttu-id="9b5ee-110">**ReplaceCopyCells**单元格的引用在 "**保护**" 部分和 " **ReplaceLockFormat**"、" **ReplaceLockShapeData**" 和 " **ReplaceLockText** " 单元格中定义的单元格上覆盖保护集。</span><span class="sxs-lookup"><span data-stu-id="9b5ee-110">References in the **ReplaceCopyCells** cell override protection set on cells as defined in the **Protection** section and the **ReplaceLockFormat**, **ReplaceLockShapeData**, and **ReplaceLockText** cells.</span></span> 
  
<span data-ttu-id="9b5ee-111">若要从另一个公式按名称获取对**ReplaceCopyCells**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="9b5ee-111">To get a reference to the **ReplaceCopyCells** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9b5ee-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9b5ee-112">Cell name:</span></span>  <br/> | <span data-ttu-id="9b5ee-113">ReplaceCopyCells</span><span class="sxs-lookup"><span data-stu-id="9b5ee-113">ReplaceCopyCells</span></span>  <br/> |
   
<span data-ttu-id="9b5ee-114">若要从某个程序按索引获取对**ReplaceCopyCells**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="9b5ee-114">To get a reference to the **ReplaceCopyCells** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9b5ee-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9b5ee-115">Section index:</span></span>  <br/> |<span data-ttu-id="9b5ee-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9b5ee-116">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="9b5ee-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="9b5ee-117">Row index:</span></span>  <br/> |<span data-ttu-id="9b5ee-118">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="9b5ee-118">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="9b5ee-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9b5ee-119">Cell index:</span></span>  <br/> |<span data-ttu-id="9b5ee-120">**visReplaceCopyCells**</span><span class="sxs-lookup"><span data-stu-id="9b5ee-120">**visReplaceCopyCells**</span></span> <br/> |
   

