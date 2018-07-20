---
title: TextBkgndTrans 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253240
localization_priority: Normal
ms.assetid: b2f9d317-cc42-bec5-66f9-f988bcbdcc24
description: 确定形状的文本块背景色的透明度级别。
ms.openlocfilehash: d9fee430cb2ccd19e8d6069e7561a8fef409a62e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781497"
---
# <a name="textbkgndtrans-cell-text-block-format-section"></a><span data-ttu-id="cd907-103">TextBkgndTrans 单元格（“Text Block Format”内容）</span><span class="sxs-lookup"><span data-stu-id="cd907-103">TextBkgndTrans Cell (Text Block Format Section)</span></span>

<span data-ttu-id="cd907-104">确定形状的文本块背景色的透明度级别。</span><span class="sxs-lookup"><span data-stu-id="cd907-104">Determines the transparency level for the background color of the shape's text block.</span></span>
  
|<span data-ttu-id="cd907-105">**值**</span><span class="sxs-lookup"><span data-stu-id="cd907-105">**Value**</span></span>|<span data-ttu-id="cd907-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="cd907-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cd907-107">0-100</span><span class="sxs-lookup"><span data-stu-id="cd907-107">0 - 100</span></span>  <br/> |<span data-ttu-id="cd907-p101">表示透明度的百分比。默认值为 0%（完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="cd907-p101">Represents the percentage of transparency. The default is 0% (completely opaque).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cd907-110">注解</span><span class="sxs-lookup"><span data-stu-id="cd907-110">Remarks</span></span>

<span data-ttu-id="cd907-p102">这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然文本背景完全透明的形状在绘图页上看起来和没有文本背景的形状相同，但是它与该页上其他对象的交互方式和透明度为 0% 的形状相同。</span><span class="sxs-lookup"><span data-stu-id="cd907-p102">Values are rounded to the nearest half percent. A value of 100% is completely transparent. Although a shape that has a completely transparent text background appears the same on the drawing page as a shape that has no text background, it interacts with other objects on the page in the same way as if its transparency were 0%.</span></span>
  
<span data-ttu-id="cd907-114">您还可以设置此值使用**文本**对话框的**字体**选项卡上的滑块控件 （在**主页**选项卡上，单击**字体**箭头）。</span><span class="sxs-lookup"><span data-stu-id="cd907-114">You can also set this value using the slider control on the **Font** tab of the **Text** dialog box (on the **Home** tab, click the **Font** arrow).</span></span> 
  
<span data-ttu-id="cd907-115">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TextBkgndTrans 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cd907-115">To get a reference to the TextBkgndTrans cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cd907-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cd907-116">Cell name:</span></span>  <br/> |<span data-ttu-id="cd907-117">TextBkgndTrans</span><span class="sxs-lookup"><span data-stu-id="cd907-117">TextBkgndTrans</span></span>  <br/> |
   
<span data-ttu-id="cd907-118">若要从某个程序按索引获取对 TextBkgndTrans 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="cd907-118">To get a reference to the TextBkgndTrans cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cd907-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cd907-119">Section index:</span></span>  <br/> |<span data-ttu-id="cd907-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="cd907-120">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="cd907-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="cd907-121">Row index:</span></span>  <br/> |<span data-ttu-id="cd907-122">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="cd907-122">**visRowText**</span></span> <br/> |
|<span data-ttu-id="cd907-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cd907-123">Cell index:</span></span>  <br/> |<span data-ttu-id="cd907-124">**visTxtBlkBkgndTrans**</span><span class="sxs-lookup"><span data-stu-id="cd907-124">**visTxtBlkBkgndTrans**</span></span> <br/> |
   
