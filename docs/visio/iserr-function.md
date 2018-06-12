---
title: ISERR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251448
localization_priority: Normal
ms.assetid: 87508007-8ad2-3bcf-55dc-f0207c7c6fe3
description: '将返回 TRUE 如果 cellreference 的值是任何错误类型除外 # n/A;否则，将返回 FALSE。 ISERR 函数可以用于引用另一个单元格的公式。'
ms.openlocfilehash: 651b095e53b7f2690aa9c8774d87d5afcede75be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780475"
---
# <a name="iserr-function"></a><span data-ttu-id="e5d53-104">ISERR 函数</span><span class="sxs-lookup"><span data-stu-id="e5d53-104">ISERR Function</span></span>

<span data-ttu-id="e5d53-105">返回_cellreference_的值为任何错误类型时为 TRUE 除外 # n/A;否则，将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="e5d53-105">Returns TRUE if the value of  _cellreference_ is any error type except #N/A; otherwise, it returns FALSE.</span></span> <span data-ttu-id="e5d53-106">ISERR 函数可以用于引用另一个单元格的公式。</span><span class="sxs-lookup"><span data-stu-id="e5d53-106">The ISERR function is used in formulas that refer to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e5d53-107">语法</span><span class="sxs-lookup"><span data-stu-id="e5d53-107">Syntax</span></span>

<span data-ttu-id="e5d53-108">ISERR (* * *cellreference* * *)</span><span class="sxs-lookup"><span data-stu-id="e5d53-108">ISERR(** *cellreference* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e5d53-109">参数</span><span class="sxs-lookup"><span data-stu-id="e5d53-109">Parameters</span></span>

|<span data-ttu-id="e5d53-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="e5d53-110">**Name**</span></span>|<span data-ttu-id="e5d53-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e5d53-111">**Required/Optional**</span></span>|<span data-ttu-id="e5d53-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e5d53-112">**Data Type**</span></span>|<span data-ttu-id="e5d53-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="e5d53-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e5d53-114">_cellreference_</span><span class="sxs-lookup"><span data-stu-id="e5d53-114">_cellreference_</span></span> <br/> |<span data-ttu-id="e5d53-115">必需</span><span class="sxs-lookup"><span data-stu-id="e5d53-115">Required</span></span>  <br/> |<span data-ttu-id="e5d53-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="e5d53-116">**String**</span></span> <br/> |<span data-ttu-id="e5d53-117">对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="e5d53-117">Reference to a cell.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="e5d53-118">示例 1</span><span class="sxs-lookup"><span data-stu-id="e5d53-118">Example 1</span></span>

|<span data-ttu-id="e5d53-119">**Cell**</span><span class="sxs-lookup"><span data-stu-id="e5d53-119">**Cell**</span></span>|<span data-ttu-id="e5d53-120">**Formula**</span><span class="sxs-lookup"><span data-stu-id="e5d53-120">**Formula**</span></span>|<span data-ttu-id="e5d53-121">**返回值**</span><span class="sxs-lookup"><span data-stu-id="e5d53-121">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5d53-122">Scratch.A1</span><span class="sxs-lookup"><span data-stu-id="e5d53-122">Scratch.A1</span></span>  <br/> |<span data-ttu-id="e5d53-123">=NA( )</span><span class="sxs-lookup"><span data-stu-id="e5d53-123">=NA( )</span></span>  <br/> |<span data-ttu-id="e5d53-124">#N/A!</span><span class="sxs-lookup"><span data-stu-id="e5d53-124">#N/A!</span></span>  <br/> |
|<span data-ttu-id="e5d53-125">Scratch.B1</span><span class="sxs-lookup"><span data-stu-id="e5d53-125">Scratch.B1</span></span>  <br/> |<span data-ttu-id="e5d53-126">=ISERR(Scratch.A1)</span><span class="sxs-lookup"><span data-stu-id="e5d53-126">=ISERR(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="e5d53-127">FALSE</span><span class="sxs-lookup"><span data-stu-id="e5d53-127">FALSE</span></span>  <br/> |
   
<span data-ttu-id="e5d53-p103">返回 FALSE，因为 ISERR 函数不能识别 #N/A! 错误。使用 ISERROR 可查找所有错误类型。</span><span class="sxs-lookup"><span data-stu-id="e5d53-p103">Returns FALSE because the #N/A! error is not recognized by the ISERR function. Use ISERROR to find all error types.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="e5d53-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="e5d53-131">Example 2</span></span>

|<span data-ttu-id="e5d53-132">**Cell**</span><span class="sxs-lookup"><span data-stu-id="e5d53-132">**Cell**</span></span>|<span data-ttu-id="e5d53-133">**Formula**</span><span class="sxs-lookup"><span data-stu-id="e5d53-133">**Formula**</span></span>|<span data-ttu-id="e5d53-134">**返回值**</span><span class="sxs-lookup"><span data-stu-id="e5d53-134">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5d53-135">Scratch.X1</span><span class="sxs-lookup"><span data-stu-id="e5d53-135">Scratch.X1</span></span>  <br/> |<span data-ttu-id="e5d53-136">="House"</span><span class="sxs-lookup"><span data-stu-id="e5d53-136">="House"</span></span>  <br/> |<span data-ttu-id="e5d53-137">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="e5d53-137">#VALUE!</span></span>  <br/> |
|<span data-ttu-id="e5d53-138">Scratch.A1</span><span class="sxs-lookup"><span data-stu-id="e5d53-138">Scratch.A1</span></span>  <br/> |<span data-ttu-id="e5d53-139">=ISERR(Scratch.X1)</span><span class="sxs-lookup"><span data-stu-id="e5d53-139">=ISERR(Scratch.X1)</span></span>  <br/> |<span data-ttu-id="e5d53-140">TRUE</span><span class="sxs-lookup"><span data-stu-id="e5d53-140">TRUE</span></span>  <br/> |
   
<span data-ttu-id="e5d53-p104">返回 TRUE，因为 ISERR 函数可以识别 #VALUE! 错误。</span><span class="sxs-lookup"><span data-stu-id="e5d53-p104">Returns TRUE because the #VALUE! error is recognized by the ISERR function.</span></span>
  

