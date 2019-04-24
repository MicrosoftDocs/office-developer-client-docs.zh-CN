---
title: POW 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251483
localization_priority: Normal
ms.assetid: c6519c55-5f98-ed0d-95b1-5443d0d23c0b
description: 返回一个按指数幂增加的数字。
ms.openlocfilehash: 7a1102aa13f54d7e323247b83af3732ebb63acf4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356047"
---
# <a name="pow-function"></a><span data-ttu-id="cbc52-103">POW 函数</span><span class="sxs-lookup"><span data-stu-id="cbc52-103">POW Function</span></span>

<span data-ttu-id="cbc52-104">返回一个按指数幂增加的数字。</span><span class="sxs-lookup"><span data-stu-id="cbc52-104">Returns a number raised to the power of an exponent.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="cbc52-105">语法</span><span class="sxs-lookup"><span data-stu-id="cbc52-105">Syntax</span></span>

<span data-ttu-id="cbc52-106">POW (\* \* *number* \* \*, \* **指数** \*)</span><span class="sxs-lookup"><span data-stu-id="cbc52-106">POW(\*\* *number* \*\*, \*\* *exponent* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="cbc52-107">参数</span><span class="sxs-lookup"><span data-stu-id="cbc52-107">Parameters</span></span>

|<span data-ttu-id="cbc52-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="cbc52-108">**Name**</span></span>|<span data-ttu-id="cbc52-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="cbc52-109">**Required/Optional**</span></span>|<span data-ttu-id="cbc52-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cbc52-110">**Data Type**</span></span>|<span data-ttu-id="cbc52-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="cbc52-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cbc52-112">_number_</span><span class="sxs-lookup"><span data-stu-id="cbc52-112">_number_</span></span> <br/> |<span data-ttu-id="cbc52-113">必需</span><span class="sxs-lookup"><span data-stu-id="cbc52-113">Required</span></span>  <br/> |<span data-ttu-id="cbc52-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="cbc52-114">**Number**</span></span> <br/> |<span data-ttu-id="cbc52-115">要计算其指数次幂的数字。</span><span class="sxs-lookup"><span data-stu-id="cbc52-115">The number to raise to the power of an exponent.</span></span>  <br/> |
| <span data-ttu-id="cbc52-116">_exponent_</span><span class="sxs-lookup"><span data-stu-id="cbc52-116">_exponent_</span></span> <br/> |<span data-ttu-id="cbc52-117">必需</span><span class="sxs-lookup"><span data-stu-id="cbc52-117">Required</span></span>  <br/> |<span data-ttu-id="cbc52-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="cbc52-118">**Number**</span></span> <br/> |<span data-ttu-id="cbc52-119">指数。</span><span class="sxs-lookup"><span data-stu-id="cbc52-119">The exponent.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cbc52-120">注解</span><span class="sxs-lookup"><span data-stu-id="cbc52-120">Remarks</span></span>

<span data-ttu-id="cbc52-121">_number_和_指数_都不能为非整数, 也可以是负数。</span><span class="sxs-lookup"><span data-stu-id="cbc52-121">Both  _number_ and  _exponent_ may be non-integers, and they may be negative.</span></span> <span data-ttu-id="cbc52-122">如果_number_不是0而_指数_为 0, 则此函数返回1。</span><span class="sxs-lookup"><span data-stu-id="cbc52-122">If  _number_ is not 0 and  _exponent_ is 0, this function returns 1.</span></span> <span data-ttu-id="cbc52-123">如果_number_为0而_指数_为负, 则此函数返回0.0。</span><span class="sxs-lookup"><span data-stu-id="cbc52-123">If  _number_ is 0 and  _exponent_ is negative, this function returns 0.0.</span></span> <span data-ttu-id="cbc52-124">如果_number_和_指数_均为 0, 或者_number_为负值且_指数_不是整数, 则此函数返回0.0。</span><span class="sxs-lookup"><span data-stu-id="cbc52-124">If both  _number_ and  _exponent_ are 0, or if  _number_ is negative and  _exponent_ is not an integer, this function returns 0.0.</span></span> <span data-ttu-id="cbc52-125">如果_number_和_指数_均为负, 则此函数将返回-1 #IND。</span><span class="sxs-lookup"><span data-stu-id="cbc52-125">If both  _number_ and  _exponent_ are negative, this function returns -1.#IND.</span></span> 
  
## <a name="example"></a><span data-ttu-id="cbc52-126">示例</span><span class="sxs-lookup"><span data-stu-id="cbc52-126">Example</span></span>

<span data-ttu-id="cbc52-127">POW (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cbc52-127">POW(5,2)</span></span> 
  
<span data-ttu-id="cbc52-128">返回 25。</span><span class="sxs-lookup"><span data-stu-id="cbc52-128">Returns 25.</span></span> 
  

