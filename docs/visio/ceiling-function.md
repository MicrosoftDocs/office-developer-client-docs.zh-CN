---
title: CEILING 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251405
localization_priority: Normal
ms.assetid: 1a8d6d48-7ae3-5483-28d2-5b1706088a53
description: 将数字从 0（零）后舍入到 multiple 的下一个实例。如果未指定 multiple，会将数字从 0 后舍入到下一个整数。
ms.openlocfilehash: 449f17d1b68c116cccb2635723a3f6277d0ac2a9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404125"
---
# <a name="ceiling-function"></a><span data-ttu-id="0cbd1-104">CEILING 函数</span><span class="sxs-lookup"><span data-stu-id="0cbd1-104">CEILING Function</span></span>

<span data-ttu-id="0cbd1-105">将数字从 0 舍入 (零) 多个 的下一  _个实例_。</span><span class="sxs-lookup"><span data-stu-id="0cbd1-105">Rounds a number away from 0 (zero) to the next instance of  _multiple_.</span></span> <span data-ttu-id="0cbd1-106">如果  _未指定 multiple，_ 则数字从 0 舍入到下一个整数。</span><span class="sxs-lookup"><span data-stu-id="0cbd1-106">If  _multiple_ is not specified, the number rounds away from 0 to the next integer.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0cbd1-107">语法</span><span class="sxs-lookup"><span data-stu-id="0cbd1-107">Syntax</span></span>

<span data-ttu-id="0cbd1-108">CEILING (\*\* *number* \*\*， \*\* *multiple* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="0cbd1-108">CEILING(\*\* *number* \*\*, \*\* *multiple* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="0cbd1-109">参数</span><span class="sxs-lookup"><span data-stu-id="0cbd1-109">Parameters</span></span>

|<span data-ttu-id="0cbd1-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="0cbd1-110">**Name**</span></span>|<span data-ttu-id="0cbd1-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="0cbd1-111">**Required/Optional**</span></span>|<span data-ttu-id="0cbd1-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0cbd1-112">**Data Type**</span></span>|<span data-ttu-id="0cbd1-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="0cbd1-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0cbd1-114">_number_</span><span class="sxs-lookup"><span data-stu-id="0cbd1-114">_number_</span></span> <br/> |<span data-ttu-id="0cbd1-115">必需</span><span class="sxs-lookup"><span data-stu-id="0cbd1-115">Required</span></span>  <br/> |<span data-ttu-id="0cbd1-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="0cbd1-116">**Number**</span></span> <br/> |<span data-ttu-id="0cbd1-117">要舍入的数字。</span><span class="sxs-lookup"><span data-stu-id="0cbd1-117">The number to round.</span></span>  <br/> |
| <span data-ttu-id="0cbd1-118">_multiple_</span><span class="sxs-lookup"><span data-stu-id="0cbd1-118">_multiple_</span></span> <br/> |<span data-ttu-id="0cbd1-119">必需</span><span class="sxs-lookup"><span data-stu-id="0cbd1-119">Required</span></span>  <br/> |<span data-ttu-id="0cbd1-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="0cbd1-120">**Number**</span></span> <br/> |<span data-ttu-id="0cbd1-121">要舍入到的倍数。</span><span class="sxs-lookup"><span data-stu-id="0cbd1-121">The multiple to round to.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0cbd1-122">备注</span><span class="sxs-lookup"><span data-stu-id="0cbd1-122">Remarks</span></span>

 <span data-ttu-id="0cbd1-123">_Number_ 和  _multiple_ 必须具有相同的符号，否则#NUM！</span><span class="sxs-lookup"><span data-stu-id="0cbd1-123">_Number_ and  _multiple_ must have the same signs, or a #NUM!</span></span> <span data-ttu-id="0cbd1-124">错误。</span><span class="sxs-lookup"><span data-stu-id="0cbd1-124">error is returned.</span></span> <span data-ttu-id="0cbd1-125">如果 _数字或__多个_ 不能转换为值，则#VALUE！</span><span class="sxs-lookup"><span data-stu-id="0cbd1-125">If either  _number_ or  _multiple_ cannot be converted to a value, a #VALUE!</span></span> <span data-ttu-id="0cbd1-126">错误。</span><span class="sxs-lookup"><span data-stu-id="0cbd1-126">error is returned.</span></span> <span data-ttu-id="0cbd1-127">如果  _number_ 或  _multiple_ 为 0，则结果为 0。</span><span class="sxs-lookup"><span data-stu-id="0cbd1-127">If either  _number_ or  _multiple_ is 0, the result is 0.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="0cbd1-128">示例 1</span><span class="sxs-lookup"><span data-stu-id="0cbd1-128">Example 1</span></span>

<span data-ttu-id="0cbd1-129">CEILING (3.7) </span><span class="sxs-lookup"><span data-stu-id="0cbd1-129">CEILING(3.7)</span></span>
  
<span data-ttu-id="0cbd1-130">返回 4</span><span class="sxs-lookup"><span data-stu-id="0cbd1-130">Returns 4</span></span>
  
## <a name="example-2"></a><span data-ttu-id="0cbd1-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="0cbd1-131">Example 2</span></span>

<span data-ttu-id="0cbd1-132">CEILING (-3.7) </span><span class="sxs-lookup"><span data-stu-id="0cbd1-132">CEILING(-3.7)</span></span>
  
<span data-ttu-id="0cbd1-133">返回 -4</span><span class="sxs-lookup"><span data-stu-id="0cbd1-133">Returns -4</span></span>
  
## <a name="example-3"></a><span data-ttu-id="0cbd1-134">示例 3</span><span class="sxs-lookup"><span data-stu-id="0cbd1-134">Example 3</span></span>

<span data-ttu-id="0cbd1-135">CEILING (3.7， 0.25) </span><span class="sxs-lookup"><span data-stu-id="0cbd1-135">CEILING(3.7, 0.25)</span></span>
  
<span data-ttu-id="0cbd1-136">返回 3.75</span><span class="sxs-lookup"><span data-stu-id="0cbd1-136">Returns 3.75</span></span>
  

