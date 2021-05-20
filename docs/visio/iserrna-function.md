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
description: '如果 cellreference 的值为错误类型，则返回 TRUE #N/A！  (不可用) ;否则，它将返回 FALSE。 ISERRNA 函数用于引用另一个单元格的公式中。'
ms.openlocfilehash: 8a398eca6da659a6b8f29e4ef8e31b18abf56fde
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432112"
---
# <a name="iserrna-function"></a><span data-ttu-id="ab96a-105">ISERRNA 函数</span><span class="sxs-lookup"><span data-stu-id="ab96a-105">ISERRNA Function</span></span>

<span data-ttu-id="ab96a-106">如果  _cellreference_ 的值为错误类型，则返回 TRUE #N/A！</span><span class="sxs-lookup"><span data-stu-id="ab96a-106">Returns TRUE if the value of  _cellreference_ is error type #N/A!</span></span> <span data-ttu-id="ab96a-107"> (不可用) ;否则，它将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="ab96a-107">(not available); otherwise, it returns FALSE.</span></span> <span data-ttu-id="ab96a-108">ISERRNA 函数用于引用另一个单元格的公式中。</span><span class="sxs-lookup"><span data-stu-id="ab96a-108">The ISERRNA function is used in formulas that refer to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ab96a-109">语法</span><span class="sxs-lookup"><span data-stu-id="ab96a-109">Syntax</span></span>

<span data-ttu-id="ab96a-110">ISERRNA (\*\* *cellreference* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="ab96a-110">ISERRNA(\*\* *cellreference* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ab96a-111">参数</span><span class="sxs-lookup"><span data-stu-id="ab96a-111">Parameters</span></span>

|<span data-ttu-id="ab96a-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="ab96a-112">**Name**</span></span>|<span data-ttu-id="ab96a-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ab96a-113">**Required/Optional**</span></span>|<span data-ttu-id="ab96a-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ab96a-114">**Data Type**</span></span>|<span data-ttu-id="ab96a-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="ab96a-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ab96a-116">_cellreference_</span><span class="sxs-lookup"><span data-stu-id="ab96a-116">_cellreference_</span></span> <br/> |<span data-ttu-id="ab96a-117">必需</span><span class="sxs-lookup"><span data-stu-id="ab96a-117">Required</span></span>  <br/> |<span data-ttu-id="ab96a-118">**String**</span><span class="sxs-lookup"><span data-stu-id="ab96a-118">**String**</span></span> <br/> |<span data-ttu-id="ab96a-119">对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="ab96a-119">Reference to a cell.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="ab96a-120">示例 1</span><span class="sxs-lookup"><span data-stu-id="ab96a-120">Example 1</span></span>

|<span data-ttu-id="ab96a-121">**Cell**</span><span class="sxs-lookup"><span data-stu-id="ab96a-121">**Cell**</span></span>|<span data-ttu-id="ab96a-122">**公式**</span><span class="sxs-lookup"><span data-stu-id="ab96a-122">**Formula**</span></span>|<span data-ttu-id="ab96a-123">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="ab96a-123">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ab96a-124">Scratch.A1</span><span class="sxs-lookup"><span data-stu-id="ab96a-124">Scratch.A1</span></span>  <br/> |<span data-ttu-id="ab96a-125">="5 + 3"</span><span class="sxs-lookup"><span data-stu-id="ab96a-125">="5 + 3"</span></span>  <br/> |<span data-ttu-id="ab96a-126">"8"</span><span class="sxs-lookup"><span data-stu-id="ab96a-126">"8"</span></span>  <br/> |
|<span data-ttu-id="ab96a-127">Scratch.B1</span><span class="sxs-lookup"><span data-stu-id="ab96a-127">Scratch.B1</span></span>  <br/> |<span data-ttu-id="ab96a-128">=ISERRNA (Scratch.A1) </span><span class="sxs-lookup"><span data-stu-id="ab96a-128">=ISERRNA(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="ab96a-129">FALSE</span><span class="sxs-lookup"><span data-stu-id="ab96a-129">FALSE</span></span>  <br/> |
   
<span data-ttu-id="ab96a-130">返回 FALSE，因为返回的值可用。</span><span class="sxs-lookup"><span data-stu-id="ab96a-130">Returns FALSE because the value returned is available.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="ab96a-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="ab96a-131">Example 2</span></span>

|<span data-ttu-id="ab96a-132">**Cell**</span><span class="sxs-lookup"><span data-stu-id="ab96a-132">**Cell**</span></span>|<span data-ttu-id="ab96a-133">**公式**</span><span class="sxs-lookup"><span data-stu-id="ab96a-133">**Formula**</span></span>|<span data-ttu-id="ab96a-134">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="ab96a-134">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ab96a-135">Scratch.A1</span><span class="sxs-lookup"><span data-stu-id="ab96a-135">Scratch.A1</span></span>  <br/> |<span data-ttu-id="ab96a-136">=NA( )</span><span class="sxs-lookup"><span data-stu-id="ab96a-136">=NA( )</span></span>  <br/> |<span data-ttu-id="ab96a-137">#N/A！</span><span class="sxs-lookup"><span data-stu-id="ab96a-137">#N/A!</span></span>  <br/> |
|<span data-ttu-id="ab96a-138">Scratch.B1</span><span class="sxs-lookup"><span data-stu-id="ab96a-138">Scratch.B1</span></span>  <br/> |<span data-ttu-id="ab96a-139">=ISERRNA (Scratch.A1) </span><span class="sxs-lookup"><span data-stu-id="ab96a-139">=ISERRNA(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="ab96a-140">TRUE</span><span class="sxs-lookup"><span data-stu-id="ab96a-140">TRUE</span></span>  <br/> |
   
<span data-ttu-id="ab96a-141">返回 TRUE，因为返回的值是 #N/A! 错误类型。</span><span class="sxs-lookup"><span data-stu-id="ab96a-141">Returns TRUE because the value returned is error type #N/A!</span></span>
  

