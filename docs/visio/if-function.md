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
description: 如果 logicalexpression 为 TURE，则返回 valueiftrue。 否则，将返回 valueiffalse。
ms.openlocfilehash: 8780bd3dd5ded1a950a5bf3f79333687f3b6843c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344763"
---
# <a name="if-function"></a><span data-ttu-id="f3414-104">IF 函数</span><span class="sxs-lookup"><span data-stu-id="f3414-104">IF Function</span></span>

<span data-ttu-id="f3414-105">如果_logicalexpression_为 TRUE, 则返回_valueiftrue_ 。</span><span class="sxs-lookup"><span data-stu-id="f3414-105">Returns  _valueiftrue_ if  _logicalexpression_ is TRUE.</span></span> <span data-ttu-id="f3414-106">否则, 它将返回_valueiffalse_。</span><span class="sxs-lookup"><span data-stu-id="f3414-106">Otherwise, it returns  _valueiffalse_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f3414-107">语法</span><span class="sxs-lookup"><span data-stu-id="f3414-107">Syntax</span></span>

<span data-ttu-id="f3414-108">如果 (\* \* *logicalexpression* \* \*, \* \* *valueiftrue* \* \*, \* \* *valueiffalse* \* \*)</span><span class="sxs-lookup"><span data-stu-id="f3414-108">IF(\*\* *logicalexpression* \*\*, \*\* *valueiftrue* \*\*, \*\* *valueiffalse* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f3414-109">参数</span><span class="sxs-lookup"><span data-stu-id="f3414-109">Parameters</span></span>

|<span data-ttu-id="f3414-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="f3414-110">**Name**</span></span>|<span data-ttu-id="f3414-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f3414-111">**Required/Optional**</span></span>|<span data-ttu-id="f3414-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f3414-112">**Data Type**</span></span>|<span data-ttu-id="f3414-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3414-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f3414-114">_logicalexpression_</span><span class="sxs-lookup"><span data-stu-id="f3414-114">_logicalexpression_</span></span> <br/> |<span data-ttu-id="f3414-115">必需</span><span class="sxs-lookup"><span data-stu-id="f3414-115">Required</span></span>  <br/> |<span data-ttu-id="f3414-116">**String**</span><span class="sxs-lookup"><span data-stu-id="f3414-116">**String**</span></span> <br/> |<span data-ttu-id="f3414-117">要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="f3414-117">Expression to evaluate.</span></span>  <br/> |
| <span data-ttu-id="f3414-118">_valueiftrue_</span><span class="sxs-lookup"><span data-stu-id="f3414-118">_valueiftrue_</span></span> <br/> |<span data-ttu-id="f3414-119">必需</span><span class="sxs-lookup"><span data-stu-id="f3414-119">Required</span></span>  <br/> |<span data-ttu-id="f3414-120">**相同**</span><span class="sxs-lookup"><span data-stu-id="f3414-120">**Varies**</span></span> <br/> |<span data-ttu-id="f3414-121">_logicalexpression_为 true 时要返回的值。</span><span class="sxs-lookup"><span data-stu-id="f3414-121">Value to return if  _logicalexpression_ is true.</span></span>  <br/> |
| <span data-ttu-id="f3414-122">_valueiffalse_</span><span class="sxs-lookup"><span data-stu-id="f3414-122">_valueiffalse_</span></span> <br/> |<span data-ttu-id="f3414-123">必需</span><span class="sxs-lookup"><span data-stu-id="f3414-123">Required</span></span>  <br/> |<span data-ttu-id="f3414-124">**相同**</span><span class="sxs-lookup"><span data-stu-id="f3414-124">**Varies**</span></span> <br/> | <span data-ttu-id="f3414-125">_logicalexpression_为 false 时要返回的值。</span><span class="sxs-lookup"><span data-stu-id="f3414-125">Value to return if  _logicalexpression_ is false.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="f3414-126">返回值</span><span class="sxs-lookup"><span data-stu-id="f3414-126">Return value</span></span>

<span data-ttu-id="f3414-127">各不相同</span><span class="sxs-lookup"><span data-stu-id="f3414-127">Varies</span></span>
  
## <a name="example"></a><span data-ttu-id="f3414-128">示例</span><span class="sxs-lookup"><span data-stu-id="f3414-128">Example</span></span>

<span data-ttu-id="f3414-129">IF (Height \> 1.25 in, 5, 7)</span><span class="sxs-lookup"><span data-stu-id="f3414-129">IF(Height \> 1.25 in,5,7)</span></span>
  
<span data-ttu-id="f3414-130">如果形状的高度大于 1.25 英寸，则返回 5。</span><span class="sxs-lookup"><span data-stu-id="f3414-130">Returns 5 if the shape's height is greater than 1.25 inches.</span></span> <span data-ttu-id="f3414-131">如果形状的高度小于或等于 1.25 英寸，则返回 7。</span><span class="sxs-lookup"><span data-stu-id="f3414-131">Returns 7 if the shape's height is less than or equal to 1.25 inches.</span></span>
  

