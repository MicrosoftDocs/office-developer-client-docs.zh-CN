---
title: LineRouteExt 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50115
localization_priority: Normal
ms.assetid: 3d16b8b3-601b-c10b-68a8-ffd47251306f
description: 确定绘图页上所有连接线的默认外观。
ms.openlocfilehash: 6daed2e06f7673e5a4ec97ec83dc31bad2766301
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410621"
---
# <a name="linerouteext-cell-page-layout-section"></a><span data-ttu-id="2533a-103">LineRouteExt 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="2533a-103">LineRouteExt Cell (Page Layout Section)</span></span>

<span data-ttu-id="2533a-104">确定绘图页上所有连接线的默认外观。</span><span class="sxs-lookup"><span data-stu-id="2533a-104">Determines the default appearance for all connectors on a drawing page.</span></span>
  
|<span data-ttu-id="2533a-105">**值**</span><span class="sxs-lookup"><span data-stu-id="2533a-105">**Value**</span></span>|<span data-ttu-id="2533a-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="2533a-106">**Description**</span></span>|<span data-ttu-id="2533a-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="2533a-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="2533a-108">0</span><span class="sxs-lookup"><span data-stu-id="2533a-108">0</span></span>  <br/> | <span data-ttu-id="2533a-109">默认值（直线）</span><span class="sxs-lookup"><span data-stu-id="2533a-109">Default (straight)</span></span>  <br/> |<span data-ttu-id="2533a-110">**visLORouteExtDefault**</span><span class="sxs-lookup"><span data-stu-id="2533a-110">**visLORouteExtDefault**</span></span> <br/> |
| <span data-ttu-id="2533a-111">1</span><span class="sxs-lookup"><span data-stu-id="2533a-111">1</span></span>  <br/> | <span data-ttu-id="2533a-112">直</span><span class="sxs-lookup"><span data-stu-id="2533a-112">Straight</span></span>  <br/> |<span data-ttu-id="2533a-113">**visLORouteExtStraight**</span><span class="sxs-lookup"><span data-stu-id="2533a-113">**visLORouteExtStraight**</span></span> <br/> |
| <span data-ttu-id="2533a-114">2</span><span class="sxs-lookup"><span data-stu-id="2533a-114">2</span></span>  <br/> | <span data-ttu-id="2533a-115">Curved</span><span class="sxs-lookup"><span data-stu-id="2533a-115">Curved</span></span>  <br/> |<span data-ttu-id="2533a-116">**visLORouteExtNURBS**</span><span class="sxs-lookup"><span data-stu-id="2533a-116">**visLORouteExtNURBS**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2533a-117">备注</span><span class="sxs-lookup"><span data-stu-id="2533a-117">Remarks</span></span>

<span data-ttu-id="2533a-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LineRouteExt 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2533a-118">To get a reference to the LineRouteExt cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2533a-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2533a-119">Cell name:</span></span>  <br/> | <span data-ttu-id="2533a-120">LineRouteExt</span><span class="sxs-lookup"><span data-stu-id="2533a-120">LineRouteExt</span></span>  <br/> |
   
<span data-ttu-id="2533a-121">要从某个程序按索引获取对 LineRouteExt 单元格的引用，请使用带下列参数的  **CellsSRC**  属性：</span><span class="sxs-lookup"><span data-stu-id="2533a-121">To get a reference to the LineRouteExt cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2533a-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2533a-122">Section index:</span></span>  <br/> |<span data-ttu-id="2533a-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2533a-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="2533a-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="2533a-124">Row index:</span></span>  <br/> |<span data-ttu-id="2533a-125">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="2533a-125">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="2533a-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2533a-126">Cell index:</span></span>  <br/> |<span data-ttu-id="2533a-127">**visPLOLineRouteExt**</span><span class="sxs-lookup"><span data-stu-id="2533a-127">**visPLOLineRouteExt**</span></span> <br/> |
   

