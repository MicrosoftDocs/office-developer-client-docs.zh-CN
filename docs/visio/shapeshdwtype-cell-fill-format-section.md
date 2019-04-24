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
ms.openlocfilehash: 607881e4a520f1376562394c6e40ab5d2508906d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342859"
---
# <a name="shapeshdwtype-cell-fill-format-section"></a><span data-ttu-id="a1515-103">ShapeShdwType 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="a1515-103">ShapeShdwType Cell (Fill Format Section)</span></span>

<span data-ttu-id="a1515-104">指定形状的阴影类型。</span><span class="sxs-lookup"><span data-stu-id="a1515-104">Specifies the type of shadow for a shape.</span></span> 
  
|<span data-ttu-id="a1515-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="a1515-105">**Value**</span></span>|<span data-ttu-id="a1515-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="a1515-106">**Description**</span></span>|<span data-ttu-id="a1515-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="a1515-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a1515-108">0</span><span class="sxs-lookup"><span data-stu-id="a1515-108">0</span></span>  <br/> |<span data-ttu-id="a1515-109">使用页面默认值（默认值）</span><span class="sxs-lookup"><span data-stu-id="a1515-109">Use page default (the default)</span></span>  <br/> |<span data-ttu-id="a1515-110">**visFSTPageDefault**</span><span class="sxs-lookup"><span data-stu-id="a1515-110">**visFSTPageDefault**</span></span> <br/> |
|<span data-ttu-id="a1515-111">1</span><span class="sxs-lookup"><span data-stu-id="a1515-111">1</span></span>  <br/> |<span data-ttu-id="a1515-112">简单</span><span class="sxs-lookup"><span data-stu-id="a1515-112">Simple</span></span>  <br/> |<span data-ttu-id="a1515-113">**visFSTSimple**</span><span class="sxs-lookup"><span data-stu-id="a1515-113">**visFSTSimple**</span></span> <br/> |
|<span data-ttu-id="a1515-114">双面</span><span class="sxs-lookup"><span data-stu-id="a1515-114">2</span></span>  <br/> |<span data-ttu-id="a1515-115">偏</span><span class="sxs-lookup"><span data-stu-id="a1515-115">Oblique</span></span>  <br/> |<span data-ttu-id="a1515-116">**visFSTOblique**</span><span class="sxs-lookup"><span data-stu-id="a1515-116">**visFSTOblique**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a1515-117">注解</span><span class="sxs-lookup"><span data-stu-id="a1515-117">Remarks</span></span>

<span data-ttu-id="a1515-118">使用此单元格应用与页面默认值不同的形状阴影 (页面默认阴影类型是在 "页面属性" 部分的 "ShdwType" 单元格中定义)。</span><span class="sxs-lookup"><span data-stu-id="a1515-118">Use this cell to apply a shape shadow that is different from the page default (the page default shadow type is defined in the ShdwType cell in the Page Properties Section).</span></span>
  
<span data-ttu-id="a1515-119">简单阴影类型是指用户界面 (UI) 中的偏移阴影。</span><span class="sxs-lookup"><span data-stu-id="a1515-119">Simple shadow types are described as offset shadows in the user interface (UI).</span></span> <span data-ttu-id="a1515-120">简单阴影的效果是将形状的阴影投射到形状背后一段距离的并行面上。</span><span class="sxs-lookup"><span data-stu-id="a1515-120">A simple shadow gives the effect of the shape being shadowed onto a parallel plane located behind the shape.</span></span> <span data-ttu-id="a1515-121">倾斜阴影是指 UI 中的倾斜阴影，其效果是将阴影投射到与形状垂直的面上。</span><span class="sxs-lookup"><span data-stu-id="a1515-121">Oblique shadows are described as oblique shadows in the UI and give the effect of a shadow being cast onto a plane perpendicular to the shape.</span></span> 
  
<span data-ttu-id="a1515-122">有关预定义的简单阴影和倾斜阴影类型的列表，请查看 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的 **“样式”** 框。</span><span class="sxs-lookup"><span data-stu-id="a1515-122">For a list of predefined simple and oblique shadow types, see the **Style** box in the **Shadow** dialog box (on the **Home** tab, in the **Shape** group, click **Shadow**, and then click **Shadow Options**).</span></span>
  
<span data-ttu-id="a1515-123">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeShdwType 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a1515-123">To get a reference to the ShapeShdwType cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a1515-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a1515-124">Cell name:</span></span>  <br/> |<span data-ttu-id="a1515-125">ShapeShdwType</span><span class="sxs-lookup"><span data-stu-id="a1515-125">ShapeShdwType</span></span>  <br/> |
   
<span data-ttu-id="a1515-126">若要从某个程序按索引获取对 ShapeShdwType 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a1515-126">To get a reference to the ShapeShdwType cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a1515-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a1515-127">Section index:</span></span>  <br/> |<span data-ttu-id="a1515-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a1515-128">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="a1515-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="a1515-129">Row index:</span></span>  <br/> |<span data-ttu-id="a1515-130">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="a1515-130">**visRowFill**</span></span> <br/> |
|<span data-ttu-id="a1515-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a1515-131">Cell index:</span></span>  <br/> |<span data-ttu-id="a1515-132">**visFillShdwType**</span><span class="sxs-lookup"><span data-stu-id="a1515-132">**visFillShdwType**</span></span> <br/> |
   

