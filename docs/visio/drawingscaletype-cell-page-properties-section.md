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
description: 确定在页面设置对话框中选中的绘图缩放比例 （单击主页选项卡上的页面设置箭头）。
ms.openlocfilehash: b93bd95a30fe5a8a5de15a8e5ea104279cf1bcda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780154"
---
# <a name="drawingscaletype-cell-page-properties-section"></a><span data-ttu-id="b253b-103">DrawingScaleType 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="b253b-103">DrawingScaleType Cell (Page Properties Section)</span></span>

<span data-ttu-id="b253b-104">确定在**页面设置**对话框中选中的绘图缩放比例 （单击**主页**选项卡上的**页面设置**箭头）。</span><span class="sxs-lookup"><span data-stu-id="b253b-104">Determines the drawing scale selected in the **Page Setup** dialog box (click the **Page Setup** arrow on the **Home** tab).</span></span> 
  
|<span data-ttu-id="b253b-105">**值**</span><span class="sxs-lookup"><span data-stu-id="b253b-105">**Value**</span></span>|<span data-ttu-id="b253b-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="b253b-106">**Description**</span></span>|<span data-ttu-id="b253b-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="b253b-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="b253b-108">0</span><span class="sxs-lookup"><span data-stu-id="b253b-108">0</span></span>  <br/> | <span data-ttu-id="b253b-109">无比例</span><span class="sxs-lookup"><span data-stu-id="b253b-109">No Scale</span></span>  <br/> |<span data-ttu-id="b253b-110">**visNoScale**</span><span class="sxs-lookup"><span data-stu-id="b253b-110">**visNoScale**</span></span> <br/> |
| <span data-ttu-id="b253b-111">1</span><span class="sxs-lookup"><span data-stu-id="b253b-111">1</span></span>  <br/> | <span data-ttu-id="b253b-112">结构比例</span><span class="sxs-lookup"><span data-stu-id="b253b-112">Architectural Scale</span></span>  <br/> |<span data-ttu-id="b253b-113">**visArchitectural**</span><span class="sxs-lookup"><span data-stu-id="b253b-113">**visArchitectural**</span></span> <br/> |
| <span data-ttu-id="b253b-114">2</span><span class="sxs-lookup"><span data-stu-id="b253b-114">2</span></span>  <br/> | <span data-ttu-id="b253b-115">土木工程比例</span><span class="sxs-lookup"><span data-stu-id="b253b-115">Civil Engineering Scale</span></span>  <br/> |<span data-ttu-id="b253b-116">**visEngineering**</span><span class="sxs-lookup"><span data-stu-id="b253b-116">**visEngineering**</span></span> <br/> |
| <span data-ttu-id="b253b-117">3</span><span class="sxs-lookup"><span data-stu-id="b253b-117">3</span></span>  <br/> | <span data-ttu-id="b253b-118">自定义缩放比例</span><span class="sxs-lookup"><span data-stu-id="b253b-118">Custom Scale</span></span>  <br/> |<span data-ttu-id="b253b-119">**visScaleCustom**</span><span class="sxs-lookup"><span data-stu-id="b253b-119">**visScaleCustom**</span></span> <br/> |
| <span data-ttu-id="b253b-120">4</span><span class="sxs-lookup"><span data-stu-id="b253b-120">4</span></span>  <br/> | <span data-ttu-id="b253b-121">公制</span><span class="sxs-lookup"><span data-stu-id="b253b-121">Metric</span></span>  <br/> |<span data-ttu-id="b253b-122">**visScaleMetric**</span><span class="sxs-lookup"><span data-stu-id="b253b-122">**visScaleMetric**</span></span> <br/> |
| <span data-ttu-id="b253b-123">5</span><span class="sxs-lookup"><span data-stu-id="b253b-123">5</span></span>  <br/> | <span data-ttu-id="b253b-124">机械工程比例</span><span class="sxs-lookup"><span data-stu-id="b253b-124">Mechanical Engineering Scale</span></span>  <br/> |<span data-ttu-id="b253b-125">**visScaleMechanical**</span><span class="sxs-lookup"><span data-stu-id="b253b-125">**visScaleMechanical**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b253b-126">备注</span><span class="sxs-lookup"><span data-stu-id="b253b-126">Remarks</span></span>

<span data-ttu-id="b253b-127">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 DrawingScaleType 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b253b-127">To get a reference to the DrawingScaleType cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b253b-128">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b253b-128">Cell name:</span></span>  <br/> | <span data-ttu-id="b253b-129">DrawingScaleType</span><span class="sxs-lookup"><span data-stu-id="b253b-129">DrawingScaleType</span></span>  <br/> |
   
<span data-ttu-id="b253b-130">若要从某个程序按索引获取对 DrawingScaleType 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="b253b-130">To get a reference to the DrawingScaleType cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b253b-131">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b253b-131">Section index:</span></span>  <br/> |<span data-ttu-id="b253b-132">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b253b-132">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="b253b-133">行索引：</span><span class="sxs-lookup"><span data-stu-id="b253b-133">Row index:</span></span>  <br/> |<span data-ttu-id="b253b-134">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="b253b-134">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="b253b-135">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b253b-135">Cell index:</span></span>  <br/> |<span data-ttu-id="b253b-136">**visPageDrawScaleType**</span><span class="sxs-lookup"><span data-stu-id="b253b-136">**visPageDrawScaleType**</span></span> <br/> |
   

