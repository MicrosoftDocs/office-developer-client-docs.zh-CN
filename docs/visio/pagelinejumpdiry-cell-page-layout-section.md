---
title: PageLineJumpDirY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm770
localization_priority: Normal
ms.assetid: f73cc157-b332-279b-f7cf-d5a090bc09a4
description: 确定在尚未应用本地跨线方向的绘图页内垂直动态连接线上的跨线方向。
ms.openlocfilehash: 21ad1d95fd83780f31778dbc8bb70f9bdb4b922d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414674"
---
# <a name="pagelinejumpdiry-cell-page-layout-section"></a><span data-ttu-id="7999a-103">PageLineJumpDirY 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="7999a-103">PageLineJumpDirY Cell (Page Layout Section)</span></span>

<span data-ttu-id="7999a-104">确定在尚未应用本地跨线方向的绘图页内垂直动态连接线上的跨线方向。</span><span class="sxs-lookup"><span data-stu-id="7999a-104">Determines the direction of line jumps on vertical dynamic connectors on the drawing page for which you haven't applied a local jump direction.</span></span>
  
|<span data-ttu-id="7999a-105">**值**</span><span class="sxs-lookup"><span data-stu-id="7999a-105">**Value**</span></span>|<span data-ttu-id="7999a-106">**跨线方向**</span><span class="sxs-lookup"><span data-stu-id="7999a-106">**Line jump direction**</span></span>|<span data-ttu-id="7999a-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="7999a-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="7999a-108">0</span><span class="sxs-lookup"><span data-stu-id="7999a-108">0</span></span>  <br/> | <span data-ttu-id="7999a-109">默认值；向上或形状的页面设置</span><span class="sxs-lookup"><span data-stu-id="7999a-109">Default; up or the page's setting for shapes</span></span>  <br/> |<span data-ttu-id="7999a-110">**visLOJumpDirYDefault**</span><span class="sxs-lookup"><span data-stu-id="7999a-110">**visLOJumpDirYDefault**</span></span> <br/> |
| <span data-ttu-id="7999a-111">1</span><span class="sxs-lookup"><span data-stu-id="7999a-111">1</span></span>  <br/> | <span data-ttu-id="7999a-112">左侧</span><span class="sxs-lookup"><span data-stu-id="7999a-112">Left</span></span>  <br/> |<span data-ttu-id="7999a-113">**visLOJumpDirYLeft**</span><span class="sxs-lookup"><span data-stu-id="7999a-113">**visLOJumpDirYLeft**</span></span> <br/> |
| <span data-ttu-id="7999a-114">2</span><span class="sxs-lookup"><span data-stu-id="7999a-114">2</span></span>  <br/> | <span data-ttu-id="7999a-115">右侧</span><span class="sxs-lookup"><span data-stu-id="7999a-115">Right</span></span>  <br/> |<span data-ttu-id="7999a-116">**visLOJumpDirYRight**</span><span class="sxs-lookup"><span data-stu-id="7999a-116">**visLOJumpDirYRight**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7999a-117">备注</span><span class="sxs-lookup"><span data-stu-id="7999a-117">Remarks</span></span>

<span data-ttu-id="7999a-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageLineJumpDirY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7999a-118">To get a reference to the PageLineJumpDirY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7999a-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7999a-119">Cell name:</span></span>  <br/> | <span data-ttu-id="7999a-120">PageLineJumpDirY</span><span class="sxs-lookup"><span data-stu-id="7999a-120">PageLineJumpDirY</span></span>  <br/> |
   
<span data-ttu-id="7999a-121">要从某个程序按索引获取对 PageLineJumpDirY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7999a-121">To get a reference to the PageLineJumpDirY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7999a-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7999a-122">Section index:</span></span>  <br/> |<span data-ttu-id="7999a-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7999a-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7999a-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="7999a-124">Row index:</span></span>  <br/> |<span data-ttu-id="7999a-125">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="7999a-125">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="7999a-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7999a-126">Cell index:</span></span>  <br/> |<span data-ttu-id="7999a-127">**visPLOJumpDirY**</span><span class="sxs-lookup"><span data-stu-id="7999a-127">**visPLOJumpDirY**</span></span> <br/> |
   

