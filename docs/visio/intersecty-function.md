---
title: INTERSECTY 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251445
localization_priority: Normal
ms.assetid: a298eead-044b-6f40-54c7-e0e6088baa19
description: 返回两条线相交的点的 y 轴坐标值 (在本地坐标系中)。
ms.openlocfilehash: 6fcd06e7086d52b9c45f1deb9d4c191f1a7b1fd2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426098"
---
# <a name="intersecty-function"></a><span data-ttu-id="d2089-103">INTERSECTY 函数</span><span class="sxs-lookup"><span data-stu-id="d2089-103">INTERSECTY Function</span></span>

<span data-ttu-id="d2089-104">返回两条线相交的点的*y*轴坐标值 (在本地坐标系中)。</span><span class="sxs-lookup"><span data-stu-id="d2089-104">Returns the  *y*  -coordinate (in the local coordinate system) of the point where two lines intersect.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d2089-105">语法</span><span class="sxs-lookup"><span data-stu-id="d2089-105">Syntax</span></span>

<span data-ttu-id="d2089-106">INTERSECTX (\* \* *x1* \* *、* \* *y1* \* *、* \* *angle1* \* *、* \* *x2* \* *、* \* *y2* \* *、* \* *angle2* \* \*)</span><span class="sxs-lookup"><span data-stu-id="d2089-106">INTERSECTX(\*\* *x1* \*\*, \*\* *y1* \*\*, \*\* *angle1* \*\*, \*\* *x2* \*\*, \*\* *y2* \*\*, \*\* *angle2* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d2089-107">参数</span><span class="sxs-lookup"><span data-stu-id="d2089-107">Parameters</span></span>

|<span data-ttu-id="d2089-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="d2089-108">**Name**</span></span>|<span data-ttu-id="d2089-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d2089-109">**Required/Optional**</span></span>|<span data-ttu-id="d2089-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d2089-110">**Data Type**</span></span>|<span data-ttu-id="d2089-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d2089-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d2089-112">_x1_</span><span class="sxs-lookup"><span data-stu-id="d2089-112">_x1_</span></span> <br/> |<span data-ttu-id="d2089-113">必需</span><span class="sxs-lookup"><span data-stu-id="d2089-113">Required</span></span>  <br/> |<span data-ttu-id="d2089-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="d2089-114">**Number**</span></span> <br/> |<span data-ttu-id="d2089-115">第一条直线上的点的_x_坐标。</span><span class="sxs-lookup"><span data-stu-id="d2089-115">The  _x_-coordinate of a point on the first line.</span></span>  <br/> |
| <span data-ttu-id="d2089-116">_y1_</span><span class="sxs-lookup"><span data-stu-id="d2089-116">_y1_</span></span> <br/> |<span data-ttu-id="d2089-117">必需</span><span class="sxs-lookup"><span data-stu-id="d2089-117">Required</span></span>  <br/> |<span data-ttu-id="d2089-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="d2089-118">**Number**</span></span> <br/> |<span data-ttu-id="d2089-119">第一条直线上的点的_y_坐标。</span><span class="sxs-lookup"><span data-stu-id="d2089-119">The  _y_-coordinate of a point on the first line.</span></span>  <br/> |
| <span data-ttu-id="d2089-120">_angle1_</span><span class="sxs-lookup"><span data-stu-id="d2089-120">_angle1_</span></span> <br/> |<span data-ttu-id="d2089-121">必需</span><span class="sxs-lookup"><span data-stu-id="d2089-121">Required</span></span>  <br/> |<span data-ttu-id="d2089-122">**Number**</span><span class="sxs-lookup"><span data-stu-id="d2089-122">**Number**</span></span> <br/> | <span data-ttu-id="d2089-123">第一条直线的 Angle 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d2089-123">The value of the Angle cell for the first line.</span></span>  <br/> |
| <span data-ttu-id="d2089-124">_x2_</span><span class="sxs-lookup"><span data-stu-id="d2089-124">_x2_</span></span> <br/> |<span data-ttu-id="d2089-125">必需</span><span class="sxs-lookup"><span data-stu-id="d2089-125">Required</span></span>  <br/> |<span data-ttu-id="d2089-126">**Number**</span><span class="sxs-lookup"><span data-stu-id="d2089-126">**Number**</span></span> <br/> |<span data-ttu-id="d2089-127">第二条直线上的点的_x_坐标。</span><span class="sxs-lookup"><span data-stu-id="d2089-127">The  _x_-coordinate of a point on the second line.</span></span>  <br/> |
| <span data-ttu-id="d2089-128">_y2_</span><span class="sxs-lookup"><span data-stu-id="d2089-128">_y2_</span></span> <br/> |<span data-ttu-id="d2089-129">必需</span><span class="sxs-lookup"><span data-stu-id="d2089-129">Required</span></span>  <br/> |<span data-ttu-id="d2089-130">**Number**</span><span class="sxs-lookup"><span data-stu-id="d2089-130">**Number**</span></span> <br/> |<span data-ttu-id="d2089-131">第二条直线上的点的_y_轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="d2089-131">The  _y_-coordinate of a point on the second line.</span></span>  <br/> |
| <span data-ttu-id="d2089-132">_angle2_</span><span class="sxs-lookup"><span data-stu-id="d2089-132">_angle2_</span></span> <br/> |<span data-ttu-id="d2089-133">必需</span><span class="sxs-lookup"><span data-stu-id="d2089-133">Required</span></span>  <br/> |<span data-ttu-id="d2089-134">**Number**</span><span class="sxs-lookup"><span data-stu-id="d2089-134">**Number**</span></span> <br/> |<span data-ttu-id="d2089-135">第二条直线的 Angle 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d2089-135">The value of the Angle cell for the second line.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="d2089-136">返回值</span><span class="sxs-lookup"><span data-stu-id="d2089-136">Return value</span></span>

<span data-ttu-id="d2089-137">数字</span><span class="sxs-lookup"><span data-stu-id="d2089-137">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d2089-138">说明</span><span class="sxs-lookup"><span data-stu-id="d2089-138">Remarks</span></span>

<span data-ttu-id="d2089-139">每一条直线都可以定义为一个点 (*x,y*) 和一个角。</span><span class="sxs-lookup"><span data-stu-id="d2089-139">Each line is defined as a point (*x,y*) and an angle.</span></span> 
  
<span data-ttu-id="d2089-140">Microsoft Visio 在粘附到旋转参考线的形状的 PinY 单元格中使用此函数。</span><span class="sxs-lookup"><span data-stu-id="d2089-140">Microsoft Visio uses this function in the PinY cell of a shape glued to a rotated guide.</span></span> 
  
<span data-ttu-id="d2089-141">如果直线未相交，则该函数将返回被零除错误 (#DIV/0!)，Visio 将忽略此错误，并还原该点的前一个已知值。</span><span class="sxs-lookup"><span data-stu-id="d2089-141">If the lines don't intersect, the function returns a divide-by-zero error (#DIV/0!), which Visio ignores, restoring the last known value for the point.</span></span> 
  
## <a name="example"></a><span data-ttu-id="d2089-142">示例</span><span class="sxs-lookup"><span data-stu-id="d2089-142">Example</span></span>

<span data-ttu-id="d2089-143">INTERSECTY (VertGuide!PinX、VertGuide!PinY、VertGuide!角、用 horzguide!PinX、用 horzguide!PinY、用 horzguide!Angle</span><span class="sxs-lookup"><span data-stu-id="d2089-143">INTERSECTY(VertGuide!PinX,VertGuide!PinY,VertGuide!Angle, HorzGuide!PinX,HorzGuide!PinY,HorzGuide!Angle)</span></span> 
  
<span data-ttu-id="d2089-144">返回 VertGuide 和用 horzguide 的交集点的*y*坐标 (以页面单位表示)。</span><span class="sxs-lookup"><span data-stu-id="d2089-144">Returns the  *y*  -coordinate of the intersection point of VertGuide and HorzGuide in page units.</span></span> 
  

