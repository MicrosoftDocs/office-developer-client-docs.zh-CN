---
title: MODULUS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251465
localization_priority: Normal
ms.assetid: cb6326a5-1bf8-b6a3-5c0d-d38c071353a5
description: 返回由 (除) 数时结果的余数模数。
ms.openlocfilehash: f6b713b1b3a9d2afa85f49de9d451642a00d8dad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429269"
---
# <a name="modulus-function"></a><span data-ttu-id="731ec-103">MODULUS 函数</span><span class="sxs-lookup"><span data-stu-id="731ec-103">MODULUS Function</span></span>

<span data-ttu-id="731ec-104">返回由 (除) 数时结果的余数模数。</span><span class="sxs-lookup"><span data-stu-id="731ec-104">Returns the remainder (modulus) that results when a number is divided by a divisor.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="731ec-105">语法</span><span class="sxs-lookup"><span data-stu-id="731ec-105">Syntax</span></span>

<span data-ttu-id="731ec-106">MODULUS (\*\* *number* \*\*， \*\* *divisor* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="731ec-106">MODULUS(\*\* *number* \*\*, \*\* *divisor* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="731ec-107">参数</span><span class="sxs-lookup"><span data-stu-id="731ec-107">Parameters</span></span>

|<span data-ttu-id="731ec-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="731ec-108">**Name**</span></span>|<span data-ttu-id="731ec-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="731ec-109">**Required/Optional**</span></span>|<span data-ttu-id="731ec-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="731ec-110">**Data Type**</span></span>|<span data-ttu-id="731ec-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="731ec-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="731ec-112">_number_</span><span class="sxs-lookup"><span data-stu-id="731ec-112">_number_</span></span> <br/> |<span data-ttu-id="731ec-113">必需</span><span class="sxs-lookup"><span data-stu-id="731ec-113">Required</span></span>  <br/> |<span data-ttu-id="731ec-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="731ec-114">**Number**</span></span> <br/> |<span data-ttu-id="731ec-115">被除数。</span><span class="sxs-lookup"><span data-stu-id="731ec-115">The dividend.</span></span>  <br/> |
| <span data-ttu-id="731ec-116">_divisor_</span><span class="sxs-lookup"><span data-stu-id="731ec-116">_divisor_</span></span> <br/> |<span data-ttu-id="731ec-117">必需</span><span class="sxs-lookup"><span data-stu-id="731ec-117">Required</span></span>  <br/> |<span data-ttu-id="731ec-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="731ec-118">**Number**</span></span> <br/> |<span data-ttu-id="731ec-119">除数。</span><span class="sxs-lookup"><span data-stu-id="731ec-119">The divisor.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="731ec-120">返回值</span><span class="sxs-lookup"><span data-stu-id="731ec-120">Return value</span></span>

<span data-ttu-id="731ec-121">帐号</span><span class="sxs-lookup"><span data-stu-id="731ec-121">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="731ec-122">备注</span><span class="sxs-lookup"><span data-stu-id="731ec-122">Remarks</span></span>

<span data-ttu-id="731ec-p101">结果与除数具有相同的符号。如果除数为 0，则将返回 #DIV/0! 错误。</span><span class="sxs-lookup"><span data-stu-id="731ec-p101">The result has the same sign as the divisor. A #DIV/0! error is returned if the divisor is 0.</span></span> 
  
<span data-ttu-id="731ec-126">在绝大多数情况下应使用 MODULUS 函数，而不使用 MOD 函数。</span><span class="sxs-lookup"><span data-stu-id="731ec-126">In almost all situations, the MODULUS function should be used rather than the MOD function.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="731ec-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="731ec-127">Example 1</span></span>

<span data-ttu-id="731ec-128">MODULUS(5, 1.4)</span><span class="sxs-lookup"><span data-stu-id="731ec-128">MODULUS(5, 1.4)</span></span>
  
<span data-ttu-id="731ec-129">返回 0.8。</span><span class="sxs-lookup"><span data-stu-id="731ec-129">Returns 0.8.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="731ec-130">示例 2</span><span class="sxs-lookup"><span data-stu-id="731ec-130">Example 2</span></span>

<span data-ttu-id="731ec-131">MODULUS(5, -1.4)</span><span class="sxs-lookup"><span data-stu-id="731ec-131">MODULUS(5, -1.4)</span></span>
  
<span data-ttu-id="731ec-132">返回 -0.6。</span><span class="sxs-lookup"><span data-stu-id="731ec-132">Returns -0.6.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="731ec-133">示例 3</span><span class="sxs-lookup"><span data-stu-id="731ec-133">Example 3</span></span>

<span data-ttu-id="731ec-134">MODULUS(-5, 1.4)</span><span class="sxs-lookup"><span data-stu-id="731ec-134">MODULUS(-5, 1.4)</span></span>
  
<span data-ttu-id="731ec-135">返回 0.6。</span><span class="sxs-lookup"><span data-stu-id="731ec-135">Returns 0.6.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="731ec-136">示例 4</span><span class="sxs-lookup"><span data-stu-id="731ec-136">Example 4</span></span>

<span data-ttu-id="731ec-137">MODULUS(-5, -1.4)</span><span class="sxs-lookup"><span data-stu-id="731ec-137">MODULUS(-5, -1.4)</span></span>
  
<span data-ttu-id="731ec-138">返回 -0.8。</span><span class="sxs-lookup"><span data-stu-id="731ec-138">Returns -0.8.</span></span>
  

