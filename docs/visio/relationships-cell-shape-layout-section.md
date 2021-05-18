---
title: Relationships 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80005
localization_priority: Normal
ms.assetid: 4168cd98-9674-1233-254f-0afe81b7245b
description: 存储容器、列表、标注和形状之间的关系。
ms.openlocfilehash: b270366fe1045aea3d628150c82e7fd798fa21df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406407"
---
# <a name="relationships-cell-shape-layout-section"></a><span data-ttu-id="005b1-103">Relationships 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="005b1-103">Relationships Cell (Shape Layout Section)</span></span>

<span data-ttu-id="005b1-104">存储容器、列表、标注和形状之间的关系。</span><span class="sxs-lookup"><span data-stu-id="005b1-104">Stores the relationships between containers, lists, callouts, and shapes.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="005b1-105">备注</span><span class="sxs-lookup"><span data-stu-id="005b1-105">Remarks</span></span>

 <span data-ttu-id="005b1-106">Microsoft Visio 使用 Relationships 单元格来存储涉及此形状的关系。</span><span class="sxs-lookup"><span data-stu-id="005b1-106">Microsoft Visio uses the Relationships cell to store the relationships that involve this shape.</span></span> <span data-ttu-id="005b1-107">一系列带有所示参数的 DEPENDSON 函数用于表示与该形状的关系，如下表中所示。</span><span class="sxs-lookup"><span data-stu-id="005b1-107">A series of DEPENDSON functions, with the parameters shown, are used to represent relationships with this shape, as shown in the following table.</span></span> 
  
|<span data-ttu-id="005b1-108">**第一个参数**</span><span class="sxs-lookup"><span data-stu-id="005b1-108">**First parameter**</span></span>|<span data-ttu-id="005b1-109">**其他参数**</span><span class="sxs-lookup"><span data-stu-id="005b1-109">**Additional parameters**</span></span>|
|:-----|:-----|
|<span data-ttu-id="005b1-110">1</span><span class="sxs-lookup"><span data-stu-id="005b1-110">1</span></span>  <br/> |<span data-ttu-id="005b1-111">属于此容器成员的形状。</span><span class="sxs-lookup"><span data-stu-id="005b1-111">Shapes that are members of this container.</span></span>  <br/> |
|<span data-ttu-id="005b1-112">2</span><span class="sxs-lookup"><span data-stu-id="005b1-112">2</span></span>  <br/> |<span data-ttu-id="005b1-113">属于此列表成员的形状。</span><span class="sxs-lookup"><span data-stu-id="005b1-113">Shapes that are members of this list.</span></span>  <br/> |
|<span data-ttu-id="005b1-114">3</span><span class="sxs-lookup"><span data-stu-id="005b1-114">3</span></span>  <br/> |<span data-ttu-id="005b1-115">与此形状相关的标注。</span><span class="sxs-lookup"><span data-stu-id="005b1-115">Callouts that are associated with this shape.</span></span>  <br/> |
|<span data-ttu-id="005b1-116">4 </span><span class="sxs-lookup"><span data-stu-id="005b1-116">4</span></span>  <br/> |<span data-ttu-id="005b1-117">此形状是其成员的容器。</span><span class="sxs-lookup"><span data-stu-id="005b1-117">Containers that this shape is a member of.</span></span>  <br/> |
|<span data-ttu-id="005b1-118">5 </span><span class="sxs-lookup"><span data-stu-id="005b1-118">5</span></span>  <br/> |<span data-ttu-id="005b1-119">此列表项是其成员的列表。</span><span class="sxs-lookup"><span data-stu-id="005b1-119">List that this list item is a member of.</span></span>  <br/> |
|<span data-ttu-id="005b1-120">6 </span><span class="sxs-lookup"><span data-stu-id="005b1-120">6</span></span>  <br/> |<span data-ttu-id="005b1-121">与此标注相关的形状。</span><span class="sxs-lookup"><span data-stu-id="005b1-121">Shape associated with this callout.</span></span>  <br/> |
|<span data-ttu-id="005b1-122">7 </span><span class="sxs-lookup"><span data-stu-id="005b1-122">7</span></span>  <br/> |<span data-ttu-id="005b1-123">此形状位于其左边界边缘的容器。</span><span class="sxs-lookup"><span data-stu-id="005b1-123">Container on the left boundary edge of which this shape sits.</span></span>  <br/> |
|<span data-ttu-id="005b1-124">8 </span><span class="sxs-lookup"><span data-stu-id="005b1-124">8</span></span>  <br/> |<span data-ttu-id="005b1-125">此形状位于其右边界边缘的容器。</span><span class="sxs-lookup"><span data-stu-id="005b1-125">Container on the right boundary edge of which this shape sits.</span></span>  <br/> |
|<span data-ttu-id="005b1-126">9 </span><span class="sxs-lookup"><span data-stu-id="005b1-126">9</span></span>  <br/> |<span data-ttu-id="005b1-127">此形状位于其上边界边缘的容器。</span><span class="sxs-lookup"><span data-stu-id="005b1-127">Container on the top boundary edge of which this shape sits.</span></span>  <br/> |
|<span data-ttu-id="005b1-128">10  </span><span class="sxs-lookup"><span data-stu-id="005b1-128">10</span></span>  <br/> |<span data-ttu-id="005b1-129">此形状位于其下边界边缘的容器。</span><span class="sxs-lookup"><span data-stu-id="005b1-129">Container on the bottom boundary edge of which this shape sits.</span></span>  <br/> |
|<span data-ttu-id="005b1-130">11</span><span class="sxs-lookup"><span data-stu-id="005b1-130">11</span></span>  <br/> |<span data-ttu-id="005b1-131">此列表重叠的列表。</span><span class="sxs-lookup"><span data-stu-id="005b1-131">List that this list overlaps.</span></span>  <br/> |
   
<span data-ttu-id="005b1-132">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Relationships 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="005b1-132">To get a reference to the Relationships cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="005b1-133">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="005b1-133">Cell name:</span></span>  <br/> |<span data-ttu-id="005b1-134">关系</span><span class="sxs-lookup"><span data-stu-id="005b1-134">Relationships</span></span>  <br/> |
   
<span data-ttu-id="005b1-135">若要从某个程序按索引获取对 Relationships 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="005b1-135">To get a reference to the Relationships cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="005b1-136">内容索引：</span><span class="sxs-lookup"><span data-stu-id="005b1-136">Section index:</span></span>  <br/> |<span data-ttu-id="005b1-137">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="005b1-137">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="005b1-138">行索引：</span><span class="sxs-lookup"><span data-stu-id="005b1-138">Row index:</span></span>  <br/> |<span data-ttu-id="005b1-139">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="005b1-139">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="005b1-140">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="005b1-140">Cell index:</span></span>  <br/> |<span data-ttu-id="005b1-141">**visSLORelationships**</span><span class="sxs-lookup"><span data-stu-id="005b1-141">**visSLORelationships**</span></span> <br/> |
   

