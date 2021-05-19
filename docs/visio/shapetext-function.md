---
title: SHAPETEXT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251788
localization_priority: Normal
ms.assetid: 87ea5e8f-c3e0-009f-4bf8-8c34fbdb83a6
description: 从形状获取文本。
ms.openlocfilehash: bb9b1fbe5900cd051828ed6c7ff07546567c1b23
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419343"
---
# <a name="shapetext-function"></a><span data-ttu-id="d5eff-103">SHAPETEXT 函数</span><span class="sxs-lookup"><span data-stu-id="d5eff-103">SHAPETEXT Function</span></span>

<span data-ttu-id="d5eff-104">从形状获取文本。</span><span class="sxs-lookup"><span data-stu-id="d5eff-104">Gets the text from a shape.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d5eff-105">语法</span><span class="sxs-lookup"><span data-stu-id="d5eff-105">Syntax</span></span>

<span data-ttu-id="d5eff-106">SHAPETEXT (\*\* *shapename！TheText* \*\* \*\* \*\*\* [，flag]\* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="d5eff-106">SHAPETEXT (\*\* *shapename!TheText* \*\* \*\* *[,flag]* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d5eff-107">参数</span><span class="sxs-lookup"><span data-stu-id="d5eff-107">Parameters</span></span>

|<span data-ttu-id="d5eff-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="d5eff-108">**Name**</span></span>|<span data-ttu-id="d5eff-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d5eff-109">**Required/Optional**</span></span>|<span data-ttu-id="d5eff-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d5eff-110">**Data Type**</span></span>|<span data-ttu-id="d5eff-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d5eff-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d5eff-112">_shapename！TheText_</span><span class="sxs-lookup"><span data-stu-id="d5eff-112">_shapename!TheText_</span></span> <br/> |<span data-ttu-id="d5eff-113">必需</span><span class="sxs-lookup"><span data-stu-id="d5eff-113">Required</span></span>  <br/> ||<span data-ttu-id="d5eff-114">对目标形状中名为 TheText 的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="d5eff-114">A reference to the cell named TheText in the target shape.</span></span>  <span data-ttu-id="d5eff-115">_Shapename！_</span><span class="sxs-lookup"><span data-stu-id="d5eff-115">_Shapename!_</span></span> <span data-ttu-id="d5eff-116">是想要从中检索文本的形状的名称。</span><span class="sxs-lookup"><span data-stu-id="d5eff-116">is the name of the shape from which you want to retrieve the text.</span></span>  <br/> |
| <span data-ttu-id="d5eff-117">_flag_</span><span class="sxs-lookup"><span data-stu-id="d5eff-117">_flag_</span></span> <br/> |<span data-ttu-id="d5eff-118">可选</span><span class="sxs-lookup"><span data-stu-id="d5eff-118">Optional</span></span>  <br/> |<span data-ttu-id="d5eff-119">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="d5eff-119">**Numeric**</span></span> <br/> |<span data-ttu-id="d5eff-p102">指定文本格式的位。默认标志 (0) 显示的文本与形状中显示的文本完全相同。</span><span class="sxs-lookup"><span data-stu-id="d5eff-p102">A bit that specifies the format of the text. The default flag (0) shows the text exactly as it is shown in the shape.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="d5eff-122">返回值</span><span class="sxs-lookup"><span data-stu-id="d5eff-122">Return value</span></span>

<span data-ttu-id="d5eff-123">String</span><span class="sxs-lookup"><span data-stu-id="d5eff-123">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d5eff-124">备注</span><span class="sxs-lookup"><span data-stu-id="d5eff-124">Remarks</span></span>

<span data-ttu-id="d5eff-125">您可以将下列任意标志组合与 SHAPETEXT 函数一起使用。</span><span class="sxs-lookup"><span data-stu-id="d5eff-125">You can use any combination of the following flags with the SHAPETEXT function.</span></span>
  
|<span data-ttu-id="d5eff-126">**Flag**</span><span class="sxs-lookup"><span data-stu-id="d5eff-126">**Flag**</span></span>|<span data-ttu-id="d5eff-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="d5eff-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d5eff-128">0</span><span class="sxs-lookup"><span data-stu-id="d5eff-128">0</span></span>  <br/> |<span data-ttu-id="d5eff-129">显示的文本与形状中显示的文本完全相同。</span><span class="sxs-lookup"><span data-stu-id="d5eff-129">Show text exactly as shown in shape.</span></span>  <br/> |
|<span data-ttu-id="d5eff-130">1</span><span class="sxs-lookup"><span data-stu-id="d5eff-130">1</span></span>  <br/> |<span data-ttu-id="d5eff-131">包括任意连字符。</span><span class="sxs-lookup"><span data-stu-id="d5eff-131">Include discretionary hyphens.</span></span>  <br/> |
|<span data-ttu-id="d5eff-132">2</span><span class="sxs-lookup"><span data-stu-id="d5eff-132">2</span></span>  <br/> |<span data-ttu-id="d5eff-133">不包括域中的扩展文本。</span><span class="sxs-lookup"><span data-stu-id="d5eff-133">Don't include expanded text in fields.</span></span>  <br/> |
|<span data-ttu-id="d5eff-134">4 </span><span class="sxs-lookup"><span data-stu-id="d5eff-134">4</span></span>  <br/> |<span data-ttu-id="d5eff-135">将制表符转换为一个空格。</span><span class="sxs-lookup"><span data-stu-id="d5eff-135">Convert tabs to a single space.</span></span>  <br/> |
|<span data-ttu-id="d5eff-136">8 </span><span class="sxs-lookup"><span data-stu-id="d5eff-136">8</span></span>  <br/> |<span data-ttu-id="d5eff-137">将制表符转换为一组空格。</span><span class="sxs-lookup"><span data-stu-id="d5eff-137">Convert tabs to a set of spaces.</span></span>  <br/> |
|<span data-ttu-id="d5eff-138">16 </span><span class="sxs-lookup"><span data-stu-id="d5eff-138">16</span></span>  <br/> |<span data-ttu-id="d5eff-139">将回车符和换行符转换为空格。</span><span class="sxs-lookup"><span data-stu-id="d5eff-139">Convert carriage returns and line feeds to spaces.</span></span>  <br/> |
|<span data-ttu-id="d5eff-140">32</span><span class="sxs-lookup"><span data-stu-id="d5eff-140">32</span></span>  <br/> |<span data-ttu-id="d5eff-141">将版式双引号转换为常规双引号。</span><span class="sxs-lookup"><span data-stu-id="d5eff-141">Convert typographer quotes to regular quotes.</span></span>  <br/> |
|<span data-ttu-id="d5eff-142">64</span><span class="sxs-lookup"><span data-stu-id="d5eff-142">64</span></span>  <br/> |<span data-ttu-id="d5eff-143">将相邻空白区域转换为单个空格。</span><span class="sxs-lookup"><span data-stu-id="d5eff-143">Convert adjacent white space to a single space.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="d5eff-144">示例 1</span><span class="sxs-lookup"><span data-stu-id="d5eff-144">Example 1</span></span>

<span data-ttu-id="d5eff-145">SHAPETEXT (sheetN！theText) </span><span class="sxs-lookup"><span data-stu-id="d5eff-145">SHAPETEXT(sheetN!theText)</span></span>
  
<span data-ttu-id="d5eff-146">返回名为 sheetN 的形状的文本，与在形状中显示的文本完全相同。</span><span class="sxs-lookup"><span data-stu-id="d5eff-146">Returns the text of the shape named sheetN, exactly as it is shown in the shape.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="d5eff-147">示例 2</span><span class="sxs-lookup"><span data-stu-id="d5eff-147">Example 2</span></span>

<span data-ttu-id="d5eff-148">SHAPETEXT (Text) </span><span class="sxs-lookup"><span data-stu-id="d5eff-148">SHAPETEXT(theText)</span></span>
  
<span data-ttu-id="d5eff-149">返回当前形状的文本，与在形状中显示的文本完全相同。</span><span class="sxs-lookup"><span data-stu-id="d5eff-149">Returns the text of the current shape exactly as it is shown in the shape.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="d5eff-150">示例 3</span><span class="sxs-lookup"><span data-stu-id="d5eff-150">Example 3</span></span>

<span data-ttu-id="d5eff-151">SHAPETEXT(theText, 84)</span><span class="sxs-lookup"><span data-stu-id="d5eff-151">SHAPETEXT(theText, 84)</span></span>
  
<span data-ttu-id="d5eff-p103">返回当前形状的文本。另外还将相邻空白区域转换为单个空格 (64)、将回车符和换行符转换为空格 (16)，并将制表符转换为单个空格 (4)。这些标志的总和为 84。</span><span class="sxs-lookup"><span data-stu-id="d5eff-p103">Returns the text of the current shape. It also converts adjacent white space to a single space (64), converts carriage returns and line feeds to spaces (16), and converts tabs to a single space (4). The sum of these flags is 84.</span></span>
  

