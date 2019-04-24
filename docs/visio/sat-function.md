---
title: SAT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251494
localization_priority: Normal
ms.assetid: 407817fb-9e4a-d2ca-6125-2440d2a417c6
description: 返回颜色饱和度组件的值。
ms.openlocfilehash: 3b3fd8e13ca9af4f0aea00d2f78c7b5c27be1932
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318996"
---
# <a name="sat-function"></a><span data-ttu-id="32d69-103">SAT 函数</span><span class="sxs-lookup"><span data-stu-id="32d69-103">SAT Function</span></span>

<span data-ttu-id="32d69-104">返回颜色饱和度组件的值。</span><span class="sxs-lookup"><span data-stu-id="32d69-104">Returns the value of a color's saturation component.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="32d69-105">语法</span><span class="sxs-lookup"><span data-stu-id="32d69-105">Syntax</span></span>

<span data-ttu-id="32d69-106">SAT (\* **表达式** \*)</span><span class="sxs-lookup"><span data-stu-id="32d69-106">SAT(\*\* *expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="32d69-107">参数</span><span class="sxs-lookup"><span data-stu-id="32d69-107">Parameters</span></span>

|<span data-ttu-id="32d69-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="32d69-108">**Name**</span></span>|<span data-ttu-id="32d69-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="32d69-109">**Required/Optional**</span></span>|<span data-ttu-id="32d69-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="32d69-110">**Data Type**</span></span>|<span data-ttu-id="32d69-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="32d69-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="32d69-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="32d69-112">_expression_</span></span> <br/> |<span data-ttu-id="32d69-113">必需</span><span class="sxs-lookup"><span data-stu-id="32d69-113">Required</span></span>  <br/> |<span data-ttu-id="32d69-114">**相同**</span><span class="sxs-lookup"><span data-stu-id="32d69-114">**Varies**</span></span> <br/> |<span data-ttu-id="32d69-115">文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="32d69-115">An index of a color in the document's color table, an expression that resolves to a custom color (like RGB or HSL), or a reference to a cell that contains a color index or color result.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="32d69-116">返回值</span><span class="sxs-lookup"><span data-stu-id="32d69-116">Return value</span></span>

<span data-ttu-id="32d69-117">Numeric</span><span class="sxs-lookup"><span data-stu-id="32d69-117">Numeric</span></span>
  
## <a name="remarks"></a><span data-ttu-id="32d69-118">注解</span><span class="sxs-lookup"><span data-stu-id="32d69-118">Remarks</span></span>

<span data-ttu-id="32d69-p101">返回值是 0 至 240 之间的数字（包括 0 和 240）。对于无效输入，该函数将返回 0。</span><span class="sxs-lookup"><span data-stu-id="32d69-p101">The return value is a number in the range 0 to 240, inclusive. The function returns 0 for invalid input.</span></span>
  
## <a name="example-1"></a><span data-ttu-id="32d69-121">示例 1</span><span class="sxs-lookup"><span data-stu-id="32d69-121">Example 1</span></span>

<span data-ttu-id="32d69-122">SAT (Sheet. 4!FillForegnd</span><span class="sxs-lookup"><span data-stu-id="32d69-122">SAT(Sheet.4!FillForegnd)</span></span>
  
<span data-ttu-id="32d69-123">返回 Sheet.4 的填充前景色的饱和度。</span><span class="sxs-lookup"><span data-stu-id="32d69-123">Returns the saturation of Sheet.4's fill foreground color.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="32d69-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="32d69-124">Example 2</span></span>

<span data-ttu-id="32d69-125">SAT (8)</span><span class="sxs-lookup"><span data-stu-id="32d69-125">SAT(8)</span></span>
  
<span data-ttu-id="32d69-126">如果文档使用默认的 Visio 调色板，其中深红色的索引值是 8，则返回 240。</span><span class="sxs-lookup"><span data-stu-id="32d69-126">Returns 240 if the document uses the default Visio color palette, where dark red is the color at index 8.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="32d69-127">示例 3</span><span class="sxs-lookup"><span data-stu-id="32d69-127">Example 3</span></span>

<span data-ttu-id="32d69-128">SAT(HSL(10, 20, 30))</span><span class="sxs-lookup"><span data-stu-id="32d69-128">SAT(HSL(10, 20, 30))</span></span>
  
<span data-ttu-id="32d69-129">返回 20。</span><span class="sxs-lookup"><span data-stu-id="32d69-129">Returns 20.</span></span>
  

