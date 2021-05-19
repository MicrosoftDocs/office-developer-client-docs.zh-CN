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
ms.openlocfilehash: b7a4a15e5a7759eddcda3ec391a81f14df545691
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415948"
---
# <a name="flipx-cell-shape-transform-section"></a><span data-ttu-id="b43b4-103">FlipX 单元格（“Shape Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="b43b4-103">FlipX Cell (Shape Transform Section)</span></span>

<span data-ttu-id="b43b4-104">指出形状是否已经水平翻转。</span><span class="sxs-lookup"><span data-stu-id="b43b4-104">Indicates whether the shape has been flipped horizontally.</span></span>
  
|<span data-ttu-id="b43b4-105">**值**</span><span class="sxs-lookup"><span data-stu-id="b43b4-105">**Value**</span></span>|<span data-ttu-id="b43b4-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="b43b4-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="b43b4-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="b43b4-107">TRUE</span></span>  <br/> | <span data-ttu-id="b43b4-108">形状已经水平翻转。</span><span class="sxs-lookup"><span data-stu-id="b43b4-108">The shape has been flipped horizontally.</span></span>  <br/> |
| <span data-ttu-id="b43b4-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="b43b4-109">FALSE</span></span>  <br/> | <span data-ttu-id="b43b4-110">形状尚未水平翻转。</span><span class="sxs-lookup"><span data-stu-id="b43b4-110">The shape has not been flipped horizontally.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b43b4-111">备注</span><span class="sxs-lookup"><span data-stu-id="b43b4-111">Remarks</span></span>

<span data-ttu-id="b43b4-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 FlipX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b43b4-112">To get a reference to the FlipX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b43b4-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b43b4-113">Cell name:</span></span>  <br/> | <span data-ttu-id="b43b4-114">FlipX</span><span class="sxs-lookup"><span data-stu-id="b43b4-114">FlipX</span></span>  <br/> |
   
<span data-ttu-id="b43b4-115">要从某个程序按索引获取对 FlipX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="b43b4-115">To get a reference to the FlipX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b43b4-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b43b4-116">Section index:</span></span>  <br/> |<span data-ttu-id="b43b4-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b43b4-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="b43b4-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="b43b4-118">Row index:</span></span>  <br/> |<span data-ttu-id="b43b4-119">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="b43b4-119">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="b43b4-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b43b4-120">Cell index:</span></span>  <br/> |<span data-ttu-id="b43b4-121">**visXFormFlipX**</span><span class="sxs-lookup"><span data-stu-id="b43b4-121">**visXFormFlipX**</span></span> <br/> |
   

