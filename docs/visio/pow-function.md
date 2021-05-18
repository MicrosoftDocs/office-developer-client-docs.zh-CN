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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406309"
---
# <a name="pow-function"></a><span data-ttu-id="8c5e2-103">POW 函数</span><span class="sxs-lookup"><span data-stu-id="8c5e2-103">POW Function</span></span>

<span data-ttu-id="8c5e2-104">返回一个按指数幂增加的数字。</span><span class="sxs-lookup"><span data-stu-id="8c5e2-104">Returns a number raised to the power of an exponent.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8c5e2-105">语法</span><span class="sxs-lookup"><span data-stu-id="8c5e2-105">Syntax</span></span>

<span data-ttu-id="8c5e2-106">POW (\*\* *number* \*\*， \*\* *exponent* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="8c5e2-106">POW(\*\* *number* \*\*, \*\* *exponent* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8c5e2-107">参数</span><span class="sxs-lookup"><span data-stu-id="8c5e2-107">Parameters</span></span>

|<span data-ttu-id="8c5e2-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="8c5e2-108">**Name**</span></span>|<span data-ttu-id="8c5e2-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8c5e2-109">**Required/Optional**</span></span>|<span data-ttu-id="8c5e2-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8c5e2-110">**Data Type**</span></span>|<span data-ttu-id="8c5e2-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="8c5e2-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8c5e2-112">_number_</span><span class="sxs-lookup"><span data-stu-id="8c5e2-112">_number_</span></span> <br/> |<span data-ttu-id="8c5e2-113">必需</span><span class="sxs-lookup"><span data-stu-id="8c5e2-113">Required</span></span>  <br/> |<span data-ttu-id="8c5e2-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="8c5e2-114">**Number**</span></span> <br/> |<span data-ttu-id="8c5e2-115">要计算其指数次幂的数字。</span><span class="sxs-lookup"><span data-stu-id="8c5e2-115">The number to raise to the power of an exponent.</span></span>  <br/> |
| <span data-ttu-id="8c5e2-116">_exponent_</span><span class="sxs-lookup"><span data-stu-id="8c5e2-116">_exponent_</span></span> <br/> |<span data-ttu-id="8c5e2-117">必需</span><span class="sxs-lookup"><span data-stu-id="8c5e2-117">Required</span></span>  <br/> |<span data-ttu-id="8c5e2-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="8c5e2-118">**Number**</span></span> <br/> |<span data-ttu-id="8c5e2-119">指数。</span><span class="sxs-lookup"><span data-stu-id="8c5e2-119">The exponent.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8c5e2-120">备注</span><span class="sxs-lookup"><span data-stu-id="8c5e2-120">Remarks</span></span>

<span data-ttu-id="8c5e2-121">_number_ 和 _exponent_ 可能是非整数，并且可能是负数。</span><span class="sxs-lookup"><span data-stu-id="8c5e2-121">Both  _number_ and  _exponent_ may be non-integers, and they may be negative.</span></span> <span data-ttu-id="8c5e2-122">如果  _number_ 不为 0，  _指数_ 为 0，则此函数返回 1。</span><span class="sxs-lookup"><span data-stu-id="8c5e2-122">If  _number_ is not 0 and  _exponent_ is 0, this function returns 1.</span></span> <span data-ttu-id="8c5e2-123">如果  _number_ 为  _0，指数为_ 负数，则此函数返回 0.0。</span><span class="sxs-lookup"><span data-stu-id="8c5e2-123">If  _number_ is 0 and  _exponent_ is negative, this function returns 0.0.</span></span> <span data-ttu-id="8c5e2-124">如果  _number 和_  _exponent_ 都为 0，或者  _number_ 为负数且  _exponent_ 不是整数，则此函数返回 0.0。</span><span class="sxs-lookup"><span data-stu-id="8c5e2-124">If both  _number_ and  _exponent_ are 0, or if  _number_ is negative and  _exponent_ is not an integer, this function returns 0.0.</span></span> <span data-ttu-id="8c5e2-125">如果  _number 和_  _exponent_ 都是负数，则此函数返回 -1.#IND。</span><span class="sxs-lookup"><span data-stu-id="8c5e2-125">If both  _number_ and  _exponent_ are negative, this function returns -1.#IND.</span></span> 
  
## <a name="example"></a><span data-ttu-id="8c5e2-126">示例</span><span class="sxs-lookup"><span data-stu-id="8c5e2-126">Example</span></span>

<span data-ttu-id="8c5e2-127">POW (5，2) </span><span class="sxs-lookup"><span data-stu-id="8c5e2-127">POW(5,2)</span></span> 
  
<span data-ttu-id="8c5e2-128">返回 25。</span><span class="sxs-lookup"><span data-stu-id="8c5e2-128">Returns 25.</span></span> 
  

