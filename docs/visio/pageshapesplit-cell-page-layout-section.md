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
ms.openlocfilehash: 7f1df0158cde6853c5518597c853cb56151eefbc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780845"
---
# <a name="pageshapesplit-cell-page-layout-section"></a><span data-ttu-id="d60d9-103">PageShapeSplit 单元格（“Page Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="d60d9-103">PageShapeSplit Cell (Page Layout Section)</span></span>

<span data-ttu-id="d60d9-104">指示是否可以自动拆分页面上的形状。</span><span class="sxs-lookup"><span data-stu-id="d60d9-104">Indicates whether shapes on the page can be automatically split.</span></span>
  
|<span data-ttu-id="d60d9-105">**值**</span><span class="sxs-lookup"><span data-stu-id="d60d9-105">**Value**</span></span>|<span data-ttu-id="d60d9-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="d60d9-106">**Description**</span></span>|<span data-ttu-id="d60d9-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="d60d9-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d60d9-108">0</span><span class="sxs-lookup"><span data-stu-id="d60d9-108">0</span></span>  <br/> |<span data-ttu-id="d60d9-109">不允许自动拆分形状。</span><span class="sxs-lookup"><span data-stu-id="d60d9-109">Do not allow automatic shape splitting.</span></span>  <br/> |<span data-ttu-id="d60d9-110">**visPLOSplitNone**</span><span class="sxs-lookup"><span data-stu-id="d60d9-110">**visPLOSplitNone**</span></span> <br/> |
|<span data-ttu-id="d60d9-111">1</span><span class="sxs-lookup"><span data-stu-id="d60d9-111">1</span></span>  <br/> |<span data-ttu-id="d60d9-112">允许自动拆分形状（默认值）。</span><span class="sxs-lookup"><span data-stu-id="d60d9-112">Allow automatic shape splitting (the default).</span></span>  <br/> |<span data-ttu-id="d60d9-113">**visPLOSplitAllow**</span><span class="sxs-lookup"><span data-stu-id="d60d9-113">**visPLOSplitAllow**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d60d9-114">注解</span><span class="sxs-lookup"><span data-stu-id="d60d9-114">Remarks</span></span>

<span data-ttu-id="d60d9-p101">形状的自动拆分是在三个不同级别上启用和禁用的：应用程序、页面和形状。默认情况下，在应用程序和页面级别上启用拆分。形状的默认设置随绘图类型的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="d60d9-p101">Automatic splitting of shapes is enabled and disabled at three different levels: application, page, and shape. By default, splitting is enabled at the application and page levels. The default setting for shapes varies by drawing type.</span></span> 
  
<span data-ttu-id="d60d9-118">若要启用或禁用应用程序级别拆分，请使用**启用连接线拆分**设置**Visio 选项**对话框的**高级**选项卡 （单击**Office**按钮，单击**Visio** **选项**选项卡，然后单击**高级**）。</span><span class="sxs-lookup"><span data-stu-id="d60d9-118">To enable or disable splitting at the application level, use the **Enable connector splitting** setting on the **Advanced** tab of the **Visio Options** dialog box (click the **Office** button, click **Options** on the **Visio** tab, and then click **Advanced** ).</span></span> 
  
<span data-ttu-id="d60d9-119">若要启用或禁用拆分在形状级别，请参阅 ShapeSplit 和 ShapeSplittable 单元格。</span><span class="sxs-lookup"><span data-stu-id="d60d9-119">To enable or disable splitting at the shape level, see the ShapeSplit and ShapeSplittable cells.</span></span> 
  
<span data-ttu-id="d60d9-120">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageShapeSplit 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d60d9-120">To get a reference to the PageShapeSplit cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d60d9-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d60d9-121">Cell name:</span></span>  <br/> |<span data-ttu-id="d60d9-122">PageShapeSplit</span><span class="sxs-lookup"><span data-stu-id="d60d9-122">PageShapeSplit</span></span>  <br/> |
   
<span data-ttu-id="d60d9-123">若要从某个程序按索引获取对 PageShapeSplit 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d60d9-123">To get a reference to the PageShapeSplit cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d60d9-124">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d60d9-124">Section index:</span></span>  <br/> |<span data-ttu-id="d60d9-125">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d60d9-125">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="d60d9-126">行索引：</span><span class="sxs-lookup"><span data-stu-id="d60d9-126">Row index:</span></span>  <br/> |<span data-ttu-id="d60d9-127">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="d60d9-127">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="d60d9-128">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d60d9-128">Cell index:</span></span>  <br/> |<span data-ttu-id="d60d9-129">**visPLOSplit**</span><span class="sxs-lookup"><span data-stu-id="d60d9-129">**visPLOSplit**</span></span> <br/> |
   

