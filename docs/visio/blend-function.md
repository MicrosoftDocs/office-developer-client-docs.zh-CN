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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432784"
---
# <a name="blend-function"></a><span data-ttu-id="7f158-103">BLEND 函数</span><span class="sxs-lookup"><span data-stu-id="7f158-103">BLEND Function</span></span>

<span data-ttu-id="7f158-104">按 float 参数指定的比例  _混合两种颜色_ 。</span><span class="sxs-lookup"><span data-stu-id="7f158-104">Blends two colors in the proportion specified by the  _float_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="7f158-105">语法</span><span class="sxs-lookup"><span data-stu-id="7f158-105">Syntax</span></span>

<span data-ttu-id="7f158-106">BLEND (\*\* *color1* \*\*， \*\* *color2* \*\*， \*\* *float[0，1]* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="7f158-106">BLEND(\*\* *color1* \*\*, \*\* *color2* \*\*, \*\* *float[0,1]* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7f158-107">参数</span><span class="sxs-lookup"><span data-stu-id="7f158-107">Parameters</span></span>

|<span data-ttu-id="7f158-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="7f158-108">**Name**</span></span>|<span data-ttu-id="7f158-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7f158-109">**Required/Optional**</span></span>|<span data-ttu-id="7f158-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7f158-110">**Data Type**</span></span>|<span data-ttu-id="7f158-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="7f158-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7f158-112">_color1_</span><span class="sxs-lookup"><span data-stu-id="7f158-112">_color1_</span></span> <br/> |<span data-ttu-id="7f158-113">必需</span><span class="sxs-lookup"><span data-stu-id="7f158-113">Required</span></span>  <br/> |<span data-ttu-id="7f158-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="7f158-114">**Numeric**</span></span> <br/> |<span data-ttu-id="7f158-115">Visio 第一种颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="7f158-115">The Visio color index or RGB value of the first color.</span></span>  <br/> |
| <span data-ttu-id="7f158-116">_color2_</span><span class="sxs-lookup"><span data-stu-id="7f158-116">_color2_</span></span> <br/> |<span data-ttu-id="7f158-117">必需</span><span class="sxs-lookup"><span data-stu-id="7f158-117">Required</span></span>  <br/> |<span data-ttu-id="7f158-118">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="7f158-118">**Numeric**</span></span> <br/> |<span data-ttu-id="7f158-119">Visio 第二种颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="7f158-119">The Visio color index or RGB value of the second color.</span></span>  <br/> |
| <span data-ttu-id="7f158-120">_float[0，1]_</span><span class="sxs-lookup"><span data-stu-id="7f158-120">_float[0,1]_</span></span> <br/> |<span data-ttu-id="7f158-121">必需</span><span class="sxs-lookup"><span data-stu-id="7f158-121">Required</span></span>  <br/> |<span data-ttu-id="7f158-122">**Float**</span><span class="sxs-lookup"><span data-stu-id="7f158-122">**Float**</span></span> <br/> |<span data-ttu-id="7f158-123">分别混合  _color2_ 和  _color1_ 的比例。</span><span class="sxs-lookup"><span data-stu-id="7f158-123">The proportion in which to blend  _color2_ and  _color1_, respectively.</span></span> <span data-ttu-id="7f158-124">0 到 1 之间的实数（包括这两个值）。</span><span class="sxs-lookup"><span data-stu-id="7f158-124">A real number from 0 to 1 inclusive.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="7f158-125">返回值</span><span class="sxs-lookup"><span data-stu-id="7f158-125">Return value</span></span>

 <span data-ttu-id="7f158-126">**RGB**</span><span class="sxs-lookup"><span data-stu-id="7f158-126">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7f158-127">备注</span><span class="sxs-lookup"><span data-stu-id="7f158-127">Remarks</span></span>

<span data-ttu-id="7f158-128">返回的颜色由分别混合  _color2_ 和  _color1_ 的相对比例决定，由  _float_ 参数指定。</span><span class="sxs-lookup"><span data-stu-id="7f158-128">The color returned is determined by the relative proportions in which to blend  _color2_ and  _color1_, respectively, as specified by the  _float_ parameter.</span></span> <span data-ttu-id="7f158-129">例如，如果  _float_ 为 0.25，则返回的颜色由  _color1_ 的 75% 和  _color2_ 的 25% 组成。</span><span class="sxs-lookup"><span data-stu-id="7f158-129">For example, if  _float_ is 0.25, the color returned is composed 75% of  _color1_ and 25% of  _color2_.</span></span> 
  
<span data-ttu-id="7f158-130">考虑它的另一种方式是浮点值对应于从 color1 到 _color2_ 的色谱 _中的点_。</span><span class="sxs-lookup"><span data-stu-id="7f158-130">Another way to think about it is that the  _float_ value corresponds to the point along the color spectrum from  _color1_ to  _color2_.</span></span> <span data-ttu-id="7f158-131">因此，浮 (的) 较小的数字会生成更靠近 color1 的混合，而较大的数字 (接近 1) 产生更接近 _color2_ 的 _混合_。</span><span class="sxs-lookup"><span data-stu-id="7f158-131">Therefore, smaller numbers (closer to zero) for  _float_ produce blends closer to  _color1_, while larger numbers (closer to 1) produce blends closer to  _color2_.</span></span>
  

