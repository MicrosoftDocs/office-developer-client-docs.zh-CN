---
title: AND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251391
localization_priority: Normal
ms.assetid: 434d7ceb-1050-c667-fb3d-b6634440c18e
description: 如果提供的所有逻辑表达式都为 TRUE，则返回 TRUE (1)。如果其中有任何逻辑表达式为 FALSE 或 0，则 AND 函数返回 FALSE (0)。
ms.openlocfilehash: 74e8301718e69a2ab61f6bf9992d0d6855bbc6f1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422010"
---
# <a name="and-function"></a><span data-ttu-id="c561c-104">AND 函数</span><span class="sxs-lookup"><span data-stu-id="c561c-104">AND Function</span></span>

<span data-ttu-id="c561c-p102">如果提供的所有逻辑表达式都为 TRUE，则返回 TRUE (1)。如果其中有任何逻辑表达式为 FALSE 或 0，则 AND 函数返回 FALSE (0)。</span><span class="sxs-lookup"><span data-stu-id="c561c-p102">Returns TRUE (1) if all of the logical expressions supplied are TRUE. If any of the logical expressions are FALSE or 0, the AND function returns FALSE (0).</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c561c-107">语法</span><span class="sxs-lookup"><span data-stu-id="c561c-107">Syntax</span></span>

<span data-ttu-id="c561c-108">AND (\*\* *logical expression1* \*\*， \*\* *logical expression2* \*\*,..., \*\* *logical expressionN* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="c561c-108">AND(\*\* *logical expression1* \*\*, \*\* *logical expression2* \*\*,..., \*\* *logical expressionN* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c561c-109">参数</span><span class="sxs-lookup"><span data-stu-id="c561c-109">Parameters</span></span>

|<span data-ttu-id="c561c-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="c561c-110">**Name**</span></span>|<span data-ttu-id="c561c-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c561c-111">**Required/Optional**</span></span>|<span data-ttu-id="c561c-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c561c-112">**Data Type**</span></span>|<span data-ttu-id="c561c-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="c561c-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c561c-114">_逻辑表达式_</span><span class="sxs-lookup"><span data-stu-id="c561c-114">_logical expression_</span></span> <br/> |<span data-ttu-id="c561c-115">必需</span><span class="sxs-lookup"><span data-stu-id="c561c-115">Required</span></span>  <br/> |<span data-ttu-id="c561c-116">**String**</span><span class="sxs-lookup"><span data-stu-id="c561c-116">**String**</span></span> <br/> | <span data-ttu-id="c561c-p103">常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。任何计算结果等于非零值的表达式都被视为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c561c-p103">A combination of constants, operators, functions, and references to ShapeSheet cells that results in a value. Any expression that evaluates to a non-zero value is considered to be TRUE.</span></span>  <br/> |
   
## <a name="example"></a><span data-ttu-id="c561c-119">示例</span><span class="sxs-lookup"><span data-stu-id="c561c-119">Example</span></span>

<span data-ttu-id="c561c-120">AND (Height \> 1，PinX \> 1) </span><span class="sxs-lookup"><span data-stu-id="c561c-120">AND(Height \> 1, PinX \> 1)</span></span>
  
<span data-ttu-id="c561c-p104">如果两个表达式都是 TRUE，则返回 TRUE。如果任意一个表达式为 FALSE，则返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="c561c-p104">Returns TRUE if both expressions are TRUE. Returns FALSE if either expression is FALSE.</span></span>
  

