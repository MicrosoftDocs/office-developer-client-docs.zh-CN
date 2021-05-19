---
title: ShapeSplittable 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60081
localization_priority: Normal
ms.assetid: 6330304a-71f3-62b4-1b27-14495e3f12c3
description: 指示此一维形状是否可以拆分。
ms.openlocfilehash: 9f92cf7d147be8e59d860bcc8a958bf0cdc008c6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427071"
---
# <a name="shapesplittable-cell-shape-layout-section"></a><span data-ttu-id="92ee4-103">ShapeSplittable 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="92ee4-103">ShapeSplittable Cell (Shape Layout Section)</span></span>

<span data-ttu-id="92ee4-104">指示此一维形状是否可以拆分。</span><span class="sxs-lookup"><span data-stu-id="92ee4-104">Indicates whether this 1-D shape can be split.</span></span> 
  
|<span data-ttu-id="92ee4-105">**值**</span><span class="sxs-lookup"><span data-stu-id="92ee4-105">**Value**</span></span>|<span data-ttu-id="92ee4-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="92ee4-106">**Description**</span></span>|<span data-ttu-id="92ee4-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="92ee4-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="92ee4-108">0</span><span class="sxs-lookup"><span data-stu-id="92ee4-108">0</span></span>  <br/> | <span data-ttu-id="92ee4-109">不允许拆分此形状。</span><span class="sxs-lookup"><span data-stu-id="92ee4-109">Do not allow this shape to be split.</span></span>  <br/> |<span data-ttu-id="92ee4-110">**visSLOSplittableNone**</span><span class="sxs-lookup"><span data-stu-id="92ee4-110">**visSLOSplittableNone**</span></span> <br/> |
| <span data-ttu-id="92ee4-111">1</span><span class="sxs-lookup"><span data-stu-id="92ee4-111">1</span></span>  <br/> | <span data-ttu-id="92ee4-112">允许拆分此形状。</span><span class="sxs-lookup"><span data-stu-id="92ee4-112">Allow this shape to be split.</span></span>  <br/> |<span data-ttu-id="92ee4-113">**visSLOSplittableAllow**</span><span class="sxs-lookup"><span data-stu-id="92ee4-113">**visSLOSplittableAllow**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="92ee4-114">备注</span><span class="sxs-lookup"><span data-stu-id="92ee4-114">Remarks</span></span>

<span data-ttu-id="92ee4-115">连接线和其他一维形状的默认行为取决于绘图类型。</span><span class="sxs-lookup"><span data-stu-id="92ee4-115">The default behavior for connectors and other 1-D shapes varies by drawing type.</span></span> 
  
<span data-ttu-id="92ee4-p101">形状的自动拆分是在三个不同级别上启用和禁用的：应用程序、页面和形状。默认情况下，在应用程序和页面级别上启用拆分。</span><span class="sxs-lookup"><span data-stu-id="92ee4-p101">Automatic splitting of shapes is enabled and disabled at three different levels: application, page, and shape. By default, splitting is enabled at the application level and page levels.</span></span> 
  
<span data-ttu-id="92ee4-118">若要在应用程序级别启用或禁用拆分，请使用 **"Visio** 选项"对话框的"高级"选项卡上的"启用连接器拆分"设置 (单击"文件"选项卡，单击"选项"，然后单击"高级) "。  </span><span class="sxs-lookup"><span data-stu-id="92ee4-118">To enable or disable splitting at the application level, use the **Enable connector splitting** setting on the **Advanced** tab of the **Visio Options** dialog box (click the **File** tab, click **Options**, and then click **Advanced** ).</span></span> 
  
<span data-ttu-id="92ee4-119">若要启用/禁用页面拆分，请参阅 [PageShapeSplit](pageshapesplit-cell-page-layout-section.md) 单元格。</span><span class="sxs-lookup"><span data-stu-id="92ee4-119">To enable or disable splitting on a page, see the [PageShapeSplit](pageshapesplit-cell-page-layout-section.md) cell.</span></span> 
  
<span data-ttu-id="92ee4-120">若要使某个形状可以拆分其他一维可拆分形状，请参阅 [ShapeSplit](shapesplit-cell-shape-layout-section.md) 单元格。</span><span class="sxs-lookup"><span data-stu-id="92ee4-120">To cause a shape to be able to split 1-D splittable shapes, see the [ShapeSplit](shapesplit-cell-shape-layout-section.md) cell.</span></span> 
  
<span data-ttu-id="92ee4-121">若要从另一个公式或使用 **CellsU** 属性从程序按名称获取对 ShapeSplittable 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="92ee4-121">To get a reference to the ShapeSplittable cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="92ee4-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="92ee4-122">Cell name:</span></span>  <br/> | <span data-ttu-id="92ee4-123">ShapeSplittable</span><span class="sxs-lookup"><span data-stu-id="92ee4-123">ShapeSplittable</span></span>  <br/> |
   
<span data-ttu-id="92ee4-124">若要从某个程序按索引获取对 ShapeSplittable 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="92ee4-124">To get a reference to the ShapeSplittable cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="92ee4-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="92ee4-125">Section index:</span></span>  <br/> |<span data-ttu-id="92ee4-126">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="92ee4-126">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="92ee4-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="92ee4-127">Row index:</span></span>  <br/> |<span data-ttu-id="92ee4-128">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="92ee4-128">**visRowShapeLayout**</span></span> <br/> |
| <span data-ttu-id="92ee4-129">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="92ee4-129">Cell index:</span></span>  <br/> |<span data-ttu-id="92ee4-130">**visSLOSplittable**</span><span class="sxs-lookup"><span data-stu-id="92ee4-130">**visSLOSplittable**</span></span> <br/> |
   

