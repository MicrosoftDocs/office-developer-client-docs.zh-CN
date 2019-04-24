---
title: PlaceFlip 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253251
localization_priority: Normal
ms.assetid: df014b98-cfd5-b6d3-4b8a-b0acb3b94412
description: 确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）时可放置形状在页面上如何翻转和/或旋转。
ms.openlocfilehash: d1c31654782012b3536d35f3a12a923c2cc7a8f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346870"
---
# <a name="placeflip-cell-page-layout-section"></a><span data-ttu-id="23172-103">PlaceFlip 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="23172-103">PlaceFlip Cell (Page Layout Section)</span></span>

<span data-ttu-id="23172-104">确定在使用 **“配置布局”** 对话框（在 **“设计”** 选项卡上的 **“布局”** 组中，单击 **“重新布局页面”**，然后单击 **“其他布局选项”**）时可放置形状在页面上如何翻转和/或旋转。</span><span class="sxs-lookup"><span data-stu-id="23172-104">Determines how placeable shapes flip and/or rotate on a page when you use the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options**).</span></span>
  
|<span data-ttu-id="23172-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="23172-105">**Value**</span></span>|<span data-ttu-id="23172-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="23172-106">**Description**</span></span>|<span data-ttu-id="23172-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="23172-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23172-108">&amp;H0</span><span class="sxs-lookup"><span data-stu-id="23172-108">&amp;H0</span></span>  <br/> |<span data-ttu-id="23172-109">默认值。</span><span class="sxs-lookup"><span data-stu-id="23172-109">Default.</span></span> <span data-ttu-id="23172-110">不翻转。</span><span class="sxs-lookup"><span data-stu-id="23172-110">Do not flip.</span></span>  <br/> |<span data-ttu-id="23172-111">**visLOFlipDefault**</span><span class="sxs-lookup"><span data-stu-id="23172-111">**visLOFlipDefault**</span></span> <br/> |
|<span data-ttu-id="23172-112">&amp;H1</span><span class="sxs-lookup"><span data-stu-id="23172-112">&amp;H1</span></span>  <br/> |<span data-ttu-id="23172-113">水平翻转。</span><span class="sxs-lookup"><span data-stu-id="23172-113">Flip horizontal.</span></span>  <br/> |<span data-ttu-id="23172-114">**visLOFlipX**</span><span class="sxs-lookup"><span data-stu-id="23172-114">**visLOFlipX**</span></span> <br/> |
|<span data-ttu-id="23172-115">&amp;H2</span><span class="sxs-lookup"><span data-stu-id="23172-115">&amp;H2</span></span>  <br/> |<span data-ttu-id="23172-116">垂直翻转。</span><span class="sxs-lookup"><span data-stu-id="23172-116">Flip vertical.</span></span>  <br/> |<span data-ttu-id="23172-117">**visLOFlipY**</span><span class="sxs-lookup"><span data-stu-id="23172-117">**visLOFlipY**</span></span> <br/> |
|<span data-ttu-id="23172-118">&amp;H4</span><span class="sxs-lookup"><span data-stu-id="23172-118">&amp;H4</span></span>  <br/> |<span data-ttu-id="23172-119">翻转以 90 度为增量进行。</span><span class="sxs-lookup"><span data-stu-id="23172-119">Flip in 90 degree increments.</span></span>  <br/> |<span data-ttu-id="23172-120">**visLOFlipRotate**</span><span class="sxs-lookup"><span data-stu-id="23172-120">**visLOFlipRotate**</span></span> <br/> |
|<span data-ttu-id="23172-121">&amp;H8</span><span class="sxs-lookup"><span data-stu-id="23172-121">&amp;H8</span></span>  <br/> |<span data-ttu-id="23172-122">不翻转。</span><span class="sxs-lookup"><span data-stu-id="23172-122">Do not flip.</span></span>  <br/> |<span data-ttu-id="23172-123">**visLOFlipNone**</span><span class="sxs-lookup"><span data-stu-id="23172-123">**visLOFlipNone**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="23172-124">注解</span><span class="sxs-lookup"><span data-stu-id="23172-124">Remarks</span></span>

<span data-ttu-id="23172-p102">PlaceFlip 单元格中的值有助于将可放置形状的方向朝向它连接的下一个可放置形状。该值通常在排放使用静态粘附的绘图时使用。</span><span class="sxs-lookup"><span data-stu-id="23172-p102">The value in the PlaceFlip cell helps orient a placeable shape toward the next placeable shape it is connected to. It is typically used when laying out drawings that use static glue.</span></span>
  
<span data-ttu-id="23172-127">若要为特定形状设置此行为，请使用“Shape Layout”内容中的 ShapePlaceFlip 单元格。</span><span class="sxs-lookup"><span data-stu-id="23172-127">To set this behavior for a particular shape, use the ShapePlaceFlip cell in the Shape Layout section.</span></span>
  
<span data-ttu-id="23172-128">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PlaceFlip 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="23172-128">To get a reference to the PlaceFlip cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23172-129">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="23172-129">Cell name:</span></span>  <br/> |<span data-ttu-id="23172-130">PlaceFlip</span><span class="sxs-lookup"><span data-stu-id="23172-130">PlaceFlip</span></span>  <br/> |
   
<span data-ttu-id="23172-131">若要从某个程序按索引获取对 PlaceFlip 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="23172-131">To get a reference to the PlaceFlip cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23172-132">内容索引：</span><span class="sxs-lookup"><span data-stu-id="23172-132">Section index:</span></span>  <br/> |<span data-ttu-id="23172-133">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="23172-133">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="23172-134">行索引：</span><span class="sxs-lookup"><span data-stu-id="23172-134">Row index:</span></span>  <br/> |<span data-ttu-id="23172-135">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="23172-135">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="23172-136">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="23172-136">Cell index:</span></span>  <br/> |<span data-ttu-id="23172-137">**visPLOPlaceFlip**</span><span class="sxs-lookup"><span data-stu-id="23172-137">**visPLOPlaceFlip**</span></span> <br/> |
   

