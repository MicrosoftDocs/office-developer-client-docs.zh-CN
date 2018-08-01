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
description: 返回表示由 x 的向量之间的角度 y 和 x 方向-轴。 结果是度量的当前单位角度的数字。
ms.openlocfilehash: dfd62ce628a3a46ff14b3ffc3f07074a39c66e14
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779641"
---
# <a name="atan2-function"></a><span data-ttu-id="72698-104">ATAN2 函数</span><span class="sxs-lookup"><span data-stu-id="72698-104">ATAN2 Function</span></span>

<span data-ttu-id="72698-105">返回表示的*x，y*和*x*方向的向量之间的角度-轴。</span><span class="sxs-lookup"><span data-stu-id="72698-105">Returns the angle between the vector represented by  *x,y*  and the direction of the  *x*  -axis.</span></span> <span data-ttu-id="72698-106">结果是度量的当前单位角度的数字。</span><span class="sxs-lookup"><span data-stu-id="72698-106">The result is a number in the current unit of measure for angles.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="72698-107">语法</span><span class="sxs-lookup"><span data-stu-id="72698-107">Syntax</span></span>

<span data-ttu-id="72698-108">ATAN2 (* * *y* * *，* * *x* * *)</span><span class="sxs-lookup"><span data-stu-id="72698-108">ATAN2(** *y* **, ** *x* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="72698-109">参数</span><span class="sxs-lookup"><span data-stu-id="72698-109">Parameters</span></span>

|<span data-ttu-id="72698-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="72698-110">**Name**</span></span>|<span data-ttu-id="72698-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="72698-111">**Required/Optional**</span></span>|<span data-ttu-id="72698-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="72698-112">**Data Type**</span></span>|<span data-ttu-id="72698-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="72698-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="72698-114">_y_</span><span class="sxs-lookup"><span data-stu-id="72698-114">_y_</span></span> <br/> |<span data-ttu-id="72698-115">必需</span><span class="sxs-lookup"><span data-stu-id="72698-115">Required</span></span>  <br/> |<span data-ttu-id="72698-116">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="72698-116">**Numeric**</span></span> <br/> |<span data-ttu-id="72698-117">_Y_-点的值。</span><span class="sxs-lookup"><span data-stu-id="72698-117">The  _y_-value of the point.</span></span>  <br/> |
| <span data-ttu-id="72698-118">_x_</span><span class="sxs-lookup"><span data-stu-id="72698-118">_x_</span></span> <br/> |<span data-ttu-id="72698-119">必需</span><span class="sxs-lookup"><span data-stu-id="72698-119">Required</span></span>  <br/> |<span data-ttu-id="72698-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="72698-120">**Numeric**</span></span> <br/> |<span data-ttu-id="72698-121">_X_-点的值。</span><span class="sxs-lookup"><span data-stu-id="72698-121">The  _x_-value of the point.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="72698-122">说明</span><span class="sxs-lookup"><span data-stu-id="72698-122">Remarks</span></span>

<span data-ttu-id="72698-123">反正切值是从误报*x*逆时针开始算起的角度-轴相交原点 (0，0) 和*x*和*y*由表示的点的行。</span><span class="sxs-lookup"><span data-stu-id="72698-123">The arctangent is the angle measured counterclockwise from the positive  *x*  -axis to a line that intersects the origin (0,0) and the point represented by  *x*  and  *y*  .</span></span> <span data-ttu-id="72698-124">在 Microsoft Visio ATAN2(0,0) 返回 0。</span><span class="sxs-lookup"><span data-stu-id="72698-124">In Microsoft Visio, ATAN2(0,0) returns 0.</span></span> <span data-ttu-id="72698-125">若要强制 ATAN2 到不同的角度度量的结果，请使用度或 RAD 函数。</span><span class="sxs-lookup"><span data-stu-id="72698-125">To force the result of ATAN2 into a different angular measurement, use the DEG or RAD function.</span></span> 
  
<span data-ttu-id="72698-126">ATAN2 函数是 TAN 函数 antifunction。</span><span class="sxs-lookup"><span data-stu-id="72698-126">The ATAN2 function is the antifunction of the TAN function.</span></span> <span data-ttu-id="72698-127">ATAN2 函数返回其角度等于*y*除以*x*的角度。</span><span class="sxs-lookup"><span data-stu-id="72698-127">The ATAN2 function returns the angle whose angle is equal to  *y*  divided by  *x*  .</span></span> <span data-ttu-id="72698-128">如果 ATAN2 （*y，x*） 表示角度直角三角形中的、 *y*是"另一侧"和*x*是"相邻端"，因此无法为 ATAN2(opposite,adjacent) 写入函数。</span><span class="sxs-lookup"><span data-stu-id="72698-128">If ATAN2(*y,x*) represents an angle in a right triangle,  *y*  is the "opposite side" and  *x*  is the "adjacent side," so the function could be written as ATAN2(opposite,adjacent).</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="72698-129">示例 1</span><span class="sxs-lookup"><span data-stu-id="72698-129">Example 1</span></span>

<span data-ttu-id="72698-130">ATAN2(1.25,2.25)</span><span class="sxs-lookup"><span data-stu-id="72698-130">ATAN2(1.25,2.25)</span></span>
  
<span data-ttu-id="72698-131">返回 29.0456 度</span><span class="sxs-lookup"><span data-stu-id="72698-131">Returns 29.0456 deg</span></span>
  
## <a name="example-2"></a><span data-ttu-id="72698-132">示例 2</span><span class="sxs-lookup"><span data-stu-id="72698-132">Example 2</span></span>

<span data-ttu-id="72698-133">ATAN2(1,SQRT(3))</span><span class="sxs-lookup"><span data-stu-id="72698-133">ATAN2(1,SQRT(3))</span></span>
  
<span data-ttu-id="72698-134">返回 30 度</span><span class="sxs-lookup"><span data-stu-id="72698-134">Returns 30 deg</span></span>
  
## <a name="example-3"></a><span data-ttu-id="72698-135">示例 3</span><span class="sxs-lookup"><span data-stu-id="72698-135">Example 3</span></span>

<span data-ttu-id="72698-136">ATAN2(1,1)</span><span class="sxs-lookup"><span data-stu-id="72698-136">ATAN2(1,1)</span></span>
  
<span data-ttu-id="72698-137">返回 45 度</span><span class="sxs-lookup"><span data-stu-id="72698-137">Returns 45 deg</span></span>
  

