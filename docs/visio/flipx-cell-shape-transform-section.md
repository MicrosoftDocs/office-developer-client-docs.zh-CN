---
title: FlipX 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251197
localization_priority: Normal
ms.assetid: 8d4f5e14-4f17-05a6-4092-5a102c9dc85f
description: 指出形状是否已经水平翻转。
ms.openlocfilehash: fc014ff6c5a3650361d6afd478a5858f84fb5c47
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780281"
---
# <a name="flipx-cell-shape-transform-section"></a><span data-ttu-id="e4481-103">FlipX 单元格（“Shape Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="e4481-103">FlipX Cell (Shape Transform Section)</span></span>

<span data-ttu-id="e4481-104">指出形状是否已经水平翻转。</span><span class="sxs-lookup"><span data-stu-id="e4481-104">Indicates whether the shape has been flipped horizontally.</span></span>
  
|<span data-ttu-id="e4481-105">**值**</span><span class="sxs-lookup"><span data-stu-id="e4481-105">**Value**</span></span>|<span data-ttu-id="e4481-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="e4481-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e4481-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="e4481-107">TRUE</span></span>  <br/> | <span data-ttu-id="e4481-108">形状已经水平翻转。</span><span class="sxs-lookup"><span data-stu-id="e4481-108">The shape has been flipped horizontally.</span></span>  <br/> |
| <span data-ttu-id="e4481-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="e4481-109">FALSE</span></span>  <br/> | <span data-ttu-id="e4481-110">形状尚未水平翻转。</span><span class="sxs-lookup"><span data-stu-id="e4481-110">The shape has not been flipped horizontally.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e4481-111">注释</span><span class="sxs-lookup"><span data-stu-id="e4481-111">Remarks</span></span>

<span data-ttu-id="e4481-112">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 FlipX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e4481-112">To get a reference to the FlipX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e4481-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e4481-113">Cell name:</span></span>  <br/> | <span data-ttu-id="e4481-114">FlipX</span><span class="sxs-lookup"><span data-stu-id="e4481-114">FlipX</span></span>  <br/> |
   
<span data-ttu-id="e4481-115">若要从某个程序按索引获取对 FlipX 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="e4481-115">To get a reference to the FlipX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e4481-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e4481-116">Section index:</span></span>  <br/> |<span data-ttu-id="e4481-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e4481-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="e4481-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="e4481-118">Row index:</span></span>  <br/> |<span data-ttu-id="e4481-119">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="e4481-119">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="e4481-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e4481-120">Cell index:</span></span>  <br/> |<span data-ttu-id="e4481-121">**visXFormFlipX**</span><span class="sxs-lookup"><span data-stu-id="e4481-121">**visXFormFlipX**</span></span> <br/> |
   

