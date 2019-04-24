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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342747"
---
# <a name="conlinejumpdirx-cell-shape-layout-section"></a><span data-ttu-id="8d6ba-103">ConLineJumpDirX 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="8d6ba-103">ConLineJumpDirX Cell (Shape Layout Section)</span></span>

<span data-ttu-id="8d6ba-104">确定出现在形状的水平动态连接线上的跨线的方向。</span><span class="sxs-lookup"><span data-stu-id="8d6ba-104">Determines the line jump direction for line jumps occurring on a horizontal dynamic connector for a shape.</span></span>
  
|<span data-ttu-id="8d6ba-105">**值**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-105">**Value**</span></span>|<span data-ttu-id="8d6ba-106">**跨线方向**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-106">**Line jump direction**</span></span>|<span data-ttu-id="8d6ba-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="8d6ba-108">0</span><span class="sxs-lookup"><span data-stu-id="8d6ba-108">0</span></span>  <br/> | <span data-ttu-id="8d6ba-109">页面默认值</span><span class="sxs-lookup"><span data-stu-id="8d6ba-109">Page default</span></span>  <br/> |<span data-ttu-id="8d6ba-110">**visLOJumpDirXDefault**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-110">**visLOJumpDirXDefault**</span></span> <br/> |
| <span data-ttu-id="8d6ba-111">1</span><span class="sxs-lookup"><span data-stu-id="8d6ba-111">1</span></span>  <br/> | <span data-ttu-id="8d6ba-112">向上</span><span class="sxs-lookup"><span data-stu-id="8d6ba-112">Up</span></span>  <br/> |<span data-ttu-id="8d6ba-113">**visLOJumpDirXUp**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-113">**visLOJumpDirXUp**</span></span> <br/> |
| <span data-ttu-id="8d6ba-114">双面</span><span class="sxs-lookup"><span data-stu-id="8d6ba-114">2</span></span>  <br/> | <span data-ttu-id="8d6ba-115">向下</span><span class="sxs-lookup"><span data-stu-id="8d6ba-115">Down</span></span>  <br/> |<span data-ttu-id="8d6ba-116">**visLOJumpDirXDown**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-116">**visLOJumpDirXDown**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8d6ba-117">注解</span><span class="sxs-lookup"><span data-stu-id="8d6ba-117">Remarks</span></span>

<span data-ttu-id="8d6ba-118">若要设置页面上*所有*连接线跨线的默认水平方向, 请使用 "页面布局" 部分中的 "PageLineJumpDirX" 单元格。</span><span class="sxs-lookup"><span data-stu-id="8d6ba-118">To set the default horizontal direction for  *all*  connector jumps on a page, use the PageLineJumpDirX cell in the Page Layout section.</span></span> 
  
<span data-ttu-id="8d6ba-119">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ConLineJumpDirX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8d6ba-119">To get a reference to the ConLineJumpDirX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8d6ba-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8d6ba-120">Cell name:</span></span>  <br/> | <span data-ttu-id="8d6ba-121">ConLineJumpDirX</span><span class="sxs-lookup"><span data-stu-id="8d6ba-121">ConLineJumpDirX</span></span>  <br/> |
   
<span data-ttu-id="8d6ba-122">要从某个程序按索引获取对 ConLineJumpDirX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8d6ba-122">To get a reference to the ConLineJumpDirX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8d6ba-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8d6ba-123">Section index:</span></span>  <br/> |<span data-ttu-id="8d6ba-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-124">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8d6ba-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="8d6ba-125">Row index:</span></span>  <br/> |<span data-ttu-id="8d6ba-126">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-126">**visRowShapeLayout**</span></span> <br/> |
| <span data-ttu-id="8d6ba-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8d6ba-127">Cell index:</span></span>  <br/> |<span data-ttu-id="8d6ba-128">**visSLOJumpDirX**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-128">**visSLOJumpDirX**</span></span> <br/> |
   

