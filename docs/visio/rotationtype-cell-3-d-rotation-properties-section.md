---
title: RotationType 单元格 ("三维旋转属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a8d5388a-8fd0-4c6e-9633-e1f03c5bef3b
description: 确定形状是采用平行旋转、透视旋转还是倾斜旋转, 为0到6的整数。
ms.openlocfilehash: 676f8a15185242aacc1affb9f1bd200ff3df454d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422941"
---
# <a name="rotationtype-cell-3-d-rotation-properties-section"></a><span data-ttu-id="58f6b-103">RotationType 单元格 ("三维旋转属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="58f6b-103">RotationType Cell (3-D Rotation Properties Section)</span></span>

<span data-ttu-id="58f6b-104">确定形状是采用平行旋转、透视旋转还是倾斜旋转, 为0到6的整数。</span><span class="sxs-lookup"><span data-stu-id="58f6b-104">Determines whether the shape follows a parallel rotation, a perspective rotation, or an oblique rotation, as an integer from 0 to 6.</span></span> 
  
|<span data-ttu-id="58f6b-105">**值**</span><span class="sxs-lookup"><span data-stu-id="58f6b-105">**Value**</span></span>|<span data-ttu-id="58f6b-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="58f6b-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58f6b-107">0</span><span class="sxs-lookup"><span data-stu-id="58f6b-107">0</span></span>  <br/> |<span data-ttu-id="58f6b-108">形状没有任何旋转。</span><span class="sxs-lookup"><span data-stu-id="58f6b-108">The shape does not have any rotation.</span></span>  <br/> |
|<span data-ttu-id="58f6b-109">1</span><span class="sxs-lookup"><span data-stu-id="58f6b-109">1</span></span>  <br/> |<span data-ttu-id="58f6b-110">形状具有平行旋转。</span><span class="sxs-lookup"><span data-stu-id="58f6b-110">The shape has a parallel rotation.</span></span>  <br/> |
|<span data-ttu-id="58f6b-111">双面</span><span class="sxs-lookup"><span data-stu-id="58f6b-111">2</span></span>  <br/> |<span data-ttu-id="58f6b-112">形状具有透视旋转。</span><span class="sxs-lookup"><span data-stu-id="58f6b-112">The shape has a perspective rotation.</span></span>  <br/> |
|<span data-ttu-id="58f6b-113">第三章</span><span class="sxs-lookup"><span data-stu-id="58f6b-113">3</span></span>  <br/> |<span data-ttu-id="58f6b-114">形状具有左上角倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="58f6b-114">The shape has a top left oblique rotation.</span></span>  <br/> |
|<span data-ttu-id="58f6b-115">4</span><span class="sxs-lookup"><span data-stu-id="58f6b-115">4</span></span>  <br/> |<span data-ttu-id="58f6b-116">形状具有右上角倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="58f6b-116">The shape has a top right oblique rotation.</span></span>  <br/> |
|<span data-ttu-id="58f6b-117">5</span><span class="sxs-lookup"><span data-stu-id="58f6b-117">5</span></span>  <br/> |<span data-ttu-id="58f6b-118">形状具有左下角倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="58f6b-118">The shape has a bottom left oblique rotation.</span></span>  <br/> |
|<span data-ttu-id="58f6b-119">型</span><span class="sxs-lookup"><span data-stu-id="58f6b-119">6</span></span>  <br/> |<span data-ttu-id="58f6b-120">形状具有右下角倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="58f6b-120">The shape has a bottom right oblique rotation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="58f6b-121">说明</span><span class="sxs-lookup"><span data-stu-id="58f6b-121">Remarks</span></span>

<span data-ttu-id="58f6b-122">若要从另一个公式按名称获取对**RotationType**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="58f6b-122">To get a reference to the **RotationType** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="58f6b-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="58f6b-123">Cell name:</span></span>  <br/> |<span data-ttu-id="58f6b-124">RotationType</span><span class="sxs-lookup"><span data-stu-id="58f6b-124">RotationType</span></span>  <br/> |
   
<span data-ttu-id="58f6b-125">若要从某个程序按索引获取对**RotationType**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="58f6b-125">To get a reference to the **RotationType** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="58f6b-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="58f6b-126">Section index:</span></span>  <br/> |<span data-ttu-id="58f6b-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="58f6b-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="58f6b-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="58f6b-128">Row index:</span></span>  <br/> |<span data-ttu-id="58f6b-129">**visRow3DRotationProperties**</span><span class="sxs-lookup"><span data-stu-id="58f6b-129">**visRow3DRotationProperties**</span></span> <br/> |
|<span data-ttu-id="58f6b-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="58f6b-130">Cell index:</span></span>  <br/> |<span data-ttu-id="58f6b-131">**visRotationType**</span><span class="sxs-lookup"><span data-stu-id="58f6b-131">**visRotationType**</span></span> <br/> |
   

