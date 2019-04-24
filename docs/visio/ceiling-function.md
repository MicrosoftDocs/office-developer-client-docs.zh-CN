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
description: 将数字从 0（零）后舍入到 multiple 的下一个实例。 如果未指定 multiple，会将数字从 0 后舍入到下一个整数。
ms.openlocfilehash: 449f17d1b68c116cccb2635723a3f6277d0ac2a9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337224"
---
# <a name="ceiling-function"></a><span data-ttu-id="66eeb-104">CEILING 函数</span><span class="sxs-lookup"><span data-stu-id="66eeb-104">CEILING Function</span></span>

<span data-ttu-id="66eeb-105">将数字从 0 (零) 舍入到下一个_多个_实例。</span><span class="sxs-lookup"><span data-stu-id="66eeb-105">Rounds a number away from 0 (zero) to the next instance of  _multiple_.</span></span> <span data-ttu-id="66eeb-106">如果未指定_多个_, 则该数字将从0舍入到下一个整数。</span><span class="sxs-lookup"><span data-stu-id="66eeb-106">If  _multiple_ is not specified, the number rounds away from 0 to the next integer.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="66eeb-107">语法</span><span class="sxs-lookup"><span data-stu-id="66eeb-107">Syntax</span></span>

<span data-ttu-id="66eeb-108">天花板 (\* \* *number* \* *、* **多** \*)</span><span class="sxs-lookup"><span data-stu-id="66eeb-108">CEILING(\*\* *number* \*\*, \*\* *multiple* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="66eeb-109">参数</span><span class="sxs-lookup"><span data-stu-id="66eeb-109">Parameters</span></span>

|<span data-ttu-id="66eeb-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="66eeb-110">**Name**</span></span>|<span data-ttu-id="66eeb-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="66eeb-111">**Required/Optional**</span></span>|<span data-ttu-id="66eeb-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="66eeb-112">**Data Type**</span></span>|<span data-ttu-id="66eeb-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="66eeb-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="66eeb-114">_number_</span><span class="sxs-lookup"><span data-stu-id="66eeb-114">_number_</span></span> <br/> |<span data-ttu-id="66eeb-115">必需</span><span class="sxs-lookup"><span data-stu-id="66eeb-115">Required</span></span>  <br/> |<span data-ttu-id="66eeb-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="66eeb-116">**Number**</span></span> <br/> |<span data-ttu-id="66eeb-117">要舍入的数字。</span><span class="sxs-lookup"><span data-stu-id="66eeb-117">The number to round.</span></span>  <br/> |
| <span data-ttu-id="66eeb-118">_多位_</span><span class="sxs-lookup"><span data-stu-id="66eeb-118">_multiple_</span></span> <br/> |<span data-ttu-id="66eeb-119">必需</span><span class="sxs-lookup"><span data-stu-id="66eeb-119">Required</span></span>  <br/> |<span data-ttu-id="66eeb-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="66eeb-120">**Number**</span></span> <br/> |<span data-ttu-id="66eeb-121">要舍入到的倍数。</span><span class="sxs-lookup"><span data-stu-id="66eeb-121">The multiple to round to.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="66eeb-122">注解</span><span class="sxs-lookup"><span data-stu-id="66eeb-122">Remarks</span></span>

 <span data-ttu-id="66eeb-123">_数字_和_多个_必须具有相同的符号或 #NUM!</span><span class="sxs-lookup"><span data-stu-id="66eeb-123">_Number_ and  _multiple_ must have the same signs, or a #NUM!</span></span> <span data-ttu-id="66eeb-124">错误。</span><span class="sxs-lookup"><span data-stu-id="66eeb-124">error is returned.</span></span> <span data-ttu-id="66eeb-125">如果_number_或_倍数_无法转换为值, #VALUE!</span><span class="sxs-lookup"><span data-stu-id="66eeb-125">If either  _number_ or  _multiple_ cannot be converted to a value, a #VALUE!</span></span> <span data-ttu-id="66eeb-126">错误。</span><span class="sxs-lookup"><span data-stu-id="66eeb-126">error is returned.</span></span> <span data-ttu-id="66eeb-127">如果有一个_数_或_多个_值为 0, 则结果为0。</span><span class="sxs-lookup"><span data-stu-id="66eeb-127">If either  _number_ or  _multiple_ is 0, the result is 0.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="66eeb-128">示例 1</span><span class="sxs-lookup"><span data-stu-id="66eeb-128">Example 1</span></span>

<span data-ttu-id="66eeb-129">天花板 (3.7)</span><span class="sxs-lookup"><span data-stu-id="66eeb-129">CEILING(3.7)</span></span>
  
<span data-ttu-id="66eeb-130">返回 4</span><span class="sxs-lookup"><span data-stu-id="66eeb-130">Returns 4</span></span>
  
## <a name="example-2"></a><span data-ttu-id="66eeb-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="66eeb-131">Example 2</span></span>

<span data-ttu-id="66eeb-132">天花板 (-3.7)</span><span class="sxs-lookup"><span data-stu-id="66eeb-132">CEILING(-3.7)</span></span>
  
<span data-ttu-id="66eeb-133">返回 -4</span><span class="sxs-lookup"><span data-stu-id="66eeb-133">Returns -4</span></span>
  
## <a name="example-3"></a><span data-ttu-id="66eeb-134">示例 3</span><span class="sxs-lookup"><span data-stu-id="66eeb-134">Example 3</span></span>

<span data-ttu-id="66eeb-135">天花板 (3.7, 0.25)</span><span class="sxs-lookup"><span data-stu-id="66eeb-135">CEILING(3.7, 0.25)</span></span>
  
<span data-ttu-id="66eeb-136">返回 3.75</span><span class="sxs-lookup"><span data-stu-id="66eeb-136">Returns 3.75</span></span>
  

