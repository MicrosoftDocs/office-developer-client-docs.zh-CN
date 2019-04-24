---
title: FillGradientEnabled 单元格 ("渐变属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 80db9c0c-13c6-47de-967f-ade6e5899f14
description: 确定是否为此形状启用填充渐变。
ms.openlocfilehash: 17f617c13b632318be22b86a3354a194f0f835f5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322489"
---
# <a name="fillgradientenabled-cell-gradient-properties-section"></a><span data-ttu-id="16347-103">FillGradientEnabled 单元格 ("渐变属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="16347-103">FillGradientEnabled Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="16347-104">确定是否为此形状启用填充渐变。</span><span class="sxs-lookup"><span data-stu-id="16347-104">Determines whether a fill gradient is enabled for this shape.</span></span> 
  
|<span data-ttu-id="16347-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="16347-105">**Value**</span></span>|<span data-ttu-id="16347-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="16347-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="16347-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="16347-107">TRUE</span></span>  <br/> |<span data-ttu-id="16347-108">渐变填充将显示在形状上。</span><span class="sxs-lookup"><span data-stu-id="16347-108">Gradient fill is displayed on the shape.</span></span>  <br/> |
|<span data-ttu-id="16347-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="16347-109">FALSE</span></span>  <br/> |<span data-ttu-id="16347-110">渐变填充不会显示在形状上。</span><span class="sxs-lookup"><span data-stu-id="16347-110">Gradient fills are not displayed on the shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="16347-111">注解</span><span class="sxs-lookup"><span data-stu-id="16347-111">Remarks</span></span>

<span data-ttu-id="16347-112">若要从另一个公式按名称获取对**FillGradientEnabled**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="16347-112">To get a reference to the **FillGradientEnabled** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="16347-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="16347-113">Cell name:</span></span>  <br/> | <span data-ttu-id="16347-114">FillGradientEnabled</span><span class="sxs-lookup"><span data-stu-id="16347-114">FillGradientEnabled</span></span>  <br/> |
   
<span data-ttu-id="16347-115">若要从某个程序按索引获取对**FillGradientEnabled**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="16347-115">To get a reference to the **FillGradientEnabled** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="16347-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="16347-116">Section index:</span></span>  <br/> |<span data-ttu-id="16347-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="16347-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="16347-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="16347-118">Row index:</span></span>  <br/> |<span data-ttu-id="16347-119">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="16347-119">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="16347-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="16347-120">Cell index:</span></span>  <br/> |<span data-ttu-id="16347-121">\* \* visFillGradientEnabled \* \*</span><span class="sxs-lookup"><span data-stu-id="16347-121">\*\*visFillGradientEnabled \*\*</span></span> <br/> |
   

