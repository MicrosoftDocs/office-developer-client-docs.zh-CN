---
title: IndFirst 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251254
localization_priority: Normal
ms.assetid: 0f2e362a-3ace-787d-6326-b5bf707f0727
description: 代表形状的文本块中每个段落的首行自该段落的左缩进始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，首行缩进仍保持不变。
ms.openlocfilehash: 03c34a0ccd1681d3523d743ebfc34af7b9dcfa87
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780438"
---
# <a name="indfirst-cell-paragraph-section"></a><span data-ttu-id="d8904-105">IndFirst 单元格（“Paragraph”部分）</span><span class="sxs-lookup"><span data-stu-id="d8904-105">IndFirst Cell (Paragraph Section)</span></span>

<span data-ttu-id="d8904-p102">代表形状的文本块中每个段落的首行自该段落的左缩进始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，首行缩进仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="d8904-p102">Represents the distance the first line of each paragraph in the shape's text block is indented from the left indent of the paragraph. This value is independent of the scale of the drawing. If the drawing is scaled, the first line indent remains the same.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d8904-109">注释</span><span class="sxs-lookup"><span data-stu-id="d8904-109">Remarks</span></span>

<span data-ttu-id="d8904-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 IndFirst 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d8904-110">To get a reference to the IndFirst cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d8904-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d8904-111">Cell name:</span></span>  <br/> | <span data-ttu-id="d8904-112">Para.IndFirst [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="d8904-112">Para.IndFirst[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="d8904-113">要从某个程序按索引获取对 IndFirst 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d8904-113">To get a reference to the IndFirst cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d8904-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d8904-114">Section index:</span></span>  <br/> |<span data-ttu-id="d8904-115">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="d8904-115">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="d8904-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="d8904-116">Row index:</span></span>  <br/> |<span data-ttu-id="d8904-117">**visRowParagraph** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="d8904-117">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="d8904-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d8904-118">Cell index:</span></span>  <br/> |<span data-ttu-id="d8904-119">**visIndentFirst**</span><span class="sxs-lookup"><span data-stu-id="d8904-119">**visIndentFirst**</span></span> <br/> |
   

