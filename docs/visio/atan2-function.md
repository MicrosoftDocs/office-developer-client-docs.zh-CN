---
title: ATAN2 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251397
localization_priority: Normal
ms.assetid: 524278fb-196e-9cf9-e27b-d03642beeee4
description: 返回由 x、y 和 x 轴方向表示的向量之间的角度。 结果是用当前的角度度量单位表示的数值。
ms.openlocfilehash: 906c024f2a78d6e11c1bbf770c14d04299cadca8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436480"
---
# <a name="atan2-function"></a><span data-ttu-id="1a36f-104">ATAN2 函数</span><span class="sxs-lookup"><span data-stu-id="1a36f-104">ATAN2 Function</span></span>

<span data-ttu-id="1a36f-105">返回由*x、y*和*x*轴方向表示的向量之间的角度。</span><span class="sxs-lookup"><span data-stu-id="1a36f-105">Returns the angle between the vector represented by  *x,y*  and the direction of the  *x*  -axis.</span></span> <span data-ttu-id="1a36f-106">结果是用当前的角度度量单位表示的数值。</span><span class="sxs-lookup"><span data-stu-id="1a36f-106">The result is a number in the current unit of measure for angles.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1a36f-107">语法</span><span class="sxs-lookup"><span data-stu-id="1a36f-107">Syntax</span></span>

<span data-ttu-id="1a36f-108">ATAN2 (\* \* *y* \* \*, \* \* *x* \* \*)</span><span class="sxs-lookup"><span data-stu-id="1a36f-108">ATAN2(\*\* *y* \*\*, \*\* *x* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1a36f-109">参数</span><span class="sxs-lookup"><span data-stu-id="1a36f-109">Parameters</span></span>

|<span data-ttu-id="1a36f-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="1a36f-110">**Name**</span></span>|<span data-ttu-id="1a36f-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1a36f-111">**Required/Optional**</span></span>|<span data-ttu-id="1a36f-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1a36f-112">**Data Type**</span></span>|<span data-ttu-id="1a36f-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="1a36f-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1a36f-114">_y_</span><span class="sxs-lookup"><span data-stu-id="1a36f-114">_y_</span></span> <br/> |<span data-ttu-id="1a36f-115">必需</span><span class="sxs-lookup"><span data-stu-id="1a36f-115">Required</span></span>  <br/> |<span data-ttu-id="1a36f-116">**数值**</span><span class="sxs-lookup"><span data-stu-id="1a36f-116">**Numeric**</span></span> <br/> |<span data-ttu-id="1a36f-117">点的_y_值。</span><span class="sxs-lookup"><span data-stu-id="1a36f-117">The  _y_-value of the point.</span></span>  <br/> |
| <span data-ttu-id="1a36f-118">_x_</span><span class="sxs-lookup"><span data-stu-id="1a36f-118">_x_</span></span> <br/> |<span data-ttu-id="1a36f-119">必需</span><span class="sxs-lookup"><span data-stu-id="1a36f-119">Required</span></span>  <br/> |<span data-ttu-id="1a36f-120">**数值**</span><span class="sxs-lookup"><span data-stu-id="1a36f-120">**Numeric**</span></span> <br/> |<span data-ttu-id="1a36f-121">点的_x_值。</span><span class="sxs-lookup"><span data-stu-id="1a36f-121">The  _x_-value of the point.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1a36f-122">说明</span><span class="sxs-lookup"><span data-stu-id="1a36f-122">Remarks</span></span>

<span data-ttu-id="1a36f-123">反正切值是从正*x*轴到与原点 (0, 0) 和由*x*和*y*表示的点相交的直线的逆时针测量角。</span><span class="sxs-lookup"><span data-stu-id="1a36f-123">The arctangent is the angle measured counterclockwise from the positive  *x*  -axis to a line that intersects the origin (0,0) and the point represented by  *x*  and  *y*  .</span></span> <span data-ttu-id="1a36f-124">在 Microsoft Visio 中，ATAN2(0,0) 返回 0。</span><span class="sxs-lookup"><span data-stu-id="1a36f-124">In Microsoft Visio, ATAN2(0,0) returns 0.</span></span> <span data-ttu-id="1a36f-125">若要将 ATAN2 结果强制为其他角度度量单位，请使用 DEG 或 RAD 函数。</span><span class="sxs-lookup"><span data-stu-id="1a36f-125">To force the result of ATAN2 into a different angular measurement, use the DEG or RAD function.</span></span> 
  
<span data-ttu-id="1a36f-126">ATAN2 函数是 TAN 函数的 antifunction。</span><span class="sxs-lookup"><span data-stu-id="1a36f-126">The ATAN2 function is the antifunction of the TAN function.</span></span> <span data-ttu-id="1a36f-127">ATAN2 函数返回角度等于*y*除以*x*的角的角度。</span><span class="sxs-lookup"><span data-stu-id="1a36f-127">The ATAN2 function returns the angle whose angle is equal to  *y*  divided by  *x*  .</span></span> <span data-ttu-id="1a36f-128">如果 ATAN2 (*y, x*) 表示直角三角形中的角度, 则*y*是 "相对边", *x*是 "相邻侧", 因此函数可以编写为 ATAN2 (反向, 相邻)。</span><span class="sxs-lookup"><span data-stu-id="1a36f-128">If ATAN2(*y,x*) represents an angle in a right triangle,  *y*  is the "opposite side" and  *x*  is the "adjacent side," so the function could be written as ATAN2(opposite,adjacent).</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="1a36f-129">示例 1</span><span class="sxs-lookup"><span data-stu-id="1a36f-129">Example 1</span></span>

<span data-ttu-id="1a36f-130">ATAN2 (1.25, 2.25)</span><span class="sxs-lookup"><span data-stu-id="1a36f-130">ATAN2(1.25,2.25)</span></span>
  
<span data-ttu-id="1a36f-131">返回 29.0456 度</span><span class="sxs-lookup"><span data-stu-id="1a36f-131">Returns 29.0456 deg</span></span>
  
## <a name="example-2"></a><span data-ttu-id="1a36f-132">示例 2</span><span class="sxs-lookup"><span data-stu-id="1a36f-132">Example 2</span></span>

<span data-ttu-id="1a36f-133">ATAN2 (1, SQRT (3))</span><span class="sxs-lookup"><span data-stu-id="1a36f-133">ATAN2(1,SQRT(3))</span></span>
  
<span data-ttu-id="1a36f-134">返回 30 度</span><span class="sxs-lookup"><span data-stu-id="1a36f-134">Returns 30 deg</span></span>
  
## <a name="example-3"></a><span data-ttu-id="1a36f-135">示例 3</span><span class="sxs-lookup"><span data-stu-id="1a36f-135">Example 3</span></span>

<span data-ttu-id="1a36f-136">ATAN2 (1, 1)</span><span class="sxs-lookup"><span data-stu-id="1a36f-136">ATAN2(1,1)</span></span>
  
<span data-ttu-id="1a36f-137">返回 45 度</span><span class="sxs-lookup"><span data-stu-id="1a36f-137">Returns 45 deg</span></span>
  

