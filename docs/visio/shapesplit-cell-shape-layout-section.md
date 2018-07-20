---
title: ShapeSplit 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60080
localization_priority: Normal
ms.assetid: 96b8c503-67b3-8623-d99b-0dad7b15c224
description: 指示此形状是否可以拆分其他可拆分的形状。
ms.openlocfilehash: b782977bd5b7e828223675eb16f4e7e48f4ca55d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781297"
---
# <a name="shapesplit-cell-shape-layout-section"></a><span data-ttu-id="60f6d-103">ShapeSplit 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="60f6d-103">ShapeSplit Cell (Shape Layout Section)</span></span>

<span data-ttu-id="60f6d-104">指示此形状是否可以拆分其他可拆分的形状。</span><span class="sxs-lookup"><span data-stu-id="60f6d-104">Indicates whether this shape can split shapes that are splittable.</span></span>
  
|<span data-ttu-id="60f6d-105">**值**</span><span class="sxs-lookup"><span data-stu-id="60f6d-105">**Value**</span></span>|<span data-ttu-id="60f6d-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="60f6d-106">**Description**</span></span>|<span data-ttu-id="60f6d-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="60f6d-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="60f6d-108">0</span><span class="sxs-lookup"><span data-stu-id="60f6d-108">0</span></span>  <br/> | <span data-ttu-id="60f6d-109">不允许此形状拆分其他形状。</span><span class="sxs-lookup"><span data-stu-id="60f6d-109">Do not allow this shape to split other shapes.</span></span>  <br/> |<span data-ttu-id="60f6d-110">**visSLOSplitNone**</span><span class="sxs-lookup"><span data-stu-id="60f6d-110">**visSLOSplitNone**</span></span> <br/> |
| <span data-ttu-id="60f6d-111">1</span><span class="sxs-lookup"><span data-stu-id="60f6d-111">1</span></span>  <br/> | <span data-ttu-id="60f6d-112">允许此形状拆分其他形状。</span><span class="sxs-lookup"><span data-stu-id="60f6d-112">Allow this shape to split other shapes.</span></span>  <br/> |<span data-ttu-id="60f6d-113">**visSLOSplitAllow**</span><span class="sxs-lookup"><span data-stu-id="60f6d-113">**visSLOSplitAllow**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="60f6d-114">注解</span><span class="sxs-lookup"><span data-stu-id="60f6d-114">Remarks</span></span>

<span data-ttu-id="60f6d-115">可以拆分其他形状的形状必须是二维形状或一维可放置形状。</span><span class="sxs-lookup"><span data-stu-id="60f6d-115">A shape that can split other shapes must be either a 2-D shape or a 1-D placeable shape.</span></span> 
  
<span data-ttu-id="60f6d-p101">形状的自动拆分是在三个不同级别上启用和禁用的：应用程序、页面和形状。默认情况下，在应用程序和页面级别上启用拆分；形状的默认设置随绘图类型的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="60f6d-p101">Automatic splitting of shapes is enabled and disabled at three different levels: application, page, and shape. By default, splitting is enabled at the application and page level; for shapes, it varies by drawing type.</span></span> 
  
<span data-ttu-id="60f6d-118">若要启用或禁用应用程序级别拆分，请使用**启用连接线拆分**设置**Visio 选项**对话框的**高级**选项卡 （**文件**选项卡，单击**选项**，然后单击**高级**)。</span><span class="sxs-lookup"><span data-stu-id="60f6d-118">To enable or disable splitting at the application level, use the **Enable connector splitting** setting on the **Advanced** tab of the **Visio Options** dialog box (click the **File** tab, click **Options**, and then click **Advanced**).</span></span> 
  
<span data-ttu-id="60f6d-119">若要启用/禁用页面拆分，请参阅 PageShapeSplit 单元格。</span><span class="sxs-lookup"><span data-stu-id="60f6d-119">To enable or disable splitting on a page, see the PageShapeSplit cell.</span></span> 
  
<span data-ttu-id="60f6d-120">要使一维形状可以拆分，请参阅 ShapeSplittable 单元格。</span><span class="sxs-lookup"><span data-stu-id="60f6d-120">To cause a 1-D shape to be splittable, see the ShapeSplittable cell.</span></span>
  
<span data-ttu-id="60f6d-121">若要获取对 ShapeSplit 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="60f6d-121">To get a reference to the ShapeSplit cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="60f6d-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="60f6d-122">Cell name:</span></span>  <br/> | <span data-ttu-id="60f6d-123">ShapeSplit</span><span class="sxs-lookup"><span data-stu-id="60f6d-123">ShapeSplit</span></span>  <br/> |
   
<span data-ttu-id="60f6d-124">若要从某个程序按索引获取对 ShapeSplit 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="60f6d-124">To get a reference to the ShapeSplit cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="60f6d-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="60f6d-125">Section index:</span></span>  <br/> |<span data-ttu-id="60f6d-126">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="60f6d-126">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="60f6d-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="60f6d-127">Row index:</span></span>  <br/> |<span data-ttu-id="60f6d-128">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="60f6d-128">**visRowShapeLayout**</span></span> <br/> |
| <span data-ttu-id="60f6d-129">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="60f6d-129">Cell index:</span></span>  <br/> |<span data-ttu-id="60f6d-130">**visSLOSplit**</span><span class="sxs-lookup"><span data-stu-id="60f6d-130">**visSLOSplit**</span></span> <br/> |
   
