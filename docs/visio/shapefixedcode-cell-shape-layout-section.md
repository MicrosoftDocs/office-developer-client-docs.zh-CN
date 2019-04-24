---
title: ShapeFixedCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm880
localization_priority: Normal
ms.assetid: a1736a5c-421c-2bdb-b164-76a8cd06cc3d
description: 指定可放置形状的放置行为。
ms.openlocfilehash: eae44a0579129fbe8da1c0cc8c37318beb024563
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325730"
---
# <a name="shapefixedcode-cell-shape-layout-section"></a><span data-ttu-id="568aa-103">ShapeFixedCode 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="568aa-103">ShapeFixedCode Cell (Shape Layout Section)</span></span>

<span data-ttu-id="568aa-104">指定可放置形状的放置行为。</span><span class="sxs-lookup"><span data-stu-id="568aa-104">Specifies placement behavior for a placeable shape.</span></span>
  
|<span data-ttu-id="568aa-105">**值**</span><span class="sxs-lookup"><span data-stu-id="568aa-105">**Value**</span></span>|<span data-ttu-id="568aa-106">**选择方式**</span><span class="sxs-lookup"><span data-stu-id="568aa-106">**Selection mode**</span></span>|<span data-ttu-id="568aa-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="568aa-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="568aa-108">&amp;H1</span><span class="sxs-lookup"><span data-stu-id="568aa-108">&amp;H1</span></span>  <br/> |<span data-ttu-id="568aa-109">在使用 "**配置布局**" 对话框对形状进行布局时, 请勿移动此形状。</span><span class="sxs-lookup"><span data-stu-id="568aa-109">Don't move this shape when shapes are laid out by using the **Configure Layout** dialog box.</span></span>  <br/> |<span data-ttu-id="568aa-110">**visSLOFixedPlacement**</span><span class="sxs-lookup"><span data-stu-id="568aa-110">**visSLOFixedPlacement**</span></span> <br/> |
|<span data-ttu-id="568aa-111">&amp;H2</span><span class="sxs-lookup"><span data-stu-id="568aa-111">&amp;H2</span></span>  <br/> |<span data-ttu-id="568aa-112">不移动该形状，并且不允许将绘制的形状放置在它的上面。</span><span class="sxs-lookup"><span data-stu-id="568aa-112">Don't move this shape and do not allow shapes that plow to be placed on top of it.</span></span>  <br/> |<span data-ttu-id="568aa-113">**visSLOFixedPlow**</span><span class="sxs-lookup"><span data-stu-id="568aa-113">**visSLOFixedPlow**</span></span> <br/> |
|<span data-ttu-id="568aa-114">&amp;H4</span><span class="sxs-lookup"><span data-stu-id="568aa-114">&amp;H4</span></span>  <br/> |<span data-ttu-id="568aa-115">不移动该形状，但允许将绘制的形状放置在它的上面。</span><span class="sxs-lookup"><span data-stu-id="568aa-115">Don't move this shape and allow shapes that plow to be placed on top of it.</span></span>  <br/> |<span data-ttu-id="568aa-116">**visSLOFixedPermeablePlow**</span><span class="sxs-lookup"><span data-stu-id="568aa-116">**visSLOFixedPermeablePlow**</span></span> <br/> |
|<span data-ttu-id="568aa-117">&amp;H20 (32)</span><span class="sxs-lookup"><span data-stu-id="568aa-117">&amp;H20 (32)</span></span>  <br/> |<span data-ttu-id="568aa-118">在排列时忽略连接点位置。</span><span class="sxs-lookup"><span data-stu-id="568aa-118">Ignore connection point locations when being routed to.</span></span>  <br/> |<span data-ttu-id="568aa-119">**visSLOFixedConnPtsIgnore**</span><span class="sxs-lookup"><span data-stu-id="568aa-119">**visSLOFixedConnPtsIgnore**</span></span> <br/> |
|<span data-ttu-id="568aa-120">&amp;H40 (64)</span><span class="sxs-lookup"><span data-stu-id="568aa-120">&amp;H40 (64)</span></span>  <br/> |<span data-ttu-id="568aa-121">仅允许排列到具有连接点的面上。</span><span class="sxs-lookup"><span data-stu-id="568aa-121">Only allow routing to sides with connection points.</span></span>  <br/> |<span data-ttu-id="568aa-122">**visSLOFixedConnPtsOnly**</span><span class="sxs-lookup"><span data-stu-id="568aa-122">**visSLOFixedConnPtsOnly**</span></span> <br/> |
|<span data-ttu-id="568aa-123">&amp;H80 (128)</span><span class="sxs-lookup"><span data-stu-id="568aa-123">&amp;H80 (128)</span></span>  <br/> |<span data-ttu-id="568aa-124">不粘附到此形状的周长。</span><span class="sxs-lookup"><span data-stu-id="568aa-124">Don't glue to the perimeter of this shape.</span></span> <span data-ttu-id="568aa-125">改为粘附到形状的对齐框。</span><span class="sxs-lookup"><span data-stu-id="568aa-125">Glue to the shape's alignment box instead.</span></span>  <br/> |<span data-ttu-id="568aa-126">**visSLOFixedNoFoldToShape**</span><span class="sxs-lookup"><span data-stu-id="568aa-126">**visSLOFixedNoFoldToShape**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="568aa-127">注解</span><span class="sxs-lookup"><span data-stu-id="568aa-127">Remarks</span></span>

