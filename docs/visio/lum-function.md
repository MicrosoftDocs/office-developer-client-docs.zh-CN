---
title: LUM 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251460
localization_priority: Normal
ms.assetid: 38e6bba7-1bf2-3d31-0912-707002454f5d
description: 返回一种颜色的发光度组件的值。
ms.openlocfilehash: 9c9594aff0149a54d7faacdf8295e6c214c43348
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780679"
---
# <a name="lum-function"></a><span data-ttu-id="2aa2b-103">LUM 函数</span><span class="sxs-lookup"><span data-stu-id="2aa2b-103">LUM Function</span></span>

<span data-ttu-id="2aa2b-104">返回一种颜色的发光度组件的值。</span><span class="sxs-lookup"><span data-stu-id="2aa2b-104">Returns the value of a color's luminosity component.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="2aa2b-105">语法</span><span class="sxs-lookup"><span data-stu-id="2aa2b-105">Syntax</span></span>

<span data-ttu-id="2aa2b-106">LUM (* **表达式** *)</span><span class="sxs-lookup"><span data-stu-id="2aa2b-106">LUM(** *expression* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2aa2b-107">参数</span><span class="sxs-lookup"><span data-stu-id="2aa2b-107">Parameters</span></span>

|<span data-ttu-id="2aa2b-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="2aa2b-108">**Name**</span></span>|<span data-ttu-id="2aa2b-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2aa2b-109">**Required/Optional**</span></span>|<span data-ttu-id="2aa2b-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2aa2b-110">**Data Type**</span></span>|<span data-ttu-id="2aa2b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2aa2b-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2aa2b-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="2aa2b-112">_expression_</span></span> <br/> |<span data-ttu-id="2aa2b-113">必需</span><span class="sxs-lookup"><span data-stu-id="2aa2b-113">Required</span></span>  <br/> |<span data-ttu-id="2aa2b-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="2aa2b-114">**Numeric**</span></span> <br/> |<span data-ttu-id="2aa2b-115">文档颜色表中的颜色索引值，或对包含颜色索引值的某单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="2aa2b-115">The index of a color in the document's color table, or a reference to a cell that contains a color index.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="2aa2b-116">返回值</span><span class="sxs-lookup"><span data-stu-id="2aa2b-116">Return value</span></span>

<span data-ttu-id="2aa2b-117">Number</span><span class="sxs-lookup"><span data-stu-id="2aa2b-117">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2aa2b-118">注解</span><span class="sxs-lookup"><span data-stu-id="2aa2b-118">Remarks</span></span>

<span data-ttu-id="2aa2b-p101">返回值是 0 至 240 之间的数字（包括 0 和 240）。对于无效输入，该函数将返回 0。</span><span class="sxs-lookup"><span data-stu-id="2aa2b-p101">The return value is a number in the range 0 to 240, inclusive. The function returns 0 for invalid input.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="2aa2b-121">示例 1</span><span class="sxs-lookup"><span data-stu-id="2aa2b-121">Example 1</span></span>

<span data-ttu-id="2aa2b-122">LUM (Sheet.4 ！FillForegnd)</span><span class="sxs-lookup"><span data-stu-id="2aa2b-122">LUM(Sheet.4!FillForegnd)</span></span>
  
<span data-ttu-id="2aa2b-123">返回 Sheet.4 的填充前景色的发光度。</span><span class="sxs-lookup"><span data-stu-id="2aa2b-123">Returns the luminosity of Sheet.4's fill foreground color.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="2aa2b-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="2aa2b-124">Example 2</span></span>

<span data-ttu-id="2aa2b-125">LUM(6)</span><span class="sxs-lookup"><span data-stu-id="2aa2b-125">LUM(6)</span></span>
  
<span data-ttu-id="2aa2b-126">如果文档使用默认的 Visio 调色板，其中洋红是索引值为 6 的颜色，则返回 120。</span><span class="sxs-lookup"><span data-stu-id="2aa2b-126">Returns 120 if the document uses the default Visio color palette, where magenta is the color at index 6.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="2aa2b-127">示例 3</span><span class="sxs-lookup"><span data-stu-id="2aa2b-127">Example 3</span></span>

<span data-ttu-id="2aa2b-128">LUM(HSL(10, 20, 30))</span><span class="sxs-lookup"><span data-stu-id="2aa2b-128">LUM(HSL(10, 20, 30))</span></span>
  
<span data-ttu-id="2aa2b-129">返回 30。</span><span class="sxs-lookup"><span data-stu-id="2aa2b-129">Returns 30.</span></span>
  
