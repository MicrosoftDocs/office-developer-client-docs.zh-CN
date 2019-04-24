---
title: INTERSECTX 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251444
localization_priority: Normal
ms.assetid: d8dc1915-f055-e858-1323-9e8c1cb7f2f1
description: 返回两条直线相交点的 x 轴坐标值 (在局部坐标系中)。
ms.openlocfilehash: 857f81d667e33ad9ce79405ef5d59874903098e6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335306"
---
# <a name="intersectx-function"></a><span data-ttu-id="5486d-103">INTERSECTX 函数</span><span class="sxs-lookup"><span data-stu-id="5486d-103">INTERSECTX Function</span></span>

<span data-ttu-id="5486d-104">返回两条直线相交点的*x*轴坐标值 (在局部坐标系中)。</span><span class="sxs-lookup"><span data-stu-id="5486d-104">Returns the  *x*  -coordinate (in the local coordinate system) of the point where two lines intersect.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5486d-105">语法</span><span class="sxs-lookup"><span data-stu-id="5486d-105">Syntax</span></span>

<span data-ttu-id="5486d-106">INTERSECTX (\* \* *x1* \* *、* \* *y1* \* *、* \* *angle1* \* *、* \* *x2* \* *、* \* *y2* \* *、* \* *angle2* \* \*)</span><span class="sxs-lookup"><span data-stu-id="5486d-106">INTERSECTX(\*\* *x1* \*\*, \*\* *y1* \*\*, \*\* *angle1* \*\*, \*\* *x2* \*\*, \*\* *y2* \*\*, \*\* *angle2* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5486d-107">参数</span><span class="sxs-lookup"><span data-stu-id="5486d-107">Parameters</span></span>

|<span data-ttu-id="5486d-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="5486d-108">**Name**</span></span>|<span data-ttu-id="5486d-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5486d-109">**Required/Optional**</span></span>|<span data-ttu-id="5486d-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5486d-110">**Data Type**</span></span>|<span data-ttu-id="5486d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5486d-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5486d-112">_x1_</span><span class="sxs-lookup"><span data-stu-id="5486d-112">_x1_</span></span> <br/> |<span data-ttu-id="5486d-113">必需</span><span class="sxs-lookup"><span data-stu-id="5486d-113">Required</span></span>  <br/> |<span data-ttu-id="5486d-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="5486d-114">**Number**</span></span> <br/> |<span data-ttu-id="5486d-115">第一条直线上的点的_x_坐标。</span><span class="sxs-lookup"><span data-stu-id="5486d-115">The  _x_-coordinate of a point on the first line.</span></span>  <br/> |
| <span data-ttu-id="5486d-116">_y1_</span><span class="sxs-lookup"><span data-stu-id="5486d-116">_y1_</span></span> <br/> |<span data-ttu-id="5486d-117">必需</span><span class="sxs-lookup"><span data-stu-id="5486d-117">Required</span></span>  <br/> |<span data-ttu-id="5486d-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="5486d-118">**Number**</span></span> <br/> |<span data-ttu-id="5486d-119">第一条直线上的点的_y_坐标。</span><span class="sxs-lookup"><span data-stu-id="5486d-119">The  _y_-coordinate of a point on the first line.</span></span>  <br/> |
| <span data-ttu-id="5486d-120">_angle1_</span><span class="sxs-lookup"><span data-stu-id="5486d-120">_angle1_</span></span> <br/> |<span data-ttu-id="5486d-121">必需</span><span class="sxs-lookup"><span data-stu-id="5486d-121">Required</span></span>  <br/> |<span data-ttu-id="5486d-122">**Number**</span><span class="sxs-lookup"><span data-stu-id="5486d-122">**Number**</span></span> <br/> | <span data-ttu-id="5486d-123">第一条直线的 Angle 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="5486d-123">The value of the Angle cell for the first line.</span></span>  <br/> |
| <span data-ttu-id="5486d-124">_x2_</span><span class="sxs-lookup"><span data-stu-id="5486d-124">_x2_</span></span> <br/> |<span data-ttu-id="5486d-125">必需</span><span class="sxs-lookup"><span data-stu-id="5486d-125">Required</span></span>  <br/> |<span data-ttu-id="5486d-126">**Number**</span><span class="sxs-lookup"><span data-stu-id="5486d-126">**Number**</span></span> <br/> |<span data-ttu-id="5486d-127">第二条直线上的点的_x_坐标。</span><span class="sxs-lookup"><span data-stu-id="5486d-127">The  _x_-coordinate of a point on the second line.</span></span>  <br/> |
| <span data-ttu-id="5486d-128">_y2_</span><span class="sxs-lookup"><span data-stu-id="5486d-128">_y2_</span></span> <br/> |<span data-ttu-id="5486d-129">必需</span><span class="sxs-lookup"><span data-stu-id="5486d-129">Required</span></span>  <br/> |<span data-ttu-id="5486d-130">**Number**</span><span class="sxs-lookup"><span data-stu-id="5486d-130">**Number**</span></span> <br/> |<span data-ttu-id="5486d-131">第二条直线上的点的_y_轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="5486d-131">The  _y_-coordinate of a point on the second line.</span></span>  <br/> |
| <span data-ttu-id="5486d-132">_angle2_</span><span class="sxs-lookup"><span data-stu-id="5486d-132">_angle2_</span></span> <br/> |<span data-ttu-id="5486d-133">必需</span><span class="sxs-lookup"><span data-stu-id="5486d-133">Required</span></span>  <br/> |<span data-ttu-id="5486d-134">**Number**</span><span class="sxs-lookup"><span data-stu-id="5486d-134">**Number**</span></span> <br/> |<span data-ttu-id="5486d-135">第二条直线的 Angle 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="5486d-135">The value of the Angle cell for the second line.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5486d-136">返回值</span><span class="sxs-lookup"><span data-stu-id="5486d-136">Return value</span></span>

<span data-ttu-id="5486d-137">帐号</span><span class="sxs-lookup"><span data-stu-id="5486d-137">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5486d-138">注解</span><span class="sxs-lookup"><span data-stu-id="5486d-138">Remarks</span></span>

<span data-ttu-id="5486d-139">每一条直线都可以定义为一个点 (*x,y*) 和一个角。</span><span class="sxs-lookup"><span data-stu-id="5486d-139">Each line is defined as a point (*x,y*) and an angle.</span></span> 
  
<span data-ttu-id="5486d-140">Microsoft Visio 在粘附到旋转参考线的形状的 PinX 单元格中使用此函数。</span><span class="sxs-lookup"><span data-stu-id="5486d-140">Microsoft Visio uses this function in the PinX cell of a shape glued to a rotated guide.</span></span> 
  
<span data-ttu-id="5486d-141">如果直线未相交，则该函数将返回被零除错误 (#DIV/0!)，Visio 将忽略此错误，并还原该点的前一个已知值。</span><span class="sxs-lookup"><span data-stu-id="5486d-141">If the lines don't intersect, the function returns a divide-by-zero error (#DIV/0!), which Visio ignores, restoring the last known value for the point.</span></span> 
  
## <a name="example"></a><span data-ttu-id="5486d-142">示例</span><span class="sxs-lookup"><span data-stu-id="5486d-142">Example</span></span>

<span data-ttu-id="5486d-143">INTERSECTX (VertGuide!PinX、VertGuide!PinY、VertGuide!角、用 horzguide!PinX、用 horzguide!PinY、用 horzguide!Angle</span><span class="sxs-lookup"><span data-stu-id="5486d-143">INTERSECTX(VertGuide!PinX,VertGuide!PinY,VertGuide!Angle, HorzGuide!PinX,HorzGuide!PinY,HorzGuide!Angle)</span></span> 
  
<span data-ttu-id="5486d-144">返回 VertGuide 和用 horzguide 的交叉点的*x*坐标 (以页面单位表示)。</span><span class="sxs-lookup"><span data-stu-id="5486d-144">Returns the  *x*  -coordinate of the intersection point of VertGuide and HorzGuide in page units.</span></span> 
  

