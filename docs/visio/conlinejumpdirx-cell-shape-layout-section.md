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
ms.openlocfilehash: 396830d0da22c15f036f95808b3a94c33e9dc5bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779950"
---
# <a name="conlinejumpdirx-cell-shape-layout-section"></a><span data-ttu-id="d6085-103">ConLineJumpDirX 单元格（“Shape Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="d6085-103">ConLineJumpDirX Cell (Shape Layout Section)</span></span>

<span data-ttu-id="d6085-104">确定出现在形状的水平动态连接线上的跨线的方向。</span><span class="sxs-lookup"><span data-stu-id="d6085-104">Determines the line jump direction for line jumps occurring on a horizontal dynamic connector for a shape.</span></span>
  
|<span data-ttu-id="d6085-105">**值**</span><span class="sxs-lookup"><span data-stu-id="d6085-105">**Value**</span></span>|<span data-ttu-id="d6085-106">**跨线方向**</span><span class="sxs-lookup"><span data-stu-id="d6085-106">**Line jump direction**</span></span>|<span data-ttu-id="d6085-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="d6085-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="d6085-108">0</span><span class="sxs-lookup"><span data-stu-id="d6085-108">0</span></span>  <br/> | <span data-ttu-id="d6085-109">页面默认值</span><span class="sxs-lookup"><span data-stu-id="d6085-109">Page default</span></span>  <br/> |<span data-ttu-id="d6085-110">**visLOJumpDirXDefault**</span><span class="sxs-lookup"><span data-stu-id="d6085-110">**visLOJumpDirXDefault**</span></span> <br/> |
| <span data-ttu-id="d6085-111">1</span><span class="sxs-lookup"><span data-stu-id="d6085-111">1</span></span>  <br/> | <span data-ttu-id="d6085-112">向上</span><span class="sxs-lookup"><span data-stu-id="d6085-112">Up</span></span>  <br/> |<span data-ttu-id="d6085-113">**visLOJumpDirXUp**</span><span class="sxs-lookup"><span data-stu-id="d6085-113">**visLOJumpDirXUp**</span></span> <br/> |
| <span data-ttu-id="d6085-114">2</span><span class="sxs-lookup"><span data-stu-id="d6085-114">2</span></span>  <br/> | <span data-ttu-id="d6085-115">向下</span><span class="sxs-lookup"><span data-stu-id="d6085-115">Down</span></span>  <br/> |<span data-ttu-id="d6085-116">**visLOJumpDirXDown**</span><span class="sxs-lookup"><span data-stu-id="d6085-116">**visLOJumpDirXDown**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d6085-117">说明</span><span class="sxs-lookup"><span data-stu-id="d6085-117">Remarks</span></span>

<span data-ttu-id="d6085-118">设置默认水平方向*所有*连接器的跨线的页上，使用 Page Layout 内容中的 PageLineJumpDirX 单元格。</span><span class="sxs-lookup"><span data-stu-id="d6085-118">To set the default horizontal direction for  *all*  connector jumps on a page, use the PageLineJumpDirX cell in the Page Layout section.</span></span> 
  
<span data-ttu-id="d6085-119">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ConLineJumpDirX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d6085-119">To get a reference to the ConLineJumpDirX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d6085-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d6085-120">Cell name:</span></span>  <br/> | <span data-ttu-id="d6085-121">ConLineJumpDirX</span><span class="sxs-lookup"><span data-stu-id="d6085-121">ConLineJumpDirX</span></span>  <br/> |
   
<span data-ttu-id="d6085-122">要从某个程序按索引获取对 ConLineJumpDirX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d6085-122">To get a reference to the ConLineJumpDirX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d6085-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d6085-123">Section index:</span></span>  <br/> |<span data-ttu-id="d6085-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d6085-124">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="d6085-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="d6085-125">Row index:</span></span>  <br/> |<span data-ttu-id="d6085-126">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="d6085-126">**visRowShapeLayout**</span></span> <br/> |
| <span data-ttu-id="d6085-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d6085-127">Cell index:</span></span>  <br/> |<span data-ttu-id="d6085-128">**visSLOJumpDirX**</span><span class="sxs-lookup"><span data-stu-id="d6085-128">**visSLOJumpDirX**</span></span> <br/> |
   

