---
title: IF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251442
localization_priority: Normal
ms.assetid: 66771ad3-0fb3-68ff-81da-d1162d37c05a
description: 如果 logicalexpression 为 TURE，则返回 valueiftrue。否则，将返回 valueiffalse。
ms.openlocfilehash: 55938e8bd78c02badb98f90665c5c26cdd70f3b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780433"
---
# <a name="if-function"></a><span data-ttu-id="c3c5f-104">IF 函数</span><span class="sxs-lookup"><span data-stu-id="c3c5f-104">IF Function</span></span>

<span data-ttu-id="c3c5f-105">如果_在 logicalexpression_为 TRUE，则返回_valueiftrue_ 。</span><span class="sxs-lookup"><span data-stu-id="c3c5f-105">Returns  _valueiftrue_ if  _logicalexpression_ is TRUE.</span></span> <span data-ttu-id="c3c5f-106">否则，它返回_valueiffalse_。</span><span class="sxs-lookup"><span data-stu-id="c3c5f-106">Otherwise, it returns  _valueiffalse_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c3c5f-107">语法</span><span class="sxs-lookup"><span data-stu-id="c3c5f-107">Syntax</span></span>

<span data-ttu-id="c3c5f-108">如果 (* **在 logicalexpression* * *，* * *valueiftrue* * *，* * *valueiffalse* * *)</span><span class="sxs-lookup"><span data-stu-id="c3c5f-108">IF(** *logicalexpression* **, ** *valueiftrue* **, ** *valueiffalse* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c3c5f-109">参数</span><span class="sxs-lookup"><span data-stu-id="c3c5f-109">Parameters</span></span>

|<span data-ttu-id="c3c5f-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="c3c5f-110">**Name**</span></span>|<span data-ttu-id="c3c5f-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c3c5f-111">**Required/Optional**</span></span>|<span data-ttu-id="c3c5f-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c3c5f-112">**Data Type**</span></span>|<span data-ttu-id="c3c5f-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="c3c5f-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c3c5f-114">_在 logicalexpression_</span><span class="sxs-lookup"><span data-stu-id="c3c5f-114">_logicalexpression_</span></span> <br/> |<span data-ttu-id="c3c5f-115">必需</span><span class="sxs-lookup"><span data-stu-id="c3c5f-115">Required</span></span>  <br/> |<span data-ttu-id="c3c5f-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="c3c5f-116">**String**</span></span> <br/> |<span data-ttu-id="c3c5f-117">要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="c3c5f-117">Expression to evaluate.</span></span>  <br/> |
| <span data-ttu-id="c3c5f-118">_valueiftrue_</span><span class="sxs-lookup"><span data-stu-id="c3c5f-118">_valueiftrue_</span></span> <br/> |<span data-ttu-id="c3c5f-119">必需</span><span class="sxs-lookup"><span data-stu-id="c3c5f-119">Required</span></span>  <br/> |<span data-ttu-id="c3c5f-120">**因情况而异**</span><span class="sxs-lookup"><span data-stu-id="c3c5f-120">**Varies**</span></span> <br/> |<span data-ttu-id="c3c5f-121">返回_在 logicalexpression_为 true 的值。</span><span class="sxs-lookup"><span data-stu-id="c3c5f-121">Value to return if  _logicalexpression_ is true.</span></span>  <br/> |
| <span data-ttu-id="c3c5f-122">_valueiffalse_</span><span class="sxs-lookup"><span data-stu-id="c3c5f-122">_valueiffalse_</span></span> <br/> |<span data-ttu-id="c3c5f-123">必需</span><span class="sxs-lookup"><span data-stu-id="c3c5f-123">Required</span></span>  <br/> |<span data-ttu-id="c3c5f-124">**因情况而异**</span><span class="sxs-lookup"><span data-stu-id="c3c5f-124">**Varies**</span></span> <br/> | <span data-ttu-id="c3c5f-125">返回_在 logicalexpression_为 false 的值。</span><span class="sxs-lookup"><span data-stu-id="c3c5f-125">Value to return if  _logicalexpression_ is false.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="c3c5f-126">返回值</span><span class="sxs-lookup"><span data-stu-id="c3c5f-126">Return value</span></span>

<span data-ttu-id="c3c5f-127">因情况而异</span><span class="sxs-lookup"><span data-stu-id="c3c5f-127">Varies</span></span>
  
## <a name="example"></a><span data-ttu-id="c3c5f-128">示例</span><span class="sxs-lookup"><span data-stu-id="c3c5f-128">Example</span></span>

<span data-ttu-id="c3c5f-129">如果 (高度\>中的 1.25 5、 7)</span><span class="sxs-lookup"><span data-stu-id="c3c5f-129">IF(Height \> 1.25 in,5,7)</span></span>
  
<span data-ttu-id="c3c5f-p103">如果形状的高度大于 1.25 英寸，则返回 5。如果形状的高度小于或等于 1.25 英寸，则返回 7。</span><span class="sxs-lookup"><span data-stu-id="c3c5f-p103">Returns 5 if the shape's height is greater than 1.25 inches. Returns 7 if the shape's height is less than or equal to 1.25 inches.</span></span>
  

