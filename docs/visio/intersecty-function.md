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
description: 返回 y-两个线相交的点的坐标 （以本地坐标系表示）。
ms.openlocfilehash: c3c0e9afef317ed4c647f1d236c4c3a29c6cdaa6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780460"
---
# <a name="intersecty-function"></a><span data-ttu-id="5496b-103">INTERSECTY 函数</span><span class="sxs-lookup"><span data-stu-id="5496b-103">INTERSECTY Function</span></span>

<span data-ttu-id="5496b-104">返回*y* -两个线相交的点的坐标 （以本地坐标系表示）。</span><span class="sxs-lookup"><span data-stu-id="5496b-104">Returns the  *y*  -coordinate (in the local coordinate system) of the point where two lines intersect.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5496b-105">语法</span><span class="sxs-lookup"><span data-stu-id="5496b-105">Syntax</span></span>

<span data-ttu-id="5496b-106">INTERSECTX (* * *x1* * *，* * *y1* * *，* **角度 1* * *，* * *x2* * *，* * *y2* * *，* **角度 2* * *)</span><span class="sxs-lookup"><span data-stu-id="5496b-106">INTERSECTX(** *x1* **, ** *y1* **, ** *angle1* **, ** *x2* **, ** *y2* **, ** *angle2* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5496b-107">参数</span><span class="sxs-lookup"><span data-stu-id="5496b-107">Parameters</span></span>

|<span data-ttu-id="5496b-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="5496b-108">**Name**</span></span>|<span data-ttu-id="5496b-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5496b-109">**Required/Optional**</span></span>|<span data-ttu-id="5496b-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5496b-110">**Data Type**</span></span>|<span data-ttu-id="5496b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5496b-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5496b-112">_x1_</span><span class="sxs-lookup"><span data-stu-id="5496b-112">_x1_</span></span> <br/> |<span data-ttu-id="5496b-113">必需</span><span class="sxs-lookup"><span data-stu-id="5496b-113">Required</span></span>  <br/> |<span data-ttu-id="5496b-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="5496b-114">**Number**</span></span> <br/> |<span data-ttu-id="5496b-115">_X_-第一个线上某个点的坐标。</span><span class="sxs-lookup"><span data-stu-id="5496b-115">The  _x_-coordinate of a point on the first line.</span></span>  <br/> |
| <span data-ttu-id="5496b-116">_y1_</span><span class="sxs-lookup"><span data-stu-id="5496b-116">_y1_</span></span> <br/> |<span data-ttu-id="5496b-117">必需</span><span class="sxs-lookup"><span data-stu-id="5496b-117">Required</span></span>  <br/> |<span data-ttu-id="5496b-118">**编号**</span><span class="sxs-lookup"><span data-stu-id="5496b-118">**Number**</span></span> <br/> |<span data-ttu-id="5496b-119">_Y_-第一个线上某个点的坐标。</span><span class="sxs-lookup"><span data-stu-id="5496b-119">The  _y_-coordinate of a point on the first line.</span></span>  <br/> |
| <span data-ttu-id="5496b-120">_角度 1_</span><span class="sxs-lookup"><span data-stu-id="5496b-120">_angle1_</span></span> <br/> |<span data-ttu-id="5496b-121">必需</span><span class="sxs-lookup"><span data-stu-id="5496b-121">Required</span></span>  <br/> |<span data-ttu-id="5496b-122">**编号**</span><span class="sxs-lookup"><span data-stu-id="5496b-122">**Number**</span></span> <br/> | <span data-ttu-id="5496b-123">第一条直线的 Angle 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="5496b-123">The value of the Angle cell for the first line.</span></span>  <br/> |
| <span data-ttu-id="5496b-124">_x2_</span><span class="sxs-lookup"><span data-stu-id="5496b-124">_x2_</span></span> <br/> |<span data-ttu-id="5496b-125">必需</span><span class="sxs-lookup"><span data-stu-id="5496b-125">Required</span></span>  <br/> |<span data-ttu-id="5496b-126">**编号**</span><span class="sxs-lookup"><span data-stu-id="5496b-126">**Number**</span></span> <br/> |<span data-ttu-id="5496b-127">_X_-第二个线上某个点的坐标。</span><span class="sxs-lookup"><span data-stu-id="5496b-127">The  _x_-coordinate of a point on the second line.</span></span>  <br/> |
| <span data-ttu-id="5496b-128">_y2_</span><span class="sxs-lookup"><span data-stu-id="5496b-128">_y2_</span></span> <br/> |<span data-ttu-id="5496b-129">必需</span><span class="sxs-lookup"><span data-stu-id="5496b-129">Required</span></span>  <br/> |<span data-ttu-id="5496b-130">**编号**</span><span class="sxs-lookup"><span data-stu-id="5496b-130">**Number**</span></span> <br/> |<span data-ttu-id="5496b-131">_Y_-第二个线上某个点的坐标。</span><span class="sxs-lookup"><span data-stu-id="5496b-131">The  _y_-coordinate of a point on the second line.</span></span>  <br/> |
| <span data-ttu-id="5496b-132">_角度 2_</span><span class="sxs-lookup"><span data-stu-id="5496b-132">_angle2_</span></span> <br/> |<span data-ttu-id="5496b-133">必需</span><span class="sxs-lookup"><span data-stu-id="5496b-133">Required</span></span>  <br/> |<span data-ttu-id="5496b-134">**编号**</span><span class="sxs-lookup"><span data-stu-id="5496b-134">**Number**</span></span> <br/> |<span data-ttu-id="5496b-135">第二条直线的 Angle 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="5496b-135">The value of the Angle cell for the second line.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5496b-136">返回值</span><span class="sxs-lookup"><span data-stu-id="5496b-136">Return value</span></span>

<span data-ttu-id="5496b-137">Number</span><span class="sxs-lookup"><span data-stu-id="5496b-137">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5496b-138">说明</span><span class="sxs-lookup"><span data-stu-id="5496b-138">Remarks</span></span>

<span data-ttu-id="5496b-139">每一条直线都可以定义为一个点 (*x,y*) 和一个角。</span><span class="sxs-lookup"><span data-stu-id="5496b-139">Each line is defined as a point (*x,y*) and an angle.</span></span> 
  
<span data-ttu-id="5496b-140">Microsoft Visio 在粘附到旋转参考线的形状的 PinY 单元格中使用此函数。</span><span class="sxs-lookup"><span data-stu-id="5496b-140">Microsoft Visio uses this function in the PinY cell of a shape glued to a rotated guide.</span></span> 
  
<span data-ttu-id="5496b-141">如果直线未相交，则该函数将返回被零除错误 (#DIV/0!)，Visio 将忽略此错误，并还原该点的前一个已知值。</span><span class="sxs-lookup"><span data-stu-id="5496b-141">If the lines don't intersect, the function returns a divide-by-zero error (#DIV/0!), which Visio ignores, restoring the last known value for the point.</span></span> 
  
## <a name="example"></a><span data-ttu-id="5496b-142">示例</span><span class="sxs-lookup"><span data-stu-id="5496b-142">Example</span></span>

<span data-ttu-id="5496b-143">INTERSECTY (VertGuide ！PinX，VertGuide ！PinY，VertGuide ！角度，HorzGuide ！PinX，HorzGuide ！PinY，HorzGuide ！角度）</span><span class="sxs-lookup"><span data-stu-id="5496b-143">INTERSECTY(VertGuide!PinX,VertGuide!PinY,VertGuide!Angle, HorzGuide!PinX,HorzGuide!PinY,HorzGuide!Angle)</span></span> 
  
<span data-ttu-id="5496b-144">返回*y* -以页面单位表示的交点 VertGuide 和 HorzGuide 的坐标。</span><span class="sxs-lookup"><span data-stu-id="5496b-144">Returns the  *y*  -coordinate of the intersection point of VertGuide and HorzGuide in page units.</span></span> 
  

