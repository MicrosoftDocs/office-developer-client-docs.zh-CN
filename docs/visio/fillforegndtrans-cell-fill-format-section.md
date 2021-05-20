---
title: FillForegndTrans 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253231
localization_priority: Normal
ms.assetid: 8b1b3904-6635-3fd1-31a9-ff32c19394af
description: 确定形状的填充图案的前景（填充）颜色的透明度级别。
ms.openlocfilehash: d05a83f83ea3d95ac3d42a2bfb3996917119f580
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427848"
---
# <a name="fillforegndtrans-cell-fill-format-section"></a><span data-ttu-id="ec4a0-103">FillForegndTrans 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="ec4a0-103">FillForegndTrans Cell (Fill Format Section)</span></span>

<span data-ttu-id="ec4a0-104">确定形状的填充图案的前景（填充）颜色的透明度级别。</span><span class="sxs-lookup"><span data-stu-id="ec4a0-104">Determines the transparency level for the foreground (fill) color of the shape's fill pattern.</span></span>
  
|<span data-ttu-id="ec4a0-105">**值**</span><span class="sxs-lookup"><span data-stu-id="ec4a0-105">**Value**</span></span>|<span data-ttu-id="ec4a0-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="ec4a0-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec4a0-107">0 - 100</span><span class="sxs-lookup"><span data-stu-id="ec4a0-107">0 - 100</span></span>  <br/> |<span data-ttu-id="ec4a0-p101">表示透明度的百分比。默认值为 0%（完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="ec4a0-p101">Represents the percentage of transparency. The default is 0% (completely opaque).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ec4a0-110">备注</span><span class="sxs-lookup"><span data-stu-id="ec4a0-110">Remarks</span></span>

<span data-ttu-id="ec4a0-p102">这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然填充色完全透明的形状在绘图页上看起来和没有填充的形状相同，但是它与该页上其他对象的交互方式和透明度为 0% 的形状相同。</span><span class="sxs-lookup"><span data-stu-id="ec4a0-p102">Values are rounded to the nearest half percent. A value of 100% is completely transparent. Although a shape with a completely transparent fill appears the same as a shape with no fill on the drawing page, it will interact with other objects on the page in the same ways as if its transparency is 0%.</span></span>
  
<span data-ttu-id="ec4a0-p103">您还可以使用 **“填充”** 对话框中的滑块控件设置此值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“填充”**，然后单击 **“填充选项”**）。此值可以控制背景和前景填充透明度的值。若要单独设置上述值，必须在 ShapeSheet 窗口中输入它们。</span><span class="sxs-lookup"><span data-stu-id="ec4a0-p103">You can also set this value using the slider control in the **Fill** dialog box (on the **Home** tab, in the **Shape** group, click **Fill**, and then click **Fill Options**). This value controls the value of both the background and foreground fill transparencies. To set these values independently, you must enter them in the ShapeSheet window.</span></span>
  
<span data-ttu-id="ec4a0-117">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 FillForegndTrans 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ec4a0-117">To get a reference to the FillForegndTrans cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ec4a0-118">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ec4a0-118">Cell name:</span></span>  <br/> |<span data-ttu-id="ec4a0-119">FillForegndTrans</span><span class="sxs-lookup"><span data-stu-id="ec4a0-119">FillForegndTrans</span></span>  <br/> |
   
<span data-ttu-id="ec4a0-120">若要从某个程序按索引获取对 FillForegndTrans 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ec4a0-120">To get a reference to the FillForegndTrans cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ec4a0-121">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ec4a0-121">Section index:</span></span>  <br/> |<span data-ttu-id="ec4a0-122">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ec4a0-122">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="ec4a0-123">行索引：</span><span class="sxs-lookup"><span data-stu-id="ec4a0-123">Row index:</span></span>  <br/> |<span data-ttu-id="ec4a0-124">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="ec4a0-124">**visRowFill**</span></span> <br/> |
|<span data-ttu-id="ec4a0-125">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ec4a0-125">Cell index:</span></span>  <br/> |<span data-ttu-id="ec4a0-126">**visFillForegndTrans**</span><span class="sxs-lookup"><span data-stu-id="ec4a0-126">**visFillForegndTrans**</span></span> <br/> |
   

