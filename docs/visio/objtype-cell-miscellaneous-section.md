---
title: ObjType 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm745
localization_priority: Normal
ms.assetid: 3afee07b-e91a-a91c-fba2-0e3251dd6385
description: 确定当使用“配置布局”对话框排放形状时对象在图表中是可放置的还是可穿绕的。
ms.openlocfilehash: 7a607fdb53ad569e84976b6f9911fbd89f7f2628
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361010"
---
# <a name="objtype-cell-miscellaneous-section"></a><span data-ttu-id="ab12e-103">ObjType 单元格（“Miscellaneous”内容）</span><span class="sxs-lookup"><span data-stu-id="ab12e-103">ObjType Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="ab12e-104">确定当使用 **“配置布局”** 对话框排放形状时对象在图表中是可放置的还是可穿绕的。</span><span class="sxs-lookup"><span data-stu-id="ab12e-104">Determines whether objects are placeable or routable in diagrams when you use the **Configure Layout** dialog box to lay out shapes.</span></span> 
  
|<span data-ttu-id="ab12e-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="ab12e-105">**Value**</span></span>|<span data-ttu-id="ab12e-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="ab12e-106">**Description**</span></span>|<span data-ttu-id="ab12e-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="ab12e-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ab12e-108">&amp;H0</span><span class="sxs-lookup"><span data-stu-id="ab12e-108">&amp;H0</span></span>  <br/> |<span data-ttu-id="ab12e-109">默认值。</span><span class="sxs-lookup"><span data-stu-id="ab12e-109">Default.</span></span> <span data-ttu-id="ab12e-110">应用程序根据绘图上下文决定。</span><span class="sxs-lookup"><span data-stu-id="ab12e-110">The application decides based on the drawing context.</span></span>  <br/> |<span data-ttu-id="ab12e-111">**visLOFlagsVisDecides**</span><span class="sxs-lookup"><span data-stu-id="ab12e-111">**visLOFlagsVisDecides**</span></span> <br/> |
|<span data-ttu-id="ab12e-112">&amp;H1</span><span class="sxs-lookup"><span data-stu-id="ab12e-112">&amp;H1</span></span>  <br/> |<span data-ttu-id="ab12e-113">形状是可放置的。</span><span class="sxs-lookup"><span data-stu-id="ab12e-113">Shape is placeable.</span></span>  <br/> |<span data-ttu-id="ab12e-114">**visLOFlagsPlacable**</span><span class="sxs-lookup"><span data-stu-id="ab12e-114">**visLOFlagsPlacable**</span></span> <br/> |
|<span data-ttu-id="ab12e-115">&amp;H2</span><span class="sxs-lookup"><span data-stu-id="ab12e-115">&amp;H2</span></span>  <br/> |<span data-ttu-id="ab12e-116">形状是可穿绕的。</span><span class="sxs-lookup"><span data-stu-id="ab12e-116">Shape is routable.</span></span> <span data-ttu-id="ab12e-117">必须是一维 (1-D) 形状。</span><span class="sxs-lookup"><span data-stu-id="ab12e-117">Must be a one-dimensional (1-D) shape.</span></span>  <br/> |<span data-ttu-id="ab12e-118">**visLOFlagsRoutable**</span><span class="sxs-lookup"><span data-stu-id="ab12e-118">**visLOFlagsRoutable**</span></span> <br/> |
|<span data-ttu-id="ab12e-119">&amp;H4</span><span class="sxs-lookup"><span data-stu-id="ab12e-119">&amp;H4</span></span>  <br/> |<span data-ttu-id="ab12e-120">形状是不可放置且不可穿绕的。</span><span class="sxs-lookup"><span data-stu-id="ab12e-120">Shape is not placeable, not routable.</span></span>  <br/> |<span data-ttu-id="ab12e-121">**visLOFlagsDont**</span><span class="sxs-lookup"><span data-stu-id="ab12e-121">**visLOFlagsDont**</span></span> <br/> |
|<span data-ttu-id="ab12e-122">&amp;H8</span><span class="sxs-lookup"><span data-stu-id="ab12e-122">&amp;H8</span></span>  <br/> |<span data-ttu-id="ab12e-123">组合包含可放置/可穿绕的形状。</span><span class="sxs-lookup"><span data-stu-id="ab12e-123">Group contains placeable/routable shapes.</span></span>  <br/> |<span data-ttu-id="ab12e-124">**visLOFlagsPNRGroup**</span><span class="sxs-lookup"><span data-stu-id="ab12e-124">**visLOFlagsPNRGroup**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ab12e-125">注解</span><span class="sxs-lookup"><span data-stu-id="ab12e-125">Remarks</span></span>

<span data-ttu-id="ab12e-p103">默认情况下，形状的 ObjType 单元格设置为“No Formula”，其计算结果为 0，意味着由应用程序根据其上下文决定该形状能否放置。例如，如果您绘制了一个简单的矩形，它的 ObjType 单元格的值为 0。如果您接着用 **“连接线”** 工具将该矩形连接到另一个形状，Visio 就会将该矩形的 ObjType 单元格的值重新设置为 1（可放置）。</span><span class="sxs-lookup"><span data-stu-id="ab12e-p103">By default, the ObjType cell is set to No Formula for a shape, which evaluates to 0, meaning that the application determines whether the shape can be placeable depending on its context. For example, if you draw a simple rectangle, the value of its ObjType cell is 0. If you then use the **Connector** tool to connect the rectangle to another shape, Visio resets the value of the rectangle's ObjType cell to 1 (placeable).</span></span> 
  
<span data-ttu-id="ab12e-129">ObjType 单元格的值可以是几个值的组合。</span><span class="sxs-lookup"><span data-stu-id="ab12e-129">The value of the ObjType cell can be a combination of values.</span></span> <span data-ttu-id="ab12e-130">但是, 如果设置了不可放置位 (&amp;H4), 则它的优先级高于除 group value (&amp;H8) 以外的其他值。</span><span class="sxs-lookup"><span data-stu-id="ab12e-130">If the non-placeable bit is set (&amp;H4), however, it takes precedence over other values except the group value (&amp;H8).</span></span>
  
<span data-ttu-id="ab12e-131">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ObjType 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ab12e-131">To get a reference to the ObjType cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ab12e-132">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ab12e-132">Cell name:</span></span>  <br/> |<span data-ttu-id="ab12e-133">ObjType</span><span class="sxs-lookup"><span data-stu-id="ab12e-133">ObjType</span></span>  <br/> |
   
<span data-ttu-id="ab12e-134">若要从某个程序按索引获取对 ObjType 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ab12e-134">To get a reference to the ObjType cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ab12e-135">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ab12e-135">Section index:</span></span>  <br/> |<span data-ttu-id="ab12e-136">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ab12e-136">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="ab12e-137">行索引：</span><span class="sxs-lookup"><span data-stu-id="ab12e-137">Row index:</span></span>  <br/> |<span data-ttu-id="ab12e-138">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="ab12e-138">**visRowMisc**</span></span> <br/> |
|<span data-ttu-id="ab12e-139">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ab12e-139">Cell index:</span></span>  <br/> |<span data-ttu-id="ab12e-140">**visLOFlags**</span><span class="sxs-lookup"><span data-stu-id="ab12e-140">**visLOFlags**</span></span> <br/> |
   

