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
description: 将数字舍入到由 numberofdigits 表示的精度。
ms.openlocfilehash: 6795cbc4d99e293da06c0ec369d2cefb84f9f5b5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315573"
---
# <a name="round-function-visioshapesheet"></a><span data-ttu-id="c14f7-103">ROUND 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="c14f7-103">ROUND Function (VisioShapeSheet)</span></span>

<span data-ttu-id="c14f7-104">将数字舍入到由*numberofdigits*表示的精度。</span><span class="sxs-lookup"><span data-stu-id="c14f7-104">Rounds a number to the precision represented by  *numberofdigits*  .</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="c14f7-105">语法</span><span class="sxs-lookup"><span data-stu-id="c14f7-105">Syntax</span></span>

<span data-ttu-id="c14f7-106">ROUND (\* \* *number* \* \*, \* \* *numberofdigits* \* \*)</span><span class="sxs-lookup"><span data-stu-id="c14f7-106">ROUND(\*\* *number* \*\*, \*\* *numberofdigits* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c14f7-107">参数</span><span class="sxs-lookup"><span data-stu-id="c14f7-107">Parameters</span></span>

|<span data-ttu-id="c14f7-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="c14f7-108">**Name**</span></span>|<span data-ttu-id="c14f7-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c14f7-109">**Required/Optional**</span></span>|<span data-ttu-id="c14f7-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c14f7-110">**Data Type**</span></span>|<span data-ttu-id="c14f7-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="c14f7-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c14f7-112">_number_</span><span class="sxs-lookup"><span data-stu-id="c14f7-112">_number_</span></span> <br/> |<span data-ttu-id="c14f7-113">必需</span><span class="sxs-lookup"><span data-stu-id="c14f7-113">Required</span></span>  <br/> |<span data-ttu-id="c14f7-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="c14f7-114">**Number**</span></span> <br/> |<span data-ttu-id="c14f7-115">要舍入的数。</span><span class="sxs-lookup"><span data-stu-id="c14f7-115">The number to round off.</span></span>  <br/> |
| <span data-ttu-id="c14f7-116">_numberofdigits_</span><span class="sxs-lookup"><span data-stu-id="c14f7-116">_numberofdigits_</span></span> <br/> |<span data-ttu-id="c14f7-117">必需</span><span class="sxs-lookup"><span data-stu-id="c14f7-117">Required</span></span>  <br/> |<span data-ttu-id="c14f7-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="c14f7-118">**Number**</span></span> <br/> |<span data-ttu-id="c14f7-119">精度的小数位数。</span><span class="sxs-lookup"><span data-stu-id="c14f7-119">The number of decimal places of precision.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c14f7-120">注解</span><span class="sxs-lookup"><span data-stu-id="c14f7-120">Remarks</span></span>

<span data-ttu-id="c14f7-121">如果_numberofdigits_大于 0, 则数字将由_numberofdigits_的小数点右边的_数字_舍入。</span><span class="sxs-lookup"><span data-stu-id="c14f7-121">If  _numberofdigits_ is greater than 0,  _number_ is rounded by  _numberofdigits_ to the right of the decimal.</span></span> <span data-ttu-id="c14f7-122">如果_numberofdigits_为 0, 则将_number_舍入为整数。</span><span class="sxs-lookup"><span data-stu-id="c14f7-122">If  _numberofdigits_ is 0,  _number_ is rounded to an integer.</span></span> <span data-ttu-id="c14f7-123">如果_numberofdigits_小于 0, 则_数字_将由_numberofdigits_ (小数的左侧) 舍入。</span><span class="sxs-lookup"><span data-stu-id="c14f7-123">If  _numberofdigits_ is less than 0,  _number_ is rounded by  _numberofdigits_ to the left of the decimal.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="c14f7-124">示例 1</span><span class="sxs-lookup"><span data-stu-id="c14f7-124">Example 1</span></span>

<span data-ttu-id="c14f7-125">ROUND (123.654, 2)</span><span class="sxs-lookup"><span data-stu-id="c14f7-125">ROUND(123.654,2)</span></span>
  
<span data-ttu-id="c14f7-126">返回 123.65。</span><span class="sxs-lookup"><span data-stu-id="c14f7-126">Returns 123.65.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="c14f7-127">示例 2</span><span class="sxs-lookup"><span data-stu-id="c14f7-127">Example 2</span></span>

<span data-ttu-id="c14f7-128">ROUND (123.654, 0)</span><span class="sxs-lookup"><span data-stu-id="c14f7-128">ROUND(123.654,0)</span></span>
  
<span data-ttu-id="c14f7-129">返回 124。</span><span class="sxs-lookup"><span data-stu-id="c14f7-129">Returns 124.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="c14f7-130">示例 3</span><span class="sxs-lookup"><span data-stu-id="c14f7-130">Example 3</span></span>

<span data-ttu-id="c14f7-131">ROUND (123.654,-1)</span><span class="sxs-lookup"><span data-stu-id="c14f7-131">ROUND(123.654,-1)</span></span>
  
<span data-ttu-id="c14f7-132">返回 120。</span><span class="sxs-lookup"><span data-stu-id="c14f7-132">Returns 120.</span></span>
  

