---
title: HSL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251438
localization_priority: Normal
ms.assetid: c9314c39-1d2e-a18f-c01b-8817286099dc
description: 返回一个值，该值代表文档的调色板中的索引。 它按色调、饱和度和亮度分量指定颜色。
ms.openlocfilehash: 55703239395c54beedf4b7383435253f9c37006f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420960"
---
# <a name="hsl-function"></a><span data-ttu-id="fffeb-104">HSL 函数</span><span class="sxs-lookup"><span data-stu-id="fffeb-104">HSL Function</span></span>

<span data-ttu-id="fffeb-105">返回一个值，该值代表文档的调色板中的索引。</span><span class="sxs-lookup"><span data-stu-id="fffeb-105">Returns a value representing an index in the document's color palette.</span></span> <span data-ttu-id="fffeb-106">它按色调、饱和度和亮度分量指定颜色。</span><span class="sxs-lookup"><span data-stu-id="fffeb-106">It specifies a color by its hue, saturation, and luminosity components.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="fffeb-107">语法</span><span class="sxs-lookup"><span data-stu-id="fffeb-107">Syntax</span></span>

<span data-ttu-id="fffeb-108">HSL (\*\* *hue* \*\*， \*\* *saturation* \*\*， \*\* *luminosity* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="fffeb-108">HSL(\*\* *hue* \*\*, \*\* *saturation* \*\*, \*\* *luminosity* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="fffeb-109">参数</span><span class="sxs-lookup"><span data-stu-id="fffeb-109">Parameters</span></span>

|<span data-ttu-id="fffeb-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="fffeb-110">**Name**</span></span>|<span data-ttu-id="fffeb-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="fffeb-111">**Required/Optional**</span></span>|<span data-ttu-id="fffeb-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fffeb-112">**Data Type**</span></span>|<span data-ttu-id="fffeb-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="fffeb-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="fffeb-114">_hue_</span><span class="sxs-lookup"><span data-stu-id="fffeb-114">_hue_</span></span> <br/> |<span data-ttu-id="fffeb-115">必需</span><span class="sxs-lookup"><span data-stu-id="fffeb-115">Required</span></span>  <br/> |<span data-ttu-id="fffeb-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="fffeb-116">**Number**</span></span> <br/> |<span data-ttu-id="fffeb-117">颜色的色调，表示为 0 至 239 之间的数字（包括 0 和 239），或可计算出此类数值的表达式。</span><span class="sxs-lookup"><span data-stu-id="fffeb-117">The color's hue, expressed as a number in the range 0 to 239, inclusive, or an expression that evaluates to such a number.</span></span>  <br/> |
| <span data-ttu-id="fffeb-118">_饱和度_</span><span class="sxs-lookup"><span data-stu-id="fffeb-118">_saturation_</span></span> <br/> |<span data-ttu-id="fffeb-119">必需</span><span class="sxs-lookup"><span data-stu-id="fffeb-119">Required</span></span>  <br/> |<span data-ttu-id="fffeb-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="fffeb-120">**Number**</span></span> <br/> |<span data-ttu-id="fffeb-121">颜色的饱和度，表示为 0 至 240 之间的数字（包括 0 和 240），或可计算出此类数值的表达式。</span><span class="sxs-lookup"><span data-stu-id="fffeb-121">The color's saturation, expressed as a number in the range 0 to 240, inclusive, or an expression that evaluates to such a number.</span></span>  <br/> |
| <span data-ttu-id="fffeb-122">_亮度_</span><span class="sxs-lookup"><span data-stu-id="fffeb-122">_luminosity_</span></span> <br/> |<span data-ttu-id="fffeb-123">必需</span><span class="sxs-lookup"><span data-stu-id="fffeb-123">Required</span></span>  <br/> |<span data-ttu-id="fffeb-124">**Number**</span><span class="sxs-lookup"><span data-stu-id="fffeb-124">**Number**</span></span> <br/> | <span data-ttu-id="fffeb-125">颜色的发光度，表示为 0 至 240 之间的数字（包括 0 和 240），或可计算出此类数值的表达式。</span><span class="sxs-lookup"><span data-stu-id="fffeb-125">The color's luminosity, expressed as a number in the range 0 to 240, inclusive, or an expression that evaluates to such a number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="fffeb-126">返回值</span><span class="sxs-lookup"><span data-stu-id="fffeb-126">Return value</span></span>

<span data-ttu-id="fffeb-127">帐号</span><span class="sxs-lookup"><span data-stu-id="fffeb-127">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fffeb-128">备注</span><span class="sxs-lookup"><span data-stu-id="fffeb-128">Remarks</span></span>

<span data-ttu-id="fffeb-129">如果该函数返回的颜色在当前文档的调色板中尚不存在，则它将添加到该文档的可用颜色列表中。</span><span class="sxs-lookup"><span data-stu-id="fffeb-129">If the color returned by the function does not already exist in the current document's color palette, it is added to the document's list of available colors.</span></span> 
  
<span data-ttu-id="fffeb-130">下表列出了一些标准颜色，以及它们的色调、饱和度和发光度的值。</span><span class="sxs-lookup"><span data-stu-id="fffeb-130">The following table lists some standard colors and their hue, saturation, and luminosity values.</span></span> 
  
|<span data-ttu-id="fffeb-131">**Color**</span><span class="sxs-lookup"><span data-stu-id="fffeb-131">**Color**</span></span>|<span data-ttu-id="fffeb-132">**色调值**</span><span class="sxs-lookup"><span data-stu-id="fffeb-132">**Hue value**</span></span>|<span data-ttu-id="fffeb-133">**饱和度值**</span><span class="sxs-lookup"><span data-stu-id="fffeb-133">**Saturation value**</span></span>|<span data-ttu-id="fffeb-134">**发光度值**</span><span class="sxs-lookup"><span data-stu-id="fffeb-134">**Luminosity value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fffeb-135">黑色</span><span class="sxs-lookup"><span data-stu-id="fffeb-135">Black</span></span>  <br/> |<span data-ttu-id="fffeb-136">0</span><span class="sxs-lookup"><span data-stu-id="fffeb-136">0</span></span>  <br/> |<span data-ttu-id="fffeb-137">0</span><span class="sxs-lookup"><span data-stu-id="fffeb-137">0</span></span>  <br/> |<span data-ttu-id="fffeb-138">24</span><span class="sxs-lookup"><span data-stu-id="fffeb-138">24</span></span>  <br/> |
|<span data-ttu-id="fffeb-139">蓝色</span><span class="sxs-lookup"><span data-stu-id="fffeb-139">Blue</span></span>  <br/> |<span data-ttu-id="fffeb-140">160</span><span class="sxs-lookup"><span data-stu-id="fffeb-140">160</span></span>  <br/> |<span data-ttu-id="fffeb-141">240</span><span class="sxs-lookup"><span data-stu-id="fffeb-141">240</span></span>  <br/> |<span data-ttu-id="fffeb-142">120</span><span class="sxs-lookup"><span data-stu-id="fffeb-142">120</span></span>  <br/> |
|<span data-ttu-id="fffeb-143">绿色</span><span class="sxs-lookup"><span data-stu-id="fffeb-143">Green</span></span>  <br/> |<span data-ttu-id="fffeb-144">80</span><span class="sxs-lookup"><span data-stu-id="fffeb-144">80</span></span>  <br/> |<span data-ttu-id="fffeb-145">240</span><span class="sxs-lookup"><span data-stu-id="fffeb-145">240</span></span>  <br/> |<span data-ttu-id="fffeb-146">120</span><span class="sxs-lookup"><span data-stu-id="fffeb-146">120</span></span>  <br/> |
|<span data-ttu-id="fffeb-147">蓝绿</span><span class="sxs-lookup"><span data-stu-id="fffeb-147">Cyan</span></span>  <br/> |<span data-ttu-id="fffeb-148">120</span><span class="sxs-lookup"><span data-stu-id="fffeb-148">120</span></span>  <br/> |<span data-ttu-id="fffeb-149">240</span><span class="sxs-lookup"><span data-stu-id="fffeb-149">240</span></span>  <br/> |<span data-ttu-id="fffeb-150">120</span><span class="sxs-lookup"><span data-stu-id="fffeb-150">120</span></span>  <br/> |
|<span data-ttu-id="fffeb-151">红色</span><span class="sxs-lookup"><span data-stu-id="fffeb-151">Red</span></span>  <br/> |<span data-ttu-id="fffeb-152">0</span><span class="sxs-lookup"><span data-stu-id="fffeb-152">0</span></span>  <br/> |<span data-ttu-id="fffeb-153">240</span><span class="sxs-lookup"><span data-stu-id="fffeb-153">240</span></span>  <br/> |<span data-ttu-id="fffeb-154">120</span><span class="sxs-lookup"><span data-stu-id="fffeb-154">120</span></span>  <br/> |
|<span data-ttu-id="fffeb-155">洋红</span><span class="sxs-lookup"><span data-stu-id="fffeb-155">Magenta</span></span>  <br/> |<span data-ttu-id="fffeb-156">200</span><span class="sxs-lookup"><span data-stu-id="fffeb-156">200</span></span>  <br/> |<span data-ttu-id="fffeb-157">240</span><span class="sxs-lookup"><span data-stu-id="fffeb-157">240</span></span>  <br/> |<span data-ttu-id="fffeb-158">120</span><span class="sxs-lookup"><span data-stu-id="fffeb-158">120</span></span>  <br/> |
|<span data-ttu-id="fffeb-159">黄色</span><span class="sxs-lookup"><span data-stu-id="fffeb-159">Yellow</span></span>  <br/> |<span data-ttu-id="fffeb-160">40</span><span class="sxs-lookup"><span data-stu-id="fffeb-160">40</span></span>  <br/> |<span data-ttu-id="fffeb-161">240</span><span class="sxs-lookup"><span data-stu-id="fffeb-161">240</span></span>  <br/> |<span data-ttu-id="fffeb-162">120</span><span class="sxs-lookup"><span data-stu-id="fffeb-162">120</span></span>  <br/> |
|<span data-ttu-id="fffeb-163">白色</span><span class="sxs-lookup"><span data-stu-id="fffeb-163">White</span></span>  <br/> |<span data-ttu-id="fffeb-164">0</span><span class="sxs-lookup"><span data-stu-id="fffeb-164">0</span></span>  <br/> |<span data-ttu-id="fffeb-165">0</span><span class="sxs-lookup"><span data-stu-id="fffeb-165">0</span></span>  <br/> |<span data-ttu-id="fffeb-166">240</span><span class="sxs-lookup"><span data-stu-id="fffeb-166">240</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="fffeb-167">示例 1</span><span class="sxs-lookup"><span data-stu-id="fffeb-167">Example 1</span></span>

<span data-ttu-id="fffeb-168">HSL (160，240，120) </span><span class="sxs-lookup"><span data-stu-id="fffeb-168">HSL(160,240,120)</span></span>
  
<span data-ttu-id="fffeb-169">返回蓝色的索引值。</span><span class="sxs-lookup"><span data-stu-id="fffeb-169">Returns the index for the color blue.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="fffeb-170">示例 2</span><span class="sxs-lookup"><span data-stu-id="fffeb-170">Example 2</span></span>

<span data-ttu-id="fffeb-171">HSL (HUE (FillForegnd) ，SAT (FillForegnd) ，MIN (LUM (FillForegnd) +100，240) ) </span><span class="sxs-lookup"><span data-stu-id="fffeb-171">HSL(HUE(FillForegnd),SAT(FillForegnd),MIN(LUM(FillForegnd)+100,240))</span></span>
  
<span data-ttu-id="fffeb-172">返回一种颜色的索引值，该颜色比填充前景色的发光度高。</span><span class="sxs-lookup"><span data-stu-id="fffeb-172">Returns the index for a color that mirrors the fill foreground color with increased luminosity.</span></span>
  

