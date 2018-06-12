---
title: ConLineJumpDirY 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251654
localization_priority: Normal
ms.assetid: 93f82ae0-3442-fac1-9906-b84afef85f5c
description: 确定出现在形状的垂直动态连接线上的跨线的跨线方向。
ms.openlocfilehash: 2d0c0964b52c9afbccc9cb507024825434702b6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779938"
---
# <a name="conlinejumpdiry-cell-shape-layout-section"></a><span data-ttu-id="365b9-103">ConLineJumpDirY 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="365b9-103">ConLineJumpDirY Cell (Shape Layout Section)</span></span>

<span data-ttu-id="365b9-104">确定出现在形状的垂直动态连接线上的跨线的跨线方向。</span><span class="sxs-lookup"><span data-stu-id="365b9-104">Determines the line jump direction for line jumps occurring on a vertical dynamic connector for a shape.</span></span>
  
|<span data-ttu-id="365b9-105">**值**</span><span class="sxs-lookup"><span data-stu-id="365b9-105">**Value**</span></span>|<span data-ttu-id="365b9-106">**跨线方向**</span><span class="sxs-lookup"><span data-stu-id="365b9-106">**Line Jump Direction**</span></span>|<span data-ttu-id="365b9-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="365b9-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="365b9-108">0</span><span class="sxs-lookup"><span data-stu-id="365b9-108">0</span></span>  <br/> | <span data-ttu-id="365b9-109">页面默认值</span><span class="sxs-lookup"><span data-stu-id="365b9-109">Page default</span></span>  <br/> |<span data-ttu-id="365b9-110">**visLOJumpDirYDefault**</span><span class="sxs-lookup"><span data-stu-id="365b9-110">**visLOJumpDirYDefault**</span></span> <br/> |
| <span data-ttu-id="365b9-111">1</span><span class="sxs-lookup"><span data-stu-id="365b9-111">1</span></span>  <br/> | <span data-ttu-id="365b9-112">左侧</span><span class="sxs-lookup"><span data-stu-id="365b9-112">Left</span></span>  <br/> |<span data-ttu-id="365b9-113">**visLOJumpDirYLeft**</span><span class="sxs-lookup"><span data-stu-id="365b9-113">**visLOJumpDirYLeft**</span></span> <br/> |
| <span data-ttu-id="365b9-114">2</span><span class="sxs-lookup"><span data-stu-id="365b9-114">2</span></span>  <br/> | <span data-ttu-id="365b9-115">右侧</span><span class="sxs-lookup"><span data-stu-id="365b9-115">Right</span></span>  <br/> |<span data-ttu-id="365b9-116">**visLOJumpDirYRight**</span><span class="sxs-lookup"><span data-stu-id="365b9-116">**visLOJumpDirYRight**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="365b9-117">备注</span><span class="sxs-lookup"><span data-stu-id="365b9-117">Remarks</span></span>

<span data-ttu-id="365b9-118">设置默认垂直方向*所有*连接器的跨线的页上，使用 Page Layout 内容中的 PageLineJumpDirY 单元格。</span><span class="sxs-lookup"><span data-stu-id="365b9-118">To set the default vertical direction for  *all*  connector jumps on a page, use the PageLineJumpDirY cell in the Page Layout section.</span></span> 
  
<span data-ttu-id="365b9-119">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ConLineJumpDirY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="365b9-119">To get a reference to the ConLineJumpDirY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="365b9-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="365b9-120">Cell name:</span></span>  <br/> | <span data-ttu-id="365b9-121">ConLineJumpDirY</span><span class="sxs-lookup"><span data-stu-id="365b9-121">ConLineJumpDirY</span></span>  <br/> |
   
<span data-ttu-id="365b9-122">若要从某个程序按索引获取对 ConLineJumpDirY 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="365b9-122">To get a reference to the ConLineJumpDirY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="365b9-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="365b9-123">Section index:</span></span>  <br/> |<span data-ttu-id="365b9-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="365b9-124">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="365b9-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="365b9-125">Row index:</span></span>  <br/> |<span data-ttu-id="365b9-126">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="365b9-126">**visRowShapeLayout**</span></span> <br/> |
| <span data-ttu-id="365b9-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="365b9-127">Cell index:</span></span>  <br/> |<span data-ttu-id="365b9-128">**visSLOJumpDirY**</span><span class="sxs-lookup"><span data-stu-id="365b9-128">**visSLOJumpDirY**</span></span> <br/> |
   

