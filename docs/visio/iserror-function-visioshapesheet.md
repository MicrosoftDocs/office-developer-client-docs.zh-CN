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
description: 返回 TRUE 的 cellreference 值是否任何错误类型;否则，将返回 FALSE。 引用另一个单元格的公式中使用 ISERROR 函数。
ms.openlocfilehash: c93801f5d61e45be5d178027405ead3aa129654d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780489"
---
# <a name="iserror-function-visioshapesheet"></a><span data-ttu-id="8fe8e-104">ISERROR 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="8fe8e-104">ISERROR Function (VisioShapeSheet)</span></span>

<span data-ttu-id="8fe8e-105">返回 TRUE 的_cellreference_值是否任何错误类型;否则，将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="8fe8e-105">Returns TRUE if the value of  _cellreference_ is any error type; otherwise, it returns FALSE.</span></span> <span data-ttu-id="8fe8e-106">引用另一个单元格的公式中使用 ISERROR 函数。</span><span class="sxs-lookup"><span data-stu-id="8fe8e-106">The ISERROR function is used in formulas that refer to another cell.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="8fe8e-107">语法</span><span class="sxs-lookup"><span data-stu-id="8fe8e-107">Syntax</span></span>

<span data-ttu-id="8fe8e-108">ISERROR (* * *cellreference* * *)</span><span class="sxs-lookup"><span data-stu-id="8fe8e-108">ISERROR(** *cellreference* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8fe8e-109">参数</span><span class="sxs-lookup"><span data-stu-id="8fe8e-109">Parameters</span></span>

|<span data-ttu-id="8fe8e-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-110">**Name**</span></span>|<span data-ttu-id="8fe8e-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-111">**Required/Optional**</span></span>|<span data-ttu-id="8fe8e-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-112">**Data Type**</span></span>|<span data-ttu-id="8fe8e-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8fe8e-114">_cellreference_</span><span class="sxs-lookup"><span data-stu-id="8fe8e-114">_cellreference_</span></span> <br/> |<span data-ttu-id="8fe8e-115">必需</span><span class="sxs-lookup"><span data-stu-id="8fe8e-115">Required</span></span>  <br/> |<span data-ttu-id="8fe8e-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-116">**String**</span></span> <br/> |<span data-ttu-id="8fe8e-117">对单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="8fe8e-117">Reference to a cell.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="8fe8e-118">示例 1</span><span class="sxs-lookup"><span data-stu-id="8fe8e-118">Example 1</span></span>

|<span data-ttu-id="8fe8e-119">**Cell**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-119">**Cell**</span></span>|<span data-ttu-id="8fe8e-120">**Formula**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-120">**Formula**</span></span>|<span data-ttu-id="8fe8e-121">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-121">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8fe8e-122">Scratch.A1</span><span class="sxs-lookup"><span data-stu-id="8fe8e-122">Scratch.A1</span></span>  <br/> |<span data-ttu-id="8fe8e-123">=NA( )</span><span class="sxs-lookup"><span data-stu-id="8fe8e-123">=NA( )</span></span>  <br/> |<span data-ttu-id="8fe8e-124">#N/A!</span><span class="sxs-lookup"><span data-stu-id="8fe8e-124">#N/A!</span></span>  <br/> |
|<span data-ttu-id="8fe8e-125">Scratch.B1</span><span class="sxs-lookup"><span data-stu-id="8fe8e-125">Scratch.B1</span></span>  <br/> |<span data-ttu-id="8fe8e-126">=ISERROR(Scratch.A1)</span><span class="sxs-lookup"><span data-stu-id="8fe8e-126">=ISERROR(Scratch.A1)</span></span>  <br/> |<span data-ttu-id="8fe8e-127">TRUE</span><span class="sxs-lookup"><span data-stu-id="8fe8e-127">TRUE</span></span>  <br/> |
   
<span data-ttu-id="8fe8e-p103">返回 TRUE，因为 ISERROR 函数可以识别 #N/A! 错误。您可以使用 ISERR 查找除 #N/A! 错误之外的所有错误类型。</span><span class="sxs-lookup"><span data-stu-id="8fe8e-p103">Returns TRUE because the #N/A! error is recognized by the ISERROR function. You can use ISERR to find all types but the #N/A! error.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="8fe8e-132">示例 2</span><span class="sxs-lookup"><span data-stu-id="8fe8e-132">Example 2</span></span>

|<span data-ttu-id="8fe8e-133">**Cell**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-133">**Cell**</span></span>|<span data-ttu-id="8fe8e-134">**Formula**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-134">**Formula**</span></span>|<span data-ttu-id="8fe8e-135">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8fe8e-135">**Value returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8fe8e-136">Scratch.X1</span><span class="sxs-lookup"><span data-stu-id="8fe8e-136">Scratch.X1</span></span>  <br/> |<span data-ttu-id="8fe8e-137">="House"</span><span class="sxs-lookup"><span data-stu-id="8fe8e-137">="House"</span></span>  <br/> |<span data-ttu-id="8fe8e-138">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="8fe8e-138">#VALUE!</span></span>  <br/> |
|<span data-ttu-id="8fe8e-139">Scratch.B1</span><span class="sxs-lookup"><span data-stu-id="8fe8e-139">Scratch.B1</span></span>  <br/> |<span data-ttu-id="8fe8e-140">=ISERROR(Scratch.X1)</span><span class="sxs-lookup"><span data-stu-id="8fe8e-140">=ISERROR(Scratch.X1)</span></span>  <br/> |<span data-ttu-id="8fe8e-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="8fe8e-141">TRUE</span></span>  <br/> |
   
<span data-ttu-id="8fe8e-p104">返回 TRUE，因为 ISERROR 函数可以识别 #VALUE! 错误。若要基于 #VALUE! 错误生成一个表达式，请使用 ISERRVALUE 函数。</span><span class="sxs-lookup"><span data-stu-id="8fe8e-p104">Returns TRUE because the #VALUE! error is recognized by the ISERROR function. To build an expression based on the #VALUE! error, use the ISERRVALUE function.</span></span>
  

