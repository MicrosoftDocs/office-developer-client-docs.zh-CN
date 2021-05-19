---
title: 'LineGradientEnabled Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 276a661f-d14e-404a-a494-ae36601a8ce3
description: 确定是否为形状的线条或边框启用线条渐变。
ms.openlocfilehash: 1d2b33275d26bb0c8e5550bcb7cf282c64d34544
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416375"
---
# <a name="linegradientenabled-cell-gradient-properties-section"></a><span data-ttu-id="3c318-103">LineGradientEnabled Cell (Gradient Properties Section) </span><span class="sxs-lookup"><span data-stu-id="3c318-103">LineGradientEnabled Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="3c318-104">确定是否为形状的线条或边框启用线条渐变。</span><span class="sxs-lookup"><span data-stu-id="3c318-104">Determines whether a line gradient is enabled for a line or border of a shape.</span></span> 
  
|<span data-ttu-id="3c318-105">**值**</span><span class="sxs-lookup"><span data-stu-id="3c318-105">**Value**</span></span>|<span data-ttu-id="3c318-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="3c318-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c318-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="3c318-107">TRUE</span></span>  <br/> |<span data-ttu-id="3c318-108">渐变显示在形状的线条或边框上。</span><span class="sxs-lookup"><span data-stu-id="3c318-108">Gradient is displayed on the line or border of a shape.</span></span>  <br/> |
|<span data-ttu-id="3c318-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="3c318-109">FALSE</span></span>  <br/> |<span data-ttu-id="3c318-110">渐变不显示在形状的线条或边框上。</span><span class="sxs-lookup"><span data-stu-id="3c318-110">Gradients are not displayed on the line or border of a shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3c318-111">备注</span><span class="sxs-lookup"><span data-stu-id="3c318-111">Remarks</span></span>

<span data-ttu-id="3c318-112">若要从另一个公式、Cell 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **LineGradientEnabled** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3c318-112">To get a reference to the **LineGradientEnabled** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3c318-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3c318-113">Cell name:</span></span>  <br/> | <span data-ttu-id="3c318-114">LineGradientEnabled</span><span class="sxs-lookup"><span data-stu-id="3c318-114">LineGradientEnabled</span></span>  <br/> |
   
<span data-ttu-id="3c318-115">若要从程序按索引获取对 **LineGradientEnabled** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="3c318-115">To get a reference to the **LineGradientEnabled** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3c318-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3c318-116">Section index:</span></span>  <br/> |<span data-ttu-id="3c318-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="3c318-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="3c318-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="3c318-118">Row index:</span></span>  <br/> |<span data-ttu-id="3c318-119">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="3c318-119">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="3c318-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3c318-120">Cell index:</span></span>  <br/> |<span data-ttu-id="3c318-121">**visLineGradientEnabled**</span><span class="sxs-lookup"><span data-stu-id="3c318-121">**visLineGradientEnabled**</span></span> <br/> |
   

