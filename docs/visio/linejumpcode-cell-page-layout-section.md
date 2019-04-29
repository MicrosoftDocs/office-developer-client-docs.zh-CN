---
title: LineJumpCode 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm540
localization_priority: Normal
ms.assetid: 56f9043d-a632-65df-c710-45867cce1627
description: 确定要向其添加跨线的连接线。
ms.openlocfilehash: 7b5b8c8f1de160a4dc766d30a5f518c5653c270b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416249"
---
# <a name="linejumpcode-cell-page-layout-section"></a><span data-ttu-id="db7b4-103">LineJumpCode 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="db7b4-103">LineJumpCode Cell (Page Layout Section)</span></span>

<span data-ttu-id="db7b4-104">确定要向其添加跨线的连接线。</span><span class="sxs-lookup"><span data-stu-id="db7b4-104">Determines the connectors to which you want to add jumps.</span></span>
  
|<span data-ttu-id="db7b4-105">**值**</span><span class="sxs-lookup"><span data-stu-id="db7b4-105">**Value**</span></span>|<span data-ttu-id="db7b4-106">**要向其添加跨线的连接线**</span><span class="sxs-lookup"><span data-stu-id="db7b4-106">**Connectors to which you want to add jumps**</span></span>|<span data-ttu-id="db7b4-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="db7b4-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="db7b4-108">0</span><span class="sxs-lookup"><span data-stu-id="db7b4-108">0</span></span>  <br/> |<span data-ttu-id="db7b4-109">None</span><span class="sxs-lookup"><span data-stu-id="db7b4-109">None</span></span>  <br/> |<span data-ttu-id="db7b4-110">**visPLOJumpNone**</span><span class="sxs-lookup"><span data-stu-id="db7b4-110">**visPLOJumpNone**</span></span> <br/> |
|<span data-ttu-id="db7b4-111">1</span><span class="sxs-lookup"><span data-stu-id="db7b4-111">1</span></span>  <br/> |<span data-ttu-id="db7b4-112">水平线</span><span class="sxs-lookup"><span data-stu-id="db7b4-112">Horizontal lines</span></span>  <br/> |<span data-ttu-id="db7b4-113">**visPLOJumpHorizontal**</span><span class="sxs-lookup"><span data-stu-id="db7b4-113">**visPLOJumpHorizontal**</span></span> <br/> |
|<span data-ttu-id="db7b4-114">双面</span><span class="sxs-lookup"><span data-stu-id="db7b4-114">2</span></span>  <br/> |<span data-ttu-id="db7b4-115">垂直线</span><span class="sxs-lookup"><span data-stu-id="db7b4-115">Vertical lines</span></span>  <br/> |<span data-ttu-id="db7b4-116">**visPLOJumpVertical**</span><span class="sxs-lookup"><span data-stu-id="db7b4-116">**visPLOJumpVertical**</span></span> <br/> |
|<span data-ttu-id="db7b4-117">第三章</span><span class="sxs-lookup"><span data-stu-id="db7b4-117">3</span></span>  <br/> |<span data-ttu-id="db7b4-118">最后一个放置的线条</span><span class="sxs-lookup"><span data-stu-id="db7b4-118">Last routed line</span></span>  <br/> |<span data-ttu-id="db7b4-119">**visPLOJumpLastRouted**</span><span class="sxs-lookup"><span data-stu-id="db7b4-119">**visPLOJumpLastRouted**</span></span> <br/> |
|<span data-ttu-id="db7b4-120">4</span><span class="sxs-lookup"><span data-stu-id="db7b4-120">4</span></span>  <br/> |<span data-ttu-id="db7b4-121">最后一个显示的线条 ( *z*顺序中的顶部形状)</span><span class="sxs-lookup"><span data-stu-id="db7b4-121">Last displayed line (top shape in the  *z*  -order)</span></span>  <br/> |<span data-ttu-id="db7b4-122">**visPLOJumpDisplayOrder**</span><span class="sxs-lookup"><span data-stu-id="db7b4-122">**visPLOJumpDisplayOrder**</span></span> <br/> |
|<span data-ttu-id="db7b4-123">5</span><span class="sxs-lookup"><span data-stu-id="db7b4-123">5</span></span>  <br/> |<span data-ttu-id="db7b4-124">第一个显示的线条 (按*z*顺序排列的底部的形状)</span><span class="sxs-lookup"><span data-stu-id="db7b4-124">First displayed line (shape at the bottom of the  *z*  -order)</span></span>  <br/> |<span data-ttu-id="db7b4-125">**visPLOJumpReverseDisplayOrder**</span><span class="sxs-lookup"><span data-stu-id="db7b4-125">**visPLOJumpReverseDisplayOrder**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="db7b4-126">说明</span><span class="sxs-lookup"><span data-stu-id="db7b4-126">Remarks</span></span>

<span data-ttu-id="db7b4-127">还可以在 **“页面设置”** 对话框中的 **“布局与排列”** 选项卡（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后单击 **“布局与排列”**）上设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="db7b4-127">You can also set the value of this cell on the **Layout and Routing** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow, and then click **Layout and Routing**).</span></span>
  
<span data-ttu-id="db7b4-128">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineJumpCode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="db7b4-128">To get a reference to the LineJumpCode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="db7b4-129">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="db7b4-129">Cell name:</span></span>  <br/> |<span data-ttu-id="db7b4-130">LineJumpCode</span><span class="sxs-lookup"><span data-stu-id="db7b4-130">LineJumpCode</span></span>  <br/> |
   
<span data-ttu-id="db7b4-131">若要从某个程序按索引获取对 LineJumpCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="db7b4-131">To get a reference to the LineJumpCode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="db7b4-132">内容索引：</span><span class="sxs-lookup"><span data-stu-id="db7b4-132">Section index:</span></span>  <br/> |<span data-ttu-id="db7b4-133">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="db7b4-133">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="db7b4-134">行索引：</span><span class="sxs-lookup"><span data-stu-id="db7b4-134">Row index:</span></span>  <br/> |<span data-ttu-id="db7b4-135">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="db7b4-135">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="db7b4-136">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="db7b4-136">Cell index:</span></span>  <br/> |<span data-ttu-id="db7b4-137">**visPLOJumpCode**</span><span class="sxs-lookup"><span data-stu-id="db7b4-137">**visPLOJumpCode**</span></span> <br/> |
   

