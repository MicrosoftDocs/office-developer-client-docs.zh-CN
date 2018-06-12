---
title: ShapeShdwShow 单元格 （Fill Format 内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ece6c889-9291-40ea-b55a-072acdcb8a52
description: 确定形状是否将阴影，显示为从 0 到 2 的整数。
ms.openlocfilehash: 72077e60089acd3cd3f8a9349691e1468f6b1f9c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781290"
---
# <a name="shapeshdwshow-cell-fill-format-section"></a><span data-ttu-id="66456-103">ShapeShdwShow 单元格 （Fill Format 内容）</span><span class="sxs-lookup"><span data-stu-id="66456-103">ShapeShdwShow Cell (Fill Format Section)</span></span>

<span data-ttu-id="66456-104">确定形状是否将阴影，显示为从 0 到 2 的整数。</span><span class="sxs-lookup"><span data-stu-id="66456-104">Determines whether the shape displays a shadow, as an integer from 0 to 2.</span></span>
  
|<span data-ttu-id="66456-105">**值**</span><span class="sxs-lookup"><span data-stu-id="66456-105">**Value**</span></span>|<span data-ttu-id="66456-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="66456-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66456-107">0</span><span class="sxs-lookup"><span data-stu-id="66456-107">0</span></span>  <br/> |<span data-ttu-id="66456-108">如果指定阴影，始终显示阴影。</span><span class="sxs-lookup"><span data-stu-id="66456-108">Always display the shadow if a shadow is specified.</span></span> <span data-ttu-id="66456-109">不显示的子形状阴影。</span><span class="sxs-lookup"><span data-stu-id="66456-109">The shadows for sub-shapes are not displayed.</span></span>  <br/> |
|<span data-ttu-id="66456-110">1</span><span class="sxs-lookup"><span data-stu-id="66456-110">1</span></span>  <br/> |<span data-ttu-id="66456-111">除非形状没有父不呈现阴影。</span><span class="sxs-lookup"><span data-stu-id="66456-111">Do not render a shadow unless the shape does not have a parent.</span></span> <span data-ttu-id="66456-112">如果组合在一起，请使用子形状阴影。</span><span class="sxs-lookup"><span data-stu-id="66456-112">Use sub-shape shadows if grouped together.</span></span>  <br/> |
|<span data-ttu-id="66456-113">2</span><span class="sxs-lookup"><span data-stu-id="66456-113">2</span></span>  <br/> |<span data-ttu-id="66456-114">如果指定阴影，始终显示阴影。</span><span class="sxs-lookup"><span data-stu-id="66456-114">Always display a shadow if a shadow is specified.</span></span> <span data-ttu-id="66456-115">显示的子形状阴影。</span><span class="sxs-lookup"><span data-stu-id="66456-115">The shadows for sub-shapes are displayed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="66456-116">备注</span><span class="sxs-lookup"><span data-stu-id="66456-116">Remarks</span></span>

<span data-ttu-id="66456-117">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ShapeShdwShow**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="66456-117">To get a reference to the **ShapeShdwShow** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="66456-118">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="66456-118">Cell name:</span></span>  <br/> | <span data-ttu-id="66456-119">ShapeShdwShow</span><span class="sxs-lookup"><span data-stu-id="66456-119">ShapeShdwShow</span></span>  <br/> |
   
<span data-ttu-id="66456-120">若要从某个程序按索引获取对**ShapeShdwShow**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="66456-120">To get a reference to the **ShapeShdwShow** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="66456-121">内容索引：</span><span class="sxs-lookup"><span data-stu-id="66456-121">Section index:</span></span>  <br/> |<span data-ttu-id="66456-122">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="66456-122">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="66456-123">行索引：</span><span class="sxs-lookup"><span data-stu-id="66456-123">Row index:</span></span>  <br/> |<span data-ttu-id="66456-124">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="66456-124">**visRowFill**</span></span> <br/> |
| <span data-ttu-id="66456-125">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="66456-125">Cell index:</span></span>  <br/> |<span data-ttu-id="66456-126">**visFillShdwShow**</span><span class="sxs-lookup"><span data-stu-id="66456-126">**visFillShdwShow**</span></span> <br/> |
   

