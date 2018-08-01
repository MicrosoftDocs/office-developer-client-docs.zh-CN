---
title: PlaceDepth 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1230
localization_priority: Normal
ms.assetid: 02c139db-fe67-f550-1d07-8c8a9a4fb427
description: 确定在创建布局之前分析绘图使用的方法，并确定布局的类型。
ms.openlocfilehash: ab2c83a94c3dd03c1fdbf0c3ee187076406b2e84
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780854"
---
# <a name="placedepth-cell-page-layout-section"></a><span data-ttu-id="92f59-103">PlaceDepth 单元格（“Page Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="92f59-103">PlaceDepth Cell (Page Layout Section)</span></span>

<span data-ttu-id="92f59-104">确定在创建布局之前分析绘图使用的方法，并确定布局的类型。</span><span class="sxs-lookup"><span data-stu-id="92f59-104">Determines the method by which the drawing is analyzed before creating the layout, and determines the type of layout.</span></span>
  
|<span data-ttu-id="92f59-105">**值**</span><span class="sxs-lookup"><span data-stu-id="92f59-105">**Value**</span></span>|<span data-ttu-id="92f59-106">**垂直和水平布局的放置深度**</span><span class="sxs-lookup"><span data-stu-id="92f59-106">**Placement depth for vertical and horizontal layouts**</span></span>|<span data-ttu-id="92f59-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="92f59-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="92f59-108">0</span><span class="sxs-lookup"><span data-stu-id="92f59-108">0</span></span>  <br/> | <span data-ttu-id="92f59-109">页面默认值</span><span class="sxs-lookup"><span data-stu-id="92f59-109">Page default</span></span>  <br/> |<span data-ttu-id="92f59-110">**visPLOPlaceDepthDefault**</span><span class="sxs-lookup"><span data-stu-id="92f59-110">**visPLOPlaceDepthDefault**</span></span> <br/> |
| <span data-ttu-id="92f59-111">1</span><span class="sxs-lookup"><span data-stu-id="92f59-111">1</span></span>  <br/> | <span data-ttu-id="92f59-112">中等</span><span class="sxs-lookup"><span data-stu-id="92f59-112">Medium</span></span>  <br/> |<span data-ttu-id="92f59-113">**visPLOPlaceDepthMedium**</span><span class="sxs-lookup"><span data-stu-id="92f59-113">**visPLOPlaceDepthMedium**</span></span> <br/> |
| <span data-ttu-id="92f59-114">2</span><span class="sxs-lookup"><span data-stu-id="92f59-114">2</span></span>  <br/> | <span data-ttu-id="92f59-115">深</span><span class="sxs-lookup"><span data-stu-id="92f59-115">Deep</span></span>  <br/> |<span data-ttu-id="92f59-116">**visPLOPlaceDepthDeep**</span><span class="sxs-lookup"><span data-stu-id="92f59-116">**visPLOPlaceDepthDeep**</span></span> <br/> |
| <span data-ttu-id="92f59-117">3</span><span class="sxs-lookup"><span data-stu-id="92f59-117">3</span></span>  <br/> | <span data-ttu-id="92f59-118">浅</span><span class="sxs-lookup"><span data-stu-id="92f59-118">Shallow</span></span>  <br/> |<span data-ttu-id="92f59-119">**visPLOPlaceDepthShallow**</span><span class="sxs-lookup"><span data-stu-id="92f59-119">**visPLOPlaceDepthShallow**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="92f59-120">说明</span><span class="sxs-lookup"><span data-stu-id="92f59-120">Remarks</span></span>

<span data-ttu-id="92f59-121">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PlaceDepth 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="92f59-121">To get a reference to the PlaceDepth cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="92f59-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="92f59-122">Cell name:</span></span>  <br/> | <span data-ttu-id="92f59-123">PlaceDepth</span><span class="sxs-lookup"><span data-stu-id="92f59-123">PlaceDepth</span></span>  <br/> |
   
<span data-ttu-id="92f59-124">要从某个程序按索引获取对 PlaceDepth 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="92f59-124">To get a reference to the PlaceDepth cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="92f59-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="92f59-125">Section index:</span></span>  <br/> |<span data-ttu-id="92f59-126">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="92f59-126">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="92f59-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="92f59-127">Row index:</span></span>  <br/> |<span data-ttu-id="92f59-128">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="92f59-128">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="92f59-129">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="92f59-129">Cell index:</span></span>  <br/> |<span data-ttu-id="92f59-130">**visPLOPlaceDepth**</span><span class="sxs-lookup"><span data-stu-id="92f59-130">**visPLOPlaceDepth**</span></span> <br/> |
   

