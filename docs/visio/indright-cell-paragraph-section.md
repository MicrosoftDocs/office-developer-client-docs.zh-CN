---
title: IndRight 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251256
localization_priority: Normal
ms.assetid: f0891064-95d9-ae1b-28f3-3aef1406b636
description: 代表段落中所有文本行自该文本块的右边距始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，右缩进仍保持不变。
ms.openlocfilehash: e6529bf41cb8fdd40371d9a663291961626afb56
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408864"
---
# <a name="indright-cell-paragraph-section"></a><span data-ttu-id="9c09c-105">IndRight 单元格（“Paragraph”内容）</span><span class="sxs-lookup"><span data-stu-id="9c09c-105">IndRight Cell (Paragraph Section)</span></span>

<span data-ttu-id="9c09c-p102">代表段落中所有文本行自该文本块的右边距始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，右缩进仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="9c09c-p102">Represents the distance all lines of text in a paragraph are indented from the right margin of the text block. This value is independent of the scale of the drawing. If the drawing is scaled, the right indent remains the same.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9c09c-109">备注</span><span class="sxs-lookup"><span data-stu-id="9c09c-109">Remarks</span></span>

<span data-ttu-id="9c09c-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 IndRight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9c09c-110">To get a reference to the IndRight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9c09c-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9c09c-111">Cell name:</span></span>  <br/> | <span data-ttu-id="9c09c-112">Para.IndRight[  *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="9c09c-112">Para.IndRight[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="9c09c-113">要从某个程序按索引获取对 IndRight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9c09c-113">To get a reference to the IndRight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9c09c-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9c09c-114">Section index:</span></span>  <br/> |<span data-ttu-id="9c09c-115">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="9c09c-115">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="9c09c-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="9c09c-116">Row index:</span></span>  <br/> |<span data-ttu-id="9c09c-117">**visRowParagraph**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="9c09c-117">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="9c09c-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9c09c-118">Cell index:</span></span>  <br/> |<span data-ttu-id="9c09c-119">**visIndentRight**</span><span class="sxs-lookup"><span data-stu-id="9c09c-119">**visIndentRight**</span></span> <br/> |
   

