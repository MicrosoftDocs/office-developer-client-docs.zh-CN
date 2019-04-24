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
description: 返回一个值, 该值代表文档调色板中的索引。 它通过色调、饱和度和明度组件指定颜色。
ms.openlocfilehash: 55703239395c54beedf4b7383435253f9c37006f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329923"
---
# <a name="hsl-function"></a><span data-ttu-id="45661-104">HSL 函数</span><span class="sxs-lookup"><span data-stu-id="45661-104">HSL Function</span></span>

<span data-ttu-id="45661-105">返回一个值, 该值代表文档调色板中的索引。</span><span class="sxs-lookup"><span data-stu-id="45661-105">Returns a value representing an index in the document's color palette.</span></span> <span data-ttu-id="45661-106">它通过色调、饱和度和明度组件指定颜色。</span><span class="sxs-lookup"><span data-stu-id="45661-106">It specifies a color by its hue, saturation, and luminosity components.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="45661-107">语法</span><span class="sxs-lookup"><span data-stu-id="45661-107">Syntax</span></span>

<span data-ttu-id="45661-108">HSL (\* **色相** *、* **饱和度** *、* **亮度** \*)</span><span class="sxs-lookup"><span data-stu-id="45661-108">HSL(\*\* *hue* \*\*, \*\* *saturation* \*\*, \*\* *luminosity* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="45661-109">参数</span><span class="sxs-lookup"><span data-stu-id="45661-109">Parameters</span></span>

|<span data-ttu-id="45661-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="45661-110">**Name**</span></span>|<span data-ttu-id="45661-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="45661-111">**Required/Optional**</span></span>|<span data-ttu-id="45661-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="45661-112">**Data Type**</span></span>|<span data-ttu-id="45661-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="45661-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="45661-114">_色调_</span><span class="sxs-lookup"><span data-stu-id="45661-114">_hue_</span></span> <br/> |<span data-ttu-id="45661-115">必需</span><span class="sxs-lookup"><span data-stu-id="45661-115">Required</span></span>  <br/> |<span data-ttu-id="45661-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="45661-116">**Number**</span></span> <br/> |<span data-ttu-id="45661-117">颜色的色调，表示为 0 至 239 之间的数字（包括 0 和 239），或可计算出此类数值的表达式。</span><span class="sxs-lookup"><span data-stu-id="45661-117">The color's hue, expressed as a number in the range 0 to 239, inclusive, or an expression that evaluates to such a number.</span></span>  <br/> |
| <span data-ttu-id="45661-118">_饱和度_</span><span class="sxs-lookup"><span data-stu-id="45661-118">_saturation_</span></span> <br/> |<span data-ttu-id="45661-119">必需</span><span class="sxs-lookup"><span data-stu-id="45661-119">Required</span></span>  <br/> |<span data-ttu-id="45661-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="45661-120">**Number**</span></span> <br/> |<span data-ttu-id="45661-121">颜色的饱和度，表示为 0 至 240 之间的数字（包括 0 和 240），或可计算出此类数值的表达式。</span><span class="sxs-lookup"><span data-stu-id="45661-121">The color's saturation, expressed as a number in the range 0 to 240, inclusive, or an expression that evaluates to such a number.</span></span>  <br/> |
| <span data-ttu-id="45661-122">_亮度_</span><span class="sxs-lookup"><span data-stu-id="45661-122">_luminosity_</span></span> <br/> |<span data-ttu-id="45661-123">必需</span><span class="sxs-lookup"><span data-stu-id="45661-123">Required</span></span>  <br/> |<span data-ttu-id="45661-124">**Number**</span><span class="sxs-lookup"><span data-stu-id="45661-124">**Number**</span></span> <br/> | <span data-ttu-id="45661-125">颜色的发光度，表示为 0 至 240 之间的数字（包括 0 和 240），或可计算出此类数值的表达式。</span><span class="sxs-lookup"><span data-stu-id="45661-125">The color's luminosity, expressed as a number in the range 0 to 240, inclusive, or an expression that evaluates to such a number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="45661-126">返回值</span><span class="sxs-lookup"><span data-stu-id="45661-126">Return value</span></span>

<span data-ttu-id="45661-127">帐号</span><span class="sxs-lookup"><span data-stu-id="45661-127">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="45661-128">注解</span><span class="sxs-lookup"><span data-stu-id="45661-128">Remarks</span></span>

<span data-ttu-id="45661-129">如果该函数返回的颜色在当前文档的调色板中尚不存在，则它将添加到该文档的可用颜色列表中。</span><span class="sxs-lookup"><span data-stu-id="45661-129">If the color returned by the function does not already exist in the current document's color palette, it is added to the document's list of available colors.</span></span> 
  
<span data-ttu-id="45661-130">下表列出了一些标准颜色，以及它们的色调、饱和度和发光度的值。</span><span class="sxs-lookup"><span data-stu-id="45661-130">The following table lists some standard colors and their hue, saturation, and luminosity values.</span></span> 
  
|<span data-ttu-id="45661-131">**Color**</span><span class="sxs-lookup"><span data-stu-id="45661-131">**Color**</span></span>|<span data-ttu-id="45661-132">**色调值**</span><span class="sxs-lookup"><span data-stu-id="45661-132">**Hue value**</span></span>|<span data-ttu-id="45661-133">**饱和度值**</span><span class="sxs-lookup"><span data-stu-id="45661-133">**Saturation value**</span></span>|<span data-ttu-id="45661-134">**发光度值**</span><span class="sxs-lookup"><span data-stu-id="45661-134">**Luminosity value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45661-135">黑色</span><span class="sxs-lookup"><span data-stu-id="45661-135">Black</span></span>  <br/> |<span data-ttu-id="45661-136">0</span><span class="sxs-lookup"><span data-stu-id="45661-136">0</span></span>  <br/> |<span data-ttu-id="45661-137">0</span><span class="sxs-lookup"><span data-stu-id="45661-137">0</span></span>  <br/> |<span data-ttu-id="45661-138">24</span><span class="sxs-lookup"><span data-stu-id="45661-138">24</span></span>  <br/> |
|<span data-ttu-id="45661-139">蓝色</span><span class="sxs-lookup"><span data-stu-id="45661-139">Blue</span></span>  <br/> |<span data-ttu-id="45661-140">160</span><span class="sxs-lookup"><span data-stu-id="45661-140">160</span></span>  <br/> |<span data-ttu-id="45661-141">240</span><span class="sxs-lookup"><span data-stu-id="45661-141">240</span></span>  <br/> |<span data-ttu-id="45661-142">120</span><span class="sxs-lookup"><span data-stu-id="45661-142">120</span></span>  <br/> |
|<span data-ttu-id="45661-143">绿色</span><span class="sxs-lookup"><span data-stu-id="45661-143">Green</span></span>  <br/> |<span data-ttu-id="45661-144">80</span><span class="sxs-lookup"><span data-stu-id="45661-144">80</span></span>  <br/> |<span data-ttu-id="45661-145">240</span><span class="sxs-lookup"><span data-stu-id="45661-145">240</span></span>  <br/> |<span data-ttu-id="45661-146">120</span><span class="sxs-lookup"><span data-stu-id="45661-146">120</span></span>  <br/> |
|<span data-ttu-id="45661-147">蓝绿</span><span class="sxs-lookup"><span data-stu-id="45661-147">Cyan</span></span>  <br/> |<span data-ttu-id="45661-148">120</span><span class="sxs-lookup"><span data-stu-id="45661-148">120</span></span>  <br/> |<span data-ttu-id="45661-149">240</span><span class="sxs-lookup"><span data-stu-id="45661-149">240</span></span>  <br/> |<span data-ttu-id="45661-150">120</span><span class="sxs-lookup"><span data-stu-id="45661-150">120</span></span>  <br/> |
|<span data-ttu-id="45661-151">红色</span><span class="sxs-lookup"><span data-stu-id="45661-151">Red</span></span>  <br/> |<span data-ttu-id="45661-152">0</span><span class="sxs-lookup"><span data-stu-id="45661-152">0</span></span>  <br/> |<span data-ttu-id="45661-153">240</span><span class="sxs-lookup"><span data-stu-id="45661-153">240</span></span>  <br/> |<span data-ttu-id="45661-154">120</span><span class="sxs-lookup"><span data-stu-id="45661-154">120</span></span>  <br/> |
|<span data-ttu-id="45661-155">洋红</span><span class="sxs-lookup"><span data-stu-id="45661-155">Magenta</span></span>  <br/> |<span data-ttu-id="45661-156">200</span><span class="sxs-lookup"><span data-stu-id="45661-156">200</span></span>  <br/> |<span data-ttu-id="45661-157">240</span><span class="sxs-lookup"><span data-stu-id="45661-157">240</span></span>  <br/> |<span data-ttu-id="45661-158">120</span><span class="sxs-lookup"><span data-stu-id="45661-158">120</span></span>  <br/> |
|<span data-ttu-id="45661-159">黄色</span><span class="sxs-lookup"><span data-stu-id="45661-159">Yellow</span></span>  <br/> |<span data-ttu-id="45661-160">40</span><span class="sxs-lookup"><span data-stu-id="45661-160">40</span></span>  <br/> |<span data-ttu-id="45661-161">240</span><span class="sxs-lookup"><span data-stu-id="45661-161">240</span></span>  <br/> |<span data-ttu-id="45661-162">120</span><span class="sxs-lookup"><span data-stu-id="45661-162">120</span></span>  <br/> |
|<span data-ttu-id="45661-163">白色</span><span class="sxs-lookup"><span data-stu-id="45661-163">White</span></span>  <br/> |<span data-ttu-id="45661-164">0</span><span class="sxs-lookup"><span data-stu-id="45661-164">0</span></span>  <br/> |<span data-ttu-id="45661-165">0</span><span class="sxs-lookup"><span data-stu-id="45661-165">0</span></span>  <br/> |<span data-ttu-id="45661-166">240</span><span class="sxs-lookup"><span data-stu-id="45661-166">240</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="45661-167">示例 1</span><span class="sxs-lookup"><span data-stu-id="45661-167">Example 1</span></span>

<span data-ttu-id="45661-168">HSL (160240120)</span><span class="sxs-lookup"><span data-stu-id="45661-168">HSL(160,240,120)</span></span>
  
<span data-ttu-id="45661-169">返回蓝色的索引值。</span><span class="sxs-lookup"><span data-stu-id="45661-169">Returns the index for the color blue.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="45661-170">示例 2</span><span class="sxs-lookup"><span data-stu-id="45661-170">Example 2</span></span>

<span data-ttu-id="45661-171">HSL (色相 (FillForegnd)、SAT (FillForegnd)、MIN (亮度 (FillForegnd) + 100240))</span><span class="sxs-lookup"><span data-stu-id="45661-171">HSL(HUE(FillForegnd),SAT(FillForegnd),MIN(LUM(FillForegnd)+100,240))</span></span>
  
<span data-ttu-id="45661-172">返回一种颜色的索引值，该颜色比填充前景色的发光度高。</span><span class="sxs-lookup"><span data-stu-id="45661-172">Returns the index for a color that mirrors the fill foreground color with increased luminosity.</span></span>
  

