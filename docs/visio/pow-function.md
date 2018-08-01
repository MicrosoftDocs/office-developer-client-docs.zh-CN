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
ms.openlocfilehash: 48870c679251a666a5756b2b684d262fe059eee0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780970"
---
# <a name="pow-function"></a><span data-ttu-id="4d59d-103">POW 函数</span><span class="sxs-lookup"><span data-stu-id="4d59d-103">POW Function</span></span>

<span data-ttu-id="4d59d-104">返回一个按指数幂增加的数字。</span><span class="sxs-lookup"><span data-stu-id="4d59d-104">Returns a number raised to the power of an exponent.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4d59d-105">语法</span><span class="sxs-lookup"><span data-stu-id="4d59d-105">Syntax</span></span>

<span data-ttu-id="4d59d-106">POW (* **数量** *，* **指数** *)</span><span class="sxs-lookup"><span data-stu-id="4d59d-106">POW(** *number* **, ** *exponent* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="4d59d-107">参数</span><span class="sxs-lookup"><span data-stu-id="4d59d-107">Parameters</span></span>

|<span data-ttu-id="4d59d-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="4d59d-108">**Name**</span></span>|<span data-ttu-id="4d59d-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4d59d-109">**Required/Optional**</span></span>|<span data-ttu-id="4d59d-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4d59d-110">**Data Type**</span></span>|<span data-ttu-id="4d59d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="4d59d-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4d59d-112">_number_</span><span class="sxs-lookup"><span data-stu-id="4d59d-112">_number_</span></span> <br/> |<span data-ttu-id="4d59d-113">必需</span><span class="sxs-lookup"><span data-stu-id="4d59d-113">Required</span></span>  <br/> |<span data-ttu-id="4d59d-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="4d59d-114">**Number**</span></span> <br/> |<span data-ttu-id="4d59d-115">要计算其指数次幂的数字。</span><span class="sxs-lookup"><span data-stu-id="4d59d-115">The number to raise to the power of an exponent.</span></span>  <br/> |
| <span data-ttu-id="4d59d-116">_exponent_</span><span class="sxs-lookup"><span data-stu-id="4d59d-116">_exponent_</span></span> <br/> |<span data-ttu-id="4d59d-117">必需</span><span class="sxs-lookup"><span data-stu-id="4d59d-117">Required</span></span>  <br/> |<span data-ttu-id="4d59d-118">**编号**</span><span class="sxs-lookup"><span data-stu-id="4d59d-118">**Number**</span></span> <br/> |<span data-ttu-id="4d59d-119">指数。</span><span class="sxs-lookup"><span data-stu-id="4d59d-119">The exponent.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4d59d-120">注解</span><span class="sxs-lookup"><span data-stu-id="4d59d-120">Remarks</span></span>

<span data-ttu-id="4d59d-121">_数字_和_指数_可能非整数，它们可能为负值。</span><span class="sxs-lookup"><span data-stu-id="4d59d-121">Both  _number_ and  _exponent_ may be non-integers, and they may be negative.</span></span> <span data-ttu-id="4d59d-122">如果_number_不 0 和_指数_为 0，则此函数返回 1。</span><span class="sxs-lookup"><span data-stu-id="4d59d-122">If  _number_ is not 0 and  _exponent_ is 0, this function returns 1.</span></span> <span data-ttu-id="4d59d-123">如果_数字_为 0，并且_指数_为负数，则此函数返回 0.0。</span><span class="sxs-lookup"><span data-stu-id="4d59d-123">If  _number_ is 0 and  _exponent_ is negative, this function returns 0.0.</span></span> <span data-ttu-id="4d59d-124">如果_数字_和_指数_0，或者如果_number_为负数和_指数_不是整数，此函数返回 0.0。</span><span class="sxs-lookup"><span data-stu-id="4d59d-124">If both  _number_ and  _exponent_ are 0, or if  _number_ is negative and  _exponent_ is not an integer, this function returns 0.0.</span></span> <span data-ttu-id="4d59d-125">如果_数字_和_指数_为负，此函数返回-1。 #IND.</span><span class="sxs-lookup"><span data-stu-id="4d59d-125">If both  _number_ and  _exponent_ are negative, this function returns -1.#IND.</span></span> 
  
## <a name="example"></a><span data-ttu-id="4d59d-126">示例</span><span class="sxs-lookup"><span data-stu-id="4d59d-126">Example</span></span>

<span data-ttu-id="4d59d-127">POW(5,2)</span><span class="sxs-lookup"><span data-stu-id="4d59d-127">POW(5,2)</span></span> 
  
<span data-ttu-id="4d59d-128">返回 25。</span><span class="sxs-lookup"><span data-stu-id="4d59d-128">Returns 25.</span></span> 
  

