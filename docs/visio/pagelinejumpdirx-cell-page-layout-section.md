---
title: PageLineJumpDirX 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251656
localization_priority: Normal
ms.assetid: 77892ec7-4c6a-78a5-5af4-5b6be7709e77
description: 确定在尚未应用本地跨线方向的绘图页内水平动态连接线上的跨线方向。
ms.openlocfilehash: 4e1213990877e1260cc8cecd5a55beda4592a844
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431006"
---
# <a name="pagelinejumpdirx-cell-page-layout-section"></a><span data-ttu-id="55346-103">PageLineJumpDirX 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="55346-103">PageLineJumpDirX Cell (Page Layout Section)</span></span>

<span data-ttu-id="55346-104">确定在尚未应用本地跨线方向的绘图页内水平动态连接线上的跨线方向。</span><span class="sxs-lookup"><span data-stu-id="55346-104">Determines the direction of line jumps on horizontal dynamic connectors on the drawing page for which you haven't applied a local jump direction.</span></span>
  
|<span data-ttu-id="55346-105">**值**</span><span class="sxs-lookup"><span data-stu-id="55346-105">**Value**</span></span>|<span data-ttu-id="55346-106">**跨线方向**</span><span class="sxs-lookup"><span data-stu-id="55346-106">**Line jump direction**</span></span>|<span data-ttu-id="55346-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="55346-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="55346-108">0</span><span class="sxs-lookup"><span data-stu-id="55346-108">0</span></span>  <br/> | <span data-ttu-id="55346-109">默认值；向左或形状的页面设置</span><span class="sxs-lookup"><span data-stu-id="55346-109">Default; left or the page's setting for shapes</span></span>  <br/> |<span data-ttu-id="55346-110">**visLOJumpDirXDefault**</span><span class="sxs-lookup"><span data-stu-id="55346-110">**visLOJumpDirXDefault**</span></span> <br/> |
| <span data-ttu-id="55346-111">1</span><span class="sxs-lookup"><span data-stu-id="55346-111">1</span></span>  <br/> | <span data-ttu-id="55346-112">向上</span><span class="sxs-lookup"><span data-stu-id="55346-112">Up</span></span>  <br/> |<span data-ttu-id="55346-113">**visLOJumpDirXUp**</span><span class="sxs-lookup"><span data-stu-id="55346-113">**visLOJumpDirXUp**</span></span> <br/> |
| <span data-ttu-id="55346-114">2</span><span class="sxs-lookup"><span data-stu-id="55346-114">2</span></span>  <br/> | <span data-ttu-id="55346-115">向下</span><span class="sxs-lookup"><span data-stu-id="55346-115">Down</span></span>  <br/> |<span data-ttu-id="55346-116">**visLOJumpDirXDown**</span><span class="sxs-lookup"><span data-stu-id="55346-116">**visLOJumpDirXDown**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="55346-117">备注</span><span class="sxs-lookup"><span data-stu-id="55346-117">Remarks</span></span>

<span data-ttu-id="55346-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageLineJumpDirX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="55346-118">To get a reference to the PageLineJumpDirX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="55346-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="55346-119">Cell name:</span></span>  <br/> | <span data-ttu-id="55346-120">PageLineJumpDirX</span><span class="sxs-lookup"><span data-stu-id="55346-120">PageLineJumpDirX</span></span>  <br/> |
   
<span data-ttu-id="55346-121">要从某个程序按索引获取对 PageLineJumpDirX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="55346-121">To get a reference to the PageLineJumpDirX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="55346-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="55346-122">Section index:</span></span>  <br/> |<span data-ttu-id="55346-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="55346-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="55346-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="55346-124">Row index:</span></span>  <br/> |<span data-ttu-id="55346-125">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="55346-125">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="55346-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="55346-126">Cell index:</span></span>  <br/> |<span data-ttu-id="55346-127">**visPLOJumpDirX**</span><span class="sxs-lookup"><span data-stu-id="55346-127">**visPLOJumpDirX**</span></span> <br/> |
   

