---
title: Transparency 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50135
localization_priority: Normal
ms.assetid: ab835a1a-9e90-126e-279f-463882c48e93
description: 确定形状的某一范围文本颜色的透明度级别。
ms.openlocfilehash: 5914a061b1bba2173b338544b05abda8780ff164
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781541"
---
# <a name="transparency-cell-character-section"></a><span data-ttu-id="38bfc-103">Transparency 单元格（“Character”部分）</span><span class="sxs-lookup"><span data-stu-id="38bfc-103">Transparency Cell (Character Section)</span></span>

<span data-ttu-id="38bfc-104">确定形状的某一范围文本颜色的透明度级别。</span><span class="sxs-lookup"><span data-stu-id="38bfc-104">Determines the transparency level for a range of a shape's text color.</span></span>
  
|<span data-ttu-id="38bfc-105">**值**</span><span class="sxs-lookup"><span data-stu-id="38bfc-105">**Value**</span></span>|<span data-ttu-id="38bfc-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="38bfc-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38bfc-107">
          0 - 100
</span><span class="sxs-lookup"><span data-stu-id="38bfc-107">0 - 100</span></span>  <br/> |<span data-ttu-id="38bfc-p101">表示透明度的百分比。默认值为 0%（完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="38bfc-p101">Represents the percentage of transparency. The default is 0% (completely opaque).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="38bfc-110">注解</span><span class="sxs-lookup"><span data-stu-id="38bfc-110">Remarks</span></span>

<span data-ttu-id="38bfc-p102">这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然文本完全透明的形状在绘图页上看起来和没有文本的形状相同，但是它与该页上其他对象的交互方式与透明度为 0% 的形状相同。</span><span class="sxs-lookup"><span data-stu-id="38bfc-p102">Values are rounded to the nearest half percent. A value of 100% is completely transparent. Although a shape that has completely transparent text appears the same on the drawing page as a shape that has no text, it interacts with other objects on the page in the same way as if its transparency were 0%.</span></span>
  
<span data-ttu-id="38bfc-114">您还可以通过使用**文本**对话框中的**字体**选项卡上的滑块控件设置此值 （在**主页**选项卡上，单击**字体**箭头）。</span><span class="sxs-lookup"><span data-stu-id="38bfc-114">You can also set this value by using the slider control on the **Font** tab in the **Text** dialog box (on the **Home** tab, click the **Font** arrow).</span></span> 
  
<span data-ttu-id="38bfc-p103">如果“Characters”内容包含多行，则 Transparency 单元格包含应用于某形状文本的一个子范围的格式设置信息。否则，它就包含该形状的所有文本的格式设置信息。</span><span class="sxs-lookup"><span data-stu-id="38bfc-p103">If the Characters section contains multiple rows, the Transparency cell contains formatting information applied to a sub-range of a shape's text. Otherwise, it contains formatting information for all of the shape's text.</span></span>
  
<span data-ttu-id="38bfc-117">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Transparency 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="38bfc-117">To get a reference to the Transparency cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="38bfc-118">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="38bfc-118">Cell name:</span></span>  <br/> |<span data-ttu-id="38bfc-119">Char.ColorTrans [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="38bfc-119">Char.ColorTrans[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="38bfc-120">若要从某个程序按索引获取对 Transparency 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="38bfc-120">To get a reference to the Transparency cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="38bfc-121">内容索引：</span><span class="sxs-lookup"><span data-stu-id="38bfc-121">Section index:</span></span>  <br/> |<span data-ttu-id="38bfc-122">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="38bfc-122">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="38bfc-123">行索引：</span><span class="sxs-lookup"><span data-stu-id="38bfc-123">Row index:</span></span>  <br/> |<span data-ttu-id="38bfc-124">**visRowCharacter** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="38bfc-124">**visRowCharacter** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="38bfc-125">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="38bfc-125">Cell index:</span></span>  <br/> |<span data-ttu-id="38bfc-126">**visCharacterColorTrans**</span><span class="sxs-lookup"><span data-stu-id="38bfc-126">**visCharacterColorTrans**</span></span> <br/> |
   

