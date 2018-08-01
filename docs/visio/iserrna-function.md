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
description: '返回 TRUE，如果 cellreference 的值为错误类型 # n/A ！ （不可用）;否则，将返回 FALSE。 ISERRNA 函数引用另一个单元格的公式中使用。'
ms.openlocfilehash: a471119265d77866e51ccc6bb556f2ce0095d31d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780487"
---
# <a name="iserrna-function"></a><span data-ttu-id="0d3ac-105">ISERRNA 函数</span><span class="sxs-lookup"><span data-stu-id="0d3ac-105">ISERRNA Function</span></span>

<span data-ttu-id="0d3ac-106">返回 TRUE，如果_cellreference_的值为错误类型 # n/A ！</span><span class="sxs-lookup"><span data-stu-id="0d3ac-106">Returns TRUE if the value of  _cellreference_ is error type #N/A!</span></span> <span data-ttu-id="0d3ac-107">（不可用）;否则，将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0d3ac-107">(not available); otherwise, it returns FALSE.</span></span> <span data-ttu-id="0d3ac-108">ISERRNA 函数引用另一个单元格的公式中使用。</span><span class="sxs-lookup"><span data-stu-id="0d3ac-108">The ISERRNA function is used in formulas that refer to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0d3ac-109">语法</span><span class="sxs-lookup"><span data-stu-id="0d3ac-109">Syntax</span></span>

<span data-ttu-id="0d3ac-110">ISERRNA (* * *cellreference* * *)</span><span class="sxs-lookup"><span data-stu-id="0d3ac-110">ISERRNA(** *cellreference* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="0d3ac-111">参数</span><span class="sxs-lookup"><span data-stu-id="0d3ac-111">Parameters</span></span>

|<span data-ttu-id="0d3ac-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-112">**Name**</span></span>|<span data-ttu-id="0d3ac-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-113">**Required/Optional**</span></span>|<span data-ttu-id="0d3ac-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-114">**Data Type**</span></span>|<span data-ttu-id="0d3ac-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0d3ac-116">_cellreference_</span><span class="sxs-lookup"><span data-stu-id="0d3ac-116">_cellreference_</span></span> <br/> |<span data-ttu-id="0d3ac-117">必需</span><span class="sxs-lookup"><span data-stu-id="0d3ac-117">Required</span></span>  <br/> |<span data-ttu-id="0d3ac-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-118">**String**</span></span> <br/> |<span data-ttu-id="0d3ac-119">对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="0d3ac-119">Reference to a cell.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="0d3ac-120">示例 1</span><span class="sxs-lookup"><span data-stu-id="0d3ac-120">Example 1</span></span>

|<span data-ttu-id="0d3ac-121">**Cell**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-121">**Cell**</span></span>|<span data-ttu-id="0d3ac-122">**Formula**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-122">**Formula**</span></span>|<span data-ttu-id="0d3ac-123">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-123">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0d3ac-124">Scratch.A1</span><span class="sxs-lookup"><span data-stu-id="0d3ac-124">Scratch.A1</span></span>  <br/> |<span data-ttu-id="0d3ac-125">="5 + 3"</span><span class="sxs-lookup"><span data-stu-id="0d3ac-125">="5 + 3"</span></span>  <br/> |<span data-ttu-id="0d3ac-126">"8"</span><span class="sxs-lookup"><span data-stu-id="0d3ac-126">"8"</span></span>  <br/> |
|<span data-ttu-id="0d3ac-127">Scratch.B1</span><span class="sxs-lookup"><span data-stu-id="0d3ac-127">Scratch.B1</span></span>  <br/> |<span data-ttu-id="0d3ac-128">=ISERRNA(Scratch.A1)</span><span class="sxs-lookup"><span data-stu-id="0d3ac-128">=ISERRNA(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="0d3ac-129">FALSE</span><span class="sxs-lookup"><span data-stu-id="0d3ac-129">FALSE</span></span>  <br/> |
   
<span data-ttu-id="0d3ac-130">返回 FALSE，因为返回的值可用。</span><span class="sxs-lookup"><span data-stu-id="0d3ac-130">Returns FALSE because the value returned is available.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="0d3ac-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="0d3ac-131">Example 2</span></span>

|<span data-ttu-id="0d3ac-132">**Cell**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-132">**Cell**</span></span>|<span data-ttu-id="0d3ac-133">**Formula**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-133">**Formula**</span></span>|<span data-ttu-id="0d3ac-134">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="0d3ac-134">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0d3ac-135">Scratch.A1</span><span class="sxs-lookup"><span data-stu-id="0d3ac-135">Scratch.A1</span></span>  <br/> |<span data-ttu-id="0d3ac-136">=NA( )</span><span class="sxs-lookup"><span data-stu-id="0d3ac-136">=NA( )</span></span>  <br/> |<span data-ttu-id="0d3ac-137">#N/A!</span><span class="sxs-lookup"><span data-stu-id="0d3ac-137">#N/A!</span></span>  <br/> |
|<span data-ttu-id="0d3ac-138">Scratch.B1</span><span class="sxs-lookup"><span data-stu-id="0d3ac-138">Scratch.B1</span></span>  <br/> |<span data-ttu-id="0d3ac-139">=ISERRNA(Scratch.A1)</span><span class="sxs-lookup"><span data-stu-id="0d3ac-139">=ISERRNA(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="0d3ac-140">TRUE</span><span class="sxs-lookup"><span data-stu-id="0d3ac-140">TRUE</span></span>  <br/> |
   
<span data-ttu-id="0d3ac-141">返回 TRUE，因为返回的值是 #N/A! 错误类型。</span><span class="sxs-lookup"><span data-stu-id="0d3ac-141">Returns TRUE because the value returned is error type #N/A!</span></span>
  

