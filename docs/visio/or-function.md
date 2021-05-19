---
title: OR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251476
localization_priority: Normal
ms.assetid: 6c2154fa-4190-0699-61f7-f2bdf87173ec
description: 如果任何作为参数传递的逻辑表达式为 TRUE，则返回 TRUE (1)。
ms.openlocfilehash: 175a1c72f5109caca786b823966f07836f4737f0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433505"
---
# <a name="or-function"></a><span data-ttu-id="bab82-103">OR 函数</span><span class="sxs-lookup"><span data-stu-id="bab82-103">OR Function</span></span>

<span data-ttu-id="bab82-104">如果任何作为参数传递的逻辑表达式为 TRUE，则返回 TRUE (1)。</span><span class="sxs-lookup"><span data-stu-id="bab82-104">Returns TRUE (1) if any of the logical expressions passed as parameters are TRUE.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="bab82-105">语法</span><span class="sxs-lookup"><span data-stu-id="bab82-105">Syntax</span></span>

<span data-ttu-id="bab82-106">OR (\*\* *logicalexpression1* \*\*， \*\* *logicalexpression2* \*\*,..., \*\* *logicalexpressionN* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="bab82-106">OR(\*\* *logicalexpression1* \*\*, \*\* *logicalexpression2* \*\*,..., \*\* *logicalexpressionN* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="bab82-107">参数</span><span class="sxs-lookup"><span data-stu-id="bab82-107">Parameters</span></span>

|<span data-ttu-id="bab82-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="bab82-108">**Name**</span></span>|<span data-ttu-id="bab82-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="bab82-109">**Required/Optional**</span></span>|<span data-ttu-id="bab82-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="bab82-110">**Data Type**</span></span>|<span data-ttu-id="bab82-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="bab82-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="bab82-112">_logicalexpression1_</span><span class="sxs-lookup"><span data-stu-id="bab82-112">_logicalexpression1_</span></span> <br/> |<span data-ttu-id="bab82-113">必需</span><span class="sxs-lookup"><span data-stu-id="bab82-113">Required</span></span>  <br/> |<span data-ttu-id="bab82-114">**String**</span><span class="sxs-lookup"><span data-stu-id="bab82-114">**String**</span></span> <br/> |<span data-ttu-id="bab82-115">要计算其真实性的第一个表达式。</span><span class="sxs-lookup"><span data-stu-id="bab82-115">The first expression whose truth you want to evaluate.</span></span>  <br/> |
| <span data-ttu-id="bab82-116">_logicalexpression2_</span><span class="sxs-lookup"><span data-stu-id="bab82-116">_logicalexpression2_</span></span> <br/> |<span data-ttu-id="bab82-117">必需</span><span class="sxs-lookup"><span data-stu-id="bab82-117">Required</span></span>  <br/> |<span data-ttu-id="bab82-118">**String**</span><span class="sxs-lookup"><span data-stu-id="bab82-118">**String**</span></span> <br/> |<span data-ttu-id="bab82-119">要计算其真实性的第二个表达式。</span><span class="sxs-lookup"><span data-stu-id="bab82-119">The second expression whose truth you want to evaluate.</span></span>  <br/> |
| <span data-ttu-id="bab82-120">_logicalexpressionN_</span><span class="sxs-lookup"><span data-stu-id="bab82-120">_logicalexpressionN_</span></span> <br/> |<span data-ttu-id="bab82-121">必需</span><span class="sxs-lookup"><span data-stu-id="bab82-121">Required</span></span>  <br/> |<span data-ttu-id="bab82-122">**String**</span><span class="sxs-lookup"><span data-stu-id="bab82-122">**String**</span></span> <br/> |<span data-ttu-id="bab82-123">要计算其真实性的第 N 个表达式。</span><span class="sxs-lookup"><span data-stu-id="bab82-123">The Nth expression whose truth you want to evaluate.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="bab82-124">返回值</span><span class="sxs-lookup"><span data-stu-id="bab82-124">Return value</span></span>

<span data-ttu-id="bab82-125">布尔值</span><span class="sxs-lookup"><span data-stu-id="bab82-125">Boolean</span></span>
  
## <a name="remarks"></a><span data-ttu-id="bab82-126">备注</span><span class="sxs-lookup"><span data-stu-id="bab82-126">Remarks</span></span>

<span data-ttu-id="bab82-p101">任何计算为非零值的表达式都被视为 TRUE。如果所有逻辑表达式都为 FALSE 或等于 0，则此函数将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="bab82-p101">Any expression that evaluates to a non-zero value is considered TRUE. If all of the logical expressions are FALSE or equal 0, this function returns FALSE.</span></span> 
  
## <a name="example"></a><span data-ttu-id="bab82-129">示例</span><span class="sxs-lookup"><span data-stu-id="bab82-129">Example</span></span>

<span data-ttu-id="bab82-130">或者 (Height \> 1，PinX \> 1) </span><span class="sxs-lookup"><span data-stu-id="bab82-130">OR(Height \> 1,PinX \> 1)</span></span> 
  
<span data-ttu-id="bab82-p102">如果两个表达式当中的任意一个为 TRUE，则返回 TRUE (1)。只有当两个表达式都为 FALSE 时，才返回 FALSE (0)。</span><span class="sxs-lookup"><span data-stu-id="bab82-p102">Returns TRUE (1) if either expression is TRUE. Returns FALSE (0) only if both expressions are FALSE.</span></span> 
  

