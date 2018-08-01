---
title: TheText 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1005
localization_priority: Normal
ms.assetid: 2d63768e-afdb-4b3f-de49-f9ba69ae5391
description: 当形状文本或文本组成成分改变时进行求值的事件单元格。
ms.openlocfilehash: 942ccee4478c87243207d8d65785857758d2a068
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781517"
---
# <a name="thetext-cell-events-section"></a><span data-ttu-id="aaae4-103">TheText 单元格（“Events”部分）</span><span class="sxs-lookup"><span data-stu-id="aaae4-103">TheText Cell (Events Section)</span></span>

<span data-ttu-id="aaae4-104">当形状文本或文本组成成分改变时进行求值的事件单元格。</span><span class="sxs-lookup"><span data-stu-id="aaae4-104">An event cell that is evaluated when a shape's text or text composition changes.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="aaae4-105">注释</span><span class="sxs-lookup"><span data-stu-id="aaae4-105">Remarks</span></span>

<span data-ttu-id="aaae4-p101">只在事件发生后（而非输入公式后）才对事件单元格求值。您可以使用 TheText 单元格触发重新计算，例如，用 TEXTWIDTH( ) 和 TEXTHEIGHT( ) 函数重新计算文本宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="aaae4-p101">Event cells are evaluated only when the event occurs, not upon formula entry. You can use the TheText cell to trigger recalculations, for example, to recalculate the text width and height with the TEXTWIDTH( ) and TEXTHEIGHT( ) functions.</span></span>
  
<span data-ttu-id="aaae4-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TheText 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="aaae4-108">To get a reference to the TheText cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="aaae4-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="aaae4-109">Cell name:</span></span>  <br/> | <span data-ttu-id="aaae4-110">TheText</span><span class="sxs-lookup"><span data-stu-id="aaae4-110">TheText</span></span>  <br/> |
   
<span data-ttu-id="aaae4-111">要从某个程序按索引获取对 TheText 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="aaae4-111">To get a reference to the TheText cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="aaae4-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="aaae4-112">Section index:</span></span>  <br/> |<span data-ttu-id="aaae4-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="aaae4-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="aaae4-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="aaae4-114">Row index:</span></span>  <br/> |<span data-ttu-id="aaae4-115">**visRowEvent**</span><span class="sxs-lookup"><span data-stu-id="aaae4-115">**visRowEvent**</span></span> <br/> |
| <span data-ttu-id="aaae4-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="aaae4-116">Cell index:</span></span>  <br/> |<span data-ttu-id="aaae4-117">**visEvtCellTheText**</span><span class="sxs-lookup"><span data-stu-id="aaae4-117">**visEvtCellTheText**</span></span> <br/> |
   

