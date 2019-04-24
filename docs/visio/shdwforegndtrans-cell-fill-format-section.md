---
title: ShdwForegndTrans 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253253
localization_priority: Normal
ms.assetid: c42d4d2e-f8f0-bc5b-6018-4bb4ffa81b64
description: 确定用于形状的投影填充图案的前景（划线）颜色的透明度级别。
ms.openlocfilehash: 0ef3ce525edcce4ccd61f36649ead512545eef58
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349096"
---
# <a name="shdwforegndtrans-cell-fill-format-section"></a><span data-ttu-id="8a54f-103">ShdwForegndTrans 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="8a54f-103">ShdwForegndTrans Cell (Fill Format Section)</span></span>

<span data-ttu-id="8a54f-104">确定用于形状的投影填充图案的前景（划线）颜色的透明度级别。</span><span class="sxs-lookup"><span data-stu-id="8a54f-104">Determines the transparency level for the color used for the foreground (stroke) of the shape's drop shadow fill pattern.</span></span>
  
|<span data-ttu-id="8a54f-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="8a54f-105">**Value**</span></span>|<span data-ttu-id="8a54f-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="8a54f-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8a54f-107">0 - 100</span><span class="sxs-lookup"><span data-stu-id="8a54f-107">0 - 100</span></span>  <br/> |<span data-ttu-id="8a54f-p101">表示透明度的百分比。默认值为 0%（完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="8a54f-p101">Represents the percentage of transparency. The default is 0% (completely opaque).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8a54f-110">注解</span><span class="sxs-lookup"><span data-stu-id="8a54f-110">Remarks</span></span>

<span data-ttu-id="8a54f-111">这些值被四舍五入为最接近的 0.5 个百分点。</span><span class="sxs-lookup"><span data-stu-id="8a54f-111">Values are rounded to the nearest half percent.</span></span> <span data-ttu-id="8a54f-112">值 100% 是完全透明。</span><span class="sxs-lookup"><span data-stu-id="8a54f-112">A value of 100% is completely transparent.</span></span> <span data-ttu-id="8a54f-113">虽然具有完全透明填充的阴影在绘图页上显示为没有填充的阴影, 但它与页面上的其他对象进行交互的方式与它的透明度为 0% 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="8a54f-113">Although a shadow that has a completely transparent fill appears the same on the drawing page as a shadow that has no fill, it interacts with other objects on the page in the same ways as if its transparency were 0%.</span></span>
  
<span data-ttu-id="8a54f-p103">您还可以使用 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的滑块控件设置此值。此值同时控制背景和前景阴影透明度的值。若要单独设置上述值，必须在 ShapeSheet 窗口中输入它们。</span><span class="sxs-lookup"><span data-stu-id="8a54f-p103">You can also set this value by using the slider control in the **Shadow** dialog box (on the **Home** tab, in the **Shape** group, click **Shadow**, and then click **Shadow Options**). This value controls the value of both the background and foreground shadow transparencies. To set these values independently, you must enter them in the ShapeSheet window.</span></span>
  
<span data-ttu-id="8a54f-117">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwForegndTrans 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8a54f-117">To get a reference to the ShdwForegndTrans cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8a54f-118">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8a54f-118">Cell name:</span></span>  <br/> |<span data-ttu-id="8a54f-119">ShdwForegndTrans</span><span class="sxs-lookup"><span data-stu-id="8a54f-119">ShdwForegndTrans</span></span>  <br/> |
   
<span data-ttu-id="8a54f-120">若要从某个程序按索引获取对 ShdwForegndTrans 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8a54f-120">To get a reference to the ShdwForegndTrans cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8a54f-121">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8a54f-121">Section index:</span></span>  <br/> |<span data-ttu-id="8a54f-122">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8a54f-122">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="8a54f-123">行索引：</span><span class="sxs-lookup"><span data-stu-id="8a54f-123">Row index:</span></span>  <br/> |<span data-ttu-id="8a54f-124">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="8a54f-124">**visRowFill**</span></span> <br/> |
|<span data-ttu-id="8a54f-125">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8a54f-125">Cell index:</span></span>  <br/> |<span data-ttu-id="8a54f-126">**visFillShdwForegndTrans**</span><span class="sxs-lookup"><span data-stu-id="8a54f-126">**visFillShdwForegndTrans**</span></span> <br/> |
   

