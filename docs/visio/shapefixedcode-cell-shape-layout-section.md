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
ms.openlocfilehash: 6ae83fa70cc545c88080ce27046bd8c226c060e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781255"
---
# <a name="shapefixedcode-cell-shape-layout-section"></a><span data-ttu-id="98d8a-103">ShapeFixedCode 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="98d8a-103">ShapeFixedCode Cell (Shape Layout Section)</span></span>

<span data-ttu-id="98d8a-104">指定可放置形状的放置行为。</span><span class="sxs-lookup"><span data-stu-id="98d8a-104">Specifies placement behavior for a placeable shape.</span></span>
  
|<span data-ttu-id="98d8a-105">**值**</span><span class="sxs-lookup"><span data-stu-id="98d8a-105">**Value**</span></span>|<span data-ttu-id="98d8a-106">**选择模式**</span><span class="sxs-lookup"><span data-stu-id="98d8a-106">**Selection mode**</span></span>|<span data-ttu-id="98d8a-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="98d8a-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="98d8a-108">&amp;H1</span><span class="sxs-lookup"><span data-stu-id="98d8a-108">&amp;H1</span></span>  <br/> |<span data-ttu-id="98d8a-109">使用**配置布局**对话框排放形状时，不移动该形状。</span><span class="sxs-lookup"><span data-stu-id="98d8a-109">Don't move this shape when shapes are laid out by using the **Configure Layout** dialog box.</span></span>  <br/> |<span data-ttu-id="98d8a-110">**visSLOFixedPlacement**</span><span class="sxs-lookup"><span data-stu-id="98d8a-110">**visSLOFixedPlacement**</span></span> <br/> |
|<span data-ttu-id="98d8a-111">&amp;H2</span><span class="sxs-lookup"><span data-stu-id="98d8a-111">&amp;H2</span></span>  <br/> |<span data-ttu-id="98d8a-112">不移动该形状，并且不允许将绘制的形状放置在它的上面。</span><span class="sxs-lookup"><span data-stu-id="98d8a-112">Don't move this shape and do not allow shapes that plow to be placed on top of it.</span></span>  <br/> |<span data-ttu-id="98d8a-113">**visSLOFixedPlow**</span><span class="sxs-lookup"><span data-stu-id="98d8a-113">**visSLOFixedPlow**</span></span> <br/> |
|<span data-ttu-id="98d8a-114">&amp;H4</span><span class="sxs-lookup"><span data-stu-id="98d8a-114">&amp;H4</span></span>  <br/> |<span data-ttu-id="98d8a-115">不移动该形状，但允许将绘制的形状放置在它的上面。</span><span class="sxs-lookup"><span data-stu-id="98d8a-115">Don't move this shape and allow shapes that plow to be placed on top of it.</span></span>  <br/> |<span data-ttu-id="98d8a-116">**visSLOFixedPermeablePlow**</span><span class="sxs-lookup"><span data-stu-id="98d8a-116">**visSLOFixedPermeablePlow**</span></span> <br/> |
|<span data-ttu-id="98d8a-117">&amp;H20 (32)</span><span class="sxs-lookup"><span data-stu-id="98d8a-117">&amp;H20 (32)</span></span>  <br/> |<span data-ttu-id="98d8a-118">在排列时忽略连接点位置。</span><span class="sxs-lookup"><span data-stu-id="98d8a-118">Ignore connection point locations when being routed to.</span></span>  <br/> |<span data-ttu-id="98d8a-119">**visSLOFixedConnPtsIgnore**</span><span class="sxs-lookup"><span data-stu-id="98d8a-119">**visSLOFixedConnPtsIgnore**</span></span> <br/> |
|<span data-ttu-id="98d8a-120">&amp;H40 (64)</span><span class="sxs-lookup"><span data-stu-id="98d8a-120">&amp;H40 (64)</span></span>  <br/> |<span data-ttu-id="98d8a-121">仅允许排列到具有连接点的面上。</span><span class="sxs-lookup"><span data-stu-id="98d8a-121">Only allow routing to sides with connection points.</span></span>  <br/> |<span data-ttu-id="98d8a-122">**visSLOFixedConnPtsOnly**</span><span class="sxs-lookup"><span data-stu-id="98d8a-122">**visSLOFixedConnPtsOnly**</span></span> <br/> |
|<span data-ttu-id="98d8a-123">&amp;H80 (128)</span><span class="sxs-lookup"><span data-stu-id="98d8a-123">&amp;H80 (128)</span></span>  <br/> |<span data-ttu-id="98d8a-p101">不粘附到该形状的周界上，而是粘附到该形状的对齐框上。</span><span class="sxs-lookup"><span data-stu-id="98d8a-p101">Don't glue to the perimeter of this shape. Glue to the shape's alignment box instead.</span></span>  <br/> |<span data-ttu-id="98d8a-126">**visSLOFixedNoFoldToShape**</span><span class="sxs-lookup"><span data-stu-id="98d8a-126">**visSLOFixedNoFoldToShape**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="98d8a-127">备注</span><span class="sxs-lookup"><span data-stu-id="98d8a-127">Remarks</span></span>

