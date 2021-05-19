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
description: 返回一个值，该值代表文档的调色板中的索引。 它通过红色、绿色和蓝色分量指定颜色，其中每个颜色都是 0 到 255 之间的一个数字（包含这两者）或计算结果为此类数字的表达式。
ms.openlocfilehash: 34f9c2f2043afe6144feba561e545dc7be35a5a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426301"
---
# <a name="rgb-function-visioshapesheet"></a><span data-ttu-id="a271f-104">RGB 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="a271f-104">RGB Function (VisioShapeSheet)</span></span>

<span data-ttu-id="a271f-105">返回一个值，该值代表文档的调色板中的索引。</span><span class="sxs-lookup"><span data-stu-id="a271f-105">Returns a value representing an index in the document's color palette.</span></span> <span data-ttu-id="a271f-106">它通过红色、绿色和蓝色分量指定颜色，其中每个颜色都是 0 到 255 之间的一个数字（包含这两者）或计算结果为此类数字的表达式。</span><span class="sxs-lookup"><span data-stu-id="a271f-106">It specifies a color by its red, green, and blue components, where each is a number in the range 0 to 255, inclusive, or an expression that evaluates to such a number.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a271f-107">语法</span><span class="sxs-lookup"><span data-stu-id="a271f-107">Syntax</span></span>

