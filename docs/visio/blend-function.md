---
title: BLEND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c67b46bb-0eb2-f094-2870-c320bd488705
description: 按 float 参数指定的比例混合两种颜色。
ms.openlocfilehash: 0a231954370416be201183026424c79942204e12
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303295"
---
# <a name="blend-function"></a><span data-ttu-id="b2fb0-103">BLEND 函数</span><span class="sxs-lookup"><span data-stu-id="b2fb0-103">BLEND Function</span></span>

<span data-ttu-id="b2fb0-104">按_float_参数指定的比例混合两种颜色。</span><span class="sxs-lookup"><span data-stu-id="b2fb0-104">Blends two colors in the proportion specified by the  _float_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b2fb0-105">语法</span><span class="sxs-lookup"><span data-stu-id="b2fb0-105">Syntax</span></span>

<span data-ttu-id="b2fb0-106">BLEND (\* \* *color1* \* \*, \* \* *color2* \* \*, \* \* *float [0, 1]* \* \*)</span><span class="sxs-lookup"><span data-stu-id="b2fb0-106">BLEND(\*\* *color1* \*\*, \*\* *color2* \*\*, \*\* *float[0,1]* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="b2fb0-107">参数</span><span class="sxs-lookup"><span data-stu-id="b2fb0-107">Parameters</span></span>

|<span data-ttu-id="b2fb0-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="b2fb0-108">**Name**</span></span>|<span data-ttu-id="b2fb0-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="b2fb0-109">**Required/Optional**</span></span>|<span data-ttu-id="b2fb0-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b2fb0-110">**Data Type**</span></span>|<span data-ttu-id="b2fb0-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="b2fb0-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b2fb0-112">_color1_</span><span class="sxs-lookup"><span data-stu-id="b2fb0-112">_color1_</span></span> <br/> |<span data-ttu-id="b2fb0-113">必需</span><span class="sxs-lookup"><span data-stu-id="b2fb0-113">Required</span></span>  <br/> |<span data-ttu-id="b2fb0-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="b2fb0-114">**Numeric**</span></span> <br/> |<span data-ttu-id="b2fb0-115">Visio 第一种颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="b2fb0-115">The Visio color index or RGB value of the first color.</span></span>  <br/> |
| <span data-ttu-id="b2fb0-116">_color2_</span><span class="sxs-lookup"><span data-stu-id="b2fb0-116">_color2_</span></span> <br/> |<span data-ttu-id="b2fb0-117">必需</span><span class="sxs-lookup"><span data-stu-id="b2fb0-117">Required</span></span>  <br/> |<span data-ttu-id="b2fb0-118">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="b2fb0-118">**Numeric**</span></span> <br/> |<span data-ttu-id="b2fb0-119">Visio 第二种颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="b2fb0-119">The Visio color index or RGB value of the second color.</span></span>  <br/> |
| <span data-ttu-id="b2fb0-120">_float [0, 1]_</span><span class="sxs-lookup"><span data-stu-id="b2fb0-120">_float[0,1]_</span></span> <br/> |<span data-ttu-id="b2fb0-121">必需</span><span class="sxs-lookup"><span data-stu-id="b2fb0-121">Required</span></span>  <br/> |<span data-ttu-id="b2fb0-122">**Float**</span><span class="sxs-lookup"><span data-stu-id="b2fb0-122">**Float**</span></span> <br/> |<span data-ttu-id="b2fb0-123">分别混合_color2_和_color1_的比例。</span><span class="sxs-lookup"><span data-stu-id="b2fb0-123">The proportion in which to blend  _color2_ and  _color1_, respectively.</span></span> <span data-ttu-id="b2fb0-124">0 到 1 之间的实数（包括这两个值）。</span><span class="sxs-lookup"><span data-stu-id="b2fb0-124">A real number from 0 to 1 inclusive.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="b2fb0-125">返回值</span><span class="sxs-lookup"><span data-stu-id="b2fb0-125">Return value</span></span>

 <span data-ttu-id="b2fb0-126">**RGB**</span><span class="sxs-lookup"><span data-stu-id="b2fb0-126">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b2fb0-127">注解</span><span class="sxs-lookup"><span data-stu-id="b2fb0-127">Remarks</span></span>

<span data-ttu-id="b2fb0-128">返回的颜色由_float_参数所指定的相对比例, 分别与_color2_和_color1_混合而成。</span><span class="sxs-lookup"><span data-stu-id="b2fb0-128">The color returned is determined by the relative proportions in which to blend  _color2_ and  _color1_, respectively, as specified by the  _float_ parameter.</span></span> <span data-ttu-id="b2fb0-129">例如, 如果_float_为 0.25, 则返回的颜色由_color1_的 75% 和 25% 的_color2_组成。</span><span class="sxs-lookup"><span data-stu-id="b2fb0-129">For example, if  _float_ is 0.25, the color returned is composed 75% of  _color1_ and 25% of  _color2_.</span></span> 
  
<span data-ttu-id="b2fb0-130">要考虑的另一种方法是, _float_值与色谱从_color1_到_color2_的点相对应。</span><span class="sxs-lookup"><span data-stu-id="b2fb0-130">Another way to think about it is that the  _float_ value corresponds to the point along the color spectrum from  _color1_ to  _color2_.</span></span> <span data-ttu-id="b2fb0-131">因此, _float_的较小数字 (更接近零) 会产生更接近_color1_的混合, 而较大的数字 (更接近于 1) 产生的融合更接近于_color2_。</span><span class="sxs-lookup"><span data-stu-id="b2fb0-131">Therefore, smaller numbers (closer to zero) for  _float_ produce blends closer to  _color1_, while larger numbers (closer to 1) produce blends closer to  _color2_.</span></span>
  

