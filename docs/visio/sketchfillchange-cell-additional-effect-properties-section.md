---
title: SketchFillChange 单元格 （其他效果属性内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 939f8f90-dee5-4175-b32a-e2964eb40681
description: 确定从形状的几何形状的填充的随机量时素描效果，使用的部分的长度的百分比。 如果 SketchFillChange 单元格的值设置为 0%，边界的形状的填充几何匹配形状的几何图形。 如果值为 100%，边界的形状的填充几何不遵循的几何形状。
ms.openlocfilehash: 8dda34e03188909e167a4abda6f62da3d43c4dd7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781379"
---
# <a name="sketchfillchange-cell-additional-effect-properties-section"></a><span data-ttu-id="297d6-105">SketchFillChange 单元格 （其他效果属性内容）</span><span class="sxs-lookup"><span data-stu-id="297d6-105">SketchFillChange Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="297d6-106">确定从形状的几何形状的填充的随机量时素描效果，使用的部分的长度的百分比。</span><span class="sxs-lookup"><span data-stu-id="297d6-106">Determines the amount of randomization of the shape's fill from the shape's geometry when using a sketch effect, as a percentage of the length of a section.</span></span> <span data-ttu-id="297d6-107">如果**SketchFillChange**单元格的值设置为 0%，边界的形状的填充几何匹配形状的几何图形。</span><span class="sxs-lookup"><span data-stu-id="297d6-107">If the value of the **SketchFillChange** cell is set to 0%, the bounding geometry of a shape's fill matches the shape's geometry.</span></span> <span data-ttu-id="297d6-108">如果值为 100%，边界的形状的填充几何不遵循的几何形状。</span><span class="sxs-lookup"><span data-stu-id="297d6-108">If the value is 100%, the bounding geometry of the shape's fill does not follow the geometry of the shape.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="297d6-109">备注</span><span class="sxs-lookup"><span data-stu-id="297d6-109">Remarks</span></span>

<span data-ttu-id="297d6-110">为了获得最佳结果，理想**SketchFillChange**单元格的值的范围是 15%到 50%之间。</span><span class="sxs-lookup"><span data-stu-id="297d6-110">For best results, the ideal range of values for the **SketchFillChange** cell is between 15% and 50%.</span></span> <span data-ttu-id="297d6-111">15%下面的值是几乎可以忽略;大于 50%的值是越来越多随机选择。</span><span class="sxs-lookup"><span data-stu-id="297d6-111">A value below 15% is barely noticeable; a value greater than 50% is increasingly more randomized.</span></span> 
  
<span data-ttu-id="297d6-112">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SketchFillChange**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="297d6-112">To get a reference to the **SketchFillChange** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="297d6-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="297d6-113">Cell name:</span></span>  <br/> | <span data-ttu-id="297d6-114">SketchFillChange</span><span class="sxs-lookup"><span data-stu-id="297d6-114">SketchFillChange</span></span>  <br/> |
   
<span data-ttu-id="297d6-115">若要从某个程序按索引获取对**SketchFillChange**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="297d6-115">To get a reference to the **SketchFillChange** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="297d6-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="297d6-116">Section index:</span></span>  <br/> |<span data-ttu-id="297d6-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="297d6-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="297d6-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="297d6-118">Row index:</span></span>  <br/> |<span data-ttu-id="297d6-119">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="297d6-119">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="297d6-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="297d6-120">Cell index:</span></span>  <br/> |<span data-ttu-id="297d6-121">**visSketchFillChange**</span><span class="sxs-lookup"><span data-stu-id="297d6-121">**visSketchFillChange**</span></span> <br/> |
   

