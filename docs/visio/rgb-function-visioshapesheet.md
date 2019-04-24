---
title: RGB 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251489
localization_priority: Normal
ms.assetid: f6b9f65c-6752-16cb-7eb1-44e1ce56e80b
description: 返回一个值, 该值代表文档调色板中的索引。 它通过它的红色、绿色和蓝色分量指定颜色, 其中每个是范围为0到 255 (含) 的数字, 或者是计算结果为此类数字的表达式。
ms.openlocfilehash: 34f9c2f2043afe6144feba561e545dc7be35a5a2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326738"
---
# <a name="rgb-function-visioshapesheet"></a><span data-ttu-id="c2577-104">RGB 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="c2577-104">RGB Function (VisioShapeSheet)</span></span>

<span data-ttu-id="c2577-105">返回一个值, 该值代表文档调色板中的索引。</span><span class="sxs-lookup"><span data-stu-id="c2577-105">Returns a value representing an index in the document's color palette.</span></span> <span data-ttu-id="c2577-106">它通过它的红色、绿色和蓝色分量指定颜色, 其中每个是范围为0到 255 (含) 的数字, 或者是计算结果为此类数字的表达式。</span><span class="sxs-lookup"><span data-stu-id="c2577-106">It specifies a color by its red, green, and blue components, where each is a number in the range 0 to 255, inclusive, or an expression that evaluates to such a number.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="c2577-107">语法</span><span class="sxs-lookup"><span data-stu-id="c2577-107">Syntax</span></span>

