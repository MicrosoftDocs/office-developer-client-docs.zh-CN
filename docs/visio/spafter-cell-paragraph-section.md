---
title: SpAfter 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm960
localization_priority: Normal
ms.assetid: 2dd56ae5-300e-ba09-a73a-83c2b6c2a0ef
description: 确定除了在 SpLine 单元格（如果段落为文本块的最后一段，则由 BottomMargin 单元格指定）中指定的任何空间量外还需要在形状的文本块中每个段落后插入的空间量。
ms.openlocfilehash: 93db93e58124b5f176fb57f843580eff6a3d4d3e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781442"
---
# <a name="spafter-cell-paragraph-section"></a><span data-ttu-id="c4315-103">SpAfter 单元格（“Paragraph”内容）</span><span class="sxs-lookup"><span data-stu-id="c4315-103">SpAfter Cell (Paragraph Section)</span></span>

<span data-ttu-id="c4315-104">确定除了在 SpLine 单元格（如果段落为文本块的最后一段，则由 BottomMargin 单元格指定）中指定的任何空间量外还需要在形状的文本块中每个段落后插入的空间量。</span><span class="sxs-lookup"><span data-stu-id="c4315-104">Determines the amount of space inserted after each paragraph in the shape's text block, in addition to any space from the SpLine cell and, if it is the last paragraph in a text block, the BottomMargin cell.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c4315-105">注释</span><span class="sxs-lookup"><span data-stu-id="c4315-105">Remarks</span></span>

<span data-ttu-id="c4315-p101">此值与绘图比例无关。即使绘图比例进行调整，“段后空间”设置仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="c4315-p101">This value is independent of the scale of the drawing. If the drawing is scaled, the Space After setting remains the same.</span></span>
  
<span data-ttu-id="c4315-108">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 SpAfter 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c4315-108">To get a reference to the SpAfter cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c4315-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c4315-109">Cell name:</span></span>  <br/> | <span data-ttu-id="c4315-110">Para.SpAfter [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="c4315-110">Para.SpAfter[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="c4315-111">若要从某个程序按索引获取对 SpAfter 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="c4315-111">To get a reference to the SpAfter cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c4315-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c4315-112">Section index:</span></span>  <br/> |<span data-ttu-id="c4315-113">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="c4315-113">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="c4315-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="c4315-114">Row index:</span></span>  <br/> |<span data-ttu-id="c4315-115">**visRowParagraph** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="c4315-115">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="c4315-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c4315-116">Cell index:</span></span>  <br/> |<span data-ttu-id="c4315-117">**visSpaceAfter**</span><span class="sxs-lookup"><span data-stu-id="c4315-117">**visSpaceAfter**</span></span> <br/> |
   

