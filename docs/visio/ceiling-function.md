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
ms.openlocfilehash: fa982b44ea4a73e7da614c49a52cd50efd612f20
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779824"
---
# <a name="ceiling-function"></a><span data-ttu-id="1e8eb-104">CEILING 函数</span><span class="sxs-lookup"><span data-stu-id="1e8eb-104">CEILING Function</span></span>

<span data-ttu-id="1e8eb-105">舍入数字向远离 0 （零） 到_多个_的下一个实例。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-105">Rounds a number away from 0 (zero) to the next instance of  _multiple_.</span></span> <span data-ttu-id="1e8eb-106">如果未指定_multiple_ ，则数字舍入数字向远离 0 到下一个整数。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-106">If  _multiple_ is not specified, the number rounds away from 0 to the next integer.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1e8eb-107">语法</span><span class="sxs-lookup"><span data-stu-id="1e8eb-107">Syntax</span></span>

<span data-ttu-id="1e8eb-108">CEILING (* **数量** *，* **多个** *)</span><span class="sxs-lookup"><span data-stu-id="1e8eb-108">CEILING(** *number* **, ** *multiple* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1e8eb-109">参数</span><span class="sxs-lookup"><span data-stu-id="1e8eb-109">Parameters</span></span>

|<span data-ttu-id="1e8eb-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="1e8eb-110">**Name**</span></span>|<span data-ttu-id="1e8eb-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1e8eb-111">**Required/Optional**</span></span>|<span data-ttu-id="1e8eb-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1e8eb-112">**Data Type**</span></span>|<span data-ttu-id="1e8eb-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="1e8eb-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1e8eb-114">_number_</span><span class="sxs-lookup"><span data-stu-id="1e8eb-114">_number_</span></span> <br/> |<span data-ttu-id="1e8eb-115">必需</span><span class="sxs-lookup"><span data-stu-id="1e8eb-115">Required</span></span>  <br/> |<span data-ttu-id="1e8eb-116">**编号**</span><span class="sxs-lookup"><span data-stu-id="1e8eb-116">**Number**</span></span> <br/> |<span data-ttu-id="1e8eb-117">要舍入的数值。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-117">The number to round.</span></span>  <br/> |
| <span data-ttu-id="1e8eb-118">_多个_</span><span class="sxs-lookup"><span data-stu-id="1e8eb-118">_multiple_</span></span> <br/> |<span data-ttu-id="1e8eb-119">必需</span><span class="sxs-lookup"><span data-stu-id="1e8eb-119">Required</span></span>  <br/> |<span data-ttu-id="1e8eb-120">**编号**</span><span class="sxs-lookup"><span data-stu-id="1e8eb-120">**Number**</span></span> <br/> |<span data-ttu-id="1e8eb-121">要舍入到的倍数。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-121">The multiple to round to.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1e8eb-122">注解</span><span class="sxs-lookup"><span data-stu-id="1e8eb-122">Remarks</span></span>

 <span data-ttu-id="1e8eb-123">_号码_和_多个_必须具有相同的迹象或 #NUM ！</span><span class="sxs-lookup"><span data-stu-id="1e8eb-123">_Number_ and  _multiple_ must have the same signs, or a #NUM!</span></span> <span data-ttu-id="1e8eb-124">将返回错误。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-124">error is returned.</span></span> <span data-ttu-id="1e8eb-125">如果_号码_或_多个_不能转换为一个值，#VALUE ！</span><span class="sxs-lookup"><span data-stu-id="1e8eb-125">If either  _number_ or  _multiple_ cannot be converted to a value, a #VALUE!</span></span> <span data-ttu-id="1e8eb-126">将返回错误。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-126">error is returned.</span></span> <span data-ttu-id="1e8eb-127">如果_号码_或_多个_为 0，则结果为 0。</span><span class="sxs-lookup"><span data-stu-id="1e8eb-127">If either  _number_ or  _multiple_ is 0, the result is 0.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="1e8eb-128">示例 1</span><span class="sxs-lookup"><span data-stu-id="1e8eb-128">Example 1</span></span>

<span data-ttu-id="1e8eb-129">CEILING(3.7)</span><span class="sxs-lookup"><span data-stu-id="1e8eb-129">CEILING(3.7)</span></span>
  
<span data-ttu-id="1e8eb-130">返回 4</span><span class="sxs-lookup"><span data-stu-id="1e8eb-130">Returns 4</span></span>
  
## <a name="example-2"></a><span data-ttu-id="1e8eb-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="1e8eb-131">Example 2</span></span>

<span data-ttu-id="1e8eb-132">CEILING(-3.7)</span><span class="sxs-lookup"><span data-stu-id="1e8eb-132">CEILING(-3.7)</span></span>
  
<span data-ttu-id="1e8eb-133">返回 -4</span><span class="sxs-lookup"><span data-stu-id="1e8eb-133">Returns -4</span></span>
  
## <a name="example-3"></a><span data-ttu-id="1e8eb-134">示例 3</span><span class="sxs-lookup"><span data-stu-id="1e8eb-134">Example 3</span></span>

<span data-ttu-id="1e8eb-135">CEILING （3.7、 0.25）</span><span class="sxs-lookup"><span data-stu-id="1e8eb-135">CEILING(3.7, 0.25)</span></span>
  
<span data-ttu-id="1e8eb-136">返回 3.75</span><span class="sxs-lookup"><span data-stu-id="1e8eb-136">Returns 3.75</span></span>
  

