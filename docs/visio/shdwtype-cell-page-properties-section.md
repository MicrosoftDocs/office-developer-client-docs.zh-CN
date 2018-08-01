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
ms.openlocfilehash: 1fc5c31a723d5d409110d94ff543a45dadabf264
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781336"
---
# <a name="shdwtype-cell-page-properties-section"></a><span data-ttu-id="4c573-103">ShdwType 单元格（“Page Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="4c573-103">ShdwType Cell (Page Properties Section)</span></span>

<span data-ttu-id="4c573-104">指示页面的默认阴影类型。</span><span class="sxs-lookup"><span data-stu-id="4c573-104">Indicates the default shadow type for a page.</span></span>
  
|<span data-ttu-id="4c573-105">**值**</span><span class="sxs-lookup"><span data-stu-id="4c573-105">**Value**</span></span>|<span data-ttu-id="4c573-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="4c573-106">**Description**</span></span>|<span data-ttu-id="4c573-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="4c573-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="4c573-108">1</span><span class="sxs-lookup"><span data-stu-id="4c573-108">1</span></span>  <br/> | <span data-ttu-id="4c573-109">简单</span><span class="sxs-lookup"><span data-stu-id="4c573-109">Simple</span></span>  <br/> |<span data-ttu-id="4c573-110">**visFSTSimple**</span><span class="sxs-lookup"><span data-stu-id="4c573-110">**visFSTSimple**</span></span> <br/> |
| <span data-ttu-id="4c573-111">2</span><span class="sxs-lookup"><span data-stu-id="4c573-111">2</span></span>  <br/> | <span data-ttu-id="4c573-112">倾斜</span><span class="sxs-lookup"><span data-stu-id="4c573-112">Oblique</span></span>  <br/> |<span data-ttu-id="4c573-113">**visFSTOblique**</span><span class="sxs-lookup"><span data-stu-id="4c573-113">**visFSTOblique**</span></span> <br/> |
|<span data-ttu-id="4c573-114">3</span><span class="sxs-lookup"><span data-stu-id="4c573-114">3</span></span>  <br/> |<span data-ttu-id="4c573-115">内部</span><span class="sxs-lookup"><span data-stu-id="4c573-115">Inner</span></span>  <br/> |<span data-ttu-id="4c573-116">**visFSTInner**</span><span class="sxs-lookup"><span data-stu-id="4c573-116">**visFSTInner**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4c573-117">说明</span><span class="sxs-lookup"><span data-stu-id="4c573-117">Remarks</span></span>

 <span data-ttu-id="4c573-118">ShapeShdwType 单元格 （页上的单个形状的阴影类型） 设置为页面默认值 (**visFSTPageDefault** ) 时使用此单元格中描述的阴影类型。</span><span class="sxs-lookup"><span data-stu-id="4c573-118">The shadow type described in this cell is used whenever the ShapeShdwType Cell (the shadow type for an individual shape on the page) is set to Page Default (**visFSTPageDefault** ).</span></span> 
  
<span data-ttu-id="4c573-119">用户界面 (UI) 中的偏移阴影介绍简单阴影类型。</span><span class="sxs-lookup"><span data-stu-id="4c573-119">Simple shadow types are described as offset shadows in the user interface (UI).</span></span> <span data-ttu-id="4c573-120">简单阴影效果的形状的阴影投射到位于其背后一些距离并行平面。</span><span class="sxs-lookup"><span data-stu-id="4c573-120">A simple shadow gives the effect of the shape being shadowed onto a parallel plane located some distance behind it.</span></span> <span data-ttu-id="4c573-121">倾斜阴影倾斜阴影在 UI 中所述，并为被强制转换到平面上垂直到形状的阴影效果。</span><span class="sxs-lookup"><span data-stu-id="4c573-121">Oblique shadows are described as oblique shadows in the UI and give the effect of a shadow being cast onto a plane perpendicular to the shape.</span></span> 
  
<span data-ttu-id="4c573-122">有关预定义的简单阴影类型和倾斜阴影类型的列表，请查看 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）的 **“阴影”** 选项卡上的 **“样式”** 列表。</span><span class="sxs-lookup"><span data-stu-id="4c573-122">For a list of predefined simple and oblique shadow types, see the **Style** list on the **Shadows** tab of the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow).</span></span> 
  
<span data-ttu-id="4c573-123">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwType 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4c573-123">To get a reference to the ShdwType cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4c573-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4c573-124">Cell name:</span></span>  <br/> | <span data-ttu-id="4c573-125">ShdwType</span><span class="sxs-lookup"><span data-stu-id="4c573-125">ShdwType</span></span>  <br/> |
   
<span data-ttu-id="4c573-126">若要从某个程序按索引获取对 ShapeShdwOffsetX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4c573-126">To get a reference to the ShapeShdwOffsetX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4c573-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4c573-127">Section index:</span></span>  <br/> |<span data-ttu-id="4c573-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4c573-128">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="4c573-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="4c573-129">Row index:</span></span>  <br/> |<span data-ttu-id="4c573-130">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="4c573-130">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="4c573-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4c573-131">Cell index:</span></span>  <br/> |<span data-ttu-id="4c573-132">**visPageShdwType**</span><span class="sxs-lookup"><span data-stu-id="4c573-132">**visPageShdwType**</span></span> <br/> |
   

