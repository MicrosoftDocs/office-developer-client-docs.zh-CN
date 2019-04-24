---
title: BottomMargin 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm120
localization_priority: Normal
ms.assetid: 3121911b-34d5-d99c-3806-76f6e2824f92
description: 确定文本块的下边框和所包含文本的最后一行之间的距离。默认值是 0.1 英寸。此值与绘图比例无关。即使绘图比例进行调整，下边距也保持不变。
ms.openlocfilehash: 544557f1e797315619bc9975db0b87a09981726c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338085"
---
# <a name="bottommargin-cell-text-block-format-section"></a><span data-ttu-id="54879-106">BottomMargin 单元格（“Text Block Format”内容）</span><span class="sxs-lookup"><span data-stu-id="54879-106">BottomMargin Cell (Text Block Format Section)</span></span>

<span data-ttu-id="54879-p102">确定文本块的下边框和所包含文本的最后一行之间的距离。默认值是 0.1 英寸。此值与绘图比例无关。即使绘图比例进行调整，下边距也保持不变。</span><span class="sxs-lookup"><span data-stu-id="54879-p102">Determines the distance between the bottom border of the text block and the last line of text it contains. The default is 0.1 inch. This value is independent of the scale of the drawing. If the drawing is scaled, the bottom margin remains the same.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="54879-111">注解</span><span class="sxs-lookup"><span data-stu-id="54879-111">Remarks</span></span>

<span data-ttu-id="54879-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BottomMargin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="54879-112">To get a reference to the BottomMargin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="54879-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="54879-113">Cell name:</span></span>  <br/> | <span data-ttu-id="54879-114">BottomMargin</span><span class="sxs-lookup"><span data-stu-id="54879-114">BottomMargin</span></span>  <br/> |
   
<span data-ttu-id="54879-115">要从某个程序按索引获取对 BottomMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="54879-115">To get a reference to the BottomMargin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="54879-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="54879-116">Section index:</span></span>  <br/> |<span data-ttu-id="54879-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="54879-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="54879-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="54879-118">Row index:</span></span>  <br/> |<span data-ttu-id="54879-119">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="54879-119">**visRowText**</span></span> <br/> |
| <span data-ttu-id="54879-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="54879-120">Cell index:</span></span>  <br/> |<span data-ttu-id="54879-121">**visTxtBlkBottomMargin**</span><span class="sxs-lookup"><span data-stu-id="54879-121">**visTxtBlkBottomMargin**</span></span> <br/> |
   

