---
title: EnableTextProps 单元格（“Style Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251697
localization_priority: Normal
ms.assetid: 8c59abaf-d2cc-94c9-08ba-004bc40efd9e
description: 确定样式是否包括文本属性。
ms.openlocfilehash: 3f1d87316955b4e6e40cea16634cff7645a720fe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328915"
---
# <a name="enabletextprops-cell-style-properties-section"></a><span data-ttu-id="c0cb3-103">EnableTextProps 单元格（“Style Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="c0cb3-103">EnableTextProps Cell (Style Properties Section)</span></span>

<span data-ttu-id="c0cb3-104">确定样式是否包括文本属性。</span><span class="sxs-lookup"><span data-stu-id="c0cb3-104">Determines whether a style includes text properties.</span></span>
  
|<span data-ttu-id="c0cb3-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="c0cb3-105">**Value**</span></span>|<span data-ttu-id="c0cb3-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="c0cb3-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0cb3-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="c0cb3-107">TRUE</span></span>  <br/> |<span data-ttu-id="c0cb3-108">包括文本属性。</span><span class="sxs-lookup"><span data-stu-id="c0cb3-108">Include text properties.</span></span>  <br/> |
|<span data-ttu-id="c0cb3-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="c0cb3-109">FALSE</span></span>  <br/> |<span data-ttu-id="c0cb3-110">不包括文本属性。</span><span class="sxs-lookup"><span data-stu-id="c0cb3-110">Exclude text properties.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c0cb3-111">注解</span><span class="sxs-lookup"><span data-stu-id="c0cb3-111">Remarks</span></span>

<span data-ttu-id="c0cb3-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableTextProps 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c0cb3-112">To get a reference to the EnableTextProps cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c0cb3-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c0cb3-113">Cell name:</span></span>  <br/> |<span data-ttu-id="c0cb3-114">EnableTextProps</span><span class="sxs-lookup"><span data-stu-id="c0cb3-114">EnableTextProps</span></span>  <br/> |
   
<span data-ttu-id="c0cb3-115">要从某个程序按索引获取对 EnableTextProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c0cb3-115">To get a reference to the EnableTextProps cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c0cb3-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c0cb3-116">Section index:</span></span>  <br/> |<span data-ttu-id="c0cb3-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c0cb3-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="c0cb3-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="c0cb3-118">Row index:</span></span>  <br/> |<span data-ttu-id="c0cb3-119">**visRowStyle**</span><span class="sxs-lookup"><span data-stu-id="c0cb3-119">**visRowStyle**</span></span> <br/> |
|<span data-ttu-id="c0cb3-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c0cb3-120">Cell index:</span></span>  <br/> |<span data-ttu-id="c0cb3-121">**visStyleIncludesText**</span><span class="sxs-lookup"><span data-stu-id="c0cb3-121">**visStyleIncludesText**</span></span> <br/> |
   

