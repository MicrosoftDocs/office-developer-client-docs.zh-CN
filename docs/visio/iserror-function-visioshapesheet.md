---
title: ISERROR 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251452
localization_priority: Normal
ms.assetid: 4864ebc2-fee6-2415-7c59-e0af8611f8d6
description: 如果 cellreference 的值为任何错误类型, 则返回 TRUE; 否则返回 false。否则, 它将返回 FALSE。 ISERROR 函数在引用其他单元格的公式中使用。
ms.openlocfilehash: a07b2345858e36dc2e4514d7e4f0f0d653491b50
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317889"
---
# <a name="iserror-function-visioshapesheet"></a><span data-ttu-id="eff4a-104">ISERROR 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="eff4a-104">ISERROR Function (VisioShapeSheet)</span></span>

<span data-ttu-id="eff4a-105">如果_cellreference_的值为任何错误类型, 则返回 TRUE; 否则返回 false。否则, 它将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="eff4a-105">Returns TRUE if the value of  _cellreference_ is any error type; otherwise, it returns FALSE.</span></span> <span data-ttu-id="eff4a-106">ISERROR 函数在引用其他单元格的公式中使用。</span><span class="sxs-lookup"><span data-stu-id="eff4a-106">The ISERROR function is used in formulas that refer to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="eff4a-107">语法</span><span class="sxs-lookup"><span data-stu-id="eff4a-107">Syntax</span></span>

<span data-ttu-id="eff4a-108">ISERROR (\* \* *cellreference* \* \*)</span><span class="sxs-lookup"><span data-stu-id="eff4a-108">ISERROR(\*\* *cellreference* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="eff4a-109">参数</span><span class="sxs-lookup"><span data-stu-id="eff4a-109">Parameters</span></span>

|<span data-ttu-id="eff4a-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="eff4a-110">**Name**</span></span>|<span data-ttu-id="eff4a-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="eff4a-111">**Required/Optional**</span></span>|<span data-ttu-id="eff4a-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="eff4a-112">**Data Type**</span></span>|<span data-ttu-id="eff4a-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="eff4a-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="eff4a-114">_cellreference_</span><span class="sxs-lookup"><span data-stu-id="eff4a-114">_cellreference_</span></span> <br/> |<span data-ttu-id="eff4a-115">必需</span><span class="sxs-lookup"><span data-stu-id="eff4a-115">Required</span></span>  <br/> |<span data-ttu-id="eff4a-116">**String**</span><span class="sxs-lookup"><span data-stu-id="eff4a-116">**String**</span></span> <br/> |<span data-ttu-id="eff4a-117">对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="eff4a-117">Reference to a cell.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="eff4a-118">示例 1</span><span class="sxs-lookup"><span data-stu-id="eff4a-118">Example 1</span></span>

|<span data-ttu-id="eff4a-119">**Cell**</span><span class="sxs-lookup"><span data-stu-id="eff4a-119">**Cell**</span></span>|<span data-ttu-id="eff4a-120">**Formula**</span><span class="sxs-lookup"><span data-stu-id="eff4a-120">**Formula**</span></span>|<span data-ttu-id="eff4a-121">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="eff4a-121">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eff4a-122">草稿。 A1</span><span class="sxs-lookup"><span data-stu-id="eff4a-122">Scratch.A1</span></span>  <br/> |<span data-ttu-id="eff4a-123">=NA( )</span><span class="sxs-lookup"><span data-stu-id="eff4a-123">=NA( )</span></span>  <br/> |<span data-ttu-id="eff4a-124">#N/A!</span><span class="sxs-lookup"><span data-stu-id="eff4a-124">#N/A!</span></span>  <br/> |
|<span data-ttu-id="eff4a-125">草稿 B1</span><span class="sxs-lookup"><span data-stu-id="eff4a-125">Scratch.B1</span></span>  <br/> |<span data-ttu-id="eff4a-126">= ISERROR (的 A1)</span><span class="sxs-lookup"><span data-stu-id="eff4a-126">=ISERROR(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="eff4a-127">TRUE</span><span class="sxs-lookup"><span data-stu-id="eff4a-127">TRUE</span></span>  <br/> |
   
<span data-ttu-id="eff4a-p103">返回 TRUE，因为 ISERROR 函数可以识别 #N/A! 错误。您可以使用 ISERR 查找除 #N/A! 错误之外的所有错误类型。</span><span class="sxs-lookup"><span data-stu-id="eff4a-p103">Returns TRUE because the #N/A! error is recognized by the ISERROR function. You can use ISERR to find all types but the #N/A! error.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="eff4a-132">示例 2</span><span class="sxs-lookup"><span data-stu-id="eff4a-132">Example 2</span></span>

|<span data-ttu-id="eff4a-133">**Cell**</span><span class="sxs-lookup"><span data-stu-id="eff4a-133">**Cell**</span></span>|<span data-ttu-id="eff4a-134">**Formula**</span><span class="sxs-lookup"><span data-stu-id="eff4a-134">**Formula**</span></span>|<span data-ttu-id="eff4a-135">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="eff4a-135">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eff4a-136">暂存. X1</span><span class="sxs-lookup"><span data-stu-id="eff4a-136">Scratch.X1</span></span>  <br/> |<span data-ttu-id="eff4a-137">= "房子"</span><span class="sxs-lookup"><span data-stu-id="eff4a-137">="House"</span></span>  <br/> |<span data-ttu-id="eff4a-138">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="eff4a-138">#VALUE!</span></span>  <br/> |
|<span data-ttu-id="eff4a-139">草稿 B1</span><span class="sxs-lookup"><span data-stu-id="eff4a-139">Scratch.B1</span></span>  <br/> |<span data-ttu-id="eff4a-140">= ISERROR (X1)</span><span class="sxs-lookup"><span data-stu-id="eff4a-140">=ISERROR(Scratch.X1)</span></span>  <br/> |<span data-ttu-id="eff4a-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="eff4a-141">TRUE</span></span>  <br/> |
   
<span data-ttu-id="eff4a-p104">返回 TRUE，因为 ISERROR 函数可以识别 #VALUE! 错误。若要基于 #VALUE! 错误生成一个表达式，请使用 ISERRVALUE 函数。</span><span class="sxs-lookup"><span data-stu-id="eff4a-p104">Returns TRUE because the #VALUE! error is recognized by the ISERROR function. To build an expression based on the #VALUE! error, use the ISERRVALUE function.</span></span>
  

