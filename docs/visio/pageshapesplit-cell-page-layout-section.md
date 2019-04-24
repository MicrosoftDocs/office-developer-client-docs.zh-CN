---
title: PageShapeSplit 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033777
localization_priority: Normal
ms.assetid: 4d3bdf77-0ad4-86a4-d215-1d5a5fbe33f7
description: 指示是否可以自动拆分页面上的形状。
ms.openlocfilehash: 18a40e0876b117556a1e7ab43f640e798dc248c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301482"
---
# <a name="pageshapesplit-cell-page-layout-section"></a><span data-ttu-id="b2dfa-103">PageShapeSplit 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="b2dfa-103">PageShapeSplit Cell (Page Layout Section)</span></span>

<span data-ttu-id="b2dfa-104">指示是否可以自动拆分页面上的形状。</span><span class="sxs-lookup"><span data-stu-id="b2dfa-104">Indicates whether shapes on the page can be automatically split.</span></span>
  
|<span data-ttu-id="b2dfa-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-105">**Value**</span></span>|<span data-ttu-id="b2dfa-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-106">**Description**</span></span>|<span data-ttu-id="b2dfa-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b2dfa-108">0</span><span class="sxs-lookup"><span data-stu-id="b2dfa-108">0</span></span>  <br/> |<span data-ttu-id="b2dfa-109">不允许自动拆分形状。</span><span class="sxs-lookup"><span data-stu-id="b2dfa-109">Do not allow automatic shape splitting.</span></span>  <br/> |<span data-ttu-id="b2dfa-110">**visPLOSplitNone**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-110">**visPLOSplitNone**</span></span> <br/> |
|<span data-ttu-id="b2dfa-111">1</span><span class="sxs-lookup"><span data-stu-id="b2dfa-111">1</span></span>  <br/> |<span data-ttu-id="b2dfa-112">允许自动拆分形状（默认值）。</span><span class="sxs-lookup"><span data-stu-id="b2dfa-112">Allow automatic shape splitting (the default).</span></span>  <br/> |<span data-ttu-id="b2dfa-113">**visPLOSplitAllow**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-113">**visPLOSplitAllow**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b2dfa-114">注解</span><span class="sxs-lookup"><span data-stu-id="b2dfa-114">Remarks</span></span>

<span data-ttu-id="b2dfa-p101">形状的自动拆分是在三个不同级别上启用和禁用的：应用程序、页面和形状。默认情况下，在应用程序和页面级别上启用拆分。形状的默认设置随绘图类型的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="b2dfa-p101">Automatic splitting of shapes is enabled and disabled at three different levels: application, page, and shape. By default, splitting is enabled at the application and page levels. The default setting for shapes varies by drawing type.</span></span> 
  
<span data-ttu-id="b2dfa-118">若要在应用程序级别启用或禁用拆分, 请使用 " **Visio 选项**" 对话框的 "**高级**" 选项卡上的 "**启用连接线拆分**" 设置 (单击 " **Office** " 按钮, 再单击**Visio**上的 "**选项**"选项卡, 然后单击 "**高级**")。</span><span class="sxs-lookup"><span data-stu-id="b2dfa-118">To enable or disable splitting at the application level, use the **Enable connector splitting** setting on the **Advanced** tab of the **Visio Options** dialog box (click the **Office** button, click **Options** on the **Visio** tab, and then click **Advanced** ).</span></span> 
  
<span data-ttu-id="b2dfa-119">若要在形状级别启用或禁用拆分, 请参阅 ShapeSplit 和 ShapeSplittable 单元格。</span><span class="sxs-lookup"><span data-stu-id="b2dfa-119">To enable or disable splitting at the shape level, see the ShapeSplit and ShapeSplittable cells.</span></span> 
  
<span data-ttu-id="b2dfa-120">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageShapeSplit 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b2dfa-120">To get a reference to the PageShapeSplit cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b2dfa-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b2dfa-121">Cell name:</span></span>  <br/> |<span data-ttu-id="b2dfa-122">PageShapeSplit</span><span class="sxs-lookup"><span data-stu-id="b2dfa-122">PageShapeSplit</span></span>  <br/> |
   
<span data-ttu-id="b2dfa-123">若要从某个程序按索引获取对 PageShapeSplit 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="b2dfa-123">To get a reference to the PageShapeSplit cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b2dfa-124">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b2dfa-124">Section index:</span></span>  <br/> |<span data-ttu-id="b2dfa-125">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-125">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="b2dfa-126">行索引：</span><span class="sxs-lookup"><span data-stu-id="b2dfa-126">Row index:</span></span>  <br/> |<span data-ttu-id="b2dfa-127">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-127">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="b2dfa-128">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b2dfa-128">Cell index:</span></span>  <br/> |<span data-ttu-id="b2dfa-129">**visPLOSplit**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-129">**visPLOSplit**</span></span> <br/> |
   

