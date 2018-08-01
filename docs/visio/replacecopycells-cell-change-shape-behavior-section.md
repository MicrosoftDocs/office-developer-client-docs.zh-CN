---
title: ReplaceCopyCells 单元格（“Change Shape Behavior”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f36aefd-da49-47ea-9b90-2fa1a2298849
description: 指示从复制旧的形状的替换形状到形状替换操作期间 ShapeSheet 中的单元格的列表。
ms.openlocfilehash: 1e3b5e4dbc29372f75b7a7ed8013a7dd82d94e1d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781058"
---
# <a name="replacecopycells-cell-change-shape-behavior-section"></a><span data-ttu-id="fe409-103">ReplaceCopyCells 单元格（“Change Shape Behavior”部分）</span><span class="sxs-lookup"><span data-stu-id="fe409-103">ReplaceCopyCells Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="fe409-104">指示从复制旧的形状的替换形状到形状替换操作期间 ShapeSheet 中的单元格的列表。</span><span class="sxs-lookup"><span data-stu-id="fe409-104">Indicates a list of cells in the ShapeSheet that are copied from an old shape to the replacement shape during a shape replacement operation.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="fe409-105">说明</span><span class="sxs-lookup"><span data-stu-id="fe409-105">Remarks</span></span>

<span data-ttu-id="fe409-106">替换为相应的主控形状必须包含**DEPENDSON**函数调用**ReplaceCopyCells**单元格中，其中函数中的每个参数都是单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="fe409-106">The master shape of the replacement must contain a **DEPENDSON** function call in the **ReplaceCopyCells** cell, where each argument in the function is a reference to a cell.</span></span> <span data-ttu-id="fe409-107">对这些单元格从旧形状复制到的形状的形状替换操作，而不考虑它们在 ShapeSheet 中的位置的结果。</span><span class="sxs-lookup"><span data-stu-id="fe409-107">Those cells are copied from the old shape to the shape that results from a shape replacement operation, regardless of where they are in the ShapeSheet.</span></span> 
  
<span data-ttu-id="fe409-108">值和/或引用的其他单元格的公式复制到生成的形状。</span><span class="sxs-lookup"><span data-stu-id="fe409-108">Values and/or formulas that reference other cells are copied to the resulting shape.</span></span> <span data-ttu-id="fe409-109">如果在生成的形状没有引用的单元格，复制单元格包含值仅。</span><span class="sxs-lookup"><span data-stu-id="fe409-109">If the resulting shape does not have the referenced cell, the copied cell contains the value only.</span></span> 
  
<span data-ttu-id="fe409-110">中**ReplaceCopyCells**单元格的引用重写保护组中**Protection**内容的**ReplaceLockFormat**、 **ReplaceLockShapeData**和**ReplaceLockText**单元格定义的单元格。</span><span class="sxs-lookup"><span data-stu-id="fe409-110">References in the **ReplaceCopyCells** cell override protection set on cells as defined in the **Protection** section and the **ReplaceLockFormat**, **ReplaceLockShapeData**, and **ReplaceLockText** cells.</span></span> 
  
<span data-ttu-id="fe409-111">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ReplaceCopyCells**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="fe409-111">To get a reference to the **ReplaceCopyCells** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="fe409-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="fe409-112">Cell name:</span></span>  <br/> | <span data-ttu-id="fe409-113">ReplaceCopyCells</span><span class="sxs-lookup"><span data-stu-id="fe409-113">ReplaceCopyCells</span></span>  <br/> |
   
<span data-ttu-id="fe409-114">若要从某个程序按索引获取对**ReplaceCopyCells**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="fe409-114">To get a reference to the **ReplaceCopyCells** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="fe409-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="fe409-115">Section index:</span></span>  <br/> |<span data-ttu-id="fe409-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="fe409-116">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="fe409-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="fe409-117">Row index:</span></span>  <br/> |<span data-ttu-id="fe409-118">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="fe409-118">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="fe409-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="fe409-119">Cell index:</span></span>  <br/> |<span data-ttu-id="fe409-120">**visReplaceCopyCells**</span><span class="sxs-lookup"><span data-stu-id="fe409-120">**visReplaceCopyCells**</span></span> <br/> |
   

