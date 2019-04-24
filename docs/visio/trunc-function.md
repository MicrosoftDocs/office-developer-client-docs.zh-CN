---
title: TRUNC 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251508
localization_priority: Normal
ms.assetid: 62f074ef-5bf8-df1e-d826-fc1027a36501
description: 返回一个被截断为指定位数的数字。
ms.openlocfilehash: 5b2138ff3091f70313344d5b38d8225d572d8e70
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335173"
---
# <a name="trunc-function"></a><span data-ttu-id="7b1c4-103">TRUNC 函数</span><span class="sxs-lookup"><span data-stu-id="7b1c4-103">TRUNC Function</span></span>

<span data-ttu-id="7b1c4-104">返回一个被截断为指定位数的数字。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-104">Returns a number truncated to the specified number of digits.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7b1c4-105">语法</span><span class="sxs-lookup"><span data-stu-id="7b1c4-105">Syntax</span></span>

<span data-ttu-id="7b1c4-106">TRUNC (\* \* *number* \* \*, \* \* *numberofdigits* \* \*)</span><span class="sxs-lookup"><span data-stu-id="7b1c4-106">TRUNC(\*\* *number* \*\*, \*\* *numberofdigits* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7b1c4-107">参数</span><span class="sxs-lookup"><span data-stu-id="7b1c4-107">Parameters</span></span>

|<span data-ttu-id="7b1c4-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="7b1c4-108">**Name**</span></span>|<span data-ttu-id="7b1c4-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7b1c4-109">**Required/Optional**</span></span>|<span data-ttu-id="7b1c4-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7b1c4-110">**Data Type**</span></span>|<span data-ttu-id="7b1c4-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="7b1c4-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7b1c4-112">_number_</span><span class="sxs-lookup"><span data-stu-id="7b1c4-112">_number_</span></span> <br/> |<span data-ttu-id="7b1c4-113">必需</span><span class="sxs-lookup"><span data-stu-id="7b1c4-113">Required</span></span>  <br/> |<span data-ttu-id="7b1c4-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="7b1c4-114">**Numeric**</span></span> <br/> |<span data-ttu-id="7b1c4-115">要截断的数字。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-115">The number to truncate.</span></span>  <br/> |
| <span data-ttu-id="7b1c4-116">_numberofdigits_</span><span class="sxs-lookup"><span data-stu-id="7b1c4-116">_numberofdigits_</span></span> <br/> |<span data-ttu-id="7b1c4-117">必需</span><span class="sxs-lookup"><span data-stu-id="7b1c4-117">Required</span></span>  <br/> |<span data-ttu-id="7b1c4-118">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="7b1c4-118">**Numeric**</span></span> <br/> |<span data-ttu-id="7b1c4-119">要向其截断_数_的数字的位数。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-119">The number of digits to which to truncate  _number_.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="7b1c4-120">返回值</span><span class="sxs-lookup"><span data-stu-id="7b1c4-120">Return value</span></span>

<span data-ttu-id="7b1c4-121">位数.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-121">Numeric.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7b1c4-122">注解</span><span class="sxs-lookup"><span data-stu-id="7b1c4-122">Remarks</span></span>

<span data-ttu-id="7b1c4-123">如果_numberofdigits_大于 0, 则将_数字_截断为小数点右边的_numberofdigits_ 。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-123">If  _numberofdigits_ is greater than 0,  _number_ is truncated to  _numberofdigits_ to the right of the decimal.</span></span> <span data-ttu-id="7b1c4-124">如果_numberofdigits_为 0, 则将_数字_截断为整数。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-124">If  _numberofdigits_ is 0,  _number_ is truncated to an integer.</span></span> <span data-ttu-id="7b1c4-125">如果_numberofdigits_小于 0, 则将_数字_截断为小数点左侧的_numberofdigits_ 。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-125">If  _numberofdigits_ is less than 0,  _number_ is truncated to  _numberofdigits_ to the left of the decimal.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="7b1c4-126">示例 1</span><span class="sxs-lookup"><span data-stu-id="7b1c4-126">Example 1</span></span>

<span data-ttu-id="7b1c4-127">TRUNC (123.654, 2)</span><span class="sxs-lookup"><span data-stu-id="7b1c4-127">TRUNC(123.654,2)</span></span>
  
<span data-ttu-id="7b1c4-128">返回 123.65。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-128">Returns 123.65.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="7b1c4-129">示例 2</span><span class="sxs-lookup"><span data-stu-id="7b1c4-129">Example 2</span></span>

<span data-ttu-id="7b1c4-130">TRUNC (123.654, 0)</span><span class="sxs-lookup"><span data-stu-id="7b1c4-130">TRUNC(123.654,0)</span></span>
  
<span data-ttu-id="7b1c4-131">返回 123。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-131">Returns 123.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="7b1c4-132">示例 3</span><span class="sxs-lookup"><span data-stu-id="7b1c4-132">Example 3</span></span>

<span data-ttu-id="7b1c4-133">TRUNC (123.654,-1)</span><span class="sxs-lookup"><span data-stu-id="7b1c4-133">TRUNC(123.654,-1)</span></span>
  
<span data-ttu-id="7b1c4-134">返回 120。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-134">Returns 120.</span></span>
  

