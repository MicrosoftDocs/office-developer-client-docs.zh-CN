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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297352"
---
# <a name="blue-function"></a><span data-ttu-id="1d8d0-105">BLUE 函数</span><span class="sxs-lookup"><span data-stu-id="1d8d0-105">BLUE Function</span></span>

<span data-ttu-id="1d8d0-106">返回颜色的蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="1d8d0-106">Returns the blue component of a color.</span></span> <span data-ttu-id="1d8d0-107">返回值是介于0到 255 (含) 之间的整数。</span><span class="sxs-lookup"><span data-stu-id="1d8d0-107">The return value is an integer in the range of 0 to 255, inclusive.</span></span> <span data-ttu-id="1d8d0-108">对于无效输入，该函数将返回 0。</span><span class="sxs-lookup"><span data-stu-id="1d8d0-108">The function returns 0 for invalid input.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1d8d0-109">语法</span><span class="sxs-lookup"><span data-stu-id="1d8d0-109">Syntax</span></span>

<span data-ttu-id="1d8d0-110">蓝色 (\* **表达式** \*)</span><span class="sxs-lookup"><span data-stu-id="1d8d0-110">BLUE(\*\* *expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1d8d0-111">参数</span><span class="sxs-lookup"><span data-stu-id="1d8d0-111">Parameters</span></span>

|<span data-ttu-id="1d8d0-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="1d8d0-112">**Name**</span></span>|<span data-ttu-id="1d8d0-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1d8d0-113">**Required/Optional**</span></span>|<span data-ttu-id="1d8d0-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1d8d0-114">**Data Type**</span></span>|<span data-ttu-id="1d8d0-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="1d8d0-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1d8d0-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="1d8d0-116">_expression_</span></span> <br/> |<span data-ttu-id="1d8d0-117">必需</span><span class="sxs-lookup"><span data-stu-id="1d8d0-117">Required</span></span>  <br/> |<span data-ttu-id="1d8d0-118">**String**</span><span class="sxs-lookup"><span data-stu-id="1d8d0-118">**String**</span></span> <br/> |<span data-ttu-id="1d8d0-119">文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="1d8d0-119">An index of a color in the document's color table, an expression that resolves to a custom color (like RGB or HSL), or a reference to a cell that contains a color index or color result.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="1d8d0-120">返回值</span><span class="sxs-lookup"><span data-stu-id="1d8d0-120">Return value</span></span>

<span data-ttu-id="1d8d0-121">整数</span><span class="sxs-lookup"><span data-stu-id="1d8d0-121">Integer</span></span>
  
## <a name="example-1"></a><span data-ttu-id="1d8d0-122">示例 1</span><span class="sxs-lookup"><span data-stu-id="1d8d0-122">Example 1</span></span>

<span data-ttu-id="1d8d0-123">蓝色 (Sheet 4!FillForegnd</span><span class="sxs-lookup"><span data-stu-id="1d8d0-123">BLUE(Sheet.4!FillForegnd)</span></span>
  
<span data-ttu-id="1d8d0-124">返回 Sheet.4 的填充前景色的蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="1d8d0-124">Returns the blue component of Sheet.4's fill foreground color.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="1d8d0-125">示例 2</span><span class="sxs-lookup"><span data-stu-id="1d8d0-125">Example 2</span></span>

<span data-ttu-id="1d8d0-126">蓝色 (13)</span><span class="sxs-lookup"><span data-stu-id="1d8d0-126">BLUE(13)</span></span>
  
<span data-ttu-id="1d8d0-127">如果文档使用默认的 Visio 调色板（其中青色是索引值为 13 的颜色），则返回 128。</span><span class="sxs-lookup"><span data-stu-id="1d8d0-127">Returns 128 if the document uses the default Visio color palette, where cyan is the color at index 13.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="1d8d0-128">示例 3</span><span class="sxs-lookup"><span data-stu-id="1d8d0-128">Example 3</span></span>

<span data-ttu-id="1d8d0-129">BLUE(RGB(10, 20, 30))</span><span class="sxs-lookup"><span data-stu-id="1d8d0-129">BLUE(RGB(10, 20, 30))</span></span>
  
<span data-ttu-id="1d8d0-130">返回 30。</span><span class="sxs-lookup"><span data-stu-id="1d8d0-130">Returns 30.</span></span>
  

