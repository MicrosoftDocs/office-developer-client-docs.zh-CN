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
description: 返回截断为指定位数的数字。
ms.openlocfilehash: 5b2138ff3091f70313344d5b38d8225d572d8e70
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426497"
---
# <a name="trunc-function"></a><span data-ttu-id="67397-103">TRUNC 函数</span><span class="sxs-lookup"><span data-stu-id="67397-103">TRUNC Function</span></span>

<span data-ttu-id="67397-104">返回截断为指定位数的数字。</span><span class="sxs-lookup"><span data-stu-id="67397-104">Returns a number truncated to the specified number of digits.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="67397-105">语法</span><span class="sxs-lookup"><span data-stu-id="67397-105">Syntax</span></span>

<span data-ttu-id="67397-106">TRUNC (\*\* *number* \*\*， \*\* *numberofdigits* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="67397-106">TRUNC(\*\* *number* \*\*, \*\* *numberofdigits* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="67397-107">参数</span><span class="sxs-lookup"><span data-stu-id="67397-107">Parameters</span></span>

|<span data-ttu-id="67397-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="67397-108">**Name**</span></span>|<span data-ttu-id="67397-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="67397-109">**Required/Optional**</span></span>|<span data-ttu-id="67397-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="67397-110">**Data Type**</span></span>|<span data-ttu-id="67397-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="67397-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="67397-112">_number_</span><span class="sxs-lookup"><span data-stu-id="67397-112">_number_</span></span> <br/> |<span data-ttu-id="67397-113">必需</span><span class="sxs-lookup"><span data-stu-id="67397-113">Required</span></span>  <br/> |<span data-ttu-id="67397-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="67397-114">**Numeric**</span></span> <br/> |<span data-ttu-id="67397-115">要截断的数字。</span><span class="sxs-lookup"><span data-stu-id="67397-115">The number to truncate.</span></span>  <br/> |
| <span data-ttu-id="67397-116">_numberofdigits_</span><span class="sxs-lookup"><span data-stu-id="67397-116">_numberofdigits_</span></span> <br/> |<span data-ttu-id="67397-117">必需</span><span class="sxs-lookup"><span data-stu-id="67397-117">Required</span></span>  <br/> |<span data-ttu-id="67397-118">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="67397-118">**Numeric**</span></span> <br/> |<span data-ttu-id="67397-119">要截断号码的  _位数_。</span><span class="sxs-lookup"><span data-stu-id="67397-119">The number of digits to which to truncate  _number_.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="67397-120">返回值</span><span class="sxs-lookup"><span data-stu-id="67397-120">Return value</span></span>

<span data-ttu-id="67397-121">数字。</span><span class="sxs-lookup"><span data-stu-id="67397-121">Numeric.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="67397-122">备注</span><span class="sxs-lookup"><span data-stu-id="67397-122">Remarks</span></span>

<span data-ttu-id="67397-123">如果 _numberofdigits_ 大于 0，_则 number_ 将被截断到小数点右边的 _numberofdigits。_</span><span class="sxs-lookup"><span data-stu-id="67397-123">If  _numberofdigits_ is greater than 0,  _number_ is truncated to  _numberofdigits_ to the right of the decimal.</span></span> <span data-ttu-id="67397-124">如果  _numberofdigits_ 为 0，  _则 number_ 将被截短为整数。</span><span class="sxs-lookup"><span data-stu-id="67397-124">If  _numberofdigits_ is 0,  _number_ is truncated to an integer.</span></span> <span data-ttu-id="67397-125">如果 _numberofdigits_ 小于 0，_则 number_ 将被截断为小数点左侧的 _numberofdigits。_</span><span class="sxs-lookup"><span data-stu-id="67397-125">If  _numberofdigits_ is less than 0,  _number_ is truncated to  _numberofdigits_ to the left of the decimal.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="67397-126">示例 1</span><span class="sxs-lookup"><span data-stu-id="67397-126">Example 1</span></span>

<span data-ttu-id="67397-127">TRUNC (123.654，2) </span><span class="sxs-lookup"><span data-stu-id="67397-127">TRUNC(123.654,2)</span></span>
  
<span data-ttu-id="67397-128">返回 123.65。</span><span class="sxs-lookup"><span data-stu-id="67397-128">Returns 123.65.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="67397-129">示例 2</span><span class="sxs-lookup"><span data-stu-id="67397-129">Example 2</span></span>

<span data-ttu-id="67397-130">TRUNC (123.654，0) </span><span class="sxs-lookup"><span data-stu-id="67397-130">TRUNC(123.654,0)</span></span>
  
<span data-ttu-id="67397-131">返回 123。</span><span class="sxs-lookup"><span data-stu-id="67397-131">Returns 123.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="67397-132">示例 3</span><span class="sxs-lookup"><span data-stu-id="67397-132">Example 3</span></span>

<span data-ttu-id="67397-133">TRUNC (123.654，-1) </span><span class="sxs-lookup"><span data-stu-id="67397-133">TRUNC(123.654,-1)</span></span>
  
<span data-ttu-id="67397-134">返回 120。</span><span class="sxs-lookup"><span data-stu-id="67397-134">Returns 120.</span></span>
  

