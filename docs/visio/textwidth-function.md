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
description: 返回形状中的撰写文本的宽度。
ms.openlocfilehash: d96b9489c08ce38205f8e9ad91e361fcb643c39c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781496"
---
# <a name="textwidth-function"></a><span data-ttu-id="de8d1-103">TEXTWIDTH 函数</span><span class="sxs-lookup"><span data-stu-id="de8d1-103">TEXTWIDTH Function</span></span>

<span data-ttu-id="de8d1-104">返回形状中的撰写文本的宽度。</span><span class="sxs-lookup"><span data-stu-id="de8d1-104">Returns the width of the composed text in a shape.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="de8d1-105">语法</span><span class="sxs-lookup"><span data-stu-id="de8d1-105">Syntax</span></span>

<span data-ttu-id="de8d1-106">TEXTWIDTH (* * *shapename ！TheText* * * * * *[，最大宽度]* * *)</span><span class="sxs-lookup"><span data-stu-id="de8d1-106">TEXTWIDTH(** *shapename!TheText* ** ** *[,maximumwidth]* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="de8d1-107">参数</span><span class="sxs-lookup"><span data-stu-id="de8d1-107">Parameters</span></span>

|<span data-ttu-id="de8d1-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="de8d1-108">**Name**</span></span>|<span data-ttu-id="de8d1-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="de8d1-109">**Required/Optional**</span></span>|<span data-ttu-id="de8d1-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="de8d1-110">**Data Type**</span></span>|<span data-ttu-id="de8d1-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="de8d1-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="de8d1-112">_shapename ！ theText_</span><span class="sxs-lookup"><span data-stu-id="de8d1-112">_shapename!theText_</span></span> <br/> |<span data-ttu-id="de8d1-113">必需</span><span class="sxs-lookup"><span data-stu-id="de8d1-113">Required</span></span>  <br/> |<span data-ttu-id="de8d1-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="de8d1-114">**String**</span></span> <br/> |<span data-ttu-id="de8d1-115">单元格的引用的目标形状中名为 TheText。</span><span class="sxs-lookup"><span data-stu-id="de8d1-115">A reference to the cell named TheText in the target shape.</span></span>  <span data-ttu-id="de8d1-116">_shapename ！_</span><span class="sxs-lookup"><span data-stu-id="de8d1-116">_shapename!_</span></span> <span data-ttu-id="de8d1-117">是要从中检索文本的名称。</span><span class="sxs-lookup"><span data-stu-id="de8d1-117">is the name of the shape from which you want to retrieve the text.</span></span>  <br/> |
| <span data-ttu-id="de8d1-118">_最大宽度_</span><span class="sxs-lookup"><span data-stu-id="de8d1-118">_maximumwidth_</span></span> <br/> |<span data-ttu-id="de8d1-119">可选</span><span class="sxs-lookup"><span data-stu-id="de8d1-119">Optional</span></span>  <br/> |<span data-ttu-id="de8d1-120">**数字**</span><span class="sxs-lookup"><span data-stu-id="de8d1-120">**Numeric**</span></span> <br/> |<span data-ttu-id="de8d1-121">文本块的最大宽度。</span><span class="sxs-lookup"><span data-stu-id="de8d1-121">The maximum width of the text block.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="de8d1-122">返回值</span><span class="sxs-lookup"><span data-stu-id="de8d1-122">Return value</span></span>

<span data-ttu-id="de8d1-123">String</span><span class="sxs-lookup"><span data-stu-id="de8d1-123">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="de8d1-124">注解</span><span class="sxs-lookup"><span data-stu-id="de8d1-124">Remarks</span></span>

<span data-ttu-id="de8d1-125">TEXTWIDTH 函数常用于调整形状的宽度，以适合它所包含的文本。</span><span class="sxs-lookup"><span data-stu-id="de8d1-125">The TEXTWIDTH function is commonly used to adjust the width of a shape to fit the text it contains.</span></span>
  
<span data-ttu-id="de8d1-126">如果_sheetN ！_</span><span class="sxs-lookup"><span data-stu-id="de8d1-126">If  _sheetN!_</span></span> <span data-ttu-id="de8d1-127">被省略，默认形状为当前形状。</span><span class="sxs-lookup"><span data-stu-id="de8d1-127">is omitted, the default shape is the current shape.</span></span> 
  
<span data-ttu-id="de8d1-128">如果指定_最大宽度_，则结果是文本的最长的_最大宽度_相适应行。</span><span class="sxs-lookup"><span data-stu-id="de8d1-128">If  _maximumwidth_ is specified, the result is the longest line of text that fits within  _maximumwidth_.</span></span> <span data-ttu-id="de8d1-129">如果省略_最大宽度_，则结果为文本的总宽度。</span><span class="sxs-lookup"><span data-stu-id="de8d1-129">If  _maximumwidth_ is omitted, the result is the total width of the text.</span></span> 
  
## <a name="example"></a><span data-ttu-id="de8d1-130">示例</span><span class="sxs-lookup"><span data-stu-id="de8d1-130">Example</span></span>

<span data-ttu-id="de8d1-131">TEXTWIDTH(TheText)</span><span class="sxs-lookup"><span data-stu-id="de8d1-131">TEXTWIDTH(TheText)</span></span> 
  
<span data-ttu-id="de8d1-132">返回当前形状中文本的总长度。</span><span class="sxs-lookup"><span data-stu-id="de8d1-132">Returns the total length of the text in the current shape.</span></span> 
  

