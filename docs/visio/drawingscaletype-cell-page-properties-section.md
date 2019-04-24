---
title: DrawingScaleType 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm270
localization_priority: Normal
ms.assetid: 5d4f1cf8-bc1f-07b8-1da5-7253808e337e
description: 确定在“页面设置”对话框（单击“开始”选项卡上的“页面设置”箭头）中所选的绘图缩放比例。
ms.openlocfilehash: d1c1c00ffe025c566646a1f8b9fe034732ad86a8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359687"
---
# <a name="drawingscaletype-cell-page-properties-section"></a><span data-ttu-id="be090-103">DrawingScaleType 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="be090-103">DrawingScaleType Cell (Page Properties Section)</span></span>

<span data-ttu-id="be090-104">确定在 **“页面设置”** 对话框（单击 **“开始”** 选项卡上的 **“页面设置”** 箭头）中所选的绘图缩放比例。</span><span class="sxs-lookup"><span data-stu-id="be090-104">Determines the drawing scale selected in the **Page Setup** dialog box (click the **Page Setup** arrow on the **Home** tab).</span></span> 
  
|<span data-ttu-id="be090-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="be090-105">**Value**</span></span>|<span data-ttu-id="be090-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="be090-106">**Description**</span></span>|<span data-ttu-id="be090-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="be090-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="be090-108">0</span><span class="sxs-lookup"><span data-stu-id="be090-108">0</span></span>  <br/> | <span data-ttu-id="be090-109">无比例</span><span class="sxs-lookup"><span data-stu-id="be090-109">No Scale</span></span>  <br/> |<span data-ttu-id="be090-110">**visNoScale**</span><span class="sxs-lookup"><span data-stu-id="be090-110">**visNoScale**</span></span> <br/> |
| <span data-ttu-id="be090-111">1</span><span class="sxs-lookup"><span data-stu-id="be090-111">1</span></span>  <br/> | <span data-ttu-id="be090-112">结构比例</span><span class="sxs-lookup"><span data-stu-id="be090-112">Architectural Scale</span></span>  <br/> |<span data-ttu-id="be090-113">**visArchitectural**</span><span class="sxs-lookup"><span data-stu-id="be090-113">**visArchitectural**</span></span> <br/> |
| <span data-ttu-id="be090-114">双面</span><span class="sxs-lookup"><span data-stu-id="be090-114">2</span></span>  <br/> | <span data-ttu-id="be090-115">土木工程比例</span><span class="sxs-lookup"><span data-stu-id="be090-115">Civil Engineering Scale</span></span>  <br/> |<span data-ttu-id="be090-116">**visEngineering**</span><span class="sxs-lookup"><span data-stu-id="be090-116">**visEngineering**</span></span> <br/> |
| <span data-ttu-id="be090-117">第三章</span><span class="sxs-lookup"><span data-stu-id="be090-117">3</span></span>  <br/> | <span data-ttu-id="be090-118">自定义缩放比例</span><span class="sxs-lookup"><span data-stu-id="be090-118">Custom Scale</span></span>  <br/> |<span data-ttu-id="be090-119">**visScaleCustom**</span><span class="sxs-lookup"><span data-stu-id="be090-119">**visScaleCustom**</span></span> <br/> |
| <span data-ttu-id="be090-120">4</span><span class="sxs-lookup"><span data-stu-id="be090-120">4</span></span>  <br/> | <span data-ttu-id="be090-121">多重</span><span class="sxs-lookup"><span data-stu-id="be090-121">Metric</span></span>  <br/> |<span data-ttu-id="be090-122">**visScaleMetric**</span><span class="sxs-lookup"><span data-stu-id="be090-122">**visScaleMetric**</span></span> <br/> |
| <span data-ttu-id="be090-123">5</span><span class="sxs-lookup"><span data-stu-id="be090-123">5</span></span>  <br/> | <span data-ttu-id="be090-124">机械工程比例</span><span class="sxs-lookup"><span data-stu-id="be090-124">Mechanical Engineering Scale</span></span>  <br/> |<span data-ttu-id="be090-125">**visScaleMechanical**</span><span class="sxs-lookup"><span data-stu-id="be090-125">**visScaleMechanical**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="be090-126">注解</span><span class="sxs-lookup"><span data-stu-id="be090-126">Remarks</span></span>

<span data-ttu-id="be090-127">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DrawingScaleType 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="be090-127">To get a reference to the DrawingScaleType cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="be090-128">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="be090-128">Cell name:</span></span>  <br/> | <span data-ttu-id="be090-129">DrawingScaleType</span><span class="sxs-lookup"><span data-stu-id="be090-129">DrawingScaleType</span></span>  <br/> |
   
<span data-ttu-id="be090-130">若要从某个程序按索引获取对 DrawingScaleType 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="be090-130">To get a reference to the DrawingScaleType cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="be090-131">内容索引：</span><span class="sxs-lookup"><span data-stu-id="be090-131">Section index:</span></span>  <br/> |<span data-ttu-id="be090-132">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="be090-132">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="be090-133">行索引：</span><span class="sxs-lookup"><span data-stu-id="be090-133">Row index:</span></span>  <br/> |<span data-ttu-id="be090-134">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="be090-134">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="be090-135">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="be090-135">Cell index:</span></span>  <br/> |<span data-ttu-id="be090-136">**visPageDrawScaleType**</span><span class="sxs-lookup"><span data-stu-id="be090-136">**visPageDrawScaleType**</span></span> <br/> |
   

