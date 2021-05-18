---
title: Ellipse 行（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm3010
localization_priority: Normal
ms.assetid: 183fb303-4acb-a486-7b97-f11f7ae3978f
description: 包含椭圆中心点和椭圆上的两个点的 x 坐标和 y 坐标。
ms.openlocfilehash: 5121ba0c7bf97eaeaaf8a438dd40eccddada4362
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421828"
---
# <a name="ellipse-row-geometry-section"></a><span data-ttu-id="45ef5-103">Ellipse 行（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="45ef5-103">Ellipse Row (Geometry Section)</span></span>

<span data-ttu-id="45ef5-104">包含椭圆中心点和椭圆上的两个点的  *x*  坐标和  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="45ef5-104">Contains the  *x*  - and  *y*  -coordinates of the ellipse's center point and two points on the ellipse.</span></span> 
  
<span data-ttu-id="45ef5-105">Ellipse 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="45ef5-105">An Ellipse row contains the following cells.</span></span>
  
|<span data-ttu-id="45ef5-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="45ef5-106">**Cell**</span></span>|<span data-ttu-id="45ef5-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="45ef5-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="45ef5-108">X</span><span class="sxs-lookup"><span data-stu-id="45ef5-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="45ef5-109">中心点的  *x*  坐标。</span><span class="sxs-lookup"><span data-stu-id="45ef5-109">The  *x*  -coordinate of the center point.</span></span>  <br/> |
|[<span data-ttu-id="45ef5-110">Y</span><span class="sxs-lookup"><span data-stu-id="45ef5-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="45ef5-111">*中心点的 y* 坐标。</span><span class="sxs-lookup"><span data-stu-id="45ef5-111">The  *y*  -coordinate of the center point.</span></span>  <br/> |
|[<span data-ttu-id="45ef5-112">A</span><span class="sxs-lookup"><span data-stu-id="45ef5-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="45ef5-113">椭圆上一个点的 x 坐标;与 B 单元格表示的  *y*  坐标配对。</span><span class="sxs-lookup"><span data-stu-id="45ef5-113">The x-coordinate of one point on the ellipse; paired with  *y*  -coordinate represented by the B cell.</span></span>  <br/> |
|[<span data-ttu-id="45ef5-114">B</span><span class="sxs-lookup"><span data-stu-id="45ef5-114">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="45ef5-115">椭圆上一个点的  *y*  坐标;与由 A 单元格表示的 x 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="45ef5-115">The  *y*  -coordinate of one point on the ellipse; paired with x-coordinate represented by the A cell.</span></span>  <br/> |
|[<span data-ttu-id="45ef5-116">C</span><span class="sxs-lookup"><span data-stu-id="45ef5-116">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="45ef5-117">椭圆上另一个点的  *x*  坐标;与由 D 单元格表示的  *y*  坐标配对。</span><span class="sxs-lookup"><span data-stu-id="45ef5-117">The  *x*  -coordinate of another point on the ellipse; paired with  *y*  -coordinate represented by the D cell.</span></span>  <br/> |
|[<span data-ttu-id="45ef5-118">D</span><span class="sxs-lookup"><span data-stu-id="45ef5-118">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="45ef5-119">椭圆上另一个点的  *y*  坐标;与 C 单元格表示的  *y*  坐标配对。</span><span class="sxs-lookup"><span data-stu-id="45ef5-119">The  *y*  -coordinate of another point on the ellipse; paired with  *y*  -coordinate represented by the C cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="45ef5-120">备注</span><span class="sxs-lookup"><span data-stu-id="45ef5-120">Remarks</span></span>

<span data-ttu-id="45ef5-121">包含 Ellipse 行或 InfiniteLine 行的“Geometry”内容不应包含任何其他行。</span><span class="sxs-lookup"><span data-stu-id="45ef5-121">A geometry section that contains an Ellipse or an InfiniteLine row should not contain any other rows.</span></span>
  

