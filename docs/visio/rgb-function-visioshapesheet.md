---
title: RGB Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251489
localization_priority: Normal
ms.assetid: f6b9f65c-6752-16cb-7eb1-44e1ce56e80b
description: 返回一个值，表示在文档的调色板中的索引。 指定一种颜色由其红色、 绿色和蓝色的组件，其中每个是 0 到 255，包括中, 号或计算出此类数值的表达式。
ms.openlocfilehash: 7fa129d3ed28441f619660ed0db035cde85979bf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781102"
---
# <a name="rgb-function-visioshapesheet"></a><span data-ttu-id="d590c-104">RGB Function (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="d590c-104">RGB Function (VisioShapeSheet)</span></span>

<span data-ttu-id="d590c-105">返回一个值，表示在文档的调色板中的索引。</span><span class="sxs-lookup"><span data-stu-id="d590c-105">Returns a value representing an index in the document's color palette.</span></span> <span data-ttu-id="d590c-106">指定一种颜色由其红色、 绿色和蓝色的组件，其中每个是 0 到 255，包括中, 号或计算出此类数值的表达式。</span><span class="sxs-lookup"><span data-stu-id="d590c-106">It specifies a color by its red, green, and blue components, where each is a number in the range 0 to 255, inclusive, or an expression that evaluates to such a number.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d590c-107">语法</span><span class="sxs-lookup"><span data-stu-id="d590c-107">Syntax</span></span>

