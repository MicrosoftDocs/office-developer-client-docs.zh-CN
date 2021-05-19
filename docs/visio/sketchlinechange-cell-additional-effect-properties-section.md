---
title: 'SketchLineChange Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 39192535-b55b-4c49-b63f-edb542c7a2e5
description: 确定使用草图效果时形状的几何图形线条的随机化量，以部分长度的百分比表示。 如果 SketchLineChange 单元格的值设置为 0%，则形状线条的几何图形与形状的几何图形匹配。 如果值为 100%，则形状线条的几何图形不遵循形状的几何图形。
ms.openlocfilehash: ba57a4d2e43a91475f4c3ab4862f723eb2653a89
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419504"
---
# <a name="sketchlinechange-cell-additional-effect-properties-section"></a><span data-ttu-id="c04fc-105">SketchLineChange Cell (Additional Effect Properties Section) </span><span class="sxs-lookup"><span data-stu-id="c04fc-105">SketchLineChange Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="c04fc-106">确定使用草图效果时形状的几何图形线条的随机化量，以部分长度的百分比表示。</span><span class="sxs-lookup"><span data-stu-id="c04fc-106">Determines the amount of randomization of the shape's line from the shape's geometry when using a sketch effect, as a percentage of the length of a section.</span></span> <span data-ttu-id="c04fc-107">如果 **SketchLineChange** 单元格的值设置为 0%，则形状线条的几何图形与形状的几何图形匹配。</span><span class="sxs-lookup"><span data-stu-id="c04fc-107">If the value of the **SketchLineChange** cell is set to 0%, the geometry of the shape's line matches the shape's geometry.</span></span> <span data-ttu-id="c04fc-108">如果值为 100%，则形状线条的几何图形不遵循形状的几何图形。</span><span class="sxs-lookup"><span data-stu-id="c04fc-108">If the value is 100%, the geometry of the shape's line does not follow the geometry of the shape.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c04fc-109">备注</span><span class="sxs-lookup"><span data-stu-id="c04fc-109">Remarks</span></span>

<span data-ttu-id="c04fc-110">为了获得最佳结果 **，SketchLineChange** 单元格的理想值范围介于 15% 到 50% 之间。</span><span class="sxs-lookup"><span data-stu-id="c04fc-110">For best results, the ideal range of values for the **SketchLineChange** cell is between 15% and 50%.</span></span> <span data-ttu-id="c04fc-111">低于 15% 的值几乎不明显;大于 50% 的值可能会过多地随机化该行。</span><span class="sxs-lookup"><span data-stu-id="c04fc-111">A value below 15% is barely noticeable; a value greater than 50% could randomize the line too much.</span></span> 
  
<span data-ttu-id="c04fc-112">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **SketchLineChange** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c04fc-112">To get a reference to the **SketchLineChange** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c04fc-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c04fc-113">Cell name:</span></span>  <br/> | <span data-ttu-id="c04fc-114">SketchLineChange</span><span class="sxs-lookup"><span data-stu-id="c04fc-114">SketchLineChange</span></span>  <br/> |
   
<span data-ttu-id="c04fc-115">若要从程序按索引获取 **对 SketchLineChange** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c04fc-115">To get a reference to the **SketchLineChange** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c04fc-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c04fc-116">Section index:</span></span>  <br/> |<span data-ttu-id="c04fc-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c04fc-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="c04fc-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="c04fc-118">Row index:</span></span>  <br/> |<span data-ttu-id="c04fc-119">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="c04fc-119">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="c04fc-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c04fc-120">Cell index:</span></span>  <br/> |<span data-ttu-id="c04fc-121">**visSketchLineChange**</span><span class="sxs-lookup"><span data-stu-id="c04fc-121">**visSketchLineChange**</span></span> <br/> |
   

