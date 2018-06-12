---
title: Transparency 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50130
localization_priority: Normal
ms.assetid: 7382e2aa-5e18-19d2-88d8-c4a19a385106
description: 确定图层颜色的透明度级别。
ms.openlocfilehash: 7c205612436e7731f268e17c851616beebf809dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781551"
---
# <a name="transparency-cell-layers-section"></a><span data-ttu-id="d494e-103">Transparency 单元格（“Layers”内容）</span><span class="sxs-lookup"><span data-stu-id="d494e-103">Transparency Cell (Layers Section)</span></span>

<span data-ttu-id="d494e-104">确定图层颜色的透明度级别。</span><span class="sxs-lookup"><span data-stu-id="d494e-104">Determines the transparency level for a layer color.</span></span>
  
|<span data-ttu-id="d494e-105">**值**</span><span class="sxs-lookup"><span data-stu-id="d494e-105">**Value**</span></span>|<span data-ttu-id="d494e-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="d494e-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d494e-107">0-100</span><span class="sxs-lookup"><span data-stu-id="d494e-107">0 - 100</span></span>  <br/> |<span data-ttu-id="d494e-p101">表示透明度的百分比。默认值为 0%（完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="d494e-p101">Represents the percentage of transparency. The default is 0% (completely opaque).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d494e-110">注解</span><span class="sxs-lookup"><span data-stu-id="d494e-110">Remarks</span></span>

<span data-ttu-id="d494e-111">值将四舍五入到最接近半百分比。</span><span class="sxs-lookup"><span data-stu-id="d494e-111">Values are rounded to the nearest half percent.</span></span> <span data-ttu-id="d494e-112">值为 100%是完全透明的。</span><span class="sxs-lookup"><span data-stu-id="d494e-112">A value of 100% is completely transparent.</span></span> <span data-ttu-id="d494e-113">尽管完全透明颜色的图层显示在绘图页上相同为无颜色的图层，它与交互页上的其他对象相同的方式透明度当作 0%。</span><span class="sxs-lookup"><span data-stu-id="d494e-113">Although a layer that has completely transparent color appears the same on the drawing page as a layer that has no color, it interacts with other objects on the page in the same way as if its transparency were 0%.</span></span> <span data-ttu-id="d494e-114">您还可以通过使用**图层属性**对话框中的滑块控件设置此值 （**主页**选项卡，在**编辑**组中，单击**图层**，，然后单击**图层属性**）。</span><span class="sxs-lookup"><span data-stu-id="d494e-114">You can also set this value by using the slider control in the **Layer Properties** dialog box (on the **Home** tab, in the **Editing** group, click **Layers**, and then click **Layer Properties**).</span></span>
  
<span data-ttu-id="d494e-115">若要获取对 Transparency 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="d494e-115">To get a reference to the Transparency cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d494e-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d494e-116">Cell name:</span></span>  <br/> |<span data-ttu-id="d494e-117">Layers.ColorTrans [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="d494e-117">Layers.ColorTrans[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="d494e-118">若要从某个程序按索引获取对 Transparency 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="d494e-118">To get a reference to the Transparency cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d494e-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d494e-119">Section index:</span></span>  <br/> |<span data-ttu-id="d494e-120">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="d494e-120">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="d494e-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="d494e-121">Row index:</span></span>  <br/> |<span data-ttu-id="d494e-122">**visRowLayer** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="d494e-122">**visRowLayer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="d494e-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d494e-123">Cell index:</span></span>  <br/> |<span data-ttu-id="d494e-124">**visLayerColorTrans**</span><span class="sxs-lookup"><span data-stu-id="d494e-124">**visLayerColorTrans**</span></span> <br/> |
   

