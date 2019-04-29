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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405469"
---
# <a name="if-function"></a><span data-ttu-id="3713d-104">IF 函数</span><span class="sxs-lookup"><span data-stu-id="3713d-104">IF Function</span></span>

<span data-ttu-id="3713d-105">如果_logicalexpression_为 TRUE, 则返回_valueiftrue_ 。</span><span class="sxs-lookup"><span data-stu-id="3713d-105">Returns  _valueiftrue_ if  _logicalexpression_ is TRUE.</span></span> <span data-ttu-id="3713d-106">否则, 它将返回_valueiffalse_。</span><span class="sxs-lookup"><span data-stu-id="3713d-106">Otherwise, it returns  _valueiffalse_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3713d-107">语法</span><span class="sxs-lookup"><span data-stu-id="3713d-107">Syntax</span></span>

<span data-ttu-id="3713d-108">如果 (\* \* *logicalexpression* \* \*, \* \* *valueiftrue* \* \*, \* \* *valueiffalse* \* \*)</span><span class="sxs-lookup"><span data-stu-id="3713d-108">IF(\*\* *logicalexpression* \*\*, \*\* *valueiftrue* \*\*, \*\* *valueiffalse* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="3713d-109">参数</span><span class="sxs-lookup"><span data-stu-id="3713d-109">Parameters</span></span>

|<span data-ttu-id="3713d-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="3713d-110">**Name**</span></span>|<span data-ttu-id="3713d-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="3713d-111">**Required/Optional**</span></span>|<span data-ttu-id="3713d-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3713d-112">**Data Type**</span></span>|<span data-ttu-id="3713d-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="3713d-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3713d-114">_logicalexpression_</span><span class="sxs-lookup"><span data-stu-id="3713d-114">_logicalexpression_</span></span> <br/> |<span data-ttu-id="3713d-115">必需</span><span class="sxs-lookup"><span data-stu-id="3713d-115">Required</span></span>  <br/> |<span data-ttu-id="3713d-116">**String**</span><span class="sxs-lookup"><span data-stu-id="3713d-116">**String**</span></span> <br/> |<span data-ttu-id="3713d-117">要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="3713d-117">Expression to evaluate.</span></span>  <br/> |
| <span data-ttu-id="3713d-118">_valueiftrue_</span><span class="sxs-lookup"><span data-stu-id="3713d-118">_valueiftrue_</span></span> <br/> |<span data-ttu-id="3713d-119">必需</span><span class="sxs-lookup"><span data-stu-id="3713d-119">Required</span></span>  <br/> |<span data-ttu-id="3713d-120">**相同**</span><span class="sxs-lookup"><span data-stu-id="3713d-120">**Varies**</span></span> <br/> |<span data-ttu-id="3713d-121">_logicalexpression_为 true 时要返回的值。</span><span class="sxs-lookup"><span data-stu-id="3713d-121">Value to return if  _logicalexpression_ is true.</span></span>  <br/> |
| <span data-ttu-id="3713d-122">_valueiffalse_</span><span class="sxs-lookup"><span data-stu-id="3713d-122">_valueiffalse_</span></span> <br/> |<span data-ttu-id="3713d-123">必需</span><span class="sxs-lookup"><span data-stu-id="3713d-123">Required</span></span>  <br/> |<span data-ttu-id="3713d-124">**相同**</span><span class="sxs-lookup"><span data-stu-id="3713d-124">**Varies**</span></span> <br/> | <span data-ttu-id="3713d-125">_logicalexpression_为 false 时要返回的值。</span><span class="sxs-lookup"><span data-stu-id="3713d-125">Value to return if  _logicalexpression_ is false.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="3713d-126">返回值</span><span class="sxs-lookup"><span data-stu-id="3713d-126">Return value</span></span>

<span data-ttu-id="3713d-127">各不相同</span><span class="sxs-lookup"><span data-stu-id="3713d-127">Varies</span></span>
  
## <a name="example"></a><span data-ttu-id="3713d-128">示例</span><span class="sxs-lookup"><span data-stu-id="3713d-128">Example</span></span>

<span data-ttu-id="3713d-129">IF (Height \> 1.25 in, 5, 7)</span><span class="sxs-lookup"><span data-stu-id="3713d-129">IF(Height \> 1.25 in,5,7)</span></span>
  
<span data-ttu-id="3713d-130">如果形状的高度大于 1.25 英寸，则返回 5。</span><span class="sxs-lookup"><span data-stu-id="3713d-130">Returns 5 if the shape's height is greater than 1.25 inches.</span></span> <span data-ttu-id="3713d-131">如果形状的高度小于或等于 1.25 英寸，则返回 7。</span><span class="sxs-lookup"><span data-stu-id="3713d-131">Returns 7 if the shape's height is less than or equal to 1.25 inches.</span></span>
  

