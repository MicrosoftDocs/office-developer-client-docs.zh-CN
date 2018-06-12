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
description: 返回一个截断为指定的数字位数的数字。
ms.openlocfilehash: 8f6a9798391d308a234469d93bc8f481de5fc8da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781557"
---
# <a name="trunc-function"></a><span data-ttu-id="5ec83-103">TRUNC 函数</span><span class="sxs-lookup"><span data-stu-id="5ec83-103">TRUNC Function</span></span>

<span data-ttu-id="5ec83-104">返回一个截断为指定的数字位数的数字。</span><span class="sxs-lookup"><span data-stu-id="5ec83-104">Returns a number truncated to the specified number of digits.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5ec83-105">语法</span><span class="sxs-lookup"><span data-stu-id="5ec83-105">Syntax</span></span>

<span data-ttu-id="5ec83-106">TRUNC (* **数量** *，* * *numberofdigits* * *)</span><span class="sxs-lookup"><span data-stu-id="5ec83-106">TRUNC(** *number* **, ** *numberofdigits* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5ec83-107">参数</span><span class="sxs-lookup"><span data-stu-id="5ec83-107">Parameters</span></span>

|<span data-ttu-id="5ec83-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="5ec83-108">**Name**</span></span>|<span data-ttu-id="5ec83-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5ec83-109">**Required/Optional**</span></span>|<span data-ttu-id="5ec83-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5ec83-110">**Data Type**</span></span>|<span data-ttu-id="5ec83-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5ec83-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5ec83-112">_number_</span><span class="sxs-lookup"><span data-stu-id="5ec83-112">_number_</span></span> <br/> |<span data-ttu-id="5ec83-113">必需</span><span class="sxs-lookup"><span data-stu-id="5ec83-113">Required</span></span>  <br/> |<span data-ttu-id="5ec83-114">**数字**</span><span class="sxs-lookup"><span data-stu-id="5ec83-114">**Numeric**</span></span> <br/> |<span data-ttu-id="5ec83-115">要截断的数字。</span><span class="sxs-lookup"><span data-stu-id="5ec83-115">The number to truncate.</span></span>  <br/> |
| <span data-ttu-id="5ec83-116">_numberofdigits_</span><span class="sxs-lookup"><span data-stu-id="5ec83-116">_numberofdigits_</span></span> <br/> |<span data-ttu-id="5ec83-117">必需</span><span class="sxs-lookup"><span data-stu-id="5ec83-117">Required</span></span>  <br/> |<span data-ttu-id="5ec83-118">**数字**</span><span class="sxs-lookup"><span data-stu-id="5ec83-118">**Numeric**</span></span> <br/> |<span data-ttu-id="5ec83-119">要_截断_的数字数。</span><span class="sxs-lookup"><span data-stu-id="5ec83-119">The number of digits to which to truncate  _number_.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5ec83-120">返回值</span><span class="sxs-lookup"><span data-stu-id="5ec83-120">Return value</span></span>

<span data-ttu-id="5ec83-121">Numeric。</span><span class="sxs-lookup"><span data-stu-id="5ec83-121">Numeric.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5ec83-122">注解</span><span class="sxs-lookup"><span data-stu-id="5ec83-122">Remarks</span></span>

<span data-ttu-id="5ec83-123">如果_numberofdigits_大于 0，_数字_将被截断到小数点右边的_numberofdigits_ 。</span><span class="sxs-lookup"><span data-stu-id="5ec83-123">If  _numberofdigits_ is greater than 0,  _number_ is truncated to  _numberofdigits_ to the right of the decimal.</span></span> <span data-ttu-id="5ec83-124">如果_numberofdigits_为 0，_数字_将被截断为一个整数值。</span><span class="sxs-lookup"><span data-stu-id="5ec83-124">If  _numberofdigits_ is 0,  _number_ is truncated to an integer.</span></span> <span data-ttu-id="5ec83-125">如果_numberofdigits_小于 0，_数字_将被截断到_numberofdigits_小数点左侧。</span><span class="sxs-lookup"><span data-stu-id="5ec83-125">If  _numberofdigits_ is less than 0,  _number_ is truncated to  _numberofdigits_ to the left of the decimal.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="5ec83-126">示例 1</span><span class="sxs-lookup"><span data-stu-id="5ec83-126">Example 1</span></span>

<span data-ttu-id="5ec83-127">TRUNC(123.654,2)</span><span class="sxs-lookup"><span data-stu-id="5ec83-127">TRUNC(123.654,2)</span></span>
  
<span data-ttu-id="5ec83-128">返回 123.65。</span><span class="sxs-lookup"><span data-stu-id="5ec83-128">Returns 123.65.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="5ec83-129">示例 2</span><span class="sxs-lookup"><span data-stu-id="5ec83-129">Example 2</span></span>

<span data-ttu-id="5ec83-130">TRUNC(123.654,0)</span><span class="sxs-lookup"><span data-stu-id="5ec83-130">TRUNC(123.654,0)</span></span>
  
<span data-ttu-id="5ec83-131">返回 123。</span><span class="sxs-lookup"><span data-stu-id="5ec83-131">Returns 123.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="5ec83-132">示例 3</span><span class="sxs-lookup"><span data-stu-id="5ec83-132">Example 3</span></span>

<span data-ttu-id="5ec83-133">TRUNC(123.654,-1)</span><span class="sxs-lookup"><span data-stu-id="5ec83-133">TRUNC(123.654,-1)</span></span>
  
<span data-ttu-id="5ec83-134">返回 120。</span><span class="sxs-lookup"><span data-stu-id="5ec83-134">Returns 120.</span></span>
  

