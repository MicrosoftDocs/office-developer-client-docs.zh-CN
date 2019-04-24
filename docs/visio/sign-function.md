---
title: SIGN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251497
localization_priority: Normal
ms.assetid: fdc032c2-d0bd-1592-de3f-33c478d066ee
description: 返回一个表示数字符号的值。
ms.openlocfilehash: 34bbbab17de94b0a8c95b4b0bfd3829a06dc7e70
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357454"
---
# <a name="sign-function"></a><span data-ttu-id="cbb6f-103">SIGN 函数</span><span class="sxs-lookup"><span data-stu-id="cbb6f-103">SIGN Function</span></span>

<span data-ttu-id="cbb6f-104">返回一个表示数字符号的值。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-104">Returns a value that represents the sign of a number.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="cbb6f-105">语法</span><span class="sxs-lookup"><span data-stu-id="cbb6f-105">Syntax</span></span>

<span data-ttu-id="cbb6f-106">SIGN (\* \* *number* \* \*, \* \* *fuzz* \* \*)</span><span class="sxs-lookup"><span data-stu-id="cbb6f-106">SIGN(\*\* *number* \*\*, \*\* *fuzz* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="cbb6f-107">参数</span><span class="sxs-lookup"><span data-stu-id="cbb6f-107">Parameters</span></span>

|<span data-ttu-id="cbb6f-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="cbb6f-108">**Name**</span></span>|<span data-ttu-id="cbb6f-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="cbb6f-109">**Required/Optional**</span></span>|<span data-ttu-id="cbb6f-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cbb6f-110">**Data Type**</span></span>|<span data-ttu-id="cbb6f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="cbb6f-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cbb6f-112">_number_</span><span class="sxs-lookup"><span data-stu-id="cbb6f-112">_number_</span></span> <br/> |<span data-ttu-id="cbb6f-113">必需</span><span class="sxs-lookup"><span data-stu-id="cbb6f-113">Required</span></span>  <br/> |<span data-ttu-id="cbb6f-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="cbb6f-114">**Numeric**</span></span> <br/> | <span data-ttu-id="cbb6f-115">要确定其符号的数字。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-115">The number for which you want to determine the sign.</span></span>  <br/> |
| <span data-ttu-id="cbb6f-116">_fuzz_</span><span class="sxs-lookup"><span data-stu-id="cbb6f-116">_fuzz_</span></span> <br/> |<span data-ttu-id="cbb6f-117">可选</span><span class="sxs-lookup"><span data-stu-id="cbb6f-117">Optional</span></span>  <br/> |<span data-ttu-id="cbb6f-118">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="cbb6f-118">**Numeric**</span></span> <br/> |<span data-ttu-id="cbb6f-119">指定数字接近零达到何种程度时才必须被视为等于零。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-119">Specifies how close to zero the number must be in order to be considered equal to zero.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="cbb6f-120">返回值</span><span class="sxs-lookup"><span data-stu-id="cbb6f-120">Return value</span></span>

<span data-ttu-id="cbb6f-121">Numeric</span><span class="sxs-lookup"><span data-stu-id="cbb6f-121">Numeric</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cbb6f-122">注解</span><span class="sxs-lookup"><span data-stu-id="cbb6f-122">Remarks</span></span>

<span data-ttu-id="cbb6f-123">如果 number 为正数, 则__ SIGN 函数返回 1; 如果__ number 为零, 则返回 0; 如果_number_为负, 则返回-1。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-123">The SIGN function returns 1 if  _number_ is positive, 0 if  _number_ is zero, or -1 if  _number_ is negative.</span></span> 
  
<span data-ttu-id="cbb6f-124">Specifyin 当计算几乎为零时, _fuzz_值有助于避免浮点 roundoff 错误。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-124">Specifyin a  _fuzz_ value helps avoid floating-point roundoff errors when a calculation is almost zero.</span></span> <span data-ttu-id="cbb6f-125">如果不指定_fuzz_值, Visio 将使用 1e-9 (0.000000001)。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-125">If you do not specify a  _fuzz_ value, Visio uses 1E-9 (0.000000001).</span></span> <span data-ttu-id="cbb6f-126">当您要缩放绘图或进行精确比较时，最好提供不同的值。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-126">You may want to supply a different value when you scale drawings or when you want an exact comparison.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="cbb6f-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="cbb6f-127">Example 1</span></span>

<span data-ttu-id="cbb6f-128">符号 (-5)</span><span class="sxs-lookup"><span data-stu-id="cbb6f-128">SIGN(-5)</span></span>
  
<span data-ttu-id="cbb6f-129">返回 -1。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-129">Returns -1.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="cbb6f-130">示例 2</span><span class="sxs-lookup"><span data-stu-id="cbb6f-130">Example 2</span></span>

<span data-ttu-id="cbb6f-131">符号 (0)</span><span class="sxs-lookup"><span data-stu-id="cbb6f-131">SIGN(0)</span></span>
  
<span data-ttu-id="cbb6f-132">返回 0。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-132">Returns 0.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="cbb6f-133">示例 3</span><span class="sxs-lookup"><span data-stu-id="cbb6f-133">Example 3</span></span>

<span data-ttu-id="cbb6f-134">符号 (0.00000000001)</span><span class="sxs-lookup"><span data-stu-id="cbb6f-134">SIGN(0.00000000001)</span></span>
  
<span data-ttu-id="cbb6f-135">返回 0。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-135">Returns 0.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="cbb6f-136">示例 4</span><span class="sxs-lookup"><span data-stu-id="cbb6f-136">Example 4</span></span>

<span data-ttu-id="cbb6f-137">SIGN (0.00000000001, 0)</span><span class="sxs-lookup"><span data-stu-id="cbb6f-137">SIGN(0.00000000001,0)</span></span>
  
<span data-ttu-id="cbb6f-138">返回 1。</span><span class="sxs-lookup"><span data-stu-id="cbb6f-138">Returns 1.</span></span>
  