<span data-ttu-id="568aa-128">您还可以在 "**行为**" 对话框 (在 "[开发工具](run-in-developer-mode-display-the-developer-tab.md)" 选项卡上的 "**形状设计**" 组中, 单击 "**行为**", 然后单击 "**位置**" 选项卡) 中的 "**放置**" 选项卡上设置此单元格的值。).</span><span class="sxs-lookup"><span data-stu-id="568aa-128">You can also set the value of this cell on the **Placement** tab in the **Behavior** dialog box (with a shape selected, on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, in the **Shape Design** group, click **Behavior**, and then click the **Placement** tab).</span></span> 
  
<span data-ttu-id="568aa-129">您可以为此单元格设置这些值的任意组合。</span><span class="sxs-lookup"><span data-stu-id="568aa-129">You can set any combination of these values for this cell.</span></span> <span data-ttu-id="568aa-130">例如, 您可以输入值 3 (&amp;H3), 这将避免在使用 "**配置布局**" 对话框 (在 "**设计**" 选项卡上的 "**布局**" 组中, 单击 "重新布局页面", 再单击\*\*\*\* **"重新布局页面") 排放形状时进行移动。更多布局选项**) 和其他可放置形状置于形状的上方或旁边。</span><span class="sxs-lookup"><span data-stu-id="568aa-130">For example, you can enter the value 3 (&amp;H3), which eliminates movement when you lay out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options** ) and when other placeable shapes are placed on or near the shape.</span></span> 
  
<span data-ttu-id="568aa-131">在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。</span><span class="sxs-lookup"><span data-stu-id="568aa-131">In versions earlier than Visio 2000, you set this behavior using the ObjInteract cell in the Miscellaneous section.</span></span> 
  
<span data-ttu-id="568aa-132">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeFixedCode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="568aa-132">To get a reference to the ShapeFixedCode cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="568aa-133">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="568aa-133">Cell name:</span></span>  <br/> |<span data-ttu-id="568aa-134">ShapeFixedCode</span><span class="sxs-lookup"><span data-stu-id="568aa-134">ShapeFixedCode</span></span>  <br/> |
   
<span data-ttu-id="568aa-135">若要从某个程序按索引获取对 ShapeFixedCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="568aa-135">To get a reference to the ShapeFixedCode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="568aa-136">内容索引：</span><span class="sxs-lookup"><span data-stu-id="568aa-136">Section index:</span></span>  <br/> |<span data-ttu-id="568aa-137">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="568aa-137">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="568aa-138">行索引：</span><span class="sxs-lookup"><span data-stu-id="568aa-138">Row index:</span></span>  <br/> |<span data-ttu-id="568aa-139">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="568aa-139">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="568aa-140">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="568aa-140">Cell index:</span></span>  <br/> |<span data-ttu-id="568aa-141">**visSLOFixedCode**</span><span class="sxs-lookup"><span data-stu-id="568aa-141">**visSLOFixedCode**</span></span> <br/> |
   