<span data-ttu-id="d590c-108">RGB (* **红色** *，* **绿色** *，* **蓝色** *)</span><span class="sxs-lookup"><span data-stu-id="d590c-108">RGB(** *red* **, ** *green* **, ** *blue* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d590c-109">参数</span><span class="sxs-lookup"><span data-stu-id="d590c-109">Parameters</span></span>

|<span data-ttu-id="d590c-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="d590c-110">**Name**</span></span>|<span data-ttu-id="d590c-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d590c-111">**Required/Optional**</span></span>|<span data-ttu-id="d590c-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d590c-112">**Data Type**</span></span>|<span data-ttu-id="d590c-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="d590c-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d590c-114">_红色_</span><span class="sxs-lookup"><span data-stu-id="d590c-114">_red_</span></span> <br/> |<span data-ttu-id="d590c-115">必需</span><span class="sxs-lookup"><span data-stu-id="d590c-115">Required</span></span>  <br/> |<span data-ttu-id="d590c-116">**编号**</span><span class="sxs-lookup"><span data-stu-id="d590c-116">**Number**</span></span> <br/> |<span data-ttu-id="d590c-117">红色成分。</span><span class="sxs-lookup"><span data-stu-id="d590c-117">The red component.</span></span>  <br/> |
| <span data-ttu-id="d590c-118">_绿色_</span><span class="sxs-lookup"><span data-stu-id="d590c-118">_green_</span></span> <br/> |<span data-ttu-id="d590c-119">必需</span><span class="sxs-lookup"><span data-stu-id="d590c-119">Required</span></span>  <br/> |<span data-ttu-id="d590c-120">**编号**</span><span class="sxs-lookup"><span data-stu-id="d590c-120">**Number**</span></span> <br/> |<span data-ttu-id="d590c-121">绿色成分。</span><span class="sxs-lookup"><span data-stu-id="d590c-121">The green component.</span></span>  <br/> |
| <span data-ttu-id="d590c-122">_蓝色_</span><span class="sxs-lookup"><span data-stu-id="d590c-122">_blue_</span></span> <br/> |<span data-ttu-id="d590c-123">必需</span><span class="sxs-lookup"><span data-stu-id="d590c-123">Required</span></span>  <br/> |<span data-ttu-id="d590c-124">**Number**</span><span class="sxs-lookup"><span data-stu-id="d590c-124">**Nmber**</span></span> <br/> |<span data-ttu-id="d590c-125">蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="d590c-125">The blue component.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="d590c-126">返回值</span><span class="sxs-lookup"><span data-stu-id="d590c-126">Return value</span></span>

<span data-ttu-id="d590c-127">Number</span><span class="sxs-lookup"><span data-stu-id="d590c-127">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d590c-128">注解</span><span class="sxs-lookup"><span data-stu-id="d590c-128">Remarks</span></span>

<span data-ttu-id="d590c-129">如果由该函数返回的颜色在当前文档的调色板中尚不存在，则它将添加到调色板中。</span><span class="sxs-lookup"><span data-stu-id="d590c-129">If the color returned by the function does not already exist in the current document's color palette, it is added to the palette.</span></span>
  
<span data-ttu-id="d590c-130">下表列出了一些标准颜色，以及它们的红、绿和蓝值。</span><span class="sxs-lookup"><span data-stu-id="d590c-130">The following table lists some standard colors and their red, green, and blue values.</span></span>
  
|<span data-ttu-id="d590c-131">**颜色**</span><span class="sxs-lookup"><span data-stu-id="d590c-131">**Color**</span></span>|<span data-ttu-id="d590c-132">**红色值**</span><span class="sxs-lookup"><span data-stu-id="d590c-132">**Red value**</span></span>|<span data-ttu-id="d590c-133">**绿色值**</span><span class="sxs-lookup"><span data-stu-id="d590c-133">**Green value**</span></span>|<span data-ttu-id="d590c-134">**蓝值**</span><span class="sxs-lookup"><span data-stu-id="d590c-134">**Blue value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d590c-135">黑色</span><span class="sxs-lookup"><span data-stu-id="d590c-135">Black</span></span>  <br/> |<span data-ttu-id="d590c-136">0</span><span class="sxs-lookup"><span data-stu-id="d590c-136">0</span></span>  <br/> |<span data-ttu-id="d590c-137">0</span><span class="sxs-lookup"><span data-stu-id="d590c-137">0</span></span>  <br/> |<span data-ttu-id="d590c-138">0</span><span class="sxs-lookup"><span data-stu-id="d590c-138">0</span></span>  <br/> |
|<span data-ttu-id="d590c-139">蓝色</span><span class="sxs-lookup"><span data-stu-id="d590c-139">Blue</span></span>  <br/> |<span data-ttu-id="d590c-140">0</span><span class="sxs-lookup"><span data-stu-id="d590c-140">0</span></span>  <br/> |<span data-ttu-id="d590c-141">0</span><span class="sxs-lookup"><span data-stu-id="d590c-141">0</span></span>  <br/> |<span data-ttu-id="d590c-142">255</span><span class="sxs-lookup"><span data-stu-id="d590c-142">255</span></span>  <br/> |
|<span data-ttu-id="d590c-143">绿色</span><span class="sxs-lookup"><span data-stu-id="d590c-143">Green</span></span>  <br/> |<span data-ttu-id="d590c-144">0</span><span class="sxs-lookup"><span data-stu-id="d590c-144">0</span></span>  <br/> |<span data-ttu-id="d590c-145">255</span><span class="sxs-lookup"><span data-stu-id="d590c-145">255</span></span>  <br/> |<span data-ttu-id="d590c-146">0</span><span class="sxs-lookup"><span data-stu-id="d590c-146">0</span></span>  <br/> |
|<span data-ttu-id="d590c-147">蓝绿色</span><span class="sxs-lookup"><span data-stu-id="d590c-147">Cyan</span></span>  <br/> |<span data-ttu-id="d590c-148">0</span><span class="sxs-lookup"><span data-stu-id="d590c-148">0</span></span>  <br/> |<span data-ttu-id="d590c-149">255</span><span class="sxs-lookup"><span data-stu-id="d590c-149">255</span></span>  <br/> |<span data-ttu-id="d590c-150">255</span><span class="sxs-lookup"><span data-stu-id="d590c-150">255</span></span>  <br/> |
|<span data-ttu-id="d590c-151">红色</span><span class="sxs-lookup"><span data-stu-id="d590c-151">Red</span></span>  <br/> |<span data-ttu-id="d590c-152">255</span><span class="sxs-lookup"><span data-stu-id="d590c-152">255</span></span>  <br/> |<span data-ttu-id="d590c-153">0</span><span class="sxs-lookup"><span data-stu-id="d590c-153">0</span></span>  <br/> |<span data-ttu-id="d590c-154">0</span><span class="sxs-lookup"><span data-stu-id="d590c-154">0</span></span>  <br/> |
|<span data-ttu-id="d590c-155">洋红色</span><span class="sxs-lookup"><span data-stu-id="d590c-155">Magenta</span></span>  <br/> |<span data-ttu-id="d590c-156">255</span><span class="sxs-lookup"><span data-stu-id="d590c-156">255</span></span>  <br/> |<span data-ttu-id="d590c-157">0</span><span class="sxs-lookup"><span data-stu-id="d590c-157">0</span></span>  <br/> |<span data-ttu-id="d590c-158">255</span><span class="sxs-lookup"><span data-stu-id="d590c-158">255</span></span>  <br/> |
|<span data-ttu-id="d590c-159">黄色</span><span class="sxs-lookup"><span data-stu-id="d590c-159">Yellow</span></span>  <br/> |<span data-ttu-id="d590c-160">255</span><span class="sxs-lookup"><span data-stu-id="d590c-160">255</span></span>  <br/> |<span data-ttu-id="d590c-161">255</span><span class="sxs-lookup"><span data-stu-id="d590c-161">255</span></span>  <br/> |<span data-ttu-id="d590c-162">0</span><span class="sxs-lookup"><span data-stu-id="d590c-162">0</span></span>  <br/> |
|<span data-ttu-id="d590c-163">白色</span><span class="sxs-lookup"><span data-stu-id="d590c-163">White</span></span>  <br/> |<span data-ttu-id="d590c-164">255</span><span class="sxs-lookup"><span data-stu-id="d590c-164">255</span></span>  <br/> |<span data-ttu-id="d590c-165">255</span><span class="sxs-lookup"><span data-stu-id="d590c-165">255</span></span>  <br/> |<span data-ttu-id="d590c-166">255</span><span class="sxs-lookup"><span data-stu-id="d590c-166">255</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="d590c-167">示例 1</span><span class="sxs-lookup"><span data-stu-id="d590c-167">Example 1</span></span>

<span data-ttu-id="d590c-168">RGB(0,0,255)</span><span class="sxs-lookup"><span data-stu-id="d590c-168">RGB(0,0,255)</span></span>
  
<span data-ttu-id="d590c-169">返回蓝色的索引值。</span><span class="sxs-lookup"><span data-stu-id="d590c-169">Returns the index for the color blue.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="d590c-170">示例 2</span><span class="sxs-lookup"><span data-stu-id="d590c-170">Example 2</span></span>

<span data-ttu-id="d590c-171">RGB （红 (Sheet.1 ！FillForegnd)，120、 0)</span><span class="sxs-lookup"><span data-stu-id="d590c-171">RGB(RED(Sheet.1!FillForegnd),120,0)</span></span>
  
<span data-ttu-id="d590c-172">返回一种颜色的索引值，它的红成分匹配 Sheet.1 的填充前景色。</span><span class="sxs-lookup"><span data-stu-id="d590c-172">Returns the index for a color whose red component mirrors Sheet.1's fill foreground.</span></span>
  

