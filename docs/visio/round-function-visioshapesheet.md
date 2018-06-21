---
title: ROUND 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251491
localization_priority: Normal
ms.assetid: a374fe7d-7302-5365-81ab-64f5474d9d5c
description: 舍入到由 numberofdigits 的精度。
ms.openlocfilehash: 2457bdf6b46a2bb44b203497f02cc9b2ff034847
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19781129"
---
# <a name="round-function-visioshapesheet"></a><span data-ttu-id="7c926-103">ROUND 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="7c926-103">ROUND Function (VisioShapeSheet)</span></span>

<span data-ttu-id="7c926-104">舍入到由*numberofdigits*的精度。</span><span class="sxs-lookup"><span data-stu-id="7c926-104">Rounds a number to the precision represented by  *numberofdigits*  .</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="7c926-105">语法</span><span class="sxs-lookup"><span data-stu-id="7c926-105">Syntax</span></span>

<span data-ttu-id="7c926-106">ROUND (* **数量** *，* * *numberofdigits* * *)</span><span class="sxs-lookup"><span data-stu-id="7c926-106">ROUND(** *number* **, ** *numberofdigits* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7c926-107">参数</span><span class="sxs-lookup"><span data-stu-id="7c926-107">Parameters</span></span>

|<span data-ttu-id="7c926-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="7c926-108">**Name**</span></span>|<span data-ttu-id="7c926-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7c926-109">**Required/Optional**</span></span>|<span data-ttu-id="7c926-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7c926-110">**Data Type**</span></span>|<span data-ttu-id="7c926-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="7c926-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7c926-112">_number_</span><span class="sxs-lookup"><span data-stu-id="7c926-112">_number_</span></span> <br/> |<span data-ttu-id="7c926-113">必需</span><span class="sxs-lookup"><span data-stu-id="7c926-113">Required</span></span>  <br/> |<span data-ttu-id="7c926-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="7c926-114">**Number**</span></span> <br/> |<span data-ttu-id="7c926-115">要舍入的数。</span><span class="sxs-lookup"><span data-stu-id="7c926-115">The number to round off.</span></span>  <br/> |
| <span data-ttu-id="7c926-116">_numberofdigits_</span><span class="sxs-lookup"><span data-stu-id="7c926-116">_numberofdigits_</span></span> <br/> |<span data-ttu-id="7c926-117">必需</span><span class="sxs-lookup"><span data-stu-id="7c926-117">Required</span></span>  <br/> |<span data-ttu-id="7c926-118">**编号**</span><span class="sxs-lookup"><span data-stu-id="7c926-118">**Number**</span></span> <br/> |<span data-ttu-id="7c926-119">精度的小数位数。</span><span class="sxs-lookup"><span data-stu-id="7c926-119">The number of decimal places of precision.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7c926-120">注解</span><span class="sxs-lookup"><span data-stu-id="7c926-120">Remarks</span></span>

<span data-ttu-id="7c926-121">如果_numberofdigits_大于 0，则会将_number_舍入的_numberofdigits_小数点右边。</span><span class="sxs-lookup"><span data-stu-id="7c926-121">If  _numberofdigits_ is greater than 0,  _number_ is rounded by  _numberofdigits_ to the right of the decimal.</span></span> <span data-ttu-id="7c926-122">如果_numberofdigits_为 0，则会将_number_舍入为一个整数值。</span><span class="sxs-lookup"><span data-stu-id="7c926-122">If  _numberofdigits_ is 0,  _number_ is rounded to an integer.</span></span> <span data-ttu-id="7c926-123">如果_numberofdigits_小于 0，则会将_number_舍入的_numberofdigits_小数点左侧。</span><span class="sxs-lookup"><span data-stu-id="7c926-123">If  _numberofdigits_ is less than 0,  _number_ is rounded by  _numberofdigits_ to the left of the decimal.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="7c926-124">示例 1</span><span class="sxs-lookup"><span data-stu-id="7c926-124">Example 1</span></span>

<span data-ttu-id="7c926-125">ROUND(123.654,2)</span><span class="sxs-lookup"><span data-stu-id="7c926-125">ROUND(123.654,2)</span></span>
  
<span data-ttu-id="7c926-126">返回 123.65。</span><span class="sxs-lookup"><span data-stu-id="7c926-126">Returns 123.65.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="7c926-127">示例 2</span><span class="sxs-lookup"><span data-stu-id="7c926-127">Example 2</span></span>

<span data-ttu-id="7c926-128">ROUND(123.654,0)</span><span class="sxs-lookup"><span data-stu-id="7c926-128">ROUND(123.654,0)</span></span>
  
<span data-ttu-id="7c926-129">返回 124。</span><span class="sxs-lookup"><span data-stu-id="7c926-129">Returns 124.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="7c926-130">示例 3</span><span class="sxs-lookup"><span data-stu-id="7c926-130">Example 3</span></span>

<span data-ttu-id="7c926-131">ROUND(123.654,-1)</span><span class="sxs-lookup"><span data-stu-id="7c926-131">ROUND(123.654,-1)</span></span>
  
<span data-ttu-id="7c926-132">返回 120。</span><span class="sxs-lookup"><span data-stu-id="7c926-132">Returns 120.</span></span>
  

