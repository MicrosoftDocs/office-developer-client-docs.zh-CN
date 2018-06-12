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
ms.openlocfilehash: 5f812dc4313e15df5d66a919707e7cdbb79f94b9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781370"
---
# <a name="sign-function"></a><span data-ttu-id="9e163-103">SIGN 函数</span><span class="sxs-lookup"><span data-stu-id="9e163-103">SIGN Function</span></span>

<span data-ttu-id="9e163-104">返回一个表示数字符号的值。</span><span class="sxs-lookup"><span data-stu-id="9e163-104">Returns a value that represents the sign of a number.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="9e163-105">语法</span><span class="sxs-lookup"><span data-stu-id="9e163-105">Syntax</span></span>

<span data-ttu-id="9e163-106">登录 (* **数量** *，* **模糊化** *)</span><span class="sxs-lookup"><span data-stu-id="9e163-106">SIGN(** *number* **, ** *fuzz* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="9e163-107">参数</span><span class="sxs-lookup"><span data-stu-id="9e163-107">Parameters</span></span>

|<span data-ttu-id="9e163-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="9e163-108">**Name**</span></span>|<span data-ttu-id="9e163-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="9e163-109">**Required/Optional**</span></span>|<span data-ttu-id="9e163-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9e163-110">**Data Type**</span></span>|<span data-ttu-id="9e163-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e163-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9e163-112">_number_</span><span class="sxs-lookup"><span data-stu-id="9e163-112">_number_</span></span> <br/> |<span data-ttu-id="9e163-113">必需</span><span class="sxs-lookup"><span data-stu-id="9e163-113">Required</span></span>  <br/> |<span data-ttu-id="9e163-114">**数字**</span><span class="sxs-lookup"><span data-stu-id="9e163-114">**Numeric**</span></span> <br/> | <span data-ttu-id="9e163-115">要确定其符号的数字。</span><span class="sxs-lookup"><span data-stu-id="9e163-115">The number for which you want to determine the sign.</span></span>  <br/> |
| <span data-ttu-id="9e163-116">_模糊化_</span><span class="sxs-lookup"><span data-stu-id="9e163-116">_fuzz_</span></span> <br/> |<span data-ttu-id="9e163-117">可选</span><span class="sxs-lookup"><span data-stu-id="9e163-117">Optional</span></span>  <br/> |<span data-ttu-id="9e163-118">**数字**</span><span class="sxs-lookup"><span data-stu-id="9e163-118">**Numeric**</span></span> <br/> |<span data-ttu-id="9e163-119">指定数字接近零达到何种程度时才必须被视为等于零。</span><span class="sxs-lookup"><span data-stu-id="9e163-119">Specifies how close to zero the number must be in order to be considered equal to zero.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="9e163-120">返回值</span><span class="sxs-lookup"><span data-stu-id="9e163-120">Return value</span></span>

<span data-ttu-id="9e163-121">Numeric</span><span class="sxs-lookup"><span data-stu-id="9e163-121">Numeric</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9e163-122">注解</span><span class="sxs-lookup"><span data-stu-id="9e163-122">Remarks</span></span>

<span data-ttu-id="9e163-123">如果_number_为正数，SIGN 函数返回 1、 0 如果_number_是零，则为-1，如果_number_为负数。</span><span class="sxs-lookup"><span data-stu-id="9e163-123">The SIGN function returns 1 if  _number_ is positive, 0 if  _number_ is zero, or -1 if  _number_ is negative.</span></span> 
  
<span data-ttu-id="9e163-124">Specifyin_模糊化_值有助于避免浮点舍入错误时计算结果近似为零。</span><span class="sxs-lookup"><span data-stu-id="9e163-124">Specifyin a  _fuzz_ value helps avoid floating-point roundoff errors when a calculation is almost zero.</span></span> <span data-ttu-id="9e163-125">如果不指定_模糊化_值，Visio 会使用 1E-9 (0.000000001)。</span><span class="sxs-lookup"><span data-stu-id="9e163-125">If you do not specify a  _fuzz_ value, Visio uses 1E-9 (0.000000001).</span></span> <span data-ttu-id="9e163-126">您可能想要扩展绘图或时所需的确切比较提供不同的值。</span><span class="sxs-lookup"><span data-stu-id="9e163-126">You may want to supply a different value when you scale drawings or when you want an exact comparison.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="9e163-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="9e163-127">Example 1</span></span>

<span data-ttu-id="9e163-128">SIGN(-5)</span><span class="sxs-lookup"><span data-stu-id="9e163-128">SIGN(-5)</span></span>
  
<span data-ttu-id="9e163-129">返回 -1。</span><span class="sxs-lookup"><span data-stu-id="9e163-129">Returns -1.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="9e163-130">示例 2</span><span class="sxs-lookup"><span data-stu-id="9e163-130">Example 2</span></span>

<span data-ttu-id="9e163-131">SIGN(0)</span><span class="sxs-lookup"><span data-stu-id="9e163-131">SIGN(0)</span></span>
  
<span data-ttu-id="9e163-132">返回 0。</span><span class="sxs-lookup"><span data-stu-id="9e163-132">Returns 0.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="9e163-133">示例 3</span><span class="sxs-lookup"><span data-stu-id="9e163-133">Example 3</span></span>

<span data-ttu-id="9e163-134">SIGN(0.00000000001)</span><span class="sxs-lookup"><span data-stu-id="9e163-134">SIGN(0.00000000001)</span></span>
  
<span data-ttu-id="9e163-135">返回 0。</span><span class="sxs-lookup"><span data-stu-id="9e163-135">Returns 0.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="9e163-136">示例 4</span><span class="sxs-lookup"><span data-stu-id="9e163-136">Example 4</span></span>

<span data-ttu-id="9e163-137">SIGN(0.00000000001,0)</span><span class="sxs-lookup"><span data-stu-id="9e163-137">SIGN(0.00000000001,0)</span></span>
  
<span data-ttu-id="9e163-138">返回 1。</span><span class="sxs-lookup"><span data-stu-id="9e163-138">Returns 1.</span></span>
  