<span data-ttu-id="c2577-108">RGB (\* \* *red* \* *、* **绿色** *、* **蓝** \*)</span><span class="sxs-lookup"><span data-stu-id="c2577-108">RGB(\*\* *red* \*\*, \*\* *green* \*\*, \*\* *blue* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c2577-109">参数</span><span class="sxs-lookup"><span data-stu-id="c2577-109">Parameters</span></span>

|<span data-ttu-id="c2577-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="c2577-110">**Name**</span></span>|<span data-ttu-id="c2577-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c2577-111">**Required/Optional**</span></span>|<span data-ttu-id="c2577-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c2577-112">**Data Type**</span></span>|<span data-ttu-id="c2577-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="c2577-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c2577-114">_表示_</span><span class="sxs-lookup"><span data-stu-id="c2577-114">_red_</span></span> <br/> |<span data-ttu-id="c2577-115">必需</span><span class="sxs-lookup"><span data-stu-id="c2577-115">Required</span></span>  <br/> |<span data-ttu-id="c2577-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="c2577-116">**Number**</span></span> <br/> |<span data-ttu-id="c2577-117">红色成分。</span><span class="sxs-lookup"><span data-stu-id="c2577-117">The red component.</span></span>  <br/> |
| <span data-ttu-id="c2577-118">_表示_</span><span class="sxs-lookup"><span data-stu-id="c2577-118">_green_</span></span> <br/> |<span data-ttu-id="c2577-119">必需</span><span class="sxs-lookup"><span data-stu-id="c2577-119">Required</span></span>  <br/> |<span data-ttu-id="c2577-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="c2577-120">**Number**</span></span> <br/> |<span data-ttu-id="c2577-121">绿色成分。</span><span class="sxs-lookup"><span data-stu-id="c2577-121">The green component.</span></span>  <br/> |
| <span data-ttu-id="c2577-122">_变为_</span><span class="sxs-lookup"><span data-stu-id="c2577-122">_blue_</span></span> <br/> |<span data-ttu-id="c2577-123">必需</span><span class="sxs-lookup"><span data-stu-id="c2577-123">Required</span></span>  <br/> |<span data-ttu-id="c2577-124">**Nmber**</span><span class="sxs-lookup"><span data-stu-id="c2577-124">**Nmber**</span></span> <br/> |<span data-ttu-id="c2577-125">蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="c2577-125">The blue component.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="c2577-126">返回值</span><span class="sxs-lookup"><span data-stu-id="c2577-126">Return value</span></span>

<span data-ttu-id="c2577-127">帐号</span><span class="sxs-lookup"><span data-stu-id="c2577-127">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c2577-128">注解</span><span class="sxs-lookup"><span data-stu-id="c2577-128">Remarks</span></span>

<span data-ttu-id="c2577-129">如果由该函数返回的颜色在当前文档的调色板中尚不存在，则它将添加到调色板中。</span><span class="sxs-lookup"><span data-stu-id="c2577-129">If the color returned by the function does not already exist in the current document's color palette, it is added to the palette.</span></span>
  
<span data-ttu-id="c2577-130">下表列出了一些标准颜色，以及它们的红、绿和蓝值。</span><span class="sxs-lookup"><span data-stu-id="c2577-130">The following table lists some standard colors and their red, green, and blue values.</span></span>
  
|<span data-ttu-id="c2577-131">**Color**</span><span class="sxs-lookup"><span data-stu-id="c2577-131">**Color**</span></span>|<span data-ttu-id="c2577-132">**红值**</span><span class="sxs-lookup"><span data-stu-id="c2577-132">**Red value**</span></span>|<span data-ttu-id="c2577-133">**绿值**</span><span class="sxs-lookup"><span data-stu-id="c2577-133">**Green value**</span></span>|<span data-ttu-id="c2577-134">**蓝值**</span><span class="sxs-lookup"><span data-stu-id="c2577-134">**Blue value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2577-135">黑色</span><span class="sxs-lookup"><span data-stu-id="c2577-135">Black</span></span>  <br/> |<span data-ttu-id="c2577-136">0</span><span class="sxs-lookup"><span data-stu-id="c2577-136">0</span></span>  <br/> |<span data-ttu-id="c2577-137">0</span><span class="sxs-lookup"><span data-stu-id="c2577-137">0</span></span>  <br/> |<span data-ttu-id="c2577-138">0</span><span class="sxs-lookup"><span data-stu-id="c2577-138">0</span></span>  <br/> |
|<span data-ttu-id="c2577-139">蓝色</span><span class="sxs-lookup"><span data-stu-id="c2577-139">Blue</span></span>  <br/> |<span data-ttu-id="c2577-140">0</span><span class="sxs-lookup"><span data-stu-id="c2577-140">0</span></span>  <br/> |<span data-ttu-id="c2577-141">0</span><span class="sxs-lookup"><span data-stu-id="c2577-141">0</span></span>  <br/> |<span data-ttu-id="c2577-142">255</span><span class="sxs-lookup"><span data-stu-id="c2577-142">255</span></span>  <br/> |
|<span data-ttu-id="c2577-143">绿色</span><span class="sxs-lookup"><span data-stu-id="c2577-143">Green</span></span>  <br/> |<span data-ttu-id="c2577-144">0</span><span class="sxs-lookup"><span data-stu-id="c2577-144">0</span></span>  <br/> |<span data-ttu-id="c2577-145">255</span><span class="sxs-lookup"><span data-stu-id="c2577-145">255</span></span>  <br/> |<span data-ttu-id="c2577-146">0</span><span class="sxs-lookup"><span data-stu-id="c2577-146">0</span></span>  <br/> |
|<span data-ttu-id="c2577-147">蓝绿</span><span class="sxs-lookup"><span data-stu-id="c2577-147">Cyan</span></span>  <br/> |<span data-ttu-id="c2577-148">0</span><span class="sxs-lookup"><span data-stu-id="c2577-148">0</span></span>  <br/> |<span data-ttu-id="c2577-149">255</span><span class="sxs-lookup"><span data-stu-id="c2577-149">255</span></span>  <br/> |<span data-ttu-id="c2577-150">255</span><span class="sxs-lookup"><span data-stu-id="c2577-150">255</span></span>  <br/> |
|<span data-ttu-id="c2577-151">红色</span><span class="sxs-lookup"><span data-stu-id="c2577-151">Red</span></span>  <br/> |<span data-ttu-id="c2577-152">255</span><span class="sxs-lookup"><span data-stu-id="c2577-152">255</span></span>  <br/> |<span data-ttu-id="c2577-153">0</span><span class="sxs-lookup"><span data-stu-id="c2577-153">0</span></span>  <br/> |<span data-ttu-id="c2577-154">0</span><span class="sxs-lookup"><span data-stu-id="c2577-154">0</span></span>  <br/> |
|<span data-ttu-id="c2577-155">洋红</span><span class="sxs-lookup"><span data-stu-id="c2577-155">Magenta</span></span>  <br/> |<span data-ttu-id="c2577-156">255</span><span class="sxs-lookup"><span data-stu-id="c2577-156">255</span></span>  <br/> |<span data-ttu-id="c2577-157">0</span><span class="sxs-lookup"><span data-stu-id="c2577-157">0</span></span>  <br/> |<span data-ttu-id="c2577-158">255</span><span class="sxs-lookup"><span data-stu-id="c2577-158">255</span></span>  <br/> |
|<span data-ttu-id="c2577-159">黄色</span><span class="sxs-lookup"><span data-stu-id="c2577-159">Yellow</span></span>  <br/> |<span data-ttu-id="c2577-160">255</span><span class="sxs-lookup"><span data-stu-id="c2577-160">255</span></span>  <br/> |<span data-ttu-id="c2577-161">255</span><span class="sxs-lookup"><span data-stu-id="c2577-161">255</span></span>  <br/> |<span data-ttu-id="c2577-162">0</span><span class="sxs-lookup"><span data-stu-id="c2577-162">0</span></span>  <br/> |
|<span data-ttu-id="c2577-163">白色</span><span class="sxs-lookup"><span data-stu-id="c2577-163">White</span></span>  <br/> |<span data-ttu-id="c2577-164">255</span><span class="sxs-lookup"><span data-stu-id="c2577-164">255</span></span>  <br/> |<span data-ttu-id="c2577-165">255</span><span class="sxs-lookup"><span data-stu-id="c2577-165">255</span></span>  <br/> |<span data-ttu-id="c2577-166">255</span><span class="sxs-lookup"><span data-stu-id="c2577-166">255</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="c2577-167">示例 1</span><span class="sxs-lookup"><span data-stu-id="c2577-167">Example 1</span></span>

<span data-ttu-id="c2577-168">RGB (0, 0255)</span><span class="sxs-lookup"><span data-stu-id="c2577-168">RGB(0,0,255)</span></span>
  
<span data-ttu-id="c2577-169">返回蓝色的索引值。</span><span class="sxs-lookup"><span data-stu-id="c2577-169">Returns the index for the color blue.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="c2577-170">示例 2</span><span class="sxs-lookup"><span data-stu-id="c2577-170">Example 2</span></span>

<span data-ttu-id="c2577-171">RGB (RED (Sheet. 1!FillForegnd)、120、0)</span><span class="sxs-lookup"><span data-stu-id="c2577-171">RGB(RED(Sheet.1!FillForegnd),120,0)</span></span>
  
<span data-ttu-id="c2577-172">返回一种颜色的索引值，它的红成分匹配 Sheet.1 的填充前景色。</span><span class="sxs-lookup"><span data-stu-id="c2577-172">Returns the index for a color whose red component mirrors Sheet.1's fill foreground.</span></span>
  

