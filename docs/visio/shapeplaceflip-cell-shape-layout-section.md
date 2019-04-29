---
title: ShapePlaceFlip 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253247
localization_priority: Normal
ms.assetid: 40008507-d9e4-9c0e-603f-d5e6da73a94b
description: 确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）排放形状时，可放置形状在页面上如何翻转、旋转或同时翻转和旋转。
ms.openlocfilehash: 72ef1b67dd87d842e6a4372d1eb08d614f0eb2d3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429276"
---
# <a name="shapeplaceflip-cell-shape-layout-section"></a><span data-ttu-id="5dcac-103">ShapePlaceFlip 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="5dcac-103">ShapePlaceFlip Cell (Shape Layout Section)</span></span>

<span data-ttu-id="5dcac-104">确定在使用 **“配置布局”** 对话框（在 **“设计”** 选项卡上的 **“布局”** 组中，单击 **“重新布局页面”**，然后单击 **“其他布局选项”**）排放形状时，可放置形状在页面上如何翻转、旋转或同时翻转和旋转。</span><span class="sxs-lookup"><span data-stu-id="5dcac-104">Determines how a placeable shape flips, rotates, or both on the page when you are laying out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options**).</span></span>
  
|<span data-ttu-id="5dcac-105">**值**</span><span class="sxs-lookup"><span data-stu-id="5dcac-105">**Value**</span></span>|<span data-ttu-id="5dcac-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="5dcac-106">**Description**</span></span>|<span data-ttu-id="5dcac-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="5dcac-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5dcac-108">0</span><span class="sxs-lookup"><span data-stu-id="5dcac-108">0</span></span>  <br/> |<span data-ttu-id="5dcac-109">使用页默认值。</span><span class="sxs-lookup"><span data-stu-id="5dcac-109">Use page default.</span></span>  <br/> |<span data-ttu-id="5dcac-110">**visLOFlipDefault**</span><span class="sxs-lookup"><span data-stu-id="5dcac-110">**visLOFlipDefault**</span></span> <br/> |
|<span data-ttu-id="5dcac-111">1</span><span class="sxs-lookup"><span data-stu-id="5dcac-111">1</span></span>  <br/> |<span data-ttu-id="5dcac-112">水平翻转。</span><span class="sxs-lookup"><span data-stu-id="5dcac-112">Flip horizontal.</span></span>  <br/> |<span data-ttu-id="5dcac-113">**visLOFlipX**</span><span class="sxs-lookup"><span data-stu-id="5dcac-113">**visLOFlipX**</span></span> <br/> |
|<span data-ttu-id="5dcac-114">双面</span><span class="sxs-lookup"><span data-stu-id="5dcac-114">2</span></span>  <br/> |<span data-ttu-id="5dcac-115">垂直翻转。</span><span class="sxs-lookup"><span data-stu-id="5dcac-115">Flip vertical.</span></span>  <br/> |<span data-ttu-id="5dcac-116">**visLOFlipY**</span><span class="sxs-lookup"><span data-stu-id="5dcac-116">**visLOFlipY**</span></span> <br/> |
|<span data-ttu-id="5dcac-117">4</span><span class="sxs-lookup"><span data-stu-id="5dcac-117">4</span></span>  <br/> |<span data-ttu-id="5dcac-118">以 90 度为增量在 0 到 270 度之间翻转。</span><span class="sxs-lookup"><span data-stu-id="5dcac-118">Flip in 90 degree increments between 0 and 270.</span></span>  <br/> |<span data-ttu-id="5dcac-119">**visLOFlipRotate**</span><span class="sxs-lookup"><span data-stu-id="5dcac-119">**visLOFlipRotate**</span></span> <br/> |
|<span data-ttu-id="5dcac-120">utf-8</span><span class="sxs-lookup"><span data-stu-id="5dcac-120">8</span></span>  <br/> |<span data-ttu-id="5dcac-121">不翻转。</span><span class="sxs-lookup"><span data-stu-id="5dcac-121">Do not flip.</span></span>  <br/> |<span data-ttu-id="5dcac-122">**visLOFlipNone**</span><span class="sxs-lookup"><span data-stu-id="5dcac-122">**visLOFlipNone**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5dcac-123">说明</span><span class="sxs-lookup"><span data-stu-id="5dcac-123">Remarks</span></span>

<span data-ttu-id="5dcac-124">ShapePlaceFlip 单元格中的值有助于将可放置形状的方向朝向它连接的下一个可放置形状。</span><span class="sxs-lookup"><span data-stu-id="5dcac-124">The value in the ShapePlaceFlip cell helps orient a placeable shape toward the next placeable shape it is connected to.</span></span>
  
<span data-ttu-id="5dcac-125">若要为绘图页上的*所有*形状设置此行为, 请使用 "页面布局" 部分中的 "PlaceFlip" 单元格。</span><span class="sxs-lookup"><span data-stu-id="5dcac-125">To set this behavior for  *all*  the shapes on the drawing page, use the PlaceFlip cell in the Page Layout section.</span></span> 
  
<span data-ttu-id="5dcac-126">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePlaceFlip 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5dcac-126">To get a reference to the ShapePlaceFlip cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5dcac-127">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5dcac-127">Cell name:</span></span>  <br/> |<span data-ttu-id="5dcac-128">ShapePlaceFlip</span><span class="sxs-lookup"><span data-stu-id="5dcac-128">ShapePlaceFlip</span></span>  <br/> |
   
<span data-ttu-id="5dcac-129">若要从某个程序按索引获取对 ShapePlaceFlip 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="5dcac-129">To get a reference to the ShapePlaceFlip cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5dcac-130">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5dcac-130">Section index:</span></span>  <br/> |<span data-ttu-id="5dcac-131">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="5dcac-131">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="5dcac-132">行索引：</span><span class="sxs-lookup"><span data-stu-id="5dcac-132">Row index:</span></span>  <br/> |<span data-ttu-id="5dcac-133">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="5dcac-133">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="5dcac-134">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5dcac-134">Cell index:</span></span>  <br/> |<span data-ttu-id="5dcac-135">**visSLOPlaceFlip**</span><span class="sxs-lookup"><span data-stu-id="5dcac-135">**visSLOPlaceFlip**</span></span> <br/> |
   

