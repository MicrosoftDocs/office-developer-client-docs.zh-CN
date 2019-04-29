---
title: ShapeShdwShow 单元格 ("填充格式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ece6c889-9291-40ea-b55a-072acdcb8a52
description: 确定形状是否显示阴影, 以从0到2的整数。
ms.openlocfilehash: 1da52c20acaa19eab79970a751fad2c225e212ae
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422115"
---
# <a name="shapeshdwshow-cell-fill-format-section"></a><span data-ttu-id="eedf5-103">ShapeShdwShow 单元格 ("填充格式" 部分)</span><span class="sxs-lookup"><span data-stu-id="eedf5-103">ShapeShdwShow Cell (Fill Format Section)</span></span>

<span data-ttu-id="eedf5-104">确定形状是否显示阴影, 以从0到2的整数。</span><span class="sxs-lookup"><span data-stu-id="eedf5-104">Determines whether the shape displays a shadow, as an integer from 0 to 2.</span></span>
  
|<span data-ttu-id="eedf5-105">**值**</span><span class="sxs-lookup"><span data-stu-id="eedf5-105">**Value**</span></span>|<span data-ttu-id="eedf5-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="eedf5-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eedf5-107">0</span><span class="sxs-lookup"><span data-stu-id="eedf5-107">0</span></span>  <br/> |<span data-ttu-id="eedf5-108">如果指定了阴影, 则始终显示阴影。</span><span class="sxs-lookup"><span data-stu-id="eedf5-108">Always display the shadow if a shadow is specified.</span></span> <span data-ttu-id="eedf5-109">子形状的阴影不显示。</span><span class="sxs-lookup"><span data-stu-id="eedf5-109">The shadows for sub-shapes are not displayed.</span></span>  <br/> |
|<span data-ttu-id="eedf5-110">1</span><span class="sxs-lookup"><span data-stu-id="eedf5-110">1</span></span>  <br/> |<span data-ttu-id="eedf5-111">除非形状没有父级, 否则不要呈现阴影。</span><span class="sxs-lookup"><span data-stu-id="eedf5-111">Do not render a shadow unless the shape does not have a parent.</span></span> <span data-ttu-id="eedf5-112">如果组合在一起, 请使用子形状阴影。</span><span class="sxs-lookup"><span data-stu-id="eedf5-112">Use sub-shape shadows if grouped together.</span></span>  <br/> |
|<span data-ttu-id="eedf5-113">双面</span><span class="sxs-lookup"><span data-stu-id="eedf5-113">2</span></span>  <br/> |<span data-ttu-id="eedf5-114">如果指定了阴影, 则始终显示阴影。</span><span class="sxs-lookup"><span data-stu-id="eedf5-114">Always display a shadow if a shadow is specified.</span></span> <span data-ttu-id="eedf5-115">将显示子形状的阴影。</span><span class="sxs-lookup"><span data-stu-id="eedf5-115">The shadows for sub-shapes are displayed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eedf5-116">说明</span><span class="sxs-lookup"><span data-stu-id="eedf5-116">Remarks</span></span>

<span data-ttu-id="eedf5-117">若要从另一个公式按名称获取对**ShapeShdwShow**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="eedf5-117">To get a reference to the **ShapeShdwShow** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eedf5-118">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="eedf5-118">Cell name:</span></span>  <br/> | <span data-ttu-id="eedf5-119">ShapeShdwShow</span><span class="sxs-lookup"><span data-stu-id="eedf5-119">ShapeShdwShow</span></span>  <br/> |
   
<span data-ttu-id="eedf5-120">若要从某个程序按索引获取对**ShapeShdwShow**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="eedf5-120">To get a reference to the **ShapeShdwShow** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eedf5-121">内容索引：</span><span class="sxs-lookup"><span data-stu-id="eedf5-121">Section index:</span></span>  <br/> |<span data-ttu-id="eedf5-122">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="eedf5-122">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="eedf5-123">行索引：</span><span class="sxs-lookup"><span data-stu-id="eedf5-123">Row index:</span></span>  <br/> |<span data-ttu-id="eedf5-124">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="eedf5-124">**visRowFill**</span></span> <br/> |
| <span data-ttu-id="eedf5-125">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="eedf5-125">Cell index:</span></span>  <br/> |<span data-ttu-id="eedf5-126">**visFillShdwShow**</span><span class="sxs-lookup"><span data-stu-id="eedf5-126">**visFillShdwShow**</span></span> <br/> |
   