<span data-ttu-id="a271f-108">RGB (\*\* *red* \*\*， \*\* *green* \*\*， \*\* *blue* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="a271f-108">RGB(\*\* *red* \*\*, \*\* *green* \*\*, \*\* *blue* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="a271f-109">参数</span><span class="sxs-lookup"><span data-stu-id="a271f-109">Parameters</span></span>

|<span data-ttu-id="a271f-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="a271f-110">**Name**</span></span>|<span data-ttu-id="a271f-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="a271f-111">**Required/Optional**</span></span>|<span data-ttu-id="a271f-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a271f-112">**Data Type**</span></span>|<span data-ttu-id="a271f-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="a271f-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a271f-114">_red_</span><span class="sxs-lookup"><span data-stu-id="a271f-114">_red_</span></span> <br/> |<span data-ttu-id="a271f-115">必需</span><span class="sxs-lookup"><span data-stu-id="a271f-115">Required</span></span>  <br/> |<span data-ttu-id="a271f-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="a271f-116">**Number**</span></span> <br/> |<span data-ttu-id="a271f-117">红色成分。</span><span class="sxs-lookup"><span data-stu-id="a271f-117">The red component.</span></span>  <br/> |
| <span data-ttu-id="a271f-118">_绿色_</span><span class="sxs-lookup"><span data-stu-id="a271f-118">_green_</span></span> <br/> |<span data-ttu-id="a271f-119">必需</span><span class="sxs-lookup"><span data-stu-id="a271f-119">Required</span></span>  <br/> |<span data-ttu-id="a271f-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="a271f-120">**Number**</span></span> <br/> |<span data-ttu-id="a271f-121">绿色成分。</span><span class="sxs-lookup"><span data-stu-id="a271f-121">The green component.</span></span>  <br/> |
| <span data-ttu-id="a271f-122">_blue_</span><span class="sxs-lookup"><span data-stu-id="a271f-122">_blue_</span></span> <br/> |<span data-ttu-id="a271f-123">必需</span><span class="sxs-lookup"><span data-stu-id="a271f-123">Required</span></span>  <br/> |<span data-ttu-id="a271f-124">**nmber**</span><span class="sxs-lookup"><span data-stu-id="a271f-124">**Nmber**</span></span> <br/> |<span data-ttu-id="a271f-125">蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="a271f-125">The blue component.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="a271f-126">返回值</span><span class="sxs-lookup"><span data-stu-id="a271f-126">Return value</span></span>

<span data-ttu-id="a271f-127">帐号</span><span class="sxs-lookup"><span data-stu-id="a271f-127">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a271f-128">备注</span><span class="sxs-lookup"><span data-stu-id="a271f-128">Remarks</span></span>

<span data-ttu-id="a271f-129">如果由该函数返回的颜色在当前文档的调色板中尚不存在，则它将添加到调色板中。</span><span class="sxs-lookup"><span data-stu-id="a271f-129">If the color returned by the function does not already exist in the current document's color palette, it is added to the palette.</span></span>
  
<span data-ttu-id="a271f-130">下表列出了一些标准颜色，以及它们的红、绿和蓝值。</span><span class="sxs-lookup"><span data-stu-id="a271f-130">The following table lists some standard colors and their red, green, and blue values.</span></span>
  
|<span data-ttu-id="a271f-131">**Color**</span><span class="sxs-lookup"><span data-stu-id="a271f-131">**Color**</span></span>|<span data-ttu-id="a271f-132">**红值**</span><span class="sxs-lookup"><span data-stu-id="a271f-132">**Red value**</span></span>|<span data-ttu-id="a271f-133">**绿值**</span><span class="sxs-lookup"><span data-stu-id="a271f-133">**Green value**</span></span>|<span data-ttu-id="a271f-134">**蓝值**</span><span class="sxs-lookup"><span data-stu-id="a271f-134">**Blue value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a271f-135">黑色</span><span class="sxs-lookup"><span data-stu-id="a271f-135">Black</span></span>  <br/> |<span data-ttu-id="a271f-136">0</span><span class="sxs-lookup"><span data-stu-id="a271f-136">0</span></span>  <br/> |<span data-ttu-id="a271f-137">0</span><span class="sxs-lookup"><span data-stu-id="a271f-137">0</span></span>  <br/> |<span data-ttu-id="a271f-138">0</span><span class="sxs-lookup"><span data-stu-id="a271f-138">0</span></span>  <br/> |
|<span data-ttu-id="a271f-139">蓝色</span><span class="sxs-lookup"><span data-stu-id="a271f-139">Blue</span></span>  <br/> |<span data-ttu-id="a271f-140">0</span><span class="sxs-lookup"><span data-stu-id="a271f-140">0</span></span>  <br/> |<span data-ttu-id="a271f-141">0</span><span class="sxs-lookup"><span data-stu-id="a271f-141">0</span></span>  <br/> |<span data-ttu-id="a271f-142">255</span><span class="sxs-lookup"><span data-stu-id="a271f-142">255</span></span>  <br/> |
|<span data-ttu-id="a271f-143">绿色</span><span class="sxs-lookup"><span data-stu-id="a271f-143">Green</span></span>  <br/> |<span data-ttu-id="a271f-144">0</span><span class="sxs-lookup"><span data-stu-id="a271f-144">0</span></span>  <br/> |<span data-ttu-id="a271f-145">255</span><span class="sxs-lookup"><span data-stu-id="a271f-145">255</span></span>  <br/> |<span data-ttu-id="a271f-146">0</span><span class="sxs-lookup"><span data-stu-id="a271f-146">0</span></span>  <br/> |
|<span data-ttu-id="a271f-147">蓝绿</span><span class="sxs-lookup"><span data-stu-id="a271f-147">Cyan</span></span>  <br/> |<span data-ttu-id="a271f-148">0</span><span class="sxs-lookup"><span data-stu-id="a271f-148">0</span></span>  <br/> |<span data-ttu-id="a271f-149">255</span><span class="sxs-lookup"><span data-stu-id="a271f-149">255</span></span>  <br/> |<span data-ttu-id="a271f-150">255</span><span class="sxs-lookup"><span data-stu-id="a271f-150">255</span></span>  <br/> |
|<span data-ttu-id="a271f-151">红色</span><span class="sxs-lookup"><span data-stu-id="a271f-151">Red</span></span>  <br/> |<span data-ttu-id="a271f-152">255</span><span class="sxs-lookup"><span data-stu-id="a271f-152">255</span></span>  <br/> |<span data-ttu-id="a271f-153">0</span><span class="sxs-lookup"><span data-stu-id="a271f-153">0</span></span>  <br/> |<span data-ttu-id="a271f-154">0</span><span class="sxs-lookup"><span data-stu-id="a271f-154">0</span></span>  <br/> |
|<span data-ttu-id="a271f-155">洋红</span><span class="sxs-lookup"><span data-stu-id="a271f-155">Magenta</span></span>  <br/> |<span data-ttu-id="a271f-156">255</span><span class="sxs-lookup"><span data-stu-id="a271f-156">255</span></span>  <br/> |<span data-ttu-id="a271f-157">0</span><span class="sxs-lookup"><span data-stu-id="a271f-157">0</span></span>  <br/> |<span data-ttu-id="a271f-158">255</span><span class="sxs-lookup"><span data-stu-id="a271f-158">255</span></span>  <br/> |
|<span data-ttu-id="a271f-159">黄色</span><span class="sxs-lookup"><span data-stu-id="a271f-159">Yellow</span></span>  <br/> |<span data-ttu-id="a271f-160">255</span><span class="sxs-lookup"><span data-stu-id="a271f-160">255</span></span>  <br/> |<span data-ttu-id="a271f-161">255</span><span class="sxs-lookup"><span data-stu-id="a271f-161">255</span></span>  <br/> |<span data-ttu-id="a271f-162">0</span><span class="sxs-lookup"><span data-stu-id="a271f-162">0</span></span>  <br/> |
|<span data-ttu-id="a271f-163">白色</span><span class="sxs-lookup"><span data-stu-id="a271f-163">White</span></span>  <br/> |<span data-ttu-id="a271f-164">255</span><span class="sxs-lookup"><span data-stu-id="a271f-164">255</span></span>  <br/> |<span data-ttu-id="a271f-165">255</span><span class="sxs-lookup"><span data-stu-id="a271f-165">255</span></span>  <br/> |<span data-ttu-id="a271f-166">255</span><span class="sxs-lookup"><span data-stu-id="a271f-166">255</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="a271f-167">示例 1</span><span class="sxs-lookup"><span data-stu-id="a271f-167">Example 1</span></span>

<span data-ttu-id="a271f-168">RGB (0，0，255) </span><span class="sxs-lookup"><span data-stu-id="a271f-168">RGB(0,0,255)</span></span>
  
<span data-ttu-id="a271f-169">返回蓝色的索引值。</span><span class="sxs-lookup"><span data-stu-id="a271f-169">Returns the index for the color blue.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="a271f-170">示例 2</span><span class="sxs-lookup"><span data-stu-id="a271f-170">Example 2</span></span>

<span data-ttu-id="a271f-171">RGB (RED (Sheet.1！FillForegnd) ，120，0) </span><span class="sxs-lookup"><span data-stu-id="a271f-171">RGB(RED(Sheet.1!FillForegnd),120,0)</span></span>
  
<span data-ttu-id="a271f-172">返回一种颜色的索引值，它的红成分匹配 Sheet.1 的填充前景色。</span><span class="sxs-lookup"><span data-stu-id="a271f-172">Returns the index for a color whose red component mirrors Sheet.1's fill foreground.</span></span>
  

