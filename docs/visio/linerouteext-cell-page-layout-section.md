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
ms.openlocfilehash: 21da283f2d9ab43837b8fe4127840e89ea9d9949
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780593"
---
# <a name="linerouteext-cell-page-layout-section"></a><span data-ttu-id="34a99-103">LineRouteExt 单元格（“Page Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="34a99-103">LineRouteExt Cell (Page Layout Section)</span></span>

<span data-ttu-id="34a99-104">确定绘图页上所有连接线的默认外观。</span><span class="sxs-lookup"><span data-stu-id="34a99-104">Determines the default appearance for all connectors on a drawing page.</span></span>
  
|<span data-ttu-id="34a99-105">**值**</span><span class="sxs-lookup"><span data-stu-id="34a99-105">**Value**</span></span>|<span data-ttu-id="34a99-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="34a99-106">**Description**</span></span>|<span data-ttu-id="34a99-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="34a99-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="34a99-108">0</span><span class="sxs-lookup"><span data-stu-id="34a99-108">0</span></span>  <br/> | <span data-ttu-id="34a99-109">默认值（直线）</span><span class="sxs-lookup"><span data-stu-id="34a99-109">Default (straight)</span></span>  <br/> |<span data-ttu-id="34a99-110">**visLORouteExtDefault**</span><span class="sxs-lookup"><span data-stu-id="34a99-110">**visLORouteExtDefault**</span></span> <br/> |
| <span data-ttu-id="34a99-111">1</span><span class="sxs-lookup"><span data-stu-id="34a99-111">1</span></span>  <br/> | <span data-ttu-id="34a99-112">直线</span><span class="sxs-lookup"><span data-stu-id="34a99-112">Straight</span></span>  <br/> |<span data-ttu-id="34a99-113">**visLORouteExtStraight**</span><span class="sxs-lookup"><span data-stu-id="34a99-113">**visLORouteExtStraight**</span></span> <br/> |
| <span data-ttu-id="34a99-114">2</span><span class="sxs-lookup"><span data-stu-id="34a99-114">2</span></span>  <br/> | <span data-ttu-id="34a99-115">曲线</span><span class="sxs-lookup"><span data-stu-id="34a99-115">Curved</span></span>  <br/> |<span data-ttu-id="34a99-116">**visLORouteExtNURBS**</span><span class="sxs-lookup"><span data-stu-id="34a99-116">**visLORouteExtNURBS**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="34a99-117">说明</span><span class="sxs-lookup"><span data-stu-id="34a99-117">Remarks</span></span>

<span data-ttu-id="34a99-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LineRouteExt 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="34a99-118">To get a reference to the LineRouteExt cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="34a99-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="34a99-119">Cell name:</span></span>  <br/> | <span data-ttu-id="34a99-120">LineRouteExt</span><span class="sxs-lookup"><span data-stu-id="34a99-120">LineRouteExt</span></span>  <br/> |
   
<span data-ttu-id="34a99-121">要从某个程序按索引获取对 LineRouteExt 单元格的引用，请使用带下列参数的  **CellsSRC**  属性：</span><span class="sxs-lookup"><span data-stu-id="34a99-121">To get a reference to the LineRouteExt cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="34a99-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="34a99-122">Section index:</span></span>  <br/> |<span data-ttu-id="34a99-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="34a99-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="34a99-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="34a99-124">Row index:</span></span>  <br/> |<span data-ttu-id="34a99-125">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="34a99-125">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="34a99-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="34a99-126">Cell index:</span></span>  <br/> |<span data-ttu-id="34a99-127">**visPLOLineRouteExt**</span><span class="sxs-lookup"><span data-stu-id="34a99-127">**visPLOLineRouteExt**</span></span> <br/> |
   

