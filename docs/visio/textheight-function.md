---
title: TEXTHEIGHT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251504
localization_priority: Normal
ms.assetid: 5a10892f-c8fa-c127-2f5a-564009ce5411
description: 返回组合文本的高度, 该形状中的文本行数超过 maximumwidth。
ms.openlocfilehash: 7455f58f14f9a4a0ae1fcd5375dba5d5860d3852
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427407"
---
# <a name="textheight-function"></a><span data-ttu-id="169a0-103">TEXTHEIGHT 函数</span><span class="sxs-lookup"><span data-stu-id="169a0-103">TEXTHEIGHT Function</span></span>

<span data-ttu-id="169a0-104">返回组合文本的高度, 该形状中的文本行数超过_maximumwidth_。</span><span class="sxs-lookup"><span data-stu-id="169a0-104">Returns the height of the composed text in a shape where no text line exceeds  _maximumwidth_.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="169a0-105">语法</span><span class="sxs-lookup"><span data-stu-id="169a0-105">Syntax</span></span>

<span data-ttu-id="169a0-106">TEXTHEIGHT (\* \* *shapename!TheText* \* \* \* \* *[, maximumwidth]* \* \*)</span><span class="sxs-lookup"><span data-stu-id="169a0-106">TEXTHEIGHT(\*\* *shapename!TheText* \*\* \*\* *[,maximumwidth]* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="169a0-107">参数</span><span class="sxs-lookup"><span data-stu-id="169a0-107">Parameters</span></span>

|<span data-ttu-id="169a0-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="169a0-108">**Name**</span></span>|<span data-ttu-id="169a0-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="169a0-109">**Required/Optional**</span></span>|<span data-ttu-id="169a0-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="169a0-110">**Data Type**</span></span>|<span data-ttu-id="169a0-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="169a0-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="169a0-112">_shapename! theText_</span><span class="sxs-lookup"><span data-stu-id="169a0-112">_shapename!theText_</span></span> <br/> |<span data-ttu-id="169a0-113">必需</span><span class="sxs-lookup"><span data-stu-id="169a0-113">Required</span></span>  <br/> |<span data-ttu-id="169a0-114">**String**</span><span class="sxs-lookup"><span data-stu-id="169a0-114">**String**</span></span> <br/> |<span data-ttu-id="169a0-115">对目标形状中名为 TheText 的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="169a0-115">A reference to the cell named TheText in the target shape.</span></span>  <span data-ttu-id="169a0-116">_shapename!_</span><span class="sxs-lookup"><span data-stu-id="169a0-116">_shapename!_</span></span> <span data-ttu-id="169a0-117">是要从中检索文本的形状的名称。</span><span class="sxs-lookup"><span data-stu-id="169a0-117">is the name of the shape from which you want to retrieve the text.</span></span>  <br/> |
| <span data-ttu-id="169a0-118">_maximumwidth_</span><span class="sxs-lookup"><span data-stu-id="169a0-118">_maximumwidth_</span></span> <br/> |<span data-ttu-id="169a0-119">可选</span><span class="sxs-lookup"><span data-stu-id="169a0-119">Optional</span></span>  <br/> |<span data-ttu-id="169a0-120">**数值**</span><span class="sxs-lookup"><span data-stu-id="169a0-120">**Numeric**</span></span> <br/> |<span data-ttu-id="169a0-121">文本块的最大宽度。</span><span class="sxs-lookup"><span data-stu-id="169a0-121">The maximum width of the text block.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="169a0-122">返回值</span><span class="sxs-lookup"><span data-stu-id="169a0-122">Return value</span></span>

<span data-ttu-id="169a0-123">String</span><span class="sxs-lookup"><span data-stu-id="169a0-123">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="169a0-124">说明</span><span class="sxs-lookup"><span data-stu-id="169a0-124">Remarks</span></span>

<span data-ttu-id="169a0-p102">返回的值包括文本高度，其中包括文本前后的空格、文本的行间距和上下文本块边距。此函数常用于调整形状的高度，以适合它所包含的文本。</span><span class="sxs-lookup"><span data-stu-id="169a0-p102">The returned value includes the height of the text including the space before and after text, the line spacing in text, and the top and bottom text block margins. This function is commonly used to adjust the height of a shape to fit the text it contains.</span></span>
  
## <a name="example"></a><span data-ttu-id="169a0-127">示例</span><span class="sxs-lookup"><span data-stu-id="169a0-127">Example</span></span>

<span data-ttu-id="169a0-128">TEXTHEIGHT(TheText,(Width - 0.5 in))</span><span class="sxs-lookup"><span data-stu-id="169a0-128">TEXTHEIGHT(TheText,(Width - 0.5 in))</span></span> 
  
<span data-ttu-id="169a0-129">返回当文本按形状宽度减去 0.5 英寸后的宽度折行时文本的高度。</span><span class="sxs-lookup"><span data-stu-id="169a0-129">Returns the height of the text when wrapped to the width of the shape minus 0.5 inches.</span></span> 
  

