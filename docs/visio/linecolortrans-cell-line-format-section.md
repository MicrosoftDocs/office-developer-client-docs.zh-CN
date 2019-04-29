---
title: LineColorTrans 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50120
localization_priority: Normal
ms.assetid: b68054b5-7efd-1156-9dc1-5ec94e18d227
description: 确定形状的线条颜色的透明度级别。
ms.openlocfilehash: 555ea15de0279a37bcf67de7374d922b8692ce02
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414436"
---
# <a name="linecolortrans-cell-line-format-section"></a><span data-ttu-id="def36-103">LineColorTrans 单元格（“Line Format”内容）</span><span class="sxs-lookup"><span data-stu-id="def36-103">LineColorTrans Cell (Line Format Section)</span></span>

<span data-ttu-id="def36-104">确定形状的线条颜色的透明度级别。</span><span class="sxs-lookup"><span data-stu-id="def36-104">Determines the transparency level of a shape's line color.</span></span>
  
|<span data-ttu-id="def36-105">**值**</span><span class="sxs-lookup"><span data-stu-id="def36-105">**Value**</span></span>|<span data-ttu-id="def36-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="def36-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="def36-107">0 - 100</span><span class="sxs-lookup"><span data-stu-id="def36-107">0 - 100</span></span>  <br/> |<span data-ttu-id="def36-p101">表示透明度的百分比。默认值为 0%（完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="def36-p101">Represents the percentage of transparency. The default is 0% (completely opaque).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="def36-110">说明</span><span class="sxs-lookup"><span data-stu-id="def36-110">Remarks</span></span>

<span data-ttu-id="def36-p102">这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然线条颜色完全透明的形状在绘图页上看起来和没有线条的形状相同，但是它与该页上其他对象的交互方式和透明度为 0% 的形状相同。</span><span class="sxs-lookup"><span data-stu-id="def36-p102">Values are rounded to the nearest half percent. A value of 100% is completely transparent. Although a shape with a completely transparent line color appears the same as a shape with no lines on the drawing page, it will interact with other objects on the page in the same ways as if its transparency is 0%.</span></span> 
  
<span data-ttu-id="def36-114">还可以使用 **“线条”** 对话框中的滑块控件设置此值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“粗细”**，然后单击 **“其他线条”**）。</span><span class="sxs-lookup"><span data-stu-id="def36-114">You can also set this value by using the slider control in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Weight**, and then click **More Lines**).</span></span>
  
<span data-ttu-id="def36-115">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineColorTrans 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="def36-115">To get a reference to the LineColorTrans cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="def36-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="def36-116">Cell name:</span></span>  <br/> |<span data-ttu-id="def36-117">LineColorTrans</span><span class="sxs-lookup"><span data-stu-id="def36-117">LineColorTrans</span></span>  <br/> |
   
<span data-ttu-id="def36-118">若要从某个程序按索引获取对 LineColorTrans 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="def36-118">To get a reference to the LineColorTrans cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="def36-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="def36-119">Section index:</span></span>  <br/> |<span data-ttu-id="def36-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="def36-120">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="def36-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="def36-121">Row index:</span></span>  <br/> |<span data-ttu-id="def36-122">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="def36-122">**visRowLine**</span></span> <br/> |
|<span data-ttu-id="def36-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="def36-123">Cell index:</span></span>  <br/> |<span data-ttu-id="def36-124">**visLineColorTrans**</span><span class="sxs-lookup"><span data-stu-id="def36-124">**visLineColorTrans**</span></span> <br/> |
   

