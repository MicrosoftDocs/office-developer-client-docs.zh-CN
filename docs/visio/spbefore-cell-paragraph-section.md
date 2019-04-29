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
ms.openlocfilehash: 9890910a11990bb5be7fe3ee4af95e578c8d9799
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425755"
---
# <a name="spbefore-cell-paragraph-section"></a><span data-ttu-id="fe76a-103">SpBefore 单元格（“Paragraph”内容）</span><span class="sxs-lookup"><span data-stu-id="fe76a-103">SpBefore Cell (Paragraph Section)</span></span>

<span data-ttu-id="fe76a-104">确定除了在 SpLine 单元格（如果段落为文本块的第一个段落，则由 TopMargin 单元格指定）中指定的任何空间量外还需要在形状的文本块中每个段落前插入的空间量。</span><span class="sxs-lookup"><span data-stu-id="fe76a-104">Determines the amount of space inserted before each paragraph in the shape's text block, in addition to any space from the SpLine cell if it is the first paragraph in a text block, the TopMargin cell.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fe76a-105">说明</span><span class="sxs-lookup"><span data-stu-id="fe76a-105">Remarks</span></span>

<span data-ttu-id="fe76a-p101">此值与绘图比例无关。即使绘图比例进行调整，“段前空间”设置仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="fe76a-p101">This value is independent of the scale of the drawing. If the drawing is scaled, the Space Before setting remains the same.</span></span>
  
<span data-ttu-id="fe76a-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 SpBefore 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="fe76a-108">To get a reference to the SpBefore cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="fe76a-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="fe76a-109">Cell name:</span></span>  <br/> | <span data-ttu-id="fe76a-110">SpBefore [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="fe76a-110">Para.SpBefore[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="fe76a-111">要从某个程序按索引获取对 SpBefore 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="fe76a-111">To get a reference to the SpBefore cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="fe76a-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="fe76a-112">Section index:</span></span>  <br/> |<span data-ttu-id="fe76a-113">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="fe76a-113">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="fe76a-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="fe76a-114">Row index:</span></span>  <br/> |<span data-ttu-id="fe76a-115">**visRowParagraph** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="fe76a-115">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="fe76a-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="fe76a-116">Cell index:</span></span>  <br/> |<span data-ttu-id="fe76a-117">**visSpaceBefore**</span><span class="sxs-lookup"><span data-stu-id="fe76a-117">**visSpaceBefore**</span></span> <br/> |
   