<span data-ttu-id="98d8a-128">您还可以在**行为**对话框中的**位置**选项卡上设置此单元格的值 （与选定形状，在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡的**形状设计**组中，单击**行为**，，然后单击**位置**选项卡).</span><span class="sxs-lookup"><span data-stu-id="98d8a-128">You can also set the value of this cell on the **Placement** tab in the **Behavior** dialog box (with a shape selected, on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, in the **Shape Design** group, click **Behavior**, and then click the **Placement** tab).</span></span> 
  
<span data-ttu-id="98d8a-129">您可以设置此单元格这些值的任意组合。</span><span class="sxs-lookup"><span data-stu-id="98d8a-129">You can set any combination of these values for this cell.</span></span> <span data-ttu-id="98d8a-130">例如，您可以输入值 3 (&amp;H3)，使用**配置布局**对话框排放形状时，从而不再移动 （在**设计**选项卡的**布局**组中，单击**Re 布局页**，然后单击**更多布局选项**) 和其他可放置形状时放置在或附近形状。</span><span class="sxs-lookup"><span data-stu-id="98d8a-130">For example, you can enter the value 3 (&amp;H3), which eliminates movement when you lay out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options** ) and when other placeable shapes are placed on or near the shape.</span></span> 
  
<span data-ttu-id="98d8a-131">在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。</span><span class="sxs-lookup"><span data-stu-id="98d8a-131">In versions earlier than Visio 2000, you set this behavior using the ObjInteract cell in the Miscellaneous section.</span></span> 
  
<span data-ttu-id="98d8a-132">若要获取对 ShapeFixedCode 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="98d8a-132">To get a reference to the ShapeFixedCode cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="98d8a-133">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="98d8a-133">Cell name:</span></span>  <br/> |<span data-ttu-id="98d8a-134">ShapeFixedCode</span><span class="sxs-lookup"><span data-stu-id="98d8a-134">ShapeFixedCode</span></span>  <br/> |
   
<span data-ttu-id="98d8a-135">若要从某个程序按索引获取对 ShapeFixedCode 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="98d8a-135">To get a reference to the ShapeFixedCode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="98d8a-136">内容索引：</span><span class="sxs-lookup"><span data-stu-id="98d8a-136">Section index:</span></span>  <br/> |<span data-ttu-id="98d8a-137">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="98d8a-137">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="98d8a-138">行索引：</span><span class="sxs-lookup"><span data-stu-id="98d8a-138">Row index:</span></span>  <br/> |<span data-ttu-id="98d8a-139">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="98d8a-139">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="98d8a-140">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="98d8a-140">Cell index:</span></span>  <br/> |<span data-ttu-id="98d8a-141">**visSLOFixedCode**</span><span class="sxs-lookup"><span data-stu-id="98d8a-141">**visSLOFixedCode**</span></span> <br/> |
   

