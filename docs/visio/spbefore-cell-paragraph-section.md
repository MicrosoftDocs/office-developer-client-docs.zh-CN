---
title: SpBefore 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm965
localization_priority: Normal
ms.assetid: a7d5b0a1-3657-8211-f0e0-eaed588fa0bc
description: 确定除了在 SpLine 单元格（如果段落为文本块的第一个段落，则由 TopMargin 单元格指定）中指定的任何空间量外还需要在形状的文本块中每个段落前插入的空间量。
ms.openlocfilehash: d33a10220499020ba1a1acedf5782fdb78925c07
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781419"
---
# <a name="spbefore-cell-paragraph-section"></a><span data-ttu-id="983c5-103">SpBefore 单元格（“Paragraph”内容）</span><span class="sxs-lookup"><span data-stu-id="983c5-103">SpBefore Cell (Paragraph Section)</span></span>

<span data-ttu-id="983c5-104">确定除了在 SpLine 单元格（如果段落为文本块的第一个段落，则由 TopMargin 单元格指定）中指定的任何空间量外还需要在形状的文本块中每个段落前插入的空间量。</span><span class="sxs-lookup"><span data-stu-id="983c5-104">Determines the amount of space inserted before each paragraph in the shape's text block, in addition to any space from the SpLine cell if it is the first paragraph in a text block, the TopMargin cell.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="983c5-105">注释</span><span class="sxs-lookup"><span data-stu-id="983c5-105">Remarks</span></span>

<span data-ttu-id="983c5-p101">此值与绘图比例无关。即使绘图比例进行调整，“段前空间”设置仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="983c5-p101">This value is independent of the scale of the drawing. If the drawing is scaled, the Space Before setting remains the same.</span></span>
  
<span data-ttu-id="983c5-108">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 SpBefore 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="983c5-108">To get a reference to the SpBefore cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="983c5-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="983c5-109">Cell name:</span></span>  <br/> | <span data-ttu-id="983c5-110">Para.SpBefore [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="983c5-110">Para.SpBefore[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="983c5-111">若要从某个程序按索引获取对 SpBefore 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="983c5-111">To get a reference to the SpBefore cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="983c5-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="983c5-112">Section index:</span></span>  <br/> |<span data-ttu-id="983c5-113">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="983c5-113">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="983c5-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="983c5-114">Row index:</span></span>  <br/> |<span data-ttu-id="983c5-115">**visRowParagraph** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="983c5-115">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="983c5-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="983c5-116">Cell index:</span></span>  <br/> |<span data-ttu-id="983c5-117">**visSpaceBefore**</span><span class="sxs-lookup"><span data-stu-id="983c5-117">**visSpaceBefore**</span></span> <br/> |
   

