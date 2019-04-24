---
title: GREEN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251434
localization_priority: Normal
ms.assetid: eccec432-32d3-15c2-06b3-dd02b6313d4c
description: 返回颜色的绿色成分。
ms.openlocfilehash: 0412e4519c2964b05d7663805d7773e8dc5deaab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360205"
---
# <a name="green-function"></a><span data-ttu-id="1e158-103">GREEN 函数</span><span class="sxs-lookup"><span data-stu-id="1e158-103">GREEN Function</span></span>

<span data-ttu-id="1e158-104">返回颜色的绿色成分。</span><span class="sxs-lookup"><span data-stu-id="1e158-104">Returns the green component of a color.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1e158-105">语法</span><span class="sxs-lookup"><span data-stu-id="1e158-105">Syntax</span></span>

<span data-ttu-id="1e158-106">绿色 (\* **表达式** \*)</span><span class="sxs-lookup"><span data-stu-id="1e158-106">GREEN(\*\* *expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1e158-107">参数</span><span class="sxs-lookup"><span data-stu-id="1e158-107">Parameters</span></span>

|<span data-ttu-id="1e158-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="1e158-108">**Name**</span></span>|<span data-ttu-id="1e158-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1e158-109">**Required/Optional**</span></span>|<span data-ttu-id="1e158-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1e158-110">**Data Type**</span></span>|<span data-ttu-id="1e158-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1e158-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1e158-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="1e158-112">_expression_</span></span> <br/> |<span data-ttu-id="1e158-113">必需</span><span class="sxs-lookup"><span data-stu-id="1e158-113">Required</span></span>  <br/> |<span data-ttu-id="1e158-114">**相同**</span><span class="sxs-lookup"><span data-stu-id="1e158-114">**Varies**</span></span> <br/> |<span data-ttu-id="1e158-115">文档颜色表中颜色的索引、解析为自定义颜色的表达式 (如 RGB 或 HSL), 或者是对包含颜色索引或颜色结果的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="1e158-115">An index of a color in the document's color table, an expression that resolves to a custom color (such as RGB or HSL), or a reference to a cell that contains a color index or color result.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="1e158-116">返回值</span><span class="sxs-lookup"><span data-stu-id="1e158-116">Return value</span></span>

<span data-ttu-id="1e158-117">整数</span><span class="sxs-lookup"><span data-stu-id="1e158-117">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1e158-118">注解</span><span class="sxs-lookup"><span data-stu-id="1e158-118">Remarks</span></span>

<span data-ttu-id="1e158-119">返回值是 0 至 255（包括 0 和 255）之间的数字，或解析为索引值的单元格引用。</span><span class="sxs-lookup"><span data-stu-id="1e158-119">The return value is a number in the range 0 to 255, inclusive, or a cell reference that resolves to an index.</span></span> <span data-ttu-id="1e158-120">如果*表达式*无效, 则返回 0 (黑色)。</span><span class="sxs-lookup"><span data-stu-id="1e158-120">If  *expression*  is invalid, it returns 0 (black).</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="1e158-121">示例 1</span><span class="sxs-lookup"><span data-stu-id="1e158-121">Example 1</span></span>

<span data-ttu-id="1e158-122">绿色 (Sheet 4!FillForegnd</span><span class="sxs-lookup"><span data-stu-id="1e158-122">GREEN(Sheet.4!FillForegnd)</span></span>
  
<span data-ttu-id="1e158-123">返回 Sheet.4 的填充前景色的绿色成分。</span><span class="sxs-lookup"><span data-stu-id="1e158-123">Returns the green component of Sheet.4's fill foreground color.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="1e158-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="1e158-124">Example 2</span></span>

<span data-ttu-id="1e158-125">绿色 (11)</span><span class="sxs-lookup"><span data-stu-id="1e158-125">GREEN(11)</span></span>
  
<span data-ttu-id="1e158-126">如果文档使用默认的 Visio 调色板（其中深黄色是索引值为 11 的颜色），则返回 128。</span><span class="sxs-lookup"><span data-stu-id="1e158-126">Returns 128 if the document uses the default Visio color palette, where dark yellow is the color at index 11.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="1e158-127">示例 3</span><span class="sxs-lookup"><span data-stu-id="1e158-127">Example 3</span></span>

<span data-ttu-id="1e158-128">GREEN(RGB(10, 20, 30))</span><span class="sxs-lookup"><span data-stu-id="1e158-128">GREEN(RGB(10, 20, 30))</span></span>
  
<span data-ttu-id="1e158-129">返回 20。</span><span class="sxs-lookup"><span data-stu-id="1e158-129">Returns 20.</span></span>
  

