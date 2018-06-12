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
description: 包含 x 和 y-椭圆中心点和椭圆上的两个点的坐标。
ms.openlocfilehash: 0a2acb0efa20f67d04581f827edbfc4fb4a2d6b0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780169"
---
# <a name="ellipse-row-geometry-section"></a><span data-ttu-id="3d95a-103">Ellipse 行（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="3d95a-103">Ellipse Row (Geometry Section)</span></span>

<span data-ttu-id="3d95a-104">包含*x*和*y* -椭圆中心点和椭圆上的两个点的坐标。</span><span class="sxs-lookup"><span data-stu-id="3d95a-104">Contains the  *x*  - and  *y*  -coordinates of the ellipse's center point and two points on the ellipse.</span></span> 
  
<span data-ttu-id="3d95a-105">Ellipse 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="3d95a-105">An Ellipse row contains the following cells.</span></span>
  
|<span data-ttu-id="3d95a-106">**Cell**</span><span class="sxs-lookup"><span data-stu-id="3d95a-106">**Cell**</span></span>|<span data-ttu-id="3d95a-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="3d95a-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3d95a-108">X</span><span class="sxs-lookup"><span data-stu-id="3d95a-108">X</span></span>](x-cell-geometry-section.md) <br/> |<span data-ttu-id="3d95a-109">*X* -中心点的坐标。</span><span class="sxs-lookup"><span data-stu-id="3d95a-109">The  *x*  -coordinate of the center point.</span></span>  <br/> |
|[<span data-ttu-id="3d95a-110">Y</span><span class="sxs-lookup"><span data-stu-id="3d95a-110">Y</span></span>](y-cell-geometry-section.md) <br/> |<span data-ttu-id="3d95a-111">*Y* -中心点的坐标。</span><span class="sxs-lookup"><span data-stu-id="3d95a-111">The  *y*  -coordinate of the center point.</span></span>  <br/> |
|[<span data-ttu-id="3d95a-112">A</span><span class="sxs-lookup"><span data-stu-id="3d95a-112">A</span></span>](a-cell-geometry-section.md) <br/> |<span data-ttu-id="3d95a-113">椭圆; 上某个点的 x 坐标与*y*配对-B 单元格所表示的坐标。</span><span class="sxs-lookup"><span data-stu-id="3d95a-113">The x-coordinate of one point on the ellipse; paired with  *y*  -coordinate represented by the B cell.</span></span>  <br/> |
|[<span data-ttu-id="3d95a-114">B</span><span class="sxs-lookup"><span data-stu-id="3d95a-114">B</span></span>](b-cell-geometry-section.md) <br/> |<span data-ttu-id="3d95a-115">*Y* -椭圆; 上某个点的坐标与 A 单元格所表示的 x 轴坐标配对。</span><span class="sxs-lookup"><span data-stu-id="3d95a-115">The  *y*  -coordinate of one point on the ellipse; paired with x-coordinate represented by the A cell.</span></span>  <br/> |
|[<span data-ttu-id="3d95a-116">C</span><span class="sxs-lookup"><span data-stu-id="3d95a-116">C</span></span>](c-cell-geometry-section.md) <br/> |<span data-ttu-id="3d95a-117">*X* -; 椭圆上另一个点的坐标与*y*配对-D 单元格所表示的坐标。</span><span class="sxs-lookup"><span data-stu-id="3d95a-117">The  *x*  -coordinate of another point on the ellipse; paired with  *y*  -coordinate represented by the D cell.</span></span>  <br/> |
|[<span data-ttu-id="3d95a-118">D</span><span class="sxs-lookup"><span data-stu-id="3d95a-118">D</span></span>](d-cell-geometry-section.md) <br/> |<span data-ttu-id="3d95a-119">*Y* -; 椭圆上另一个点的坐标与*y*配对-C 单元格所表示的坐标。</span><span class="sxs-lookup"><span data-stu-id="3d95a-119">The  *y*  -coordinate of another point on the ellipse; paired with  *y*  -coordinate represented by the C cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3d95a-120">注解</span><span class="sxs-lookup"><span data-stu-id="3d95a-120">Remarks</span></span>

<span data-ttu-id="3d95a-121">包含 Ellipse 行或 InfiniteLine 行的“Geometry”内容不应包含任何其他行。</span><span class="sxs-lookup"><span data-stu-id="3d95a-121">A geometry section that contains an Ellipse or an InfiniteLine row should not contain any other rows.</span></span>
  

