---
title: TEXTWIDTH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251505
localization_priority: Normal
ms.assetid: a9b8efcf-edc0-ad99-deae-21df16c58807
description: 返回形状中组合文字的宽度。
ms.openlocfilehash: 43848bba4d24a0c31a3a084d123cd56140bf0709
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422031"
---
# <a name="textwidth-function"></a><span data-ttu-id="9da21-103">TEXTWIDTH 函数</span><span class="sxs-lookup"><span data-stu-id="9da21-103">TEXTWIDTH Function</span></span>

<span data-ttu-id="9da21-104">返回形状中组合文字的宽度。</span><span class="sxs-lookup"><span data-stu-id="9da21-104">Returns the width of the composed text in a shape.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="9da21-105">语法</span><span class="sxs-lookup"><span data-stu-id="9da21-105">Syntax</span></span>

<span data-ttu-id="9da21-106">TEXTWIDTH (\*\* *shapename！TheText* \*\* \*\* *[，maximumwidth]* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="9da21-106">TEXTWIDTH(\*\* *shapename!TheText* \*\* \*\* *[,maximumwidth]* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="9da21-107">参数</span><span class="sxs-lookup"><span data-stu-id="9da21-107">Parameters</span></span>

|<span data-ttu-id="9da21-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="9da21-108">**Name**</span></span>|<span data-ttu-id="9da21-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="9da21-109">**Required/Optional**</span></span>|<span data-ttu-id="9da21-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9da21-110">**Data Type**</span></span>|<span data-ttu-id="9da21-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="9da21-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9da21-112">_shapename！theText_</span><span class="sxs-lookup"><span data-stu-id="9da21-112">_shapename!theText_</span></span> <br/> |<span data-ttu-id="9da21-113">必需</span><span class="sxs-lookup"><span data-stu-id="9da21-113">Required</span></span>  <br/> |<span data-ttu-id="9da21-114">**String**</span><span class="sxs-lookup"><span data-stu-id="9da21-114">**String**</span></span> <br/> |<span data-ttu-id="9da21-115">对目标形状中名为 TheText 的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="9da21-115">A reference to the cell named TheText in the target shape.</span></span>  <span data-ttu-id="9da21-116">_shapename！_</span><span class="sxs-lookup"><span data-stu-id="9da21-116">_shapename!_</span></span> <span data-ttu-id="9da21-117">是想要从中检索文本的形状的名称。</span><span class="sxs-lookup"><span data-stu-id="9da21-117">is the name of the shape from which you want to retrieve the text.</span></span>  <br/> |
| <span data-ttu-id="9da21-118">_maximumwidth_</span><span class="sxs-lookup"><span data-stu-id="9da21-118">_maximumwidth_</span></span> <br/> |<span data-ttu-id="9da21-119">可选</span><span class="sxs-lookup"><span data-stu-id="9da21-119">Optional</span></span>  <br/> |<span data-ttu-id="9da21-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="9da21-120">**Numeric**</span></span> <br/> |<span data-ttu-id="9da21-121">文本块的最大宽度。</span><span class="sxs-lookup"><span data-stu-id="9da21-121">The maximum width of the text block.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="9da21-122">返回值</span><span class="sxs-lookup"><span data-stu-id="9da21-122">Return value</span></span>

<span data-ttu-id="9da21-123">String</span><span class="sxs-lookup"><span data-stu-id="9da21-123">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9da21-124">备注</span><span class="sxs-lookup"><span data-stu-id="9da21-124">Remarks</span></span>

<span data-ttu-id="9da21-125">TEXTWIDTH 函数常用于调整形状的宽度，以适合它所包含的文本。</span><span class="sxs-lookup"><span data-stu-id="9da21-125">The TEXTWIDTH function is commonly used to adjust the width of a shape to fit the text it contains.</span></span>
  
<span data-ttu-id="9da21-126">如果  _sheetN！_</span><span class="sxs-lookup"><span data-stu-id="9da21-126">If  _sheetN!_</span></span> <span data-ttu-id="9da21-127">省略，默认形状是当前形状。</span><span class="sxs-lookup"><span data-stu-id="9da21-127">is omitted, the default shape is the current shape.</span></span> 
  
<span data-ttu-id="9da21-128">如果  _指定了 maximumwidth，_ 则结果是适合  _maximumwidth_ 的最长文本行。</span><span class="sxs-lookup"><span data-stu-id="9da21-128">If  _maximumwidth_ is specified, the result is the longest line of text that fits within  _maximumwidth_.</span></span> <span data-ttu-id="9da21-129">如果  _省略 maximumwidth，_ 则结果是文本的总宽度。</span><span class="sxs-lookup"><span data-stu-id="9da21-129">If  _maximumwidth_ is omitted, the result is the total width of the text.</span></span> 
  
## <a name="example"></a><span data-ttu-id="9da21-130">示例</span><span class="sxs-lookup"><span data-stu-id="9da21-130">Example</span></span>

<span data-ttu-id="9da21-131">TEXTWIDTH (Text) </span><span class="sxs-lookup"><span data-stu-id="9da21-131">TEXTWIDTH(TheText)</span></span> 
  
<span data-ttu-id="9da21-132">返回当前形状中文本的总长度。</span><span class="sxs-lookup"><span data-stu-id="9da21-132">Returns the total length of the text in the current shape.</span></span> 
  

