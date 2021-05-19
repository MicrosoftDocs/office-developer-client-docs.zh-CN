---
title: ConLineJumpDirX 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm185
localization_priority: Normal
ms.assetid: f0671835-8d48-907a-eca6-43953658f800
description: 确定出现在形状的水平动态连接线上的跨线的方向。
ms.openlocfilehash: 22b9366b750a85a76498b83880aac2b9b974e1ac
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415038"
---
# <a name="conlinejumpdirx-cell-shape-layout-section"></a><span data-ttu-id="68940-103">ConLineJumpDirX 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="68940-103">ConLineJumpDirX Cell (Shape Layout Section)</span></span>

<span data-ttu-id="68940-104">确定出现在形状的水平动态连接线上的跨线的方向。</span><span class="sxs-lookup"><span data-stu-id="68940-104">Determines the line jump direction for line jumps occurring on a horizontal dynamic connector for a shape.</span></span>
  
|<span data-ttu-id="68940-105">**值**</span><span class="sxs-lookup"><span data-stu-id="68940-105">**Value**</span></span>|<span data-ttu-id="68940-106">**跨线方向**</span><span class="sxs-lookup"><span data-stu-id="68940-106">**Line jump direction**</span></span>|<span data-ttu-id="68940-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="68940-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="68940-108">0</span><span class="sxs-lookup"><span data-stu-id="68940-108">0</span></span>  <br/> | <span data-ttu-id="68940-109">页面默认值</span><span class="sxs-lookup"><span data-stu-id="68940-109">Page default</span></span>  <br/> |<span data-ttu-id="68940-110">**visLOJumpDirXDefault**</span><span class="sxs-lookup"><span data-stu-id="68940-110">**visLOJumpDirXDefault**</span></span> <br/> |
| <span data-ttu-id="68940-111">1</span><span class="sxs-lookup"><span data-stu-id="68940-111">1</span></span>  <br/> | <span data-ttu-id="68940-112">向上</span><span class="sxs-lookup"><span data-stu-id="68940-112">Up</span></span>  <br/> |<span data-ttu-id="68940-113">**visLOJumpDirXUp**</span><span class="sxs-lookup"><span data-stu-id="68940-113">**visLOJumpDirXUp**</span></span> <br/> |
| <span data-ttu-id="68940-114">2</span><span class="sxs-lookup"><span data-stu-id="68940-114">2</span></span>  <br/> | <span data-ttu-id="68940-115">向下</span><span class="sxs-lookup"><span data-stu-id="68940-115">Down</span></span>  <br/> |<span data-ttu-id="68940-116">**visLOJumpDirXDown**</span><span class="sxs-lookup"><span data-stu-id="68940-116">**visLOJumpDirXDown**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="68940-117">备注</span><span class="sxs-lookup"><span data-stu-id="68940-117">Remarks</span></span>

<span data-ttu-id="68940-118">若要设置页面上所有连接线跨线的默认水平方向，请使用"页面布局"部分中的 PageLineJumpDirX 单元格。</span><span class="sxs-lookup"><span data-stu-id="68940-118">To set the default horizontal direction for  *all*  connector jumps on a page, use the PageLineJumpDirX cell in the Page Layout section.</span></span> 
  
<span data-ttu-id="68940-119">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ConLineJumpDirX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="68940-119">To get a reference to the ConLineJumpDirX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="68940-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="68940-120">Cell name:</span></span>  <br/> | <span data-ttu-id="68940-121">ConLineJumpDirX</span><span class="sxs-lookup"><span data-stu-id="68940-121">ConLineJumpDirX</span></span>  <br/> |
   
<span data-ttu-id="68940-122">要从某个程序按索引获取对 ConLineJumpDirX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="68940-122">To get a reference to the ConLineJumpDirX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="68940-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="68940-123">Section index:</span></span>  <br/> |<span data-ttu-id="68940-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="68940-124">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="68940-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="68940-125">Row index:</span></span>  <br/> |<span data-ttu-id="68940-126">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="68940-126">**visRowShapeLayout**</span></span> <br/> |
| <span data-ttu-id="68940-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="68940-127">Cell index:</span></span>  <br/> |<span data-ttu-id="68940-128">**visSLOJumpDirX**</span><span class="sxs-lookup"><span data-stu-id="68940-128">**visSLOJumpDirX**</span></span> <br/> |
   

