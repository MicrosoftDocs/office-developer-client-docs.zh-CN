---
title: 'ShapeShdwShow Cell (Fill Format Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ece6c889-9291-40ea-b55a-072acdcb8a52
description: 确定形状是否以 0 到 2 的整数显示阴影。
ms.openlocfilehash: 1da52c20acaa19eab79970a751fad2c225e212ae
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422115"
---
# <a name="shapeshdwshow-cell-fill-format-section"></a><span data-ttu-id="d48bd-103">ShapeShdwShow Cell (Fill Format Section) </span><span class="sxs-lookup"><span data-stu-id="d48bd-103">ShapeShdwShow Cell (Fill Format Section)</span></span>

<span data-ttu-id="d48bd-104">确定形状是否以 0 到 2 的整数显示阴影。</span><span class="sxs-lookup"><span data-stu-id="d48bd-104">Determines whether the shape displays a shadow, as an integer from 0 to 2.</span></span>
  
|<span data-ttu-id="d48bd-105">**值**</span><span class="sxs-lookup"><span data-stu-id="d48bd-105">**Value**</span></span>|<span data-ttu-id="d48bd-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="d48bd-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d48bd-107">0</span><span class="sxs-lookup"><span data-stu-id="d48bd-107">0</span></span>  <br/> |<span data-ttu-id="d48bd-108">如果指定阴影，则始终显示阴影。</span><span class="sxs-lookup"><span data-stu-id="d48bd-108">Always display the shadow if a shadow is specified.</span></span> <span data-ttu-id="d48bd-109">不显示子形状的阴影。</span><span class="sxs-lookup"><span data-stu-id="d48bd-109">The shadows for sub-shapes are not displayed.</span></span>  <br/> |
|<span data-ttu-id="d48bd-110">1</span><span class="sxs-lookup"><span data-stu-id="d48bd-110">1</span></span>  <br/> |<span data-ttu-id="d48bd-111">除非形状没有父形状，否则不要呈现阴影。</span><span class="sxs-lookup"><span data-stu-id="d48bd-111">Do not render a shadow unless the shape does not have a parent.</span></span> <span data-ttu-id="d48bd-112">如果组合在一起，请使用子形状阴影。</span><span class="sxs-lookup"><span data-stu-id="d48bd-112">Use sub-shape shadows if grouped together.</span></span>  <br/> |
|<span data-ttu-id="d48bd-113">2</span><span class="sxs-lookup"><span data-stu-id="d48bd-113">2</span></span>  <br/> |<span data-ttu-id="d48bd-114">如果指定阴影，则始终显示阴影。</span><span class="sxs-lookup"><span data-stu-id="d48bd-114">Always display a shadow if a shadow is specified.</span></span> <span data-ttu-id="d48bd-115">将显示子形状的阴影。</span><span class="sxs-lookup"><span data-stu-id="d48bd-115">The shadows for sub-shapes are displayed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d48bd-116">备注</span><span class="sxs-lookup"><span data-stu-id="d48bd-116">Remarks</span></span>

<span data-ttu-id="d48bd-117">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **ShapeShdwShow** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d48bd-117">To get a reference to the **ShapeShdwShow** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d48bd-118">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d48bd-118">Cell name:</span></span>  <br/> | <span data-ttu-id="d48bd-119">ShapeShdwShow</span><span class="sxs-lookup"><span data-stu-id="d48bd-119">ShapeShdwShow</span></span>  <br/> |
   
<span data-ttu-id="d48bd-120">若要从程序按索引获取对 **ShapeShdwShow** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d48bd-120">To get a reference to the **ShapeShdwShow** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d48bd-121">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d48bd-121">Section index:</span></span>  <br/> |<span data-ttu-id="d48bd-122">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d48bd-122">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="d48bd-123">行索引：</span><span class="sxs-lookup"><span data-stu-id="d48bd-123">Row index:</span></span>  <br/> |<span data-ttu-id="d48bd-124">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="d48bd-124">**visRowFill**</span></span> <br/> |
| <span data-ttu-id="d48bd-125">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d48bd-125">Cell index:</span></span>  <br/> |<span data-ttu-id="d48bd-126">**visFillShdwShow**</span><span class="sxs-lookup"><span data-stu-id="d48bd-126">**visFillShdwShow**</span></span> <br/> |
   

