---
title: HUE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251440
localization_priority: Normal
ms.assetid: 0f5c6097-eef5-5f58-e2ef-2c348e42dc9a
description: 返回颜色色调组件的值。
ms.openlocfilehash: 39fdd160f5cd792e95930a3e7c7cea3c37ed16c1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439490"
---
# <a name="hue-function"></a><span data-ttu-id="8f712-103">HUE 函数</span><span class="sxs-lookup"><span data-stu-id="8f712-103">HUE Function</span></span>

<span data-ttu-id="8f712-104">返回颜色色调组件的值。</span><span class="sxs-lookup"><span data-stu-id="8f712-104">Returns the value of a color's hue component.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8f712-105">语法</span><span class="sxs-lookup"><span data-stu-id="8f712-105">Syntax</span></span>

<span data-ttu-id="8f712-106">色相 (\* **表达式** \*)</span><span class="sxs-lookup"><span data-stu-id="8f712-106">HUE(\*\* *expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8f712-107">参数</span><span class="sxs-lookup"><span data-stu-id="8f712-107">Parameters</span></span>

|<span data-ttu-id="8f712-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="8f712-108">**Name**</span></span>|<span data-ttu-id="8f712-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8f712-109">**Required/Optional**</span></span>|<span data-ttu-id="8f712-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8f712-110">**Data Type**</span></span>|<span data-ttu-id="8f712-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f712-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8f712-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="8f712-112">_expression_</span></span> <br/> |<span data-ttu-id="8f712-113">必需</span><span class="sxs-lookup"><span data-stu-id="8f712-113">Required</span></span>  <br/> |<span data-ttu-id="8f712-114">**String**</span><span class="sxs-lookup"><span data-stu-id="8f712-114">**String**</span></span> <br/> |<span data-ttu-id="8f712-115">一个计算结果为某种颜色的表达式。</span><span class="sxs-lookup"><span data-stu-id="8f712-115">An expression that evaluates to a color.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="8f712-116">返回值</span><span class="sxs-lookup"><span data-stu-id="8f712-116">Return value</span></span>

<span data-ttu-id="8f712-117">数字</span><span class="sxs-lookup"><span data-stu-id="8f712-117">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8f712-118">说明</span><span class="sxs-lookup"><span data-stu-id="8f712-118">Remarks</span></span>

<span data-ttu-id="8f712-p101">返回值是 0 至 239 之间的数字（包括 0 和 239）。输入内容为文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。对于无效输入，该函数将返回 0。</span><span class="sxs-lookup"><span data-stu-id="8f712-p101">The return value is a number in the range 0 to 239, inclusive. The input is an index of a color in the document's color table, an expression that resolves to a custom color (like RGB or HSL), or a reference to a cell that contains a color index or color result. The function returns 0 for invalid input.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="8f712-122">示例 1</span><span class="sxs-lookup"><span data-stu-id="8f712-122">Example 1</span></span>

<span data-ttu-id="8f712-123">色相 (Sheet. 4!FillForegnd</span><span class="sxs-lookup"><span data-stu-id="8f712-123">HUE(Sheet.4!FillForegnd)</span></span>
  
<span data-ttu-id="8f712-124">返回 Sheet.4 的填充前景色的色调。</span><span class="sxs-lookup"><span data-stu-id="8f712-124">Returns the hue of Sheet.4's fill foreground color.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="8f712-125">示例 2</span><span class="sxs-lookup"><span data-stu-id="8f712-125">Example 2</span></span>

<span data-ttu-id="8f712-126">色相 (7)</span><span class="sxs-lookup"><span data-stu-id="8f712-126">HUE(7)</span></span>
  
<span data-ttu-id="8f712-127">如果文档使用默认的 Microsoft Visio 调色板，其中青色是索引值为 7 的颜色，则返回 120。</span><span class="sxs-lookup"><span data-stu-id="8f712-127">Returns 120 if the document uses the default Microsoft Visio color palette, where cyan is the color at index 7.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="8f712-128">示例 3</span><span class="sxs-lookup"><span data-stu-id="8f712-128">Example 3</span></span>

<span data-ttu-id="8f712-129">HUE(HSL(10, 20, 30) )</span><span class="sxs-lookup"><span data-stu-id="8f712-129">HUE(HSL(10, 20, 30) )</span></span>
  
<span data-ttu-id="8f712-130">返回 10。</span><span class="sxs-lookup"><span data-stu-id="8f712-130">Returns 10.</span></span>
  

