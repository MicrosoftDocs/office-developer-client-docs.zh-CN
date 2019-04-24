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
description: 返回形状中撰写的文本的宽度。
ms.openlocfilehash: 43848bba4d24a0c31a3a084d123cd56140bf0709
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332268"
---
# <a name="textwidth-function"></a><span data-ttu-id="b083b-103">TEXTWIDTH 函数</span><span class="sxs-lookup"><span data-stu-id="b083b-103">TEXTWIDTH Function</span></span>

<span data-ttu-id="b083b-104">返回形状中撰写的文本的宽度。</span><span class="sxs-lookup"><span data-stu-id="b083b-104">Returns the width of the composed text in a shape.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b083b-105">语法</span><span class="sxs-lookup"><span data-stu-id="b083b-105">Syntax</span></span>

<span data-ttu-id="b083b-106">TEXTWIDTH (\* \* *shapename!TheText* \* \* \* \* *[, maximumwidth]* \* \*)</span><span class="sxs-lookup"><span data-stu-id="b083b-106">TEXTWIDTH(\*\* *shapename!TheText* \*\* \*\* *[,maximumwidth]* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="b083b-107">参数</span><span class="sxs-lookup"><span data-stu-id="b083b-107">Parameters</span></span>

|<span data-ttu-id="b083b-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="b083b-108">**Name**</span></span>|<span data-ttu-id="b083b-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="b083b-109">**Required/Optional**</span></span>|<span data-ttu-id="b083b-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b083b-110">**Data Type**</span></span>|<span data-ttu-id="b083b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="b083b-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b083b-112">_shapename! theText_</span><span class="sxs-lookup"><span data-stu-id="b083b-112">_shapename!theText_</span></span> <br/> |<span data-ttu-id="b083b-113">必需</span><span class="sxs-lookup"><span data-stu-id="b083b-113">Required</span></span>  <br/> |<span data-ttu-id="b083b-114">**String**</span><span class="sxs-lookup"><span data-stu-id="b083b-114">**String**</span></span> <br/> |<span data-ttu-id="b083b-115">对目标形状中名为 TheText 的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="b083b-115">A reference to the cell named TheText in the target shape.</span></span>  <span data-ttu-id="b083b-116">_shapename!_</span><span class="sxs-lookup"><span data-stu-id="b083b-116">_shapename!_</span></span> <span data-ttu-id="b083b-117">是要从中检索文本的形状的名称。</span><span class="sxs-lookup"><span data-stu-id="b083b-117">is the name of the shape from which you want to retrieve the text.</span></span>  <br/> |
| <span data-ttu-id="b083b-118">_maximumwidth_</span><span class="sxs-lookup"><span data-stu-id="b083b-118">_maximumwidth_</span></span> <br/> |<span data-ttu-id="b083b-119">可选</span><span class="sxs-lookup"><span data-stu-id="b083b-119">Optional</span></span>  <br/> |<span data-ttu-id="b083b-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="b083b-120">**Numeric**</span></span> <br/> |<span data-ttu-id="b083b-121">文本块的最大宽度。</span><span class="sxs-lookup"><span data-stu-id="b083b-121">The maximum width of the text block.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="b083b-122">返回值</span><span class="sxs-lookup"><span data-stu-id="b083b-122">Return value</span></span>

<span data-ttu-id="b083b-123">字符串</span><span class="sxs-lookup"><span data-stu-id="b083b-123">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b083b-124">注解</span><span class="sxs-lookup"><span data-stu-id="b083b-124">Remarks</span></span>

<span data-ttu-id="b083b-125">TEXTWIDTH 函数常用于调整形状的宽度，以适合它所包含的文本。</span><span class="sxs-lookup"><span data-stu-id="b083b-125">The TEXTWIDTH function is commonly used to adjust the width of a shape to fit the text it contains.</span></span>
  
<span data-ttu-id="b083b-126">如果_sheetN!_</span><span class="sxs-lookup"><span data-stu-id="b083b-126">If  _sheetN!_</span></span> <span data-ttu-id="b083b-127">被省略, 则默认形状为当前形状。</span><span class="sxs-lookup"><span data-stu-id="b083b-127">is omitted, the default shape is the current shape.</span></span> 
  
<span data-ttu-id="b083b-128">如果指定了_maximumwidth_ , 则结果是适合在_maximumwidth_中的文本的最长行。</span><span class="sxs-lookup"><span data-stu-id="b083b-128">If  _maximumwidth_ is specified, the result is the longest line of text that fits within  _maximumwidth_.</span></span> <span data-ttu-id="b083b-129">如果省略_maximumwidth_ , 则结果为文本的总宽度。</span><span class="sxs-lookup"><span data-stu-id="b083b-129">If  _maximumwidth_ is omitted, the result is the total width of the text.</span></span> 
  
## <a name="example"></a><span data-ttu-id="b083b-130">示例</span><span class="sxs-lookup"><span data-stu-id="b083b-130">Example</span></span>

<span data-ttu-id="b083b-131">TEXTWIDTH (TheText)</span><span class="sxs-lookup"><span data-stu-id="b083b-131">TEXTWIDTH(TheText)</span></span> 
  
<span data-ttu-id="b083b-132">返回当前形状中文本的总长度。</span><span class="sxs-lookup"><span data-stu-id="b083b-132">Returns the total length of the text in the current shape.</span></span> 
  

