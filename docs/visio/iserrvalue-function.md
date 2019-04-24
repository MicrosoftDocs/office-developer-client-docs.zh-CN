---
title: ISERRVALUE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251453
localization_priority: Normal
ms.assetid: c7feec6f-f47a-60ee-b056-7b2dc51ed9a9
description: '如果 cellreference 的值为错误类型 #VALUE, 则返回 TRUE, 其中公式中的参数的类型错误。 在引用另一个单元格的逻辑表达式中使用 ISERRVALUE 函数。'
ms.openlocfilehash: 62058522dc8a2387aec9867e4892da740aba9b44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317883"
---
# <a name="iserrvalue-function"></a><span data-ttu-id="0a651-104">ISERRVALUE 函数</span><span class="sxs-lookup"><span data-stu-id="0a651-104">ISERRVALUE Function</span></span>

<span data-ttu-id="0a651-105">如果_cellreference_的值为错误类型 #VALUE, 则返回 TRUE, 其中公式中的参数的类型错误。</span><span class="sxs-lookup"><span data-stu-id="0a651-105">Returns TRUE if the value of  _cellreference_ is error type #VALUE, where an argument in the formula is the wrong type.</span></span> <span data-ttu-id="0a651-106">在引用另一个单元格的逻辑表达式中使用 ISERRVALUE 函数。</span><span class="sxs-lookup"><span data-stu-id="0a651-106">The ISERRVALUE function is used in logical expressions that refer to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0a651-107">语法</span><span class="sxs-lookup"><span data-stu-id="0a651-107">Syntax</span></span>

<span data-ttu-id="0a651-108">ISERRVALUE (\* \* *cellreference* \* \*)</span><span class="sxs-lookup"><span data-stu-id="0a651-108">ISERRVALUE(\*\* *cellreference* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="0a651-109">参数</span><span class="sxs-lookup"><span data-stu-id="0a651-109">Parameters</span></span>

|<span data-ttu-id="0a651-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="0a651-110">**Name**</span></span>|<span data-ttu-id="0a651-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="0a651-111">**Required/Optional**</span></span>|<span data-ttu-id="0a651-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0a651-112">**Data Type**</span></span>|<span data-ttu-id="0a651-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="0a651-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0a651-114">_cellreference_</span><span class="sxs-lookup"><span data-stu-id="0a651-114">_cellreference_</span></span> <br/> |<span data-ttu-id="0a651-115">必需</span><span class="sxs-lookup"><span data-stu-id="0a651-115">Required</span></span>  <br/> |<span data-ttu-id="0a651-116">**String**</span><span class="sxs-lookup"><span data-stu-id="0a651-116">**String**</span></span> <br/> |<span data-ttu-id="0a651-117">对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="0a651-117">Reference to a cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0a651-118">注解</span><span class="sxs-lookup"><span data-stu-id="0a651-118">Remarks</span></span>

<span data-ttu-id="0a651-p103">Scratch 单元格 A 到 D 不会返回 #VALUE! 错误，因为该公式可以在同一字符串中包含数字和字母。单元格 X 和 Y 必须只包含数字。</span><span class="sxs-lookup"><span data-stu-id="0a651-p103">Scratch cells A through D won't return a #VALUE! error because the formula can contain numbers and letters in the same string. Cells X and Y must contain numbers only.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="0a651-122">示例 1</span><span class="sxs-lookup"><span data-stu-id="0a651-122">Example 1</span></span>

|<span data-ttu-id="0a651-123">**Cell**</span><span class="sxs-lookup"><span data-stu-id="0a651-123">**Cell**</span></span>|<span data-ttu-id="0a651-124">**Formula**</span><span class="sxs-lookup"><span data-stu-id="0a651-124">**Formula**</span></span>|<span data-ttu-id="0a651-125">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="0a651-125">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a651-126">暂存. X1</span><span class="sxs-lookup"><span data-stu-id="0a651-126">Scratch.X1</span></span>  <br/> |<span data-ttu-id="0a651-127">= "House"</span><span class="sxs-lookup"><span data-stu-id="0a651-127">= "House"</span></span>  <br/> |<span data-ttu-id="0a651-128">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="0a651-128">#VALUE!</span></span>  <br/> |
|<span data-ttu-id="0a651-129">草稿。 A1</span><span class="sxs-lookup"><span data-stu-id="0a651-129">Scratch.A1</span></span>  <br/> |<span data-ttu-id="0a651-130">= If (ISERRVALUE(Scratch.X1),2,Scratch.X1)</span><span class="sxs-lookup"><span data-stu-id="0a651-130">= If (ISERRVALUE(Scratch.X1),2,Scratch.X1)</span></span>  <br/> |<span data-ttu-id="0a651-131">双面</span><span class="sxs-lookup"><span data-stu-id="0a651-131">2</span></span>  <br/> |
   
<span data-ttu-id="0a651-p104">返回 2，因为返回的值是 #VALUE! 错误，而表达式指示 Microsoft Visio 在出现错误时返回 2。</span><span class="sxs-lookup"><span data-stu-id="0a651-p104">Returns 2 because the value returned is a #VALUE! error, and the expression instructs Microsoft Visio to return a 2 in place of the error.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="0a651-134">示例 2</span><span class="sxs-lookup"><span data-stu-id="0a651-134">Example 2</span></span>

|<span data-ttu-id="0a651-135">**Cell**</span><span class="sxs-lookup"><span data-stu-id="0a651-135">**Cell**</span></span>|<span data-ttu-id="0a651-136">**Formula**</span><span class="sxs-lookup"><span data-stu-id="0a651-136">**Formula**</span></span>|<span data-ttu-id="0a651-137">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="0a651-137">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a651-138">草稿。 A1</span><span class="sxs-lookup"><span data-stu-id="0a651-138">Scratch.A1</span></span>  <br/> |<span data-ttu-id="0a651-139">="5 + 7"</span><span class="sxs-lookup"><span data-stu-id="0a651-139">="5 + 7"</span></span>  <br/> |<span data-ttu-id="0a651-140">5 + 7</span><span class="sxs-lookup"><span data-stu-id="0a651-140">5 + 7</span></span>  <br/> |
|<span data-ttu-id="0a651-141">草稿 B1</span><span class="sxs-lookup"><span data-stu-id="0a651-141">Scratch.B1</span></span>  <br/> |<span data-ttu-id="0a651-142">=If (ISERRVALUE(Scratch.A1),2,Scratch.A1)</span><span class="sxs-lookup"><span data-stu-id="0a651-142">=If (ISERRVALUE(Scratch.A1),2,Scratch.A1)</span></span>  <br/> |<span data-ttu-id="0a651-143">5 + 7</span><span class="sxs-lookup"><span data-stu-id="0a651-143">5 + 7</span></span>  <br/> |
   
<span data-ttu-id="0a651-p105">返回 12，因为返回的值不是 #VALUE! 错误，而表达式指示 Visio 返回原始单元格的值。</span><span class="sxs-lookup"><span data-stu-id="0a651-p105">Returns 12 because the value returned is not a #VALUE! error, and the expression instructs Visio to return the value of the original cell.</span></span>
  

