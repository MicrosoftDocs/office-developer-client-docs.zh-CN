---
title: FLOOR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251423
localization_priority: Normal
ms.assetid: 6788bc96-cc86-5f21-781f-67274e7f605a
description: 将数值向 0（零）舍入为下一个整数或 multiple 的下一个实例。
ms.openlocfilehash: 7a16a77a990180f34dd7a5706c24ec3232438467
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346177"
---
# <a name="floor-function"></a><span data-ttu-id="79e6c-103">FLOOR 函数</span><span class="sxs-lookup"><span data-stu-id="79e6c-103">FLOOR Function</span></span>

<span data-ttu-id="79e6c-104">将数字向 0 (零) 舍入为下一个整数或下一个实例的_倍数_。</span><span class="sxs-lookup"><span data-stu-id="79e6c-104">Rounds a number toward 0 (zero), to the next integer, or to the next instance of  _multiple_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="79e6c-105">语法</span><span class="sxs-lookup"><span data-stu-id="79e6c-105">Syntax</span></span>

<span data-ttu-id="79e6c-106">基底 (\* **数字** *、* **多** \*)</span><span class="sxs-lookup"><span data-stu-id="79e6c-106">FLOOR(\*\* *number* \*\*, \*\* *multiple* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="79e6c-107">参数</span><span class="sxs-lookup"><span data-stu-id="79e6c-107">Parameters</span></span>

|<span data-ttu-id="79e6c-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="79e6c-108">**Name**</span></span>|<span data-ttu-id="79e6c-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="79e6c-109">**Required/Optional**</span></span>|<span data-ttu-id="79e6c-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="79e6c-110">**Data Type**</span></span>|<span data-ttu-id="79e6c-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="79e6c-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="79e6c-112">_number_</span><span class="sxs-lookup"><span data-stu-id="79e6c-112">_number_</span></span> <br/> |<span data-ttu-id="79e6c-113">必需</span><span class="sxs-lookup"><span data-stu-id="79e6c-113">Required</span></span>  <br/> |<span data-ttu-id="79e6c-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="79e6c-114">**Number**</span></span> <br/> |<span data-ttu-id="79e6c-115">要舍入的数字。</span><span class="sxs-lookup"><span data-stu-id="79e6c-115">The number to round.</span></span>  <br/> |
| <span data-ttu-id="79e6c-116">_多位_</span><span class="sxs-lookup"><span data-stu-id="79e6c-116">_multiple_</span></span> <br/> |<span data-ttu-id="79e6c-117">必需</span><span class="sxs-lookup"><span data-stu-id="79e6c-117">Required</span></span>  <br/> |<span data-ttu-id="79e6c-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="79e6c-118">**Number**</span></span> <br/> |<span data-ttu-id="79e6c-119">要舍入到的倍数。</span><span class="sxs-lookup"><span data-stu-id="79e6c-119">The multiple to which to round.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="79e6c-120">返回值</span><span class="sxs-lookup"><span data-stu-id="79e6c-120">Return value</span></span>

<span data-ttu-id="79e6c-121">帐号</span><span class="sxs-lookup"><span data-stu-id="79e6c-121">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="79e6c-122">注解</span><span class="sxs-lookup"><span data-stu-id="79e6c-122">Remarks</span></span>

<span data-ttu-id="79e6c-123">如果未指定_多个_, 则数字将向0舍入到下一个整数。</span><span class="sxs-lookup"><span data-stu-id="79e6c-123">If  _multiple_ is not specified, the number rounds toward 0 to the next integer.</span></span> 
  
 <span data-ttu-id="79e6c-124">_数字_和_多个_必须具有相同的符号或 #NUM!</span><span class="sxs-lookup"><span data-stu-id="79e6c-124">_Number_ and  _multiple_ must have the same signs, or a #NUM!</span></span> <span data-ttu-id="79e6c-125">错误。</span><span class="sxs-lookup"><span data-stu-id="79e6c-125">error is returned.</span></span> <span data-ttu-id="79e6c-126">如果_number_或_倍数_无法转换为值, #VALUE!</span><span class="sxs-lookup"><span data-stu-id="79e6c-126">If either  _number_ or  _multiple_ cannot be converted to a value, a #VALUE!</span></span> <span data-ttu-id="79e6c-127">错误。</span><span class="sxs-lookup"><span data-stu-id="79e6c-127">error is returned.</span></span> <span data-ttu-id="79e6c-128">如果有一个_数_或_多个_值为 0, 则结果为0。</span><span class="sxs-lookup"><span data-stu-id="79e6c-128">If either  _number_ or  _multiple_ is 0, the result is 0.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="79e6c-129">示例 1</span><span class="sxs-lookup"><span data-stu-id="79e6c-129">Example 1</span></span>

<span data-ttu-id="79e6c-130">基底 (3.7)</span><span class="sxs-lookup"><span data-stu-id="79e6c-130">FLOOR(3.7)</span></span>
  
<span data-ttu-id="79e6c-131">返回 3。</span><span class="sxs-lookup"><span data-stu-id="79e6c-131">Returns 3.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="79e6c-132">示例 2</span><span class="sxs-lookup"><span data-stu-id="79e6c-132">Example 2</span></span>

<span data-ttu-id="79e6c-133">基底 (-3.7)</span><span class="sxs-lookup"><span data-stu-id="79e6c-133">FLOOR(-3.7)</span></span>
  
<span data-ttu-id="79e6c-134">返回 -3。</span><span class="sxs-lookup"><span data-stu-id="79e6c-134">Returns -3.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="79e6c-135">示例 3</span><span class="sxs-lookup"><span data-stu-id="79e6c-135">Example 3</span></span>

<span data-ttu-id="79e6c-136">基底 (3.7, 0.5)</span><span class="sxs-lookup"><span data-stu-id="79e6c-136">FLOOR(3.7, 0.5)</span></span>
  
<span data-ttu-id="79e6c-137">返回 3.5。</span><span class="sxs-lookup"><span data-stu-id="79e6c-137">Returns 3.5.</span></span>
  

