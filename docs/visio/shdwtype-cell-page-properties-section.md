---
title: ShdwType 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60084
localization_priority: Normal
ms.assetid: 551166d0-3aaa-0fd7-e742-cf3450ba90ed
description: 指示页面的默认阴影类型。
ms.openlocfilehash: f1fc72484d94788ca2798760ca935c89c3e841ad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424096"
---
# <a name="shdwtype-cell-page-properties-section"></a><span data-ttu-id="8ed7e-103">ShdwType 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="8ed7e-103">ShdwType Cell (Page Properties Section)</span></span>

<span data-ttu-id="8ed7e-104">指示页面的默认阴影类型。</span><span class="sxs-lookup"><span data-stu-id="8ed7e-104">Indicates the default shadow type for a page.</span></span>
  
|<span data-ttu-id="8ed7e-105">**值**</span><span class="sxs-lookup"><span data-stu-id="8ed7e-105">**Value**</span></span>|<span data-ttu-id="8ed7e-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="8ed7e-106">**Description**</span></span>|<span data-ttu-id="8ed7e-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="8ed7e-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="8ed7e-108">1</span><span class="sxs-lookup"><span data-stu-id="8ed7e-108">1</span></span>  <br/> | <span data-ttu-id="8ed7e-109">简单</span><span class="sxs-lookup"><span data-stu-id="8ed7e-109">Simple</span></span>  <br/> |<span data-ttu-id="8ed7e-110">**visFSTSimple**</span><span class="sxs-lookup"><span data-stu-id="8ed7e-110">**visFSTSimple**</span></span> <br/> |
| <span data-ttu-id="8ed7e-111">双面</span><span class="sxs-lookup"><span data-stu-id="8ed7e-111">2</span></span>  <br/> | <span data-ttu-id="8ed7e-112">偏</span><span class="sxs-lookup"><span data-stu-id="8ed7e-112">Oblique</span></span>  <br/> |<span data-ttu-id="8ed7e-113">**visFSTOblique**</span><span class="sxs-lookup"><span data-stu-id="8ed7e-113">**visFSTOblique**</span></span> <br/> |
|<span data-ttu-id="8ed7e-114">第三章</span><span class="sxs-lookup"><span data-stu-id="8ed7e-114">3</span></span>  <br/> |<span data-ttu-id="8ed7e-115">Inner</span><span class="sxs-lookup"><span data-stu-id="8ed7e-115">Inner</span></span>  <br/> |<span data-ttu-id="8ed7e-116">**visFSTInner**</span><span class="sxs-lookup"><span data-stu-id="8ed7e-116">**visFSTInner**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8ed7e-117">说明</span><span class="sxs-lookup"><span data-stu-id="8ed7e-117">Remarks</span></span>

 <span data-ttu-id="8ed7e-118">只要 ShapeShdwType 单元格 (页面上的单个形状的阴影类型) 设置为 "页面默认值" (**visFSTPageDefault** ), 此单元格中所述的阴影类型将被使用。</span><span class="sxs-lookup"><span data-stu-id="8ed7e-118">The shadow type described in this cell is used whenever the ShapeShdwType Cell (the shadow type for an individual shape on the page) is set to Page Default (**visFSTPageDefault** ).</span></span> 
  
<span data-ttu-id="8ed7e-119">简单阴影类型是指用户界面 (UI) 中的偏移阴影。</span><span class="sxs-lookup"><span data-stu-id="8ed7e-119">Simple shadow types are described as offset shadows in the user interface (UI).</span></span> <span data-ttu-id="8ed7e-120">简单阴影的效果是将形状的阴影投射到形状背后一段距离的并行面上。</span><span class="sxs-lookup"><span data-stu-id="8ed7e-120">A simple shadow gives the effect of the shape being shadowed onto a parallel plane located some distance behind it.</span></span> <span data-ttu-id="8ed7e-121">倾斜阴影是指 UI 中的倾斜阴影，其效果是将阴影投射到与形状垂直的面上。</span><span class="sxs-lookup"><span data-stu-id="8ed7e-121">Oblique shadows are described as oblique shadows in the UI and give the effect of a shadow being cast onto a plane perpendicular to the shape.</span></span> 
  
<span data-ttu-id="8ed7e-122">有关预定义的简单阴影类型和倾斜阴影类型的列表，请查看 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）的 **“阴影”** 选项卡上的 **“样式”** 列表。</span><span class="sxs-lookup"><span data-stu-id="8ed7e-122">For a list of predefined simple and oblique shadow types, see the **Style** list on the **Shadows** tab of the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow).</span></span> 
  
<span data-ttu-id="8ed7e-123">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwType 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8ed7e-123">To get a reference to the ShdwType cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8ed7e-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8ed7e-124">Cell name:</span></span>  <br/> | <span data-ttu-id="8ed7e-125">ShdwType</span><span class="sxs-lookup"><span data-stu-id="8ed7e-125">ShdwType</span></span>  <br/> |
   
<span data-ttu-id="8ed7e-126">若要从某个程序按索引获取对 ShapeShdwOffsetX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8ed7e-126">To get a reference to the ShapeShdwOffsetX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8ed7e-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8ed7e-127">Section index:</span></span>  <br/> |<span data-ttu-id="8ed7e-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8ed7e-128">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8ed7e-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="8ed7e-129">Row index:</span></span>  <br/> |<span data-ttu-id="8ed7e-130">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="8ed7e-130">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="8ed7e-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8ed7e-131">Cell index:</span></span>  <br/> |<span data-ttu-id="8ed7e-132">**visPageShdwType**</span><span class="sxs-lookup"><span data-stu-id="8ed7e-132">**visPageShdwType**</span></span> <br/> |
   

