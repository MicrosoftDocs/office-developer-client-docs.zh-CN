---
title: ShapeShdwType 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033173
localization_priority: Normal
ms.assetid: 1461148d-90a9-6f7c-1b28-9310ffaf0e3b
description: 指定形状的阴影类型。
ms.openlocfilehash: b96ad4a877d72bf4457ec3cf038a29a2b414e0f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781287"
---
# <a name="shapeshdwtype-cell-fill-format-section"></a><span data-ttu-id="b33fe-103">ShapeShdwType 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="b33fe-103">ShapeShdwType Cell (Fill Format Section)</span></span>

<span data-ttu-id="b33fe-104">指定形状的阴影类型。</span><span class="sxs-lookup"><span data-stu-id="b33fe-104">Specifies the type of shadow for a shape.</span></span> 
  
|<span data-ttu-id="b33fe-105">**值**</span><span class="sxs-lookup"><span data-stu-id="b33fe-105">**Value**</span></span>|<span data-ttu-id="b33fe-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="b33fe-106">**Description**</span></span>|<span data-ttu-id="b33fe-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="b33fe-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b33fe-108">0</span><span class="sxs-lookup"><span data-stu-id="b33fe-108">0</span></span>  <br/> |<span data-ttu-id="b33fe-109">使用页面默认值（默认值）</span><span class="sxs-lookup"><span data-stu-id="b33fe-109">Use page default (the default)</span></span>  <br/> |<span data-ttu-id="b33fe-110">**visFSTPageDefault**</span><span class="sxs-lookup"><span data-stu-id="b33fe-110">**visFSTPageDefault**</span></span> <br/> |
|<span data-ttu-id="b33fe-111">1</span><span class="sxs-lookup"><span data-stu-id="b33fe-111">1</span></span>  <br/> |<span data-ttu-id="b33fe-112">简单</span><span class="sxs-lookup"><span data-stu-id="b33fe-112">Simple</span></span>  <br/> |<span data-ttu-id="b33fe-113">**visFSTSimple**</span><span class="sxs-lookup"><span data-stu-id="b33fe-113">**visFSTSimple**</span></span> <br/> |
|<span data-ttu-id="b33fe-114">2</span><span class="sxs-lookup"><span data-stu-id="b33fe-114">2</span></span>  <br/> |<span data-ttu-id="b33fe-115">倾斜</span><span class="sxs-lookup"><span data-stu-id="b33fe-115">Oblique</span></span>  <br/> |<span data-ttu-id="b33fe-116">**visFSTOblique**</span><span class="sxs-lookup"><span data-stu-id="b33fe-116">**visFSTOblique**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b33fe-117">备注</span><span class="sxs-lookup"><span data-stu-id="b33fe-117">Remarks</span></span>

<span data-ttu-id="b33fe-118">使用此单元格应用形状阴影的不同页面默认值 （在属性页部分的 ShdwType 单元格定义页面默认阴影类型）。</span><span class="sxs-lookup"><span data-stu-id="b33fe-118">Use this cell to apply a shape shadow that is different from the page default (the page default shadow type is defined in the ShdwType cell in the Page Properties Section).</span></span>
  
<span data-ttu-id="b33fe-119">用户界面 (UI) 中的偏移阴影介绍简单阴影类型。</span><span class="sxs-lookup"><span data-stu-id="b33fe-119">Simple shadow types are described as offset shadows in the user interface (UI).</span></span> <span data-ttu-id="b33fe-120">简单阴影效果的形状的阴影投射到的并行面上形状后面。</span><span class="sxs-lookup"><span data-stu-id="b33fe-120">A simple shadow gives the effect of the shape being shadowed onto a parallel plane located behind the shape.</span></span> <span data-ttu-id="b33fe-121">倾斜阴影倾斜阴影在 UI 中所述，并为被强制转换到平面上垂直到形状的阴影效果。</span><span class="sxs-lookup"><span data-stu-id="b33fe-121">Oblique shadows are described as oblique shadows in the UI and give the effect of a shadow being cast onto a plane perpendicular to the shape.</span></span> 
  
<span data-ttu-id="b33fe-122">预定义的简单和倾斜阴影类型的列表，请参阅**样式**框中**阴影**对话框 （在**主页**选项卡，**形状**组中，单击**阴影**，然后单击**阴影选项**）。</span><span class="sxs-lookup"><span data-stu-id="b33fe-122">For a list of predefined simple and oblique shadow types, see the **Style** box in the **Shadow** dialog box (on the **Home** tab, in the **Shape** group, click **Shadow**, and then click **Shadow Options**).</span></span>
  
<span data-ttu-id="b33fe-123">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShapeShdwType 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b33fe-123">To get a reference to the ShapeShdwType cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b33fe-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b33fe-124">Cell name:</span></span>  <br/> |<span data-ttu-id="b33fe-125">ShapeShdwType</span><span class="sxs-lookup"><span data-stu-id="b33fe-125">ShapeShdwType</span></span>  <br/> |
   
<span data-ttu-id="b33fe-126">若要从某个程序按索引获取对 ShapeShdwType 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="b33fe-126">To get a reference to the ShapeShdwType cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b33fe-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b33fe-127">Section index:</span></span>  <br/> |<span data-ttu-id="b33fe-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b33fe-128">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="b33fe-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="b33fe-129">Row index:</span></span>  <br/> |<span data-ttu-id="b33fe-130">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="b33fe-130">**visRowFill**</span></span> <br/> |
|<span data-ttu-id="b33fe-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b33fe-131">Cell index:</span></span>  <br/> |<span data-ttu-id="b33fe-132">**visFillShdwType**</span><span class="sxs-lookup"><span data-stu-id="b33fe-132">**visFillShdwType**</span></span> <br/> |
   

