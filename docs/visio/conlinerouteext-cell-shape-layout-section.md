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
ms.openlocfilehash: 7724466b6ad225fcf39243bc80ba2e440f3b700b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779956"
---
# <a name="conlinerouteext-cell-shape-layout-section"></a><span data-ttu-id="6f8be-103">ConLineRouteExt 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="6f8be-103">ConLineRouteExt Cell (Shape Layout Section)</span></span>

<span data-ttu-id="6f8be-104">确定连接线的外观。</span><span class="sxs-lookup"><span data-stu-id="6f8be-104">Determines the appearance of a connector.</span></span>
  
|<span data-ttu-id="6f8be-105">**值**</span><span class="sxs-lookup"><span data-stu-id="6f8be-105">**Value**</span></span>|<span data-ttu-id="6f8be-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="6f8be-106">**Description**</span></span>|<span data-ttu-id="6f8be-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="6f8be-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="6f8be-108">0</span><span class="sxs-lookup"><span data-stu-id="6f8be-108">0</span></span>  <br/> | <span data-ttu-id="6f8be-109">默认值；使用页面设置</span><span class="sxs-lookup"><span data-stu-id="6f8be-109">Default; use page setting</span></span>  <br/> |<span data-ttu-id="6f8be-110">**visLORouteExtDefault**</span><span class="sxs-lookup"><span data-stu-id="6f8be-110">**visLORouteExtDefault**</span></span> <br/> |
| <span data-ttu-id="6f8be-111">1</span><span class="sxs-lookup"><span data-stu-id="6f8be-111">1</span></span>  <br/> | <span data-ttu-id="6f8be-112">直线</span><span class="sxs-lookup"><span data-stu-id="6f8be-112">Straight</span></span>  <br/> |<span data-ttu-id="6f8be-113">**visLORouteExtStraight**</span><span class="sxs-lookup"><span data-stu-id="6f8be-113">**visLORouteExtStraight**</span></span> <br/> |
| <span data-ttu-id="6f8be-114">2</span><span class="sxs-lookup"><span data-stu-id="6f8be-114">2</span></span>  <br/> | <span data-ttu-id="6f8be-115">曲线</span><span class="sxs-lookup"><span data-stu-id="6f8be-115">Curved</span></span>  <br/> |<span data-ttu-id="6f8be-116">**visLORouteExtNURBS**</span><span class="sxs-lookup"><span data-stu-id="6f8be-116">**visLORouteExtNURBS**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6f8be-117">备注</span><span class="sxs-lookup"><span data-stu-id="6f8be-117">Remarks</span></span>

<span data-ttu-id="6f8be-118">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ConLineRouteExt 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6f8be-118">To get a reference to the ConLineRouteExt cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6f8be-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6f8be-119">Cell name:</span></span>  <br/> | <span data-ttu-id="6f8be-120">ConLineRouteExt</span><span class="sxs-lookup"><span data-stu-id="6f8be-120">ConLineRouteExt</span></span>  <br/> |
   
<span data-ttu-id="6f8be-121">若要从某个程序按索引获取对 ConLineRouteExt 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="6f8be-121">To get a reference to the ConLineRouteExt cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6f8be-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6f8be-122">Section index:</span></span>  <br/> |<span data-ttu-id="6f8be-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="6f8be-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="6f8be-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="6f8be-124">Row index:</span></span>  <br/> |<span data-ttu-id="6f8be-125">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="6f8be-125">**visRowShapeLayout**</span></span> <br/> |
| <span data-ttu-id="6f8be-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6f8be-126">Cell index:</span></span>  <br/> |<span data-ttu-id="6f8be-127">**visSLOLineRouteExt**</span><span class="sxs-lookup"><span data-stu-id="6f8be-127">**visSLOLineRouteExt**</span></span> <br/> |
   

