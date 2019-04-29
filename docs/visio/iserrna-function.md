---
title: ISERRNA 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251451
localization_priority: Normal
ms.assetid: 6ee7dc3d-efe9-c862-f71d-034b3d9c3ec6
description: '如果 cellreference 的值为错误类型 #N/a!, 则返回 TRUE。 (不可用);否则, 它将返回 FALSE。 ISERRNA 函数在引用其他单元格的公式中使用。'
ms.openlocfilehash: 8a398eca6da659a6b8f29e4ef8e31b18abf56fde
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432112"
---
# <a name="iserrna-function"></a><span data-ttu-id="166c0-105">ISERRNA 函数</span><span class="sxs-lookup"><span data-stu-id="166c0-105">ISERRNA Function</span></span>

<span data-ttu-id="166c0-106">如果_cellreference_的值为错误类型 #N/a!, 则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="166c0-106">Returns TRUE if the value of  _cellreference_ is error type #N/A!</span></span> <span data-ttu-id="166c0-107">(不可用);否则, 它将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="166c0-107">(not available); otherwise, it returns FALSE.</span></span> <span data-ttu-id="166c0-108">ISERRNA 函数在引用其他单元格的公式中使用。</span><span class="sxs-lookup"><span data-stu-id="166c0-108">The ISERRNA function is used in formulas that refer to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="166c0-109">语法</span><span class="sxs-lookup"><span data-stu-id="166c0-109">Syntax</span></span>

<span data-ttu-id="166c0-110">ISERRNA (\* \* *cellreference* \* \*)</span><span class="sxs-lookup"><span data-stu-id="166c0-110">ISERRNA(\*\* *cellreference* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="166c0-111">参数</span><span class="sxs-lookup"><span data-stu-id="166c0-111">Parameters</span></span>

|<span data-ttu-id="166c0-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="166c0-112">**Name**</span></span>|<span data-ttu-id="166c0-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="166c0-113">**Required/Optional**</span></span>|<span data-ttu-id="166c0-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="166c0-114">**Data Type**</span></span>|<span data-ttu-id="166c0-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="166c0-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="166c0-116">_cellreference_</span><span class="sxs-lookup"><span data-stu-id="166c0-116">_cellreference_</span></span> <br/> |<span data-ttu-id="166c0-117">必需</span><span class="sxs-lookup"><span data-stu-id="166c0-117">Required</span></span>  <br/> |<span data-ttu-id="166c0-118">**String**</span><span class="sxs-lookup"><span data-stu-id="166c0-118">**String**</span></span> <br/> |<span data-ttu-id="166c0-119">对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="166c0-119">Reference to a cell.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="166c0-120">示例 1</span><span class="sxs-lookup"><span data-stu-id="166c0-120">Example 1</span></span>

|<span data-ttu-id="166c0-121">**单元格**</span><span class="sxs-lookup"><span data-stu-id="166c0-121">**Cell**</span></span>|<span data-ttu-id="166c0-122">**Formula**</span><span class="sxs-lookup"><span data-stu-id="166c0-122">**Formula**</span></span>|<span data-ttu-id="166c0-123">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="166c0-123">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="166c0-124">草稿。 A1</span><span class="sxs-lookup"><span data-stu-id="166c0-124">Scratch.A1</span></span>  <br/> |<span data-ttu-id="166c0-125">="5 + 3"</span><span class="sxs-lookup"><span data-stu-id="166c0-125">="5 + 3"</span></span>  <br/> |<span data-ttu-id="166c0-126">utf-8</span><span class="sxs-lookup"><span data-stu-id="166c0-126">"8"</span></span>  <br/> |
|<span data-ttu-id="166c0-127">草稿 B1</span><span class="sxs-lookup"><span data-stu-id="166c0-127">Scratch.B1</span></span>  <br/> |<span data-ttu-id="166c0-128">= ISERRNA (的 A1)</span><span class="sxs-lookup"><span data-stu-id="166c0-128">=ISERRNA(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="166c0-129">FALSE</span><span class="sxs-lookup"><span data-stu-id="166c0-129">FALSE</span></span>  <br/> |
   
<span data-ttu-id="166c0-130">返回 FALSE，因为返回的值可用。</span><span class="sxs-lookup"><span data-stu-id="166c0-130">Returns FALSE because the value returned is available.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="166c0-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="166c0-131">Example 2</span></span>

|<span data-ttu-id="166c0-132">**单元格**</span><span class="sxs-lookup"><span data-stu-id="166c0-132">**Cell**</span></span>|<span data-ttu-id="166c0-133">**Formula**</span><span class="sxs-lookup"><span data-stu-id="166c0-133">**Formula**</span></span>|<span data-ttu-id="166c0-134">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="166c0-134">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="166c0-135">草稿。 A1</span><span class="sxs-lookup"><span data-stu-id="166c0-135">Scratch.A1</span></span>  <br/> |<span data-ttu-id="166c0-136">=NA( )</span><span class="sxs-lookup"><span data-stu-id="166c0-136">=NA( )</span></span>  <br/> |<span data-ttu-id="166c0-137">#N/A!</span><span class="sxs-lookup"><span data-stu-id="166c0-137">#N/A!</span></span>  <br/> |
|<span data-ttu-id="166c0-138">草稿 B1</span><span class="sxs-lookup"><span data-stu-id="166c0-138">Scratch.B1</span></span>  <br/> |<span data-ttu-id="166c0-139">= ISERRNA (的 A1)</span><span class="sxs-lookup"><span data-stu-id="166c0-139">=ISERRNA(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="166c0-140">TRUE</span><span class="sxs-lookup"><span data-stu-id="166c0-140">TRUE</span></span>  <br/> |
   
<span data-ttu-id="166c0-141">返回 TRUE，因为返回的值是 #N/A! 错误类型。</span><span class="sxs-lookup"><span data-stu-id="166c0-141">Returns TRUE because the value returned is error type #N/A!</span></span>
  

