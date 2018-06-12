---
title: SETATREFEVAL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1042150
localization_priority: Normal
ms.assetid: b3f3a0a0-7b14-0b71-d247-ada81b93b66b
description: SETATREF 函数的 set_expression 参数中用于指示该 set_expression 应计算之前将分配给中 SETATREF 引用参数。
ms.openlocfilehash: 0826ef9ca91e180576c0b2611452758b238736a6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781235"
---
# <a name="setatrefeval-function"></a><span data-ttu-id="28832-103">SETATREFEVAL 函数</span><span class="sxs-lookup"><span data-stu-id="28832-103">SETATREFEVAL Function</span></span>

<span data-ttu-id="28832-104">SETATREF 函数的_set_expression_参数中用于指示在 SETATREF_引用_参数为分配之前应计算_set_expression_的。</span><span class="sxs-lookup"><span data-stu-id="28832-104">Used in the  _set_expression_ parameter of the SETATREF function to indicate that  _set_expression_ should be evaluated before assigning to the  _reference_ parameter in SETATREF.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="28832-105">语法</span><span class="sxs-lookup"><span data-stu-id="28832-105">Syntax</span></span>

<span data-ttu-id="28832-106">SETATREFEVAL (* * *expr* * *)</span><span class="sxs-lookup"><span data-stu-id="28832-106">SETATREFEVAL(** *expr* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="28832-107">参数</span><span class="sxs-lookup"><span data-stu-id="28832-107">Parameters</span></span>

|<span data-ttu-id="28832-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="28832-108">**Name**</span></span>|<span data-ttu-id="28832-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="28832-109">**Required/Optional**</span></span>|<span data-ttu-id="28832-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="28832-110">**Data Type**</span></span>|<span data-ttu-id="28832-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="28832-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="28832-112">_expr_</span><span class="sxs-lookup"><span data-stu-id="28832-112">_expr_</span></span> <br/> |<span data-ttu-id="28832-113">必需</span><span class="sxs-lookup"><span data-stu-id="28832-113">Required</span></span>  <br/> |<span data-ttu-id="28832-114">**而异**</span><span class="sxs-lookup"><span data-stu-id="28832-114">**Varies**</span></span> <br/> | <span data-ttu-id="28832-115">SETATREF 函数将_set_expression_重定向到另一个单元格时计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="28832-115">An expression that is evaluated when the SETATREF function redirects  _set_expression_ to another cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="28832-116">备注</span><span class="sxs-lookup"><span data-stu-id="28832-116">Remarks</span></span>

<span data-ttu-id="28832-117">将 SETATREF 函数的*set_expression*参数分配给引用的单元格，Microsoft Visio 将*set_expression*写入单元格表达式作为默认情况下。</span><span class="sxs-lookup"><span data-stu-id="28832-117">When assigning the  *set_expression*  parameter of the SETATREF function to a referenced cell, Microsoft Visio writes  *set_expression*  to the cell as an expression by default.</span></span> <span data-ttu-id="28832-118">但是，如果*set_expression*参数的任何部分由 SETATREFEVAL 函数包装，Visio 将计算表达式并 SETATREFEVAL 函数替换之前解析 SETATREF 表达式及其结果。</span><span class="sxs-lookup"><span data-stu-id="28832-118">However, if any portion of the  *set_expression*  parameter is wrapped by the SETATREFEVAL function, Visio evaluates the expression and replaces the SETATREFEVAL function with its result prior to resolving the SETATREF expression.</span></span> 
  
## <a name="example"></a><span data-ttu-id="28832-119">示例</span><span class="sxs-lookup"><span data-stu-id="28832-119">Example</span></span>

<span data-ttu-id="28832-120">有关示例，请参阅[SETATREF](setatref-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="28832-120">For an example, see the [SETATREF](setatref-function.md) function.</span></span> 
  

