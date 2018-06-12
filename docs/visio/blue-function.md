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
description: 返回一种颜色的蓝色成分。 返回值是整数，范围为 0 到 255。 此函数返回无效输入的 0。
ms.openlocfilehash: 6a86a0ee91054c89f2def95c0e3521508462bdaa
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779776"
---
# <a name="blue-function"></a><span data-ttu-id="76ccb-105">BLUE 函数</span><span class="sxs-lookup"><span data-stu-id="76ccb-105">BLUE Function</span></span>

<span data-ttu-id="76ccb-106">返回一种颜色的蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="76ccb-106">Returns the blue component of a color.</span></span> <span data-ttu-id="76ccb-107">返回值是整数，范围为 0 到 255。</span><span class="sxs-lookup"><span data-stu-id="76ccb-107">The return value is an integer in the range of 0 to 255, inclusive.</span></span> <span data-ttu-id="76ccb-108">此函数返回无效输入的 0。</span><span class="sxs-lookup"><span data-stu-id="76ccb-108">The function returns 0 for invalid input.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="76ccb-109">语法</span><span class="sxs-lookup"><span data-stu-id="76ccb-109">Syntax</span></span>

<span data-ttu-id="76ccb-110">蓝色 (* **表达式** *)</span><span class="sxs-lookup"><span data-stu-id="76ccb-110">BLUE(** *expression* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="76ccb-111">参数</span><span class="sxs-lookup"><span data-stu-id="76ccb-111">Parameters</span></span>

|<span data-ttu-id="76ccb-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="76ccb-112">**Name**</span></span>|<span data-ttu-id="76ccb-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="76ccb-113">**Required/Optional**</span></span>|<span data-ttu-id="76ccb-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="76ccb-114">**Data Type**</span></span>|<span data-ttu-id="76ccb-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="76ccb-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="76ccb-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="76ccb-116">_expression_</span></span> <br/> |<span data-ttu-id="76ccb-117">必需</span><span class="sxs-lookup"><span data-stu-id="76ccb-117">Required</span></span>  <br/> |<span data-ttu-id="76ccb-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="76ccb-118">**String**</span></span> <br/> |<span data-ttu-id="76ccb-119">文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="76ccb-119">An index of a color in the document's color table, an expression that resolves to a custom color (like RGB or HSL), or a reference to a cell that contains a color index or color result.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="76ccb-120">返回值</span><span class="sxs-lookup"><span data-stu-id="76ccb-120">Return value</span></span>

<span data-ttu-id="76ccb-121">Integer</span><span class="sxs-lookup"><span data-stu-id="76ccb-121">Integer</span></span>
  
## <a name="example-1"></a><span data-ttu-id="76ccb-122">示例 1</span><span class="sxs-lookup"><span data-stu-id="76ccb-122">Example 1</span></span>

<span data-ttu-id="76ccb-123">蓝色 (Sheet.4 ！FillForegnd)</span><span class="sxs-lookup"><span data-stu-id="76ccb-123">BLUE(Sheet.4!FillForegnd)</span></span>
  
<span data-ttu-id="76ccb-124">返回 Sheet.4 的填充前景色的蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="76ccb-124">Returns the blue component of Sheet.4's fill foreground color.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="76ccb-125">示例 2</span><span class="sxs-lookup"><span data-stu-id="76ccb-125">Example 2</span></span>

<span data-ttu-id="76ccb-126">BLUE(13)</span><span class="sxs-lookup"><span data-stu-id="76ccb-126">BLUE(13)</span></span>
  
<span data-ttu-id="76ccb-127">如果文档使用默认的 Visio 调色板（其中青色是索引值为 13 的颜色），则返回 128。</span><span class="sxs-lookup"><span data-stu-id="76ccb-127">Returns 128 if the document uses the default Visio color palette, where cyan is the color at index 13.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="76ccb-128">示例 3</span><span class="sxs-lookup"><span data-stu-id="76ccb-128">Example 3</span></span>

<span data-ttu-id="76ccb-129">BLUE(RGB(10, 20, 30))</span><span class="sxs-lookup"><span data-stu-id="76ccb-129">BLUE(RGB(10, 20, 30))</span></span>
  
<span data-ttu-id="76ccb-130">返回 30。</span><span class="sxs-lookup"><span data-stu-id="76ccb-130">Returns 30.</span></span>
  

