---
title: RightMargin 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251266
localization_priority: Normal
ms.assetid: bc8f5469-e79f-4a68-73cb-d11c938353a4
description: 确定文本块的右边框和它所包含的文本之间的距离。默认值是 0.1 英寸。
ms.openlocfilehash: 57fdb320395a9a6562983a0148b37c4a70a9a9b6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781105"
---
# <a name="rightmargin-cell-text-block-format-section"></a><span data-ttu-id="40903-104">RightMargin 单元格（“Text Block Format”部分）</span><span class="sxs-lookup"><span data-stu-id="40903-104">RightMargin Cell (Text Block Format Section)</span></span>

<span data-ttu-id="40903-p102">确定文本块的右边框和它所包含的文本之间的距离。默认值是 0.1 英寸。</span><span class="sxs-lookup"><span data-stu-id="40903-p102">Determines the distance between the right border of the text block and the text it contains. The default is 0.1 inch.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="40903-107">注释</span><span class="sxs-lookup"><span data-stu-id="40903-107">Remarks</span></span>

<span data-ttu-id="40903-p103">此值与绘图比例无关。即使绘图比例进行调整，右边距仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="40903-p103">This value is independent of the scale of the drawing. If the drawing is scaled, the right margin remains the same.</span></span>
  
<span data-ttu-id="40903-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 RightMargin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="40903-110">To get a reference to the RightMargin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="40903-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="40903-111">Cell name:</span></span>  <br/> | <span data-ttu-id="40903-112">RightMargin</span><span class="sxs-lookup"><span data-stu-id="40903-112">RightMargin</span></span>  <br/> |
   
<span data-ttu-id="40903-113">要从某个程序按索引获取对 RightMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="40903-113">To get a reference to the RightMargin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="40903-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="40903-114">Section index:</span></span>  <br/> |<span data-ttu-id="40903-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="40903-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="40903-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="40903-116">Row index:</span></span>  <br/> |<span data-ttu-id="40903-117">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="40903-117">**visRowText**</span></span> <br/> |
| <span data-ttu-id="40903-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="40903-118">Cell index:</span></span>  <br/> |<span data-ttu-id="40903-119">**visTxtBlkRightMargin**</span><span class="sxs-lookup"><span data-stu-id="40903-119">**visTxtBlkRightMargin**</span></span> <br/> |
   

