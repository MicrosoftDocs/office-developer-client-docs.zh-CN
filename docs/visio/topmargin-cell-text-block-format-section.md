---
title: TopMargin 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1015
localization_priority: Normal
ms.assetid: c599b444-4d0e-a855-b04b-dd9dcaedf263
description: 确定文本块的上边界和它包含的第一行文本之间的距离。默认值是 4.0000 磅。此值与绘图比例无关。即使对绘图比例进行了调整，上边距仍保持不变。
ms.openlocfilehash: 97d349fd4ddc3c76cda61e1ee7ce25909161e6fa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280922"
---
# <a name="topmargin-cell-text-block-format-section"></a><span data-ttu-id="55a49-106">TopMargin 单元格（“Text Block Format”内容）</span><span class="sxs-lookup"><span data-stu-id="55a49-106">TopMargin Cell (Text Block Format Section)</span></span>

<span data-ttu-id="55a49-p102">确定文本块的上边界和它包含的第一行文本之间的距离。默认值是 4.0000 磅。此值与绘图比例无关。即使对绘图比例进行了调整，上边距仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="55a49-p102">Determines the distance between the top border of the text block and the first line of text it contains. The default is 4.0000 point. This value is independent of the scale of the drawing. If the drawing is scaled, the top margin remains the same.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="55a49-111">注解</span><span class="sxs-lookup"><span data-stu-id="55a49-111">Remarks</span></span>

<span data-ttu-id="55a49-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TopMargin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="55a49-112">To get a reference to the TopMargin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="55a49-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="55a49-113">Cell name:</span></span>  <br/> | <span data-ttu-id="55a49-114">TopMargin</span><span class="sxs-lookup"><span data-stu-id="55a49-114">TopMargin</span></span>  <br/> |
   
<span data-ttu-id="55a49-115">要从某个程序按索引获取对 TopMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="55a49-115">To get a reference to the TopMargin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="55a49-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="55a49-116">Section index:</span></span>  <br/> |<span data-ttu-id="55a49-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="55a49-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="55a49-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="55a49-118">Row index:</span></span>  <br/> |<span data-ttu-id="55a49-119">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="55a49-119">**visRowText**</span></span> <br/> |
| <span data-ttu-id="55a49-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="55a49-120">Cell index:</span></span>  <br/> |<span data-ttu-id="55a49-121">**visTxtBlkTopMargin**</span><span class="sxs-lookup"><span data-stu-id="55a49-121">**visTxtBlkTopMargin**</span></span> <br/> |
   

