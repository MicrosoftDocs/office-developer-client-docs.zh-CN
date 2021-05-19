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
description: 在 SETATREF set_expression 的 set_expression 参数中用于指示在将set_expression SETATREF 中的引用参数之前应先计算该参数。
ms.openlocfilehash: a11a7485e04d4deb31e9497476bb198d675bc68f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432980"
---
# <a name="setatrefeval-function"></a><span data-ttu-id="ae9d7-103">SETATREFEVAL 函数</span><span class="sxs-lookup"><span data-stu-id="ae9d7-103">SETATREFEVAL Function</span></span>

<span data-ttu-id="ae9d7-104">在 SETATREF set_expression 的 set_expression 参数中用来指示在将 set_expression分配给 SETATREF 中的 _引用_ 参数之前应先计算该参数。 </span><span class="sxs-lookup"><span data-stu-id="ae9d7-104">Used in the  _set_expression_ parameter of the SETATREF function to indicate that  _set_expression_ should be evaluated before assigning to the  _reference_ parameter in SETATREF.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ae9d7-105">语法</span><span class="sxs-lookup"><span data-stu-id="ae9d7-105">Syntax</span></span>

<span data-ttu-id="ae9d7-106">SETATREFEVAL (\*\* *expr* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="ae9d7-106">SETATREFEVAL(\*\* *expr* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ae9d7-107">参数</span><span class="sxs-lookup"><span data-stu-id="ae9d7-107">Parameters</span></span>

|<span data-ttu-id="ae9d7-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="ae9d7-108">**Name**</span></span>|<span data-ttu-id="ae9d7-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ae9d7-109">**Required/Optional**</span></span>|<span data-ttu-id="ae9d7-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ae9d7-110">**Data Type**</span></span>|<span data-ttu-id="ae9d7-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae9d7-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ae9d7-112">_expr_</span><span class="sxs-lookup"><span data-stu-id="ae9d7-112">_expr_</span></span> <br/> |<span data-ttu-id="ae9d7-113">必需</span><span class="sxs-lookup"><span data-stu-id="ae9d7-113">Required</span></span>  <br/> |<span data-ttu-id="ae9d7-114">**变化**</span><span class="sxs-lookup"><span data-stu-id="ae9d7-114">**Varies**</span></span> <br/> | <span data-ttu-id="ae9d7-115">一个表达式，在 SETATREF 函数将 set_expression重定向到  _另_ 一个单元格时计算。</span><span class="sxs-lookup"><span data-stu-id="ae9d7-115">An expression that is evaluated when the SETATREF function redirects  _set_expression_ to another cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ae9d7-116">备注</span><span class="sxs-lookup"><span data-stu-id="ae9d7-116">Remarks</span></span>

<span data-ttu-id="ae9d7-117">将 SETATREF set_expression 的 *set_expression* 参数分配给引用的单元格时，Microsoft Visio 默认情况下会将set_expression作为表达式写入该单元格。</span><span class="sxs-lookup"><span data-stu-id="ae9d7-117">When assigning the  *set_expression*  parameter of the SETATREF function to a referenced cell, Microsoft Visio writes  *set_expression*  to the cell as an expression by default.</span></span> <span data-ttu-id="ae9d7-118">但是，如果 *set_expression* 参数的任何部分由 SETATREFEVAL 函数包装，Visio 将计算表达式，在解析 SETATREF 表达式之前，将 SETATREFEVAL 函数替换为其结果。</span><span class="sxs-lookup"><span data-stu-id="ae9d7-118">However, if any portion of the  *set_expression*  parameter is wrapped by the SETATREFEVAL function, Visio evaluates the expression and replaces the SETATREFEVAL function with its result prior to resolving the SETATREF expression.</span></span> 
  
## <a name="example"></a><span data-ttu-id="ae9d7-119">示例</span><span class="sxs-lookup"><span data-stu-id="ae9d7-119">Example</span></span>

<span data-ttu-id="ae9d7-120">有关示例，请参阅 [SETATREF](setatref-function.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="ae9d7-120">For an example, see the [SETATREF](setatref-function.md) function.</span></span> 
  

