---
title: RED 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251487
localization_priority: Normal
ms.assetid: a95fd86d-ebc1-66b6-e7d9-9c8ea84d23ab
description: 返回一种颜色的红色成分。
ms.openlocfilehash: 801ebb64564df81f72c41cb720fe53f0f1b4c10d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19781015"
---
# <a name="red-function"></a><span data-ttu-id="f845c-103">RED 函数</span><span class="sxs-lookup"><span data-stu-id="f845c-103">RED Function</span></span>

<span data-ttu-id="f845c-104">返回一种颜色的红色成分。</span><span class="sxs-lookup"><span data-stu-id="f845c-104">Returns the red component of a color.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f845c-105">语法</span><span class="sxs-lookup"><span data-stu-id="f845c-105">Syntax</span></span>

<span data-ttu-id="f845c-106">红色 (* **表达式** *)</span><span class="sxs-lookup"><span data-stu-id="f845c-106">RED(** *expression* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f845c-107">参数</span><span class="sxs-lookup"><span data-stu-id="f845c-107">Parameters</span></span>

|<span data-ttu-id="f845c-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="f845c-108">**Name**</span></span>|<span data-ttu-id="f845c-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f845c-109">**Required/Optional**</span></span>|<span data-ttu-id="f845c-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f845c-110">**Data Type**</span></span>|<span data-ttu-id="f845c-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f845c-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f845c-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="f845c-112">_expression_</span></span> <br/> |<span data-ttu-id="f845c-113">必需</span><span class="sxs-lookup"><span data-stu-id="f845c-113">Required</span></span>  <br/> |<span data-ttu-id="f845c-114">**因情况而异**</span><span class="sxs-lookup"><span data-stu-id="f845c-114">**Varies**</span></span> <br/> |<span data-ttu-id="f845c-115">文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="f845c-115">An index of a color in the document's color table, an expression that resolves to a custom color (like RGB or HSL), or a reference to a cell that contains a color index or color result.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="f845c-116">返回值</span><span class="sxs-lookup"><span data-stu-id="f845c-116">Return value</span></span>

<span data-ttu-id="f845c-117">Number</span><span class="sxs-lookup"><span data-stu-id="f845c-117">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f845c-118">说明</span><span class="sxs-lookup"><span data-stu-id="f845c-118">Remarks</span></span>

<span data-ttu-id="f845c-119">返回值是 0 到 255，包括的数字或解析为索引的单元格引用。</span><span class="sxs-lookup"><span data-stu-id="f845c-119">The return value is a number in the range 0 to 255, inclusive, or a cell reference that resolves to an index.</span></span> <span data-ttu-id="f845c-120">如果_表达式_无效，本函数将返回 0 （黑色）。</span><span class="sxs-lookup"><span data-stu-id="f845c-120">If  _expression_ is invalid, this function returns 0 (black).</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="f845c-121">示例 1</span><span class="sxs-lookup"><span data-stu-id="f845c-121">Example 1</span></span>

<span data-ttu-id="f845c-122">RED(22)</span><span class="sxs-lookup"><span data-stu-id="f845c-122">RED(22)</span></span>
  
<span data-ttu-id="f845c-123">如果文档使用默认的 Microsoft Office Visio 调色板，其中深灰色是索引值为 22 的颜色，则返回 51。</span><span class="sxs-lookup"><span data-stu-id="f845c-123">Returns 51 if the document uses the default Microsoft Office Visio color palette, where dark gray is the color at index 22.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="f845c-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="f845c-124">Example 2</span></span>

<span data-ttu-id="f845c-125">RED(Char.Color)</span><span class="sxs-lookup"><span data-stu-id="f845c-125">RED(Char.Color)</span></span>
  
<span data-ttu-id="f845c-126">返回当前字体颜色的红色成分值。</span><span class="sxs-lookup"><span data-stu-id="f845c-126">Returns the value of the red component of the current font color.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="f845c-127">示例 3</span><span class="sxs-lookup"><span data-stu-id="f845c-127">Example 3</span></span>

<span data-ttu-id="f845c-128">RED(RGB(10, 20, 30))</span><span class="sxs-lookup"><span data-stu-id="f845c-128">RED(RGB(10, 20, 30))</span></span>
  
<span data-ttu-id="f845c-129">返回 10。</span><span class="sxs-lookup"><span data-stu-id="f845c-129">Returns 10.</span></span>
  

