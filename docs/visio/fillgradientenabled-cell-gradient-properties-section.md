---
title: FillGradientEnabled 单元格 （渐变 Properties 内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 80db9c0c-13c6-47de-967f-ade6e5899f14
description: 确定是否启用此形状填充渐变。
ms.openlocfilehash: 20a38d4c45af163bc00364a45dc31269bf97251f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780258"
---
# <a name="fillgradientenabled-cell-gradient-properties-section"></a><span data-ttu-id="becf9-103">FillGradientEnabled 单元格 （渐变 Properties 内容）</span><span class="sxs-lookup"><span data-stu-id="becf9-103">FillGradientEnabled Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="becf9-104">确定是否启用此形状填充渐变。</span><span class="sxs-lookup"><span data-stu-id="becf9-104">Determines whether a fill gradient is enabled for this shape.</span></span> 
  
|<span data-ttu-id="becf9-105">**值**</span><span class="sxs-lookup"><span data-stu-id="becf9-105">**Value**</span></span>|<span data-ttu-id="becf9-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="becf9-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="becf9-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="becf9-107">TRUE</span></span>  <br/> |<span data-ttu-id="becf9-108">渐变填充形状上显示。</span><span class="sxs-lookup"><span data-stu-id="becf9-108">Gradient fill is displayed on the shape.</span></span>  <br/> |
|<span data-ttu-id="becf9-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="becf9-109">FALSE</span></span>  <br/> |<span data-ttu-id="becf9-110">渐变填充形状上不显示。</span><span class="sxs-lookup"><span data-stu-id="becf9-110">Gradient fills are not displayed on the shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="becf9-111">备注</span><span class="sxs-lookup"><span data-stu-id="becf9-111">Remarks</span></span>

<span data-ttu-id="becf9-112">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**FillGradientEnabled**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="becf9-112">To get a reference to the **FillGradientEnabled** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="becf9-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="becf9-113">Cell name:</span></span>  <br/> | <span data-ttu-id="becf9-114">FillGradientEnabled</span><span class="sxs-lookup"><span data-stu-id="becf9-114">FillGradientEnabled</span></span>  <br/> |
   
<span data-ttu-id="becf9-115">若要从某个程序按索引获取对**FillGradientEnabled**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="becf9-115">To get a reference to the **FillGradientEnabled** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="becf9-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="becf9-116">Section index:</span></span>  <br/> |<span data-ttu-id="becf9-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="becf9-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="becf9-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="becf9-118">Row index:</span></span>  <br/> |<span data-ttu-id="becf9-119">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="becf9-119">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="becf9-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="becf9-120">Cell index:</span></span>  <br/> |<span data-ttu-id="becf9-121">* * visFillGradientEnabled * *</span><span class="sxs-lookup"><span data-stu-id="becf9-121">**visFillGradientEnabled **</span></span> <br/> |
   

