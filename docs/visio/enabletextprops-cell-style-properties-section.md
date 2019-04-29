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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419259"
---
# <a name="enabletextprops-cell-style-properties-section"></a><span data-ttu-id="23210-103">EnableTextProps 单元格（“Style Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="23210-103">EnableTextProps Cell (Style Properties Section)</span></span>

<span data-ttu-id="23210-104">确定样式是否包括文本属性。</span><span class="sxs-lookup"><span data-stu-id="23210-104">Determines whether a style includes text properties.</span></span>
  
|<span data-ttu-id="23210-105">**值**</span><span class="sxs-lookup"><span data-stu-id="23210-105">**Value**</span></span>|<span data-ttu-id="23210-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="23210-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23210-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="23210-107">TRUE</span></span>  <br/> |<span data-ttu-id="23210-108">包括文本属性。</span><span class="sxs-lookup"><span data-stu-id="23210-108">Include text properties.</span></span>  <br/> |
|<span data-ttu-id="23210-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="23210-109">FALSE</span></span>  <br/> |<span data-ttu-id="23210-110">不包括文本属性。</span><span class="sxs-lookup"><span data-stu-id="23210-110">Exclude text properties.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="23210-111">说明</span><span class="sxs-lookup"><span data-stu-id="23210-111">Remarks</span></span>

<span data-ttu-id="23210-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableTextProps 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="23210-112">To get a reference to the EnableTextProps cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23210-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="23210-113">Cell name:</span></span>  <br/> |<span data-ttu-id="23210-114">EnableTextProps</span><span class="sxs-lookup"><span data-stu-id="23210-114">EnableTextProps</span></span>  <br/> |
   
<span data-ttu-id="23210-115">要从某个程序按索引获取对 EnableTextProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="23210-115">To get a reference to the EnableTextProps cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23210-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="23210-116">Section index:</span></span>  <br/> |<span data-ttu-id="23210-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="23210-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="23210-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="23210-118">Row index:</span></span>  <br/> |<span data-ttu-id="23210-119">**visRowStyle**</span><span class="sxs-lookup"><span data-stu-id="23210-119">**visRowStyle**</span></span> <br/> |
|<span data-ttu-id="23210-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="23210-120">Cell index:</span></span>  <br/> |<span data-ttu-id="23210-121">**visStyleIncludesText**</span><span class="sxs-lookup"><span data-stu-id="23210-121">**visStyleIncludesText**</span></span> <br/> |
   

