---
title: LeftMargin 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251265
localization_priority: Normal
ms.assetid: 47d84d7d-08a0-1934-d156-702da848e01c
description: 确定文本块左边框和它所包含的文本之间的距离。默认值是 0.1 英寸。此值与绘图比例无关。即使绘图比例进行调整，左边距仍保持不变。
ms.openlocfilehash: fee8eca8b5730e40518babe0c76549e10bebd902
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359386"
---
# <a name="leftmargin-cell-text-block-format-section"></a><span data-ttu-id="74e4d-106">LeftMargin 单元格（“Text Block Format”内容）</span><span class="sxs-lookup"><span data-stu-id="74e4d-106">LeftMargin Cell (Text Block Format Section)</span></span>

<span data-ttu-id="74e4d-p102">确定文本块左边框和它所包含的文本之间的距离。默认值是 0.1 英寸。此值与绘图比例无关。即使绘图比例进行调整，左边距仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="74e4d-p102">Determines the distance between the left border of the text block and the text it contains. The default is 0.1 inch. This value is independent of the scale of the drawing. If the drawing is scaled, the left margin remains the same.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="74e4d-111">注解</span><span class="sxs-lookup"><span data-stu-id="74e4d-111">Remarks</span></span>

<span data-ttu-id="74e4d-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LeftMargin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="74e4d-112">To get a reference to the LeftMargin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="74e4d-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="74e4d-113">Cell name:</span></span>  <br/> | <span data-ttu-id="74e4d-114">LeftMargin</span><span class="sxs-lookup"><span data-stu-id="74e4d-114">LeftMargin</span></span>  <br/> |
   
<span data-ttu-id="74e4d-115">要从某个程序按索引获取对 LeftMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="74e4d-115">To get a reference to the LeftMargin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="74e4d-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="74e4d-116">Section index:</span></span>  <br/> |<span data-ttu-id="74e4d-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="74e4d-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="74e4d-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="74e4d-118">Row index:</span></span>  <br/> |<span data-ttu-id="74e4d-119">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="74e4d-119">**visRowText**</span></span> <br/> |
| <span data-ttu-id="74e4d-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="74e4d-120">Cell index:</span></span>  <br/> |<span data-ttu-id="74e4d-121">**visTxtBlkLeftMargin**</span><span class="sxs-lookup"><span data-stu-id="74e4d-121">**visTxtBlkLeftMargin**</span></span> <br/> |
   

