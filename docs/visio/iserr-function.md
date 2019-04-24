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
description: '如果 cellreference 的值是除 #N/a 之外的任何错误类型, 则返回 TRUE; 否则, 返回 false。否则, 它将返回 FALSE。 ISERR 函数在引用其他单元格的公式中使用。'
ms.openlocfilehash: e2117c38d3cad2408295ed6894aefc78e107596e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297247"
---
# <a name="iserr-function"></a><span data-ttu-id="af2ce-104">ISERR 函数</span><span class="sxs-lookup"><span data-stu-id="af2ce-104">ISERR Function</span></span>

<span data-ttu-id="af2ce-105">如果_cellreference_的值是除 #N/a 之外的任何错误类型, 则返回 TRUE; 否则, 返回 false。否则, 它将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="af2ce-105">Returns TRUE if the value of  _cellreference_ is any error type except #N/A; otherwise, it returns FALSE.</span></span> <span data-ttu-id="af2ce-106">ISERR 函数在引用其他单元格的公式中使用。</span><span class="sxs-lookup"><span data-stu-id="af2ce-106">The ISERR function is used in formulas that refer to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="af2ce-107">语法</span><span class="sxs-lookup"><span data-stu-id="af2ce-107">Syntax</span></span>

<span data-ttu-id="af2ce-108">ISERR (\* \* *cellreference* \* \*)</span><span class="sxs-lookup"><span data-stu-id="af2ce-108">ISERR(\*\* *cellreference* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="af2ce-109">参数</span><span class="sxs-lookup"><span data-stu-id="af2ce-109">Parameters</span></span>

|<span data-ttu-id="af2ce-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="af2ce-110">**Name**</span></span>|<span data-ttu-id="af2ce-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="af2ce-111">**Required/Optional**</span></span>|<span data-ttu-id="af2ce-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="af2ce-112">**Data Type**</span></span>|<span data-ttu-id="af2ce-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="af2ce-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="af2ce-114">_cellreference_</span><span class="sxs-lookup"><span data-stu-id="af2ce-114">_cellreference_</span></span> <br/> |<span data-ttu-id="af2ce-115">必需</span><span class="sxs-lookup"><span data-stu-id="af2ce-115">Required</span></span>  <br/> |<span data-ttu-id="af2ce-116">**String**</span><span class="sxs-lookup"><span data-stu-id="af2ce-116">**String**</span></span> <br/> |<span data-ttu-id="af2ce-117">对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="af2ce-117">Reference to a cell.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="af2ce-118">示例 1</span><span class="sxs-lookup"><span data-stu-id="af2ce-118">Example 1</span></span>

|<span data-ttu-id="af2ce-119">**Cell**</span><span class="sxs-lookup"><span data-stu-id="af2ce-119">**Cell**</span></span>|<span data-ttu-id="af2ce-120">**Formula**</span><span class="sxs-lookup"><span data-stu-id="af2ce-120">**Formula**</span></span>|<span data-ttu-id="af2ce-121">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="af2ce-121">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af2ce-122">草稿。 A1</span><span class="sxs-lookup"><span data-stu-id="af2ce-122">Scratch.A1</span></span>  <br/> |<span data-ttu-id="af2ce-123">=NA( )</span><span class="sxs-lookup"><span data-stu-id="af2ce-123">=NA( )</span></span>  <br/> |<span data-ttu-id="af2ce-124">#N/A!</span><span class="sxs-lookup"><span data-stu-id="af2ce-124">#N/A!</span></span>  <br/> |
|<span data-ttu-id="af2ce-125">草稿 B1</span><span class="sxs-lookup"><span data-stu-id="af2ce-125">Scratch.B1</span></span>  <br/> |<span data-ttu-id="af2ce-126">= ISERR (的 A1)</span><span class="sxs-lookup"><span data-stu-id="af2ce-126">=ISERR(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="af2ce-127">FALSE</span><span class="sxs-lookup"><span data-stu-id="af2ce-127">FALSE</span></span>  <br/> |
   
<span data-ttu-id="af2ce-p103">返回 FALSE，因为 ISERR 函数不能识别 #N/A! 错误。使用 ISERROR 可查找所有错误类型。</span><span class="sxs-lookup"><span data-stu-id="af2ce-p103">Returns FALSE because the #N/A! error is not recognized by the ISERR function. Use ISERROR to find all error types.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="af2ce-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="af2ce-131">Example 2</span></span>

|<span data-ttu-id="af2ce-132">**Cell**</span><span class="sxs-lookup"><span data-stu-id="af2ce-132">**Cell**</span></span>|<span data-ttu-id="af2ce-133">**Formula**</span><span class="sxs-lookup"><span data-stu-id="af2ce-133">**Formula**</span></span>|<span data-ttu-id="af2ce-134">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="af2ce-134">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af2ce-135">暂存. X1</span><span class="sxs-lookup"><span data-stu-id="af2ce-135">Scratch.X1</span></span>  <br/> |<span data-ttu-id="af2ce-136">= "房子"</span><span class="sxs-lookup"><span data-stu-id="af2ce-136">="House"</span></span>  <br/> |<span data-ttu-id="af2ce-137">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="af2ce-137">#VALUE!</span></span>  <br/> |
|<span data-ttu-id="af2ce-138">草稿。 A1</span><span class="sxs-lookup"><span data-stu-id="af2ce-138">Scratch.A1</span></span>  <br/> |<span data-ttu-id="af2ce-139">= ISERR (X1)</span><span class="sxs-lookup"><span data-stu-id="af2ce-139">=ISERR(Scratch.X1)</span></span>  <br/> |<span data-ttu-id="af2ce-140">TRUE</span><span class="sxs-lookup"><span data-stu-id="af2ce-140">TRUE</span></span>  <br/> |
   
<span data-ttu-id="af2ce-p104">返回 TRUE，因为 ISERR 函数可以识别 #VALUE! 错误。</span><span class="sxs-lookup"><span data-stu-id="af2ce-p104">Returns TRUE because the #VALUE! error is recognized by the ISERR function.</span></span>
  

