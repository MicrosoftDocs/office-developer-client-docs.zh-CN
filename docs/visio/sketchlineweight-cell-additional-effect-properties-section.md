---
title: SketchLineWeight 单元格 （其他效果属性内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cb838be-1d6d-48e1-8e9e-bd126f0c2385
description: 确定其他粗细素描效果，以从 0 到 50 磅的结果添加到线条粗细。 形状的线条的粗细随着 SketchLineWeight 增加单元格的值。
ms.openlocfilehash: 9ab99faab907ddf0d944abbeea39672906b4c03d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781391"
---
# <a name="sketchlineweight-cell-additional-effect-properties-section"></a><span data-ttu-id="0ac6e-104">SketchLineWeight 单元格 （其他效果属性内容）</span><span class="sxs-lookup"><span data-stu-id="0ac6e-104">SketchLineWeight Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="0ac6e-105">确定其他粗细素描效果，以从 0 到 50 磅的结果添加到线条粗细。</span><span class="sxs-lookup"><span data-stu-id="0ac6e-105">Determines the additional thickness added to line weight as the result of a sketch effect, in points from 0 to 50.</span></span> <span data-ttu-id="0ac6e-106">形状的线条的粗细随着**SketchLineWeight**单元格增加的值。</span><span class="sxs-lookup"><span data-stu-id="0ac6e-106">The thickness of a shape's line increases as the value of the **SketchLineWeight** cell increases.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="0ac6e-107">备注</span><span class="sxs-lookup"><span data-stu-id="0ac6e-107">Remarks</span></span>

<span data-ttu-id="0ac6e-108">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SketchLineWeight**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="0ac6e-108">To get a reference to the **SketchLineWeight** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0ac6e-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="0ac6e-109">Cell name:</span></span>  <br/> | <span data-ttu-id="0ac6e-110">SketchLineWeight</span><span class="sxs-lookup"><span data-stu-id="0ac6e-110">SketchLineWeight</span></span>  <br/> |
   
<span data-ttu-id="0ac6e-111">若要从某个程序按索引获取对**SketchLineWeight**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="0ac6e-111">To get a reference to the **SketchLineWeight** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0ac6e-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="0ac6e-112">Section index:</span></span>  <br/> |<span data-ttu-id="0ac6e-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="0ac6e-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="0ac6e-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="0ac6e-114">Row index:</span></span>  <br/> |<span data-ttu-id="0ac6e-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="0ac6e-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="0ac6e-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="0ac6e-116">Cell index:</span></span>  <br/> |<span data-ttu-id="0ac6e-117">**visSketchLineWeight**</span><span class="sxs-lookup"><span data-stu-id="0ac6e-117">**visSketchLineWeight**</span></span> <br/> |
   

