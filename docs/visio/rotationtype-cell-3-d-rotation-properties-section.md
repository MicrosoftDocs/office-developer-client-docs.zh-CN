---
title: 'RotationType Cell (3-D Rotation Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a8d5388a-8fd0-4c6e-9633-e1f03c5bef3b
description: 确定形状是按照从 0 到 6 的整数进行平行旋转、透视旋转还是倾斜旋转。
ms.openlocfilehash: 676f8a15185242aacc1affb9f1bd200ff3df454d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422941"
---
# <a name="rotationtype-cell-3-d-rotation-properties-section"></a><span data-ttu-id="21888-103">RotationType Cell (3-D Rotation Properties Section) </span><span class="sxs-lookup"><span data-stu-id="21888-103">RotationType Cell (3-D Rotation Properties Section)</span></span>

<span data-ttu-id="21888-104">确定形状是按照从 0 到 6 的整数进行平行旋转、透视旋转还是倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="21888-104">Determines whether the shape follows a parallel rotation, a perspective rotation, or an oblique rotation, as an integer from 0 to 6.</span></span> 
  
|<span data-ttu-id="21888-105">**值**</span><span class="sxs-lookup"><span data-stu-id="21888-105">**Value**</span></span>|<span data-ttu-id="21888-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="21888-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="21888-107">0</span><span class="sxs-lookup"><span data-stu-id="21888-107">0</span></span>  <br/> |<span data-ttu-id="21888-108">形状没有任何旋转。</span><span class="sxs-lookup"><span data-stu-id="21888-108">The shape does not have any rotation.</span></span>  <br/> |
|<span data-ttu-id="21888-109">1</span><span class="sxs-lookup"><span data-stu-id="21888-109">1</span></span>  <br/> |<span data-ttu-id="21888-110">形状具有平行旋转。</span><span class="sxs-lookup"><span data-stu-id="21888-110">The shape has a parallel rotation.</span></span>  <br/> |
|<span data-ttu-id="21888-111">2</span><span class="sxs-lookup"><span data-stu-id="21888-111">2</span></span>  <br/> |<span data-ttu-id="21888-112">形状具有透视旋转。</span><span class="sxs-lookup"><span data-stu-id="21888-112">The shape has a perspective rotation.</span></span>  <br/> |
|<span data-ttu-id="21888-113">3</span><span class="sxs-lookup"><span data-stu-id="21888-113">3</span></span>  <br/> |<span data-ttu-id="21888-114">形状具有左上倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="21888-114">The shape has a top left oblique rotation.</span></span>  <br/> |
|<span data-ttu-id="21888-115">4 </span><span class="sxs-lookup"><span data-stu-id="21888-115">4</span></span>  <br/> |<span data-ttu-id="21888-116">形状有右上倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="21888-116">The shape has a top right oblique rotation.</span></span>  <br/> |
|<span data-ttu-id="21888-117">5 </span><span class="sxs-lookup"><span data-stu-id="21888-117">5</span></span>  <br/> |<span data-ttu-id="21888-118">形状左下倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="21888-118">The shape has a bottom left oblique rotation.</span></span>  <br/> |
|<span data-ttu-id="21888-119">6 </span><span class="sxs-lookup"><span data-stu-id="21888-119">6</span></span>  <br/> |<span data-ttu-id="21888-120">形状有右下倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="21888-120">The shape has a bottom right oblique rotation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="21888-121">备注</span><span class="sxs-lookup"><span data-stu-id="21888-121">Remarks</span></span>

<span data-ttu-id="21888-122">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **RotationType** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="21888-122">To get a reference to the **RotationType** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="21888-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="21888-123">Cell name:</span></span>  <br/> |<span data-ttu-id="21888-124">RotationType</span><span class="sxs-lookup"><span data-stu-id="21888-124">RotationType</span></span>  <br/> |
   
<span data-ttu-id="21888-125">若要从程序按索引获取对 **RotationType** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="21888-125">To get a reference to the **RotationType** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="21888-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="21888-126">Section index:</span></span>  <br/> |<span data-ttu-id="21888-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="21888-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="21888-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="21888-128">Row index:</span></span>  <br/> |<span data-ttu-id="21888-129">**visRow3DRotationProperties**</span><span class="sxs-lookup"><span data-stu-id="21888-129">**visRow3DRotationProperties**</span></span> <br/> |
|<span data-ttu-id="21888-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="21888-130">Cell index:</span></span>  <br/> |<span data-ttu-id="21888-131">**visRotationType**</span><span class="sxs-lookup"><span data-stu-id="21888-131">**visRotationType**</span></span> <br/> |
   

