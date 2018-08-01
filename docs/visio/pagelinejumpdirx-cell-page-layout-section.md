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
ms.openlocfilehash: d414313e98107790f9236c0afabdc5747c6a2a10
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780830"
---
# <a name="pagelinejumpdirx-cell-page-layout-section"></a><span data-ttu-id="3626c-103">PageLineJumpDirX 单元格（“Page Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="3626c-103">PageLineJumpDirX Cell (Page Layout Section)</span></span>

<span data-ttu-id="3626c-104">确定在尚未应用本地跨线方向的绘图页内水平动态连接线上的跨线方向。</span><span class="sxs-lookup"><span data-stu-id="3626c-104">Determines the direction of line jumps on horizontal dynamic connectors on the drawing page for which you haven't applied a local jump direction.</span></span>
  
|<span data-ttu-id="3626c-105">**值**</span><span class="sxs-lookup"><span data-stu-id="3626c-105">**Value**</span></span>|<span data-ttu-id="3626c-106">**跨线方向**</span><span class="sxs-lookup"><span data-stu-id="3626c-106">**Line jump direction**</span></span>|<span data-ttu-id="3626c-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="3626c-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="3626c-108">0</span><span class="sxs-lookup"><span data-stu-id="3626c-108">0</span></span>  <br/> | <span data-ttu-id="3626c-109">默认值；向左或形状的页面设置</span><span class="sxs-lookup"><span data-stu-id="3626c-109">Default; left or the page's setting for shapes</span></span>  <br/> |<span data-ttu-id="3626c-110">**visLOJumpDirXDefault**</span><span class="sxs-lookup"><span data-stu-id="3626c-110">**visLOJumpDirXDefault**</span></span> <br/> |
| <span data-ttu-id="3626c-111">1</span><span class="sxs-lookup"><span data-stu-id="3626c-111">1</span></span>  <br/> | <span data-ttu-id="3626c-112">向上</span><span class="sxs-lookup"><span data-stu-id="3626c-112">Up</span></span>  <br/> |<span data-ttu-id="3626c-113">**visLOJumpDirXUp**</span><span class="sxs-lookup"><span data-stu-id="3626c-113">**visLOJumpDirXUp**</span></span> <br/> |
| <span data-ttu-id="3626c-114">2</span><span class="sxs-lookup"><span data-stu-id="3626c-114">2</span></span>  <br/> | <span data-ttu-id="3626c-115">向下</span><span class="sxs-lookup"><span data-stu-id="3626c-115">Down</span></span>  <br/> |<span data-ttu-id="3626c-116">**visLOJumpDirXDown**</span><span class="sxs-lookup"><span data-stu-id="3626c-116">**visLOJumpDirXDown**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3626c-117">说明</span><span class="sxs-lookup"><span data-stu-id="3626c-117">Remarks</span></span>

<span data-ttu-id="3626c-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageLineJumpDirX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3626c-118">To get a reference to the PageLineJumpDirX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3626c-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3626c-119">Cell name:</span></span>  <br/> | <span data-ttu-id="3626c-120">PageLineJumpDirX</span><span class="sxs-lookup"><span data-stu-id="3626c-120">PageLineJumpDirX</span></span>  <br/> |
   
<span data-ttu-id="3626c-121">要从某个程序按索引获取对 PageLineJumpDirX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="3626c-121">To get a reference to the PageLineJumpDirX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3626c-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3626c-122">Section index:</span></span>  <br/> |<span data-ttu-id="3626c-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="3626c-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="3626c-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="3626c-124">Row index:</span></span>  <br/> |<span data-ttu-id="3626c-125">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="3626c-125">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="3626c-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3626c-126">Cell index:</span></span>  <br/> |<span data-ttu-id="3626c-127">**visPLOJumpDirX**</span><span class="sxs-lookup"><span data-stu-id="3626c-127">**visPLOJumpDirX**</span></span> <br/> |
   

