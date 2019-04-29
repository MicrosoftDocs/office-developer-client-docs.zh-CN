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
ms.openlocfilehash: 463c7dad39955161538aa89d1482685189bf7fdc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432035"
---
# <a name="placedepth-cell-page-layout-section"></a><span data-ttu-id="c41df-103">PlaceDepth 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="c41df-103">PlaceDepth Cell (Page Layout Section)</span></span>

<span data-ttu-id="c41df-104">确定在创建布局之前分析绘图使用的方法，并确定布局的类型。</span><span class="sxs-lookup"><span data-stu-id="c41df-104">Determines the method by which the drawing is analyzed before creating the layout, and determines the type of layout.</span></span>
  
|<span data-ttu-id="c41df-105">**值**</span><span class="sxs-lookup"><span data-stu-id="c41df-105">**Value**</span></span>|<span data-ttu-id="c41df-106">**垂直和水平布局的放置深度**</span><span class="sxs-lookup"><span data-stu-id="c41df-106">**Placement depth for vertical and horizontal layouts**</span></span>|<span data-ttu-id="c41df-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="c41df-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="c41df-108">0</span><span class="sxs-lookup"><span data-stu-id="c41df-108">0</span></span>  <br/> | <span data-ttu-id="c41df-109">页面默认值</span><span class="sxs-lookup"><span data-stu-id="c41df-109">Page default</span></span>  <br/> |<span data-ttu-id="c41df-110">**visPLOPlaceDepthDefault**</span><span class="sxs-lookup"><span data-stu-id="c41df-110">**visPLOPlaceDepthDefault**</span></span> <br/> |
| <span data-ttu-id="c41df-111">1</span><span class="sxs-lookup"><span data-stu-id="c41df-111">1</span></span>  <br/> | <span data-ttu-id="c41df-112">中</span><span class="sxs-lookup"><span data-stu-id="c41df-112">Medium</span></span>  <br/> |<span data-ttu-id="c41df-113">**visPLOPlaceDepthMedium**</span><span class="sxs-lookup"><span data-stu-id="c41df-113">**visPLOPlaceDepthMedium**</span></span> <br/> |
| <span data-ttu-id="c41df-114">双面</span><span class="sxs-lookup"><span data-stu-id="c41df-114">2</span></span>  <br/> | <span data-ttu-id="c41df-115">深</span><span class="sxs-lookup"><span data-stu-id="c41df-115">Deep</span></span>  <br/> |<span data-ttu-id="c41df-116">**visPLOPlaceDepthDeep**</span><span class="sxs-lookup"><span data-stu-id="c41df-116">**visPLOPlaceDepthDeep**</span></span> <br/> |
| <span data-ttu-id="c41df-117">第三章</span><span class="sxs-lookup"><span data-stu-id="c41df-117">3</span></span>  <br/> | <span data-ttu-id="c41df-118">浅</span><span class="sxs-lookup"><span data-stu-id="c41df-118">Shallow</span></span>  <br/> |<span data-ttu-id="c41df-119">**visPLOPlaceDepthShallow**</span><span class="sxs-lookup"><span data-stu-id="c41df-119">**visPLOPlaceDepthShallow**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c41df-120">说明</span><span class="sxs-lookup"><span data-stu-id="c41df-120">Remarks</span></span>

<span data-ttu-id="c41df-121">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PlaceDepth 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c41df-121">To get a reference to the PlaceDepth cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c41df-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c41df-122">Cell name:</span></span>  <br/> | <span data-ttu-id="c41df-123">PlaceDepth</span><span class="sxs-lookup"><span data-stu-id="c41df-123">PlaceDepth</span></span>  <br/> |
   
<span data-ttu-id="c41df-124">要从某个程序按索引获取对 PlaceDepth 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c41df-124">To get a reference to the PlaceDepth cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c41df-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c41df-125">Section index:</span></span>  <br/> |<span data-ttu-id="c41df-126">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c41df-126">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="c41df-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="c41df-127">Row index:</span></span>  <br/> |<span data-ttu-id="c41df-128">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="c41df-128">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="c41df-129">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c41df-129">Cell index:</span></span>  <br/> |<span data-ttu-id="c41df-130">**visPLOPlaceDepth**</span><span class="sxs-lookup"><span data-stu-id="c41df-130">**visPLOPlaceDepth**</span></span> <br/> |
   

