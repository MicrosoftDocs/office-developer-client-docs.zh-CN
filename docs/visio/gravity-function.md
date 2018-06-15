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
description: 计算文本块的正确的要防止颠倒文本的指定的形状旋转的旋转角度。
ms.openlocfilehash: 0d8b0160c7e7d63fb5a272219a2694d35e6e6b61
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19780356"
---
# <a name="gravity-function"></a><span data-ttu-id="e2b13-103">GRAVITY 函数</span><span class="sxs-lookup"><span data-stu-id="e2b13-103">GRAVITY Function</span></span>

<span data-ttu-id="e2b13-104">计算文本块的正确的要防止颠倒文本的指定的形状旋转的旋转角度。</span><span class="sxs-lookup"><span data-stu-id="e2b13-104">Calculates a text block's correct angle of rotation for the indicated shape rotation to prevent the text from turning upside down.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e2b13-105">语法</span><span class="sxs-lookup"><span data-stu-id="e2b13-105">Syntax</span></span>

<span data-ttu-id="e2b13-106">GRAVITY (* **角度** *，[* **介于 limit1* * *]，[* * *limit2* * *])</span><span class="sxs-lookup"><span data-stu-id="e2b13-106">GRAVITY(** *angle* **,[ ** *limit1* ** ],[ ** *limit2* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e2b13-107">参数</span><span class="sxs-lookup"><span data-stu-id="e2b13-107">Parameters</span></span>

|<span data-ttu-id="e2b13-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="e2b13-108">**Name**</span></span>|<span data-ttu-id="e2b13-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e2b13-109">**Required/Optional**</span></span>|<span data-ttu-id="e2b13-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e2b13-110">**Data Type**</span></span>|<span data-ttu-id="e2b13-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e2b13-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e2b13-112">_角度_</span><span class="sxs-lookup"><span data-stu-id="e2b13-112">_angle_</span></span> <br/> |<span data-ttu-id="e2b13-113">必需</span><span class="sxs-lookup"><span data-stu-id="e2b13-113">Required</span></span>  <br/> |<span data-ttu-id="e2b13-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="e2b13-114">**String**</span></span> <br/> | <span data-ttu-id="e2b13-115">形状的角度。</span><span class="sxs-lookup"><span data-stu-id="e2b13-115">The shape's angle.</span></span>  <br/> |
| <span data-ttu-id="e2b13-116">_介于 limit1_</span><span class="sxs-lookup"><span data-stu-id="e2b13-116">_limit1_</span></span> <br/> |<span data-ttu-id="e2b13-117">可选</span><span class="sxs-lookup"><span data-stu-id="e2b13-117">Optional</span></span>  <br/> |<span data-ttu-id="e2b13-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="e2b13-118">**String**</span></span> <br/> |<span data-ttu-id="e2b13-p101">第一个旋转限制条件。默认值为 90 度。</span><span class="sxs-lookup"><span data-stu-id="e2b13-p101">First limit of rotation. Default is 90 degrees.</span></span>  <br/> |
| <span data-ttu-id="e2b13-121">_limit2_</span><span class="sxs-lookup"><span data-stu-id="e2b13-121">_limit2_</span></span> <br/> |<span data-ttu-id="e2b13-122">可选</span><span class="sxs-lookup"><span data-stu-id="e2b13-122">Optional</span></span>  <br/> |<span data-ttu-id="e2b13-123">**字符串**</span><span class="sxs-lookup"><span data-stu-id="e2b13-123">**String**</span></span> <br/> |<span data-ttu-id="e2b13-p102">第二个旋转限制条件。默认值为 270 度。</span><span class="sxs-lookup"><span data-stu-id="e2b13-p102">Second limit of rotation. Default is 270 degrees.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="e2b13-126">返回值</span><span class="sxs-lookup"><span data-stu-id="e2b13-126">Return value</span></span>

<span data-ttu-id="e2b13-127">String</span><span class="sxs-lookup"><span data-stu-id="e2b13-127">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e2b13-128">注解</span><span class="sxs-lookup"><span data-stu-id="e2b13-128">Remarks</span></span>

<span data-ttu-id="e2b13-129">GRAVITY 函数通常在 TxtAngle 单元格中使用。</span><span class="sxs-lookup"><span data-stu-id="e2b13-129">The GRAVITY function is usually used in the TxtAngle cell.</span></span> 
  
<span data-ttu-id="e2b13-130">如果_angle_ _介于 limit1_和_limit2_; 指定的值之间，则，返回的值是 180 度否则，返回的值是 0 度。</span><span class="sxs-lookup"><span data-stu-id="e2b13-130">The value returned is 180 degrees if  _angle_ is between the values specified by  _limit1_ and  _limit2_; otherwise the value returned is 0 degrees.</span></span>
  
<span data-ttu-id="e2b13-p103">所有参数都由该函数在 0 和 360 度之间自动规范化。如果参数未指定单位，则假定为弧度。</span><span class="sxs-lookup"><span data-stu-id="e2b13-p103">All of the arguments are automatically normalized between 0 and 360 degrees by the function. If an argument does not specify units, radians are assumed.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="e2b13-133">示例 1</span><span class="sxs-lookup"><span data-stu-id="e2b13-133">Example 1</span></span>

<span data-ttu-id="e2b13-134">GRAVITY(Angle)</span><span class="sxs-lookup"><span data-stu-id="e2b13-134">GRAVITY(Angle)</span></span>
  
<span data-ttu-id="e2b13-135">返回 180 度如果*angle*介于 90 至 270 度;否则，返回 0 度。</span><span class="sxs-lookup"><span data-stu-id="e2b13-135">Returns 180 degrees if  *angle*  is between 90 and 270 degrees; otherwise, returns 0 degrees.</span></span> 
  
## <a name="example-2"></a><span data-ttu-id="e2b13-136">示例 2</span><span class="sxs-lookup"><span data-stu-id="e2b13-136">Example 2</span></span>

<span data-ttu-id="e2b13-137">GRAVITY(2)</span><span class="sxs-lookup"><span data-stu-id="e2b13-137">GRAVITY(2)</span></span>
  
<span data-ttu-id="e2b13-138">返回 180 度，因为 2 弧度介于 90 至 270 度之间。</span><span class="sxs-lookup"><span data-stu-id="e2b13-138">Returns 180 degrees, because 2 radians is between 90 and 270 degrees.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="e2b13-139">示例 3</span><span class="sxs-lookup"><span data-stu-id="e2b13-139">Example 3</span></span>

<span data-ttu-id="e2b13-140">GRAVITY(100 deg, 110 deg, 290 deg)</span><span class="sxs-lookup"><span data-stu-id="e2b13-140">GRAVITY(100 deg, 110 deg, 290 deg)</span></span>
  
<span data-ttu-id="e2b13-141">返回 0 度。</span><span class="sxs-lookup"><span data-stu-id="e2b13-141">Returns 0 degrees.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="e2b13-142">示例 4</span><span class="sxs-lookup"><span data-stu-id="e2b13-142">Example 4</span></span>

<span data-ttu-id="e2b13-143">GRAVITY(100 deg, 290 deg, 110 deg)</span><span class="sxs-lookup"><span data-stu-id="e2b13-143">GRAVITY(100 deg, 290 deg, 110 deg)</span></span>
  
<span data-ttu-id="e2b13-144">返回 0 度。</span><span class="sxs-lookup"><span data-stu-id="e2b13-144">Returns 0 degrees.</span></span>
  

