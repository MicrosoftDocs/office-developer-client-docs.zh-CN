---
title: IndLeft 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251255
localization_priority: Normal
ms.assetid: 31a7d0d4-4666-ddef-c5eb-4d13803e6a2f
description: 代表段落中所有文本行自该文本块的左边距始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，左缩进仍保持不变。
ms.openlocfilehash: 2ccccfdeacc73539c612790613c7eca85de55b34
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780447"
---
# <a name="indleft-cell-paragraph-section"></a><span data-ttu-id="dafeb-105">IndLeft 单元格（“Paragraph”部分）</span><span class="sxs-lookup"><span data-stu-id="dafeb-105">IndLeft Cell (Paragraph Section)</span></span>

<span data-ttu-id="dafeb-p102">代表段落中所有文本行自该文本块的左边距始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，左缩进仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="dafeb-p102">Represents the distance all lines of text in a paragraph are indented from the left margin of the text block. This value is independent of the scale of the drawing. If the drawing is scaled, the left indent remains the same.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="dafeb-109">注释</span><span class="sxs-lookup"><span data-stu-id="dafeb-109">Remarks</span></span>

<span data-ttu-id="dafeb-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 IndLeft 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="dafeb-110">To get a reference to the IndLeft cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dafeb-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="dafeb-111">Cell name:</span></span>  <br/> | <span data-ttu-id="dafeb-112">Para.IndLeft [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="dafeb-112">Para.IndLeft[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="dafeb-113">要从某个程序按索引获取对 IndLeft 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="dafeb-113">To get a reference to the IndLeft cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dafeb-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="dafeb-114">Section index:</span></span>  <br/> |<span data-ttu-id="dafeb-115">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="dafeb-115">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="dafeb-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="dafeb-116">Row index:</span></span>  <br/> |<span data-ttu-id="dafeb-117">**visRowParagraph** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="dafeb-117">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="dafeb-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="dafeb-118">Cell index:</span></span>  <br/> |<span data-ttu-id="dafeb-119">**visIndentLeft**</span><span class="sxs-lookup"><span data-stu-id="dafeb-119">**visIndentLeft**</span></span> <br/> |
   

