---
title: SketchFillChange 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 939f8f90-dee5-4175-b32a-e2964eb40681
description: 根据某一节的长度的百分比, 确定在使用草图效果时形状的几何图形的随机填充量。 如果 SketchFillChange 单元格的值设置为 0%, 则形状的填充的边界几何图形与形状的几何图形相匹配。 如果值为 100%, 则该形状的填充的边界几何图形不遵循形状的几何图形。
ms.openlocfilehash: 8726e9dd6ca6257fb8dbbbef3dce1d4ec344e28b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339808"
---
# <a name="sketchfillchange-cell-additional-effect-properties-section"></a><span data-ttu-id="4a7ac-105">SketchFillChange 单元格 ("其他效果属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="4a7ac-105">SketchFillChange Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="4a7ac-106">根据某一节的长度的百分比, 确定在使用草图效果时形状的几何图形的随机填充量。</span><span class="sxs-lookup"><span data-stu-id="4a7ac-106">Determines the amount of randomization of the shape's fill from the shape's geometry when using a sketch effect, as a percentage of the length of a section.</span></span> <span data-ttu-id="4a7ac-107">如果**SketchFillChange**单元格的值设置为 0%, 则形状的填充的边界几何图形与形状的几何图形相匹配。</span><span class="sxs-lookup"><span data-stu-id="4a7ac-107">If the value of the **SketchFillChange** cell is set to 0%, the bounding geometry of a shape's fill matches the shape's geometry.</span></span> <span data-ttu-id="4a7ac-108">如果值为 100%, 则该形状的填充的边界几何图形不遵循形状的几何图形。</span><span class="sxs-lookup"><span data-stu-id="4a7ac-108">If the value is 100%, the bounding geometry of the shape's fill does not follow the geometry of the shape.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="4a7ac-109">注解</span><span class="sxs-lookup"><span data-stu-id="4a7ac-109">Remarks</span></span>

<span data-ttu-id="4a7ac-110">为获得最佳结果, **SketchFillChange**单元格的理想值范围为 15% 到 50%。</span><span class="sxs-lookup"><span data-stu-id="4a7ac-110">For best results, the ideal range of values for the **SketchFillChange** cell is between 15% and 50%.</span></span> <span data-ttu-id="4a7ac-111">小于 15% 的值几乎是显而易见的;大于 50% 的值的随机化程度越来越高。</span><span class="sxs-lookup"><span data-stu-id="4a7ac-111">A value below 15% is barely noticeable; a value greater than 50% is increasingly more randomized.</span></span> 
  
<span data-ttu-id="4a7ac-112">若要从另一个公式按名称获取对**SketchFillChange**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="4a7ac-112">To get a reference to the **SketchFillChange** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4a7ac-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4a7ac-113">Cell name:</span></span>  <br/> | <span data-ttu-id="4a7ac-114">SketchFillChange</span><span class="sxs-lookup"><span data-stu-id="4a7ac-114">SketchFillChange</span></span>  <br/> |
   
<span data-ttu-id="4a7ac-115">若要从某个程序按索引获取对**SketchFillChange**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="4a7ac-115">To get a reference to the **SketchFillChange** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4a7ac-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4a7ac-116">Section index:</span></span>  <br/> |<span data-ttu-id="4a7ac-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4a7ac-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="4a7ac-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="4a7ac-118">Row index:</span></span>  <br/> |<span data-ttu-id="4a7ac-119">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="4a7ac-119">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="4a7ac-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4a7ac-120">Cell index:</span></span>  <br/> |<span data-ttu-id="4a7ac-121">**visSketchFillChange**</span><span class="sxs-lookup"><span data-stu-id="4a7ac-121">**visSketchFillChange**</span></span> <br/> |
   

