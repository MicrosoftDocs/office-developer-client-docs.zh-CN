---
title: SketchLineWeight 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cb838be-1d6d-48e1-8e9e-bd126f0c2385
description: 确定作为素描效果的结果添加到线条粗细的额外厚度, 以从0到50的磅为单位。 当 SketchLineWeight 单元格的值增加时, 该形状的线条的粗细将增加。
ms.openlocfilehash: 0ee71bbaec59f5c79b72314b08478f8028b4e0ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315118"
---
# <a name="sketchlineweight-cell-additional-effect-properties-section"></a><span data-ttu-id="c49c0-104">SketchLineWeight 单元格 ("其他效果属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="c49c0-104">SketchLineWeight Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="c49c0-105">确定作为素描效果的结果添加到线条粗细的额外厚度, 以从0到50的磅为单位。</span><span class="sxs-lookup"><span data-stu-id="c49c0-105">Determines the additional thickness added to line weight as the result of a sketch effect, in points from 0 to 50.</span></span> <span data-ttu-id="c49c0-106">当**SketchLineWeight**单元格的值增加时, 该形状的线条的粗细将增加。</span><span class="sxs-lookup"><span data-stu-id="c49c0-106">The thickness of a shape's line increases as the value of the **SketchLineWeight** cell increases.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c49c0-107">注解</span><span class="sxs-lookup"><span data-stu-id="c49c0-107">Remarks</span></span>

<span data-ttu-id="c49c0-108">若要从另一个公式按名称获取对**SketchLineWeight**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="c49c0-108">To get a reference to the **SketchLineWeight** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c49c0-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c49c0-109">Cell name:</span></span>  <br/> | <span data-ttu-id="c49c0-110">SketchLineWeight</span><span class="sxs-lookup"><span data-stu-id="c49c0-110">SketchLineWeight</span></span>  <br/> |
   
<span data-ttu-id="c49c0-111">若要从某个程序按索引获取对**SketchLineWeight**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="c49c0-111">To get a reference to the **SketchLineWeight** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c49c0-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c49c0-112">Section index:</span></span>  <br/> |<span data-ttu-id="c49c0-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c49c0-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="c49c0-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="c49c0-114">Row index:</span></span>  <br/> |<span data-ttu-id="c49c0-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="c49c0-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="c49c0-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c49c0-116">Cell index:</span></span>  <br/> |<span data-ttu-id="c49c0-117">**visSketchLineWeight**</span><span class="sxs-lookup"><span data-stu-id="c49c0-117">**visSketchLineWeight**</span></span> <br/> |
   

