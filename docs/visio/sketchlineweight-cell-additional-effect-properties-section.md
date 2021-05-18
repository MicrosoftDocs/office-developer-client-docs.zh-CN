---
title: 'SketchLineWeight Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cb838be-1d6d-48e1-8e9e-bd126f0c2385
description: 确定作为草图效果的结果添加到线条粗细的额外粗细（以 0 到 50 磅）。 随着 SketchLineWeight 单元格值的增加，形状线条的粗细增加。
ms.openlocfilehash: 0ee71bbaec59f5c79b72314b08478f8028b4e0ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404510"
---
# <a name="sketchlineweight-cell-additional-effect-properties-section"></a><span data-ttu-id="8cff8-104">SketchLineWeight Cell (Additional Effect Properties Section) </span><span class="sxs-lookup"><span data-stu-id="8cff8-104">SketchLineWeight Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="8cff8-105">确定作为草图效果的结果添加到线条粗细的额外粗细（以 0 到 50 磅）。</span><span class="sxs-lookup"><span data-stu-id="8cff8-105">Determines the additional thickness added to line weight as the result of a sketch effect, in points from 0 to 50.</span></span> <span data-ttu-id="8cff8-106">随着 **SketchLineWeight** 单元格值的增加，形状线条的粗细增加。</span><span class="sxs-lookup"><span data-stu-id="8cff8-106">The thickness of a shape's line increases as the value of the **SketchLineWeight** cell increases.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="8cff8-107">备注</span><span class="sxs-lookup"><span data-stu-id="8cff8-107">Remarks</span></span>

<span data-ttu-id="8cff8-108">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **SketchLineWeight** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8cff8-108">To get a reference to the **SketchLineWeight** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8cff8-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8cff8-109">Cell name:</span></span>  <br/> | <span data-ttu-id="8cff8-110">SketchLineWeight</span><span class="sxs-lookup"><span data-stu-id="8cff8-110">SketchLineWeight</span></span>  <br/> |
   
<span data-ttu-id="8cff8-111">若要从程序按索引获取 **对 SketchLineWeight** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8cff8-111">To get a reference to the **SketchLineWeight** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8cff8-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8cff8-112">Section index:</span></span>  <br/> |<span data-ttu-id="8cff8-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8cff8-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8cff8-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="8cff8-114">Row index:</span></span>  <br/> |<span data-ttu-id="8cff8-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="8cff8-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="8cff8-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8cff8-116">Cell index:</span></span>  <br/> |<span data-ttu-id="8cff8-117">**visSketchLineWeight**</span><span class="sxs-lookup"><span data-stu-id="8cff8-117">**visSketchLineWeight**</span></span> <br/> |
   

