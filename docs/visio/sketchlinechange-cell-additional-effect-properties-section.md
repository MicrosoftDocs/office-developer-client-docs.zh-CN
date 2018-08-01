---
title: SketchLineChange 单元格（“Additional Effect Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 39192535-b55b-4c49-b63f-edb542c7a2e5
description: 确定随机选择的形状的线条从形状的几何量时使用素描效果的部分的长度的百分比。 如果 SketchLineChange 单元格的值设置为 0%的几何形状的行匹配形状的几何图形。 如果值为 100%的几何形状的线条不遵循的几何形状。
ms.openlocfilehash: 57d2af1a914710d7e5a58686b577014ceb7af424
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781374"
---
# <a name="sketchlinechange-cell-additional-effect-properties-section"></a><span data-ttu-id="3729b-105">SketchLineChange 单元格（“Additional Effect Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="3729b-105">SketchLineChange Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="3729b-106">确定随机选择的形状的线条从形状的几何量时使用素描效果的部分的长度的百分比。</span><span class="sxs-lookup"><span data-stu-id="3729b-106">Determines the amount of randomization of the shape's line from the shape's geometry when using a sketch effect, as a percentage of the length of a section.</span></span> <span data-ttu-id="3729b-107">如果**SketchLineChange**单元格的值设置为 0%的几何形状的行匹配形状的几何图形。</span><span class="sxs-lookup"><span data-stu-id="3729b-107">If the value of the **SketchLineChange** cell is set to 0%, the geometry of the shape's line matches the shape's geometry.</span></span> <span data-ttu-id="3729b-108">如果值为 100%的几何形状的线条不遵循的几何形状。</span><span class="sxs-lookup"><span data-stu-id="3729b-108">If the value is 100%, the geometry of the shape's line does not follow the geometry of the shape.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="3729b-109">说明</span><span class="sxs-lookup"><span data-stu-id="3729b-109">Remarks</span></span>

<span data-ttu-id="3729b-110">为了获得最佳结果，理想**SketchLineChange**单元格的值的范围是 15%到 50%之间。</span><span class="sxs-lookup"><span data-stu-id="3729b-110">For best results, the ideal range of values for the **SketchLineChange** cell is between 15% and 50%.</span></span> <span data-ttu-id="3729b-111">15%下面的值是几乎可以忽略;大于 50%的值可能太多 randomize 行。</span><span class="sxs-lookup"><span data-stu-id="3729b-111">A value below 15% is barely noticeable; a value greater than 50% could randomize the line too much.</span></span> 
  
<span data-ttu-id="3729b-112">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SketchLineChange**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3729b-112">To get a reference to the **SketchLineChange** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3729b-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3729b-113">Cell name:</span></span>  <br/> | <span data-ttu-id="3729b-114">SketchLineChange</span><span class="sxs-lookup"><span data-stu-id="3729b-114">SketchLineChange</span></span>  <br/> |
   
<span data-ttu-id="3729b-115">若要从某个程序按索引获取对**SketchLineChange**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="3729b-115">To get a reference to the **SketchLineChange** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3729b-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3729b-116">Section index:</span></span>  <br/> |<span data-ttu-id="3729b-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="3729b-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="3729b-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="3729b-118">Row index:</span></span>  <br/> |<span data-ttu-id="3729b-119">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="3729b-119">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="3729b-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3729b-120">Cell index:</span></span>  <br/> |<span data-ttu-id="3729b-121">**visSketchLineChange**</span><span class="sxs-lookup"><span data-stu-id="3729b-121">**visSketchLineChange**</span></span> <br/> |
   

