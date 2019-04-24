---
title: ConLineRouteExt 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50110
localization_priority: Normal
ms.assetid: cafd7589-1c94-b9bc-b1a6-40f7c15fba71
description: 确定连接线的外观。
ms.openlocfilehash: 19fe948daf7aa3d67db858849ecb2b15f40ba02d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327102"
---
# <a name="conlinerouteext-cell-shape-layout-section"></a><span data-ttu-id="9d562-103">ConLineRouteExt 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="9d562-103">ConLineRouteExt Cell (Shape Layout Section)</span></span>

<span data-ttu-id="9d562-104">确定连接线的外观。</span><span class="sxs-lookup"><span data-stu-id="9d562-104">Determines the appearance of a connector.</span></span>
  
|<span data-ttu-id="9d562-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="9d562-105">**Value**</span></span>|<span data-ttu-id="9d562-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="9d562-106">**Description**</span></span>|<span data-ttu-id="9d562-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="9d562-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="9d562-108">0</span><span class="sxs-lookup"><span data-stu-id="9d562-108">0</span></span>  <br/> | <span data-ttu-id="9d562-109">默认值；使用页面设置</span><span class="sxs-lookup"><span data-stu-id="9d562-109">Default; use page setting</span></span>  <br/> |<span data-ttu-id="9d562-110">**visLORouteExtDefault**</span><span class="sxs-lookup"><span data-stu-id="9d562-110">**visLORouteExtDefault**</span></span> <br/> |
| <span data-ttu-id="9d562-111">1</span><span class="sxs-lookup"><span data-stu-id="9d562-111">1</span></span>  <br/> | <span data-ttu-id="9d562-112">式</span><span class="sxs-lookup"><span data-stu-id="9d562-112">Straight</span></span>  <br/> |<span data-ttu-id="9d562-113">**visLORouteExtStraight**</span><span class="sxs-lookup"><span data-stu-id="9d562-113">**visLORouteExtStraight**</span></span> <br/> |
| <span data-ttu-id="9d562-114">双面</span><span class="sxs-lookup"><span data-stu-id="9d562-114">2</span></span>  <br/> | <span data-ttu-id="9d562-115">带</span><span class="sxs-lookup"><span data-stu-id="9d562-115">Curved</span></span>  <br/> |<span data-ttu-id="9d562-116">**visLORouteExtNURBS**</span><span class="sxs-lookup"><span data-stu-id="9d562-116">**visLORouteExtNURBS**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9d562-117">注解</span><span class="sxs-lookup"><span data-stu-id="9d562-117">Remarks</span></span>

<span data-ttu-id="9d562-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ConLineRouteExt 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9d562-118">To get a reference to the ConLineRouteExt cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9d562-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9d562-119">Cell name:</span></span>  <br/> | <span data-ttu-id="9d562-120">ConLineRouteExt</span><span class="sxs-lookup"><span data-stu-id="9d562-120">ConLineRouteExt</span></span>  <br/> |
   
<span data-ttu-id="9d562-121">要从某个程序按索引获取对 ConLineRouteExt 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9d562-121">To get a reference to the ConLineRouteExt cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9d562-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9d562-122">Section index:</span></span>  <br/> |<span data-ttu-id="9d562-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9d562-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="9d562-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="9d562-124">Row index:</span></span>  <br/> |<span data-ttu-id="9d562-125">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="9d562-125">**visRowShapeLayout**</span></span> <br/> |
| <span data-ttu-id="9d562-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9d562-126">Cell index:</span></span>  <br/> |<span data-ttu-id="9d562-127">**visSLOLineRouteExt**</span><span class="sxs-lookup"><span data-stu-id="9d562-127">**visSLOLineRouteExt**</span></span> <br/> |
   

