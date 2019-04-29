---
title: GRAVITY 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251433
localization_priority: Normal
ms.assetid: db80f147-71a0-0b23-bc7e-fe1915dfdd21
description: 为指示的形状旋转计算文本块的正确旋转角度, 以防止文本倒置。
ms.openlocfilehash: 77c944d954292e231f8bacbe3c8a4433aad5d689
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429283"
---
# <a name="gravity-function"></a><span data-ttu-id="94fde-103">GRAVITY 函数</span><span class="sxs-lookup"><span data-stu-id="94fde-103">GRAVITY Function</span></span>

<span data-ttu-id="94fde-104">为指示的形状旋转计算文本块的正确旋转角度, 以防止文本倒置。</span><span class="sxs-lookup"><span data-stu-id="94fde-104">Calculates a text block's correct angle of rotation for the indicated shape rotation to prevent the text from turning upside down.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="94fde-105">语法</span><span class="sxs-lookup"><span data-stu-id="94fde-105">Syntax</span></span>

<span data-ttu-id="94fde-106">重力 (\* \* *angle* \* *、[* \**限制 1* \* *]、[* \* *limit2* \* \*])</span><span class="sxs-lookup"><span data-stu-id="94fde-106">GRAVITY(\*\* *angle* \*\*,[ \*\* *limit1* \*\* ],[ \*\* *limit2* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="94fde-107">参数</span><span class="sxs-lookup"><span data-stu-id="94fde-107">Parameters</span></span>

|<span data-ttu-id="94fde-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="94fde-108">**Name**</span></span>|<span data-ttu-id="94fde-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="94fde-109">**Required/Optional**</span></span>|<span data-ttu-id="94fde-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="94fde-110">**Data Type**</span></span>|<span data-ttu-id="94fde-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="94fde-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="94fde-112">_angle_</span><span class="sxs-lookup"><span data-stu-id="94fde-112">_angle_</span></span> <br/> |<span data-ttu-id="94fde-113">必需</span><span class="sxs-lookup"><span data-stu-id="94fde-113">Required</span></span>  <br/> |<span data-ttu-id="94fde-114">**String**</span><span class="sxs-lookup"><span data-stu-id="94fde-114">**String**</span></span> <br/> | <span data-ttu-id="94fde-115">形状的角度。</span><span class="sxs-lookup"><span data-stu-id="94fde-115">The shape's angle.</span></span>  <br/> |
| <span data-ttu-id="94fde-116">_限制1_</span><span class="sxs-lookup"><span data-stu-id="94fde-116">_limit1_</span></span> <br/> |<span data-ttu-id="94fde-117">可选</span><span class="sxs-lookup"><span data-stu-id="94fde-117">Optional</span></span>  <br/> |<span data-ttu-id="94fde-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="94fde-118">**String**</span></span> <br/> |<span data-ttu-id="94fde-119">第一个旋转限制条件。</span><span class="sxs-lookup"><span data-stu-id="94fde-119">First limit of rotation.</span></span> <span data-ttu-id="94fde-120">默认值为 90 度。</span><span class="sxs-lookup"><span data-stu-id="94fde-120">Default is 90 degrees.</span></span>  <br/> |
| <span data-ttu-id="94fde-121">_limit2_</span><span class="sxs-lookup"><span data-stu-id="94fde-121">_limit2_</span></span> <br/> |<span data-ttu-id="94fde-122">可选</span><span class="sxs-lookup"><span data-stu-id="94fde-122">Optional</span></span>  <br/> |<span data-ttu-id="94fde-123">**字符串**</span><span class="sxs-lookup"><span data-stu-id="94fde-123">**String**</span></span> <br/> |<span data-ttu-id="94fde-124">第二个旋转限制条件。</span><span class="sxs-lookup"><span data-stu-id="94fde-124">Second limit of rotation.</span></span> <span data-ttu-id="94fde-125">默认值为 270 度。</span><span class="sxs-lookup"><span data-stu-id="94fde-125">Default is 270 degrees.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="94fde-126">返回值</span><span class="sxs-lookup"><span data-stu-id="94fde-126">Return value</span></span>

<span data-ttu-id="94fde-127">String</span><span class="sxs-lookup"><span data-stu-id="94fde-127">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="94fde-128">说明</span><span class="sxs-lookup"><span data-stu-id="94fde-128">Remarks</span></span>

<span data-ttu-id="94fde-129">GRAVITY 函数通常在 TxtAngle 单元格中使用。</span><span class="sxs-lookup"><span data-stu-id="94fde-129">The GRAVITY function is usually used in the TxtAngle cell.</span></span> 
  
<span data-ttu-id="94fde-130">如果_angle_值介于_限制 1_和_limit2_指定的值之间, 则返回的值为180度;否则, 返回的值为0度。</span><span class="sxs-lookup"><span data-stu-id="94fde-130">The value returned is 180 degrees if  _angle_ is between the values specified by  _limit1_ and  _limit2_; otherwise the value returned is 0 degrees.</span></span>
  
<span data-ttu-id="94fde-131">所有参数都由该函数在 0 和 360 度之间自动规范化。</span><span class="sxs-lookup"><span data-stu-id="94fde-131">All of the arguments are automatically normalized between 0 and 360 degrees by the function.</span></span> <span data-ttu-id="94fde-132">如果参数未指定单位，则假定为弧度。</span><span class="sxs-lookup"><span data-stu-id="94fde-132">If an argument does not specify units, radians are assumed.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="94fde-133">示例 1</span><span class="sxs-lookup"><span data-stu-id="94fde-133">Example 1</span></span>

<span data-ttu-id="94fde-134">重力 (角)</span><span class="sxs-lookup"><span data-stu-id="94fde-134">GRAVITY(Angle)</span></span>
  
<span data-ttu-id="94fde-135">如果*angle*介于90和270度之间, 则返回180度;否则, 返回0度。</span><span class="sxs-lookup"><span data-stu-id="94fde-135">Returns 180 degrees if  *angle*  is between 90 and 270 degrees; otherwise, returns 0 degrees.</span></span> 
  
## <a name="example-2"></a><span data-ttu-id="94fde-136">示例 2</span><span class="sxs-lookup"><span data-stu-id="94fde-136">Example 2</span></span>

<span data-ttu-id="94fde-137">重力 (2)</span><span class="sxs-lookup"><span data-stu-id="94fde-137">GRAVITY(2)</span></span>
  
<span data-ttu-id="94fde-138">返回 180 度，因为 2 弧度介于 90 至 270 度之间。</span><span class="sxs-lookup"><span data-stu-id="94fde-138">Returns 180 degrees, because 2 radians is between 90 and 270 degrees.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="94fde-139">示例 3</span><span class="sxs-lookup"><span data-stu-id="94fde-139">Example 3</span></span>

<span data-ttu-id="94fde-140">GRAVITY(100 deg, 110 deg, 290 deg)</span><span class="sxs-lookup"><span data-stu-id="94fde-140">GRAVITY(100 deg, 110 deg, 290 deg)</span></span>
  
<span data-ttu-id="94fde-141">返回 0 度。</span><span class="sxs-lookup"><span data-stu-id="94fde-141">Returns 0 degrees.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="94fde-142">示例 4</span><span class="sxs-lookup"><span data-stu-id="94fde-142">Example 4</span></span>

<span data-ttu-id="94fde-143">GRAVITY(100 deg, 290 deg, 110 deg)</span><span class="sxs-lookup"><span data-stu-id="94fde-143">GRAVITY(100 deg, 290 deg, 110 deg)</span></span>
  
<span data-ttu-id="94fde-144">返回 0 度。</span><span class="sxs-lookup"><span data-stu-id="94fde-144">Returns 0 degrees.</span></span>
  

