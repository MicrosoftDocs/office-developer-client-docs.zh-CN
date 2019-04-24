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
description: 在 SETATREF 函数的 set_expression 参数中使用, 以指示在将 set_expression 分配给 SETATREF 中的 reference 参数之前应计算。
ms.openlocfilehash: a11a7485e04d4deb31e9497476bb198d675bc68f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326157"
---
# <a name="setatrefeval-function"></a><span data-ttu-id="c4547-103">SETATREFEVAL 函数</span><span class="sxs-lookup"><span data-stu-id="c4547-103">SETATREFEVAL Function</span></span>

<span data-ttu-id="c4547-104">在 SETATREF 函数的_set_expression_参数中使用, 以指示在将 set_expression 分配给 SETATREF 中的_reference_参数之前应计算__ 。</span><span class="sxs-lookup"><span data-stu-id="c4547-104">Used in the  _set_expression_ parameter of the SETATREF function to indicate that  _set_expression_ should be evaluated before assigning to the  _reference_ parameter in SETATREF.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="c4547-105">语法</span><span class="sxs-lookup"><span data-stu-id="c4547-105">Syntax</span></span>

<span data-ttu-id="c4547-106">SETATREFEVAL (\* \* *expr* \* \*)</span><span class="sxs-lookup"><span data-stu-id="c4547-106">SETATREFEVAL(\*\* *expr* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c4547-107">参数</span><span class="sxs-lookup"><span data-stu-id="c4547-107">Parameters</span></span>

|<span data-ttu-id="c4547-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="c4547-108">**Name**</span></span>|<span data-ttu-id="c4547-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c4547-109">**Required/Optional**</span></span>|<span data-ttu-id="c4547-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c4547-110">**Data Type**</span></span>|<span data-ttu-id="c4547-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="c4547-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c4547-112">_expr_</span><span class="sxs-lookup"><span data-stu-id="c4547-112">_expr_</span></span> <br/> |<span data-ttu-id="c4547-113">必需</span><span class="sxs-lookup"><span data-stu-id="c4547-113">Required</span></span>  <br/> |<span data-ttu-id="c4547-114">**相同**</span><span class="sxs-lookup"><span data-stu-id="c4547-114">**Varies**</span></span> <br/> | <span data-ttu-id="c4547-115">当 SETATREF 函数将_set_expression_重定向到另一个单元格时计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="c4547-115">An expression that is evaluated when the SETATREF function redirects  _set_expression_ to another cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c4547-116">注解</span><span class="sxs-lookup"><span data-stu-id="c4547-116">Remarks</span></span>

<span data-ttu-id="c4547-117">为引用的单元格分配 SETATREF 函数的*set_expression*参数时, 默认情况下, Microsoft Visio 会将*set_expression*作为表达式写入单元格。</span><span class="sxs-lookup"><span data-stu-id="c4547-117">When assigning the  *set_expression*  parameter of the SETATREF function to a referenced cell, Microsoft Visio writes  *set_expression*  to the cell as an expression by default.</span></span> <span data-ttu-id="c4547-118">但是, 如果 SETATREFEVAL 函数封装了*set_expression*参数的任何部分, Visio 将对表达式进行求值, 并在解析 SETATREF 表达式之前将 SETATREFEVAL 函数替换为其结果。</span><span class="sxs-lookup"><span data-stu-id="c4547-118">However, if any portion of the  *set_expression*  parameter is wrapped by the SETATREFEVAL function, Visio evaluates the expression and replaces the SETATREFEVAL function with its result prior to resolving the SETATREF expression.</span></span> 
  
## <a name="example"></a><span data-ttu-id="c4547-119">示例</span><span class="sxs-lookup"><span data-stu-id="c4547-119">Example</span></span>

<span data-ttu-id="c4547-120">有关示例，请参阅 [SETATREF](setatref-function.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="c4547-120">For an example, see the [SETATREF](setatref-function.md) function.</span></span> 
  

