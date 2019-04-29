---
title: BLUE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251402
localization_priority: Normal
ms.assetid: da9fb933-4e2c-3e2a-1879-6e70db0cd830
description: 返回颜色的蓝色成分。 返回值是介于0到 255 (含) 之间的整数。 对于无效输入，该函数将返回 0。
ms.openlocfilehash: adefbe0f8c2df0ead0f3e50cd5d4945501972865
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439035"
---
# <a name="blue-function"></a><span data-ttu-id="5bc22-105">BLUE 函数</span><span class="sxs-lookup"><span data-stu-id="5bc22-105">BLUE Function</span></span>

<span data-ttu-id="5bc22-106">返回颜色的蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="5bc22-106">Returns the blue component of a color.</span></span> <span data-ttu-id="5bc22-107">返回值是介于0到 255 (含) 之间的整数。</span><span class="sxs-lookup"><span data-stu-id="5bc22-107">The return value is an integer in the range of 0 to 255, inclusive.</span></span> <span data-ttu-id="5bc22-108">对于无效输入，该函数将返回 0。</span><span class="sxs-lookup"><span data-stu-id="5bc22-108">The function returns 0 for invalid input.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5bc22-109">语法</span><span class="sxs-lookup"><span data-stu-id="5bc22-109">Syntax</span></span>

<span data-ttu-id="5bc22-110">蓝色 (\* **表达式** \*)</span><span class="sxs-lookup"><span data-stu-id="5bc22-110">BLUE(\*\* *expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5bc22-111">参数</span><span class="sxs-lookup"><span data-stu-id="5bc22-111">Parameters</span></span>

|<span data-ttu-id="5bc22-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="5bc22-112">**Name**</span></span>|<span data-ttu-id="5bc22-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5bc22-113">**Required/Optional**</span></span>|<span data-ttu-id="5bc22-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5bc22-114">**Data Type**</span></span>|<span data-ttu-id="5bc22-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="5bc22-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5bc22-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="5bc22-116">_expression_</span></span> <br/> |<span data-ttu-id="5bc22-117">必需</span><span class="sxs-lookup"><span data-stu-id="5bc22-117">Required</span></span>  <br/> |<span data-ttu-id="5bc22-118">**String**</span><span class="sxs-lookup"><span data-stu-id="5bc22-118">**String**</span></span> <br/> |<span data-ttu-id="5bc22-119">文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="5bc22-119">An index of a color in the document's color table, an expression that resolves to a custom color (like RGB or HSL), or a reference to a cell that contains a color index or color result.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5bc22-120">返回值</span><span class="sxs-lookup"><span data-stu-id="5bc22-120">Return value</span></span>

<span data-ttu-id="5bc22-121">整数</span><span class="sxs-lookup"><span data-stu-id="5bc22-121">Integer</span></span>
  
## <a name="example-1"></a><span data-ttu-id="5bc22-122">示例 1</span><span class="sxs-lookup"><span data-stu-id="5bc22-122">Example 1</span></span>

<span data-ttu-id="5bc22-123">蓝色 (Sheet 4!FillForegnd</span><span class="sxs-lookup"><span data-stu-id="5bc22-123">BLUE(Sheet.4!FillForegnd)</span></span>
  
<span data-ttu-id="5bc22-124">返回 Sheet.4 的填充前景色的蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="5bc22-124">Returns the blue component of Sheet.4's fill foreground color.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="5bc22-125">示例 2</span><span class="sxs-lookup"><span data-stu-id="5bc22-125">Example 2</span></span>

<span data-ttu-id="5bc22-126">蓝色 (13)</span><span class="sxs-lookup"><span data-stu-id="5bc22-126">BLUE(13)</span></span>
  
<span data-ttu-id="5bc22-127">如果文档使用默认的 Visio 调色板（其中青色是索引值为 13 的颜色），则返回 128。</span><span class="sxs-lookup"><span data-stu-id="5bc22-127">Returns 128 if the document uses the default Visio color palette, where cyan is the color at index 13.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="5bc22-128">示例 3</span><span class="sxs-lookup"><span data-stu-id="5bc22-128">Example 3</span></span>

<span data-ttu-id="5bc22-129">BLUE(RGB(10, 20, 30))</span><span class="sxs-lookup"><span data-stu-id="5bc22-129">BLUE(RGB(10, 20, 30))</span></span>
  
<span data-ttu-id="5bc22-130">返回 30。</span><span class="sxs-lookup"><span data-stu-id="5bc22-130">Returns 30.</span></span>
  

