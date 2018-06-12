---
title: BLEND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c67b46bb-0eb2-f094-2870-c320bd488705
description: 混合两种颜色按 float 参数指定的比例。
ms.openlocfilehash: 61993cea9eed6583d62004e1c756368b67c7bb33
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779768"
---
# <a name="blend-function"></a><span data-ttu-id="53c59-103">BLEND 函数</span><span class="sxs-lookup"><span data-stu-id="53c59-103">BLEND Function</span></span>

<span data-ttu-id="53c59-104">混合两种颜色按_float_参数指定的比例。</span><span class="sxs-lookup"><span data-stu-id="53c59-104">Blends two colors in the proportion specified by the  _float_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="53c59-105">语法</span><span class="sxs-lookup"><span data-stu-id="53c59-105">Syntax</span></span>

<span data-ttu-id="53c59-106">混合 (* * *color1* * *，* * *color2* * *，* * *float [0，1]* * *)</span><span class="sxs-lookup"><span data-stu-id="53c59-106">BLEND(** *color1* **, ** *color2* **, ** *float[0,1]* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="53c59-107">参数</span><span class="sxs-lookup"><span data-stu-id="53c59-107">Parameters</span></span>

|<span data-ttu-id="53c59-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="53c59-108">**Name**</span></span>|<span data-ttu-id="53c59-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="53c59-109">**Required/Optional**</span></span>|<span data-ttu-id="53c59-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="53c59-110">**Data Type**</span></span>|<span data-ttu-id="53c59-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="53c59-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="53c59-112">_color1_</span><span class="sxs-lookup"><span data-stu-id="53c59-112">_color1_</span></span> <br/> |<span data-ttu-id="53c59-113">必需</span><span class="sxs-lookup"><span data-stu-id="53c59-113">Required</span></span>  <br/> |<span data-ttu-id="53c59-114">**数字**</span><span class="sxs-lookup"><span data-stu-id="53c59-114">**Numeric**</span></span> <br/> |<span data-ttu-id="53c59-115">Visio 第一种颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="53c59-115">The Visio color index or RGB value of the first color.</span></span>  <br/> |
| <span data-ttu-id="53c59-116">_color2_</span><span class="sxs-lookup"><span data-stu-id="53c59-116">_color2_</span></span> <br/> |<span data-ttu-id="53c59-117">必需</span><span class="sxs-lookup"><span data-stu-id="53c59-117">Required</span></span>  <br/> |<span data-ttu-id="53c59-118">**数字**</span><span class="sxs-lookup"><span data-stu-id="53c59-118">**Numeric**</span></span> <br/> |<span data-ttu-id="53c59-119">Visio 第二种颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="53c59-119">The Visio color index or RGB value of the second color.</span></span>  <br/> |
| <span data-ttu-id="53c59-120">_float [0，1]_</span><span class="sxs-lookup"><span data-stu-id="53c59-120">_float[0,1]_</span></span> <br/> |<span data-ttu-id="53c59-121">必需</span><span class="sxs-lookup"><span data-stu-id="53c59-121">Required</span></span>  <br/> |<span data-ttu-id="53c59-122">**Float**</span><span class="sxs-lookup"><span data-stu-id="53c59-122">**Float**</span></span> <br/> |<span data-ttu-id="53c59-123">用于混合_color2_和_color1_，分别比例。</span><span class="sxs-lookup"><span data-stu-id="53c59-123">The proportion in which to blend  _color2_ and  _color1_, respectively.</span></span> <span data-ttu-id="53c59-124">实数从 0 到 1 之间。</span><span class="sxs-lookup"><span data-stu-id="53c59-124">A real number from 0 to 1 inclusive.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="53c59-125">返回值</span><span class="sxs-lookup"><span data-stu-id="53c59-125">Return value</span></span>

 <span data-ttu-id="53c59-126">**RGB**</span><span class="sxs-lookup"><span data-stu-id="53c59-126">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="53c59-127">备注</span><span class="sxs-lookup"><span data-stu-id="53c59-127">Remarks</span></span>

<span data-ttu-id="53c59-128">返回的颜色由用于混合_color2_和_color1_，分别，按_float_参数指定的相对比例决定。</span><span class="sxs-lookup"><span data-stu-id="53c59-128">The color returned is determined by the relative proportions in which to blend  _color2_ and  _color1_, respectively, as specified by the  _float_ parameter.</span></span> <span data-ttu-id="53c59-129">例如，如果_float_为 0.25，返回的颜色是 color1 的组合的 75%__ 和_color2_的 25%。</span><span class="sxs-lookup"><span data-stu-id="53c59-129">For example, if  _float_ is 0.25, the color returned is composed 75% of  _color1_ and 25% of  _color2_.</span></span> 
  
<span data-ttu-id="53c59-130">另一种方法需要考虑的事项它是对应于沿颜色彩虹的点的_浮点_值从_color1_到_color2_。</span><span class="sxs-lookup"><span data-stu-id="53c59-130">Another way to think about it is that the  _float_ value corresponds to the point along the color spectrum from  _color1_ to  _color2_.</span></span> <span data-ttu-id="53c59-131">因此，较小数字 （接近零） 的接近_float_生成混合_color1_，对大数字 （接近 1） 时生成混合接近到_color2_。</span><span class="sxs-lookup"><span data-stu-id="53c59-131">Therefore, smaller numbers (closer to zero) for  _float_ produce blends closer to  _color1_, while larger numbers (closer to 1) produce blends closer to  _color2_.</span></span>
  

