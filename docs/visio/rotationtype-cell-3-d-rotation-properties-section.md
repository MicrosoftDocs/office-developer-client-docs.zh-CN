---
title: RotationType 单元格（“3-D Rotation Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a8d5388a-8fd0-4c6e-9633-e1f03c5bef3b
description: 确定形状遵循并行旋转、 角度旋转或倾斜旋转，为从 0 到 6 的整数。
ms.openlocfilehash: 85effcef3969d7b7c57551ec88710ba84b3fc163
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781155"
---
# <a name="rotationtype-cell-3-d-rotation-properties-section"></a><span data-ttu-id="bcfeb-103">RotationType 单元格（“3-D Rotation Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="bcfeb-103">RotationType Cell (3-D Rotation Properties Section)</span></span>

<span data-ttu-id="bcfeb-104">确定形状遵循并行旋转、 角度旋转或倾斜旋转，为从 0 到 6 的整数。</span><span class="sxs-lookup"><span data-stu-id="bcfeb-104">Determines whether the shape follows a parallel rotation, a perspective rotation, or an oblique rotation, as an integer from 0 to 6.</span></span> 
  
|<span data-ttu-id="bcfeb-105">**值**</span><span class="sxs-lookup"><span data-stu-id="bcfeb-105">**Value**</span></span>|<span data-ttu-id="bcfeb-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="bcfeb-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bcfeb-107">0</span><span class="sxs-lookup"><span data-stu-id="bcfeb-107">0</span></span>  <br/> |<span data-ttu-id="bcfeb-108">形状没有任何旋转。</span><span class="sxs-lookup"><span data-stu-id="bcfeb-108">The shape does not have any rotation.</span></span>  <br/> |
|<span data-ttu-id="bcfeb-109">1</span><span class="sxs-lookup"><span data-stu-id="bcfeb-109">1</span></span>  <br/> |<span data-ttu-id="bcfeb-110">形状具有并行旋转。</span><span class="sxs-lookup"><span data-stu-id="bcfeb-110">The shape has a parallel rotation.</span></span>  <br/> |
|<span data-ttu-id="bcfeb-111">2</span><span class="sxs-lookup"><span data-stu-id="bcfeb-111">2</span></span>  <br/> |<span data-ttu-id="bcfeb-112">形状的旋转角度。</span><span class="sxs-lookup"><span data-stu-id="bcfeb-112">The shape has a perspective rotation.</span></span>  <br/> |
|<span data-ttu-id="bcfeb-113">3</span><span class="sxs-lookup"><span data-stu-id="bcfeb-113">3</span></span>  <br/> |<span data-ttu-id="bcfeb-114">形状的顶部左侧倾斜旋转角度。</span><span class="sxs-lookup"><span data-stu-id="bcfeb-114">The shape has a top left oblique rotation.</span></span>  <br/> |
|<span data-ttu-id="bcfeb-115">4</span><span class="sxs-lookup"><span data-stu-id="bcfeb-115">4</span></span>  <br/> |<span data-ttu-id="bcfeb-116">形状的顶部的倾斜朝右旋转。</span><span class="sxs-lookup"><span data-stu-id="bcfeb-116">The shape has a top right oblique rotation.</span></span>  <br/> |
|<span data-ttu-id="bcfeb-117">5</span><span class="sxs-lookup"><span data-stu-id="bcfeb-117">5</span></span>  <br/> |<span data-ttu-id="bcfeb-118">形状的底部左侧倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="bcfeb-118">The shape has a bottom left oblique rotation.</span></span>  <br/> |
|<span data-ttu-id="bcfeb-119">6</span><span class="sxs-lookup"><span data-stu-id="bcfeb-119">6</span></span>  <br/> |<span data-ttu-id="bcfeb-120">形状具有底部右键倾斜旋转。</span><span class="sxs-lookup"><span data-stu-id="bcfeb-120">The shape has a bottom right oblique rotation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bcfeb-121">说明</span><span class="sxs-lookup"><span data-stu-id="bcfeb-121">Remarks</span></span>

<span data-ttu-id="bcfeb-122">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**RotationType**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="bcfeb-122">To get a reference to the **RotationType** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bcfeb-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="bcfeb-123">Cell name:</span></span>  <br/> |<span data-ttu-id="bcfeb-124">RotationType</span><span class="sxs-lookup"><span data-stu-id="bcfeb-124">RotationType</span></span>  <br/> |
   
<span data-ttu-id="bcfeb-125">若要从某个程序按索引获取对**RotationType**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="bcfeb-125">To get a reference to the **RotationType** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bcfeb-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="bcfeb-126">Section index:</span></span>  <br/> |<span data-ttu-id="bcfeb-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="bcfeb-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="bcfeb-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="bcfeb-128">Row index:</span></span>  <br/> |<span data-ttu-id="bcfeb-129">**visRow3DRotationProperties**</span><span class="sxs-lookup"><span data-stu-id="bcfeb-129">**visRow3DRotationProperties**</span></span> <br/> |
|<span data-ttu-id="bcfeb-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="bcfeb-130">Cell index:</span></span>  <br/> |<span data-ttu-id="bcfeb-131">**visRotationType**</span><span class="sxs-lookup"><span data-stu-id="bcfeb-131">**visRotationType**</span></span> <br/> |
   

