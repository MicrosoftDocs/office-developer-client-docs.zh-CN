---
title: Transparency 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm51095
localization_priority: Normal
ms.assetid: 5b265356-1602-4241-fbe1-4d5a55392a52
description: 确定图层颜色的透明度级别。
ms.openlocfilehash: defe5307e57c433fcf85a4132939d08cb1ddec77
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405833"
---
# <a name="transparency-cell-image-properties-section"></a><span data-ttu-id="e6b71-103">Transparency 单元格（“Image Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="e6b71-103">Transparency Cell (Image Properties Section)</span></span>

<span data-ttu-id="e6b71-104">确定图层颜色的透明度级别。</span><span class="sxs-lookup"><span data-stu-id="e6b71-104">Determines the transparency level for a layer color.</span></span>
  
|<span data-ttu-id="e6b71-105">**值**</span><span class="sxs-lookup"><span data-stu-id="e6b71-105">**Value**</span></span>|<span data-ttu-id="e6b71-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="e6b71-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6b71-107">0 - 100</span><span class="sxs-lookup"><span data-stu-id="e6b71-107">0 - 100</span></span>  <br/> |<span data-ttu-id="e6b71-p101">表示透明度的百分比。默认值为 0%（完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="e6b71-p101">Represents the percentage of transparency. The default is 0% (completely opaque).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6b71-110">说明</span><span class="sxs-lookup"><span data-stu-id="e6b71-110">Remarks</span></span>

<span data-ttu-id="e6b71-p102">这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然颜色完全透明的图层在绘图页上看起来和没有颜色的图层相同，但是它与该页上其他对象的交互方式和透明度为 0% 的形状相同。您还可以使用 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中的滑块控件设置此值。</span><span class="sxs-lookup"><span data-stu-id="e6b71-p102">Values are rounded to the nearest half percent. A value of 100% is completely transparent. Although a layer that has completely transparent color appears the same on the drawing page as a layer that has no color, it interacts with other objects on the page in the same way as if its transparency were 0%. You can also set this value by using the slider control in the **Layer Properties** dialog box (on the **Home** tab, in the **Editing** group, click **Layers**, and then click **Layer Properties**).</span></span>
  
<span data-ttu-id="e6b71-115">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Transparency 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e6b71-115">To get a reference to the Transparency cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6b71-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e6b71-116">Cell name:</span></span>  <br/> |<span data-ttu-id="e6b71-117">透明度</span><span class="sxs-lookup"><span data-stu-id="e6b71-117">Transparency</span></span>  <br/> |
   
<span data-ttu-id="e6b71-118">若要从某个程序按索引获取对 Transparency 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e6b71-118">To get a reference to the Transparency cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6b71-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e6b71-119">Section index:</span></span>  <br/> |<span data-ttu-id="e6b71-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e6b71-120">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="e6b71-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="e6b71-121">Row index:</span></span>  <br/> |<span data-ttu-id="e6b71-122">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="e6b71-122">**visRowImage**</span></span> <br/> |
|<span data-ttu-id="e6b71-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e6b71-123">Cell index:</span></span>  <br/> |<span data-ttu-id="e6b71-124">**visImageTransparency**</span><span class="sxs-lookup"><span data-stu-id="e6b71-124">**visImageTransparency**</span></span> <br/> |
   

