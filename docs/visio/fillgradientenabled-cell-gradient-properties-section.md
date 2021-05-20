---
title: 'FillGradientEnabled Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 80db9c0c-13c6-47de-967f-ade6e5899f14
description: 确定是否为此形状启用填充渐变。
ms.openlocfilehash: 17f617c13b632318be22b86a3354a194f0f835f5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431209"
---
# <a name="fillgradientenabled-cell-gradient-properties-section"></a><span data-ttu-id="06d86-103">FillGradientEnabled Cell (Gradient Properties Section) </span><span class="sxs-lookup"><span data-stu-id="06d86-103">FillGradientEnabled Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="06d86-104">确定是否为此形状启用填充渐变。</span><span class="sxs-lookup"><span data-stu-id="06d86-104">Determines whether a fill gradient is enabled for this shape.</span></span> 
  
|<span data-ttu-id="06d86-105">**值**</span><span class="sxs-lookup"><span data-stu-id="06d86-105">**Value**</span></span>|<span data-ttu-id="06d86-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="06d86-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="06d86-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="06d86-107">TRUE</span></span>  <br/> |<span data-ttu-id="06d86-108">渐变填充显示在形状上。</span><span class="sxs-lookup"><span data-stu-id="06d86-108">Gradient fill is displayed on the shape.</span></span>  <br/> |
|<span data-ttu-id="06d86-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="06d86-109">FALSE</span></span>  <br/> |<span data-ttu-id="06d86-110">渐变填充不显示在形状上。</span><span class="sxs-lookup"><span data-stu-id="06d86-110">Gradient fills are not displayed on the shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="06d86-111">备注</span><span class="sxs-lookup"><span data-stu-id="06d86-111">Remarks</span></span>

<span data-ttu-id="06d86-112">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **FillGradientEnabled** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="06d86-112">To get a reference to the **FillGradientEnabled** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="06d86-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="06d86-113">Cell name:</span></span>  <br/> | <span data-ttu-id="06d86-114">FillGradientEnabled</span><span class="sxs-lookup"><span data-stu-id="06d86-114">FillGradientEnabled</span></span>  <br/> |
   
<span data-ttu-id="06d86-115">若要从程序按索引获取对 **FillGradientEnabled** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="06d86-115">To get a reference to the **FillGradientEnabled** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="06d86-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="06d86-116">Section index:</span></span>  <br/> |<span data-ttu-id="06d86-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="06d86-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="06d86-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="06d86-118">Row index:</span></span>  <br/> |<span data-ttu-id="06d86-119">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="06d86-119">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="06d86-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="06d86-120">Cell index:</span></span>  <br/> |<span data-ttu-id="06d86-121">\*\*visFillGradientEnabled \*\*</span><span class="sxs-lookup"><span data-stu-id="06d86-121">\*\*visFillGradientEnabled \*\*</span></span> <br/> |
   

