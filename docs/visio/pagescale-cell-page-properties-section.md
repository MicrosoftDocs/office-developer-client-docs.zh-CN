---
title: PageScale 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm775
localization_priority: Normal
ms.assetid: e1da84b3-fd15-12b9-9342-0412e818b3b9
description: 确定当前绘图比例中页面单位的值。页面的绘图比例是 PageScale 单元格中显示的页面单位与 DrawingScale 单元格中显示的绘图单位之比。
ms.openlocfilehash: 0763fd6fad5f64bc741cbdd1e1227b0982323841
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339450"
---
# <a name="pagescale-cell-page-properties-section"></a><span data-ttu-id="692bc-104">PageScale 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="692bc-104">PageScale Cell (Page Properties Section)</span></span>

<span data-ttu-id="692bc-p102">确定当前绘图比例中页面单位的值。页面的绘图比例是 PageScale 单元格中显示的页面单位与 DrawingScale 单元格中显示的绘图单位之比。</span><span class="sxs-lookup"><span data-stu-id="692bc-p102">Determines the value of the page unit in the current drawing scale. The drawing scale for the page is the ratio of the page unit shown in the PageScale cell to the drawing unit shown in the DrawingScale cell.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="692bc-107">注解</span><span class="sxs-lookup"><span data-stu-id="692bc-107">Remarks</span></span>

<span data-ttu-id="692bc-p103">您还可以在 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）中的 **“绘图缩放比例”** 选项卡上设置 PageScale 单元格的值。该单元格的值是 **“预定义缩放比例”** 框或 **“自定义缩放比例”** 框中两个数字中的第一个数字，具体情况则取决于在 **“绘图缩放比例”** 下选择的绘图缩放比例设置。例如，如果为绘图选择结构缩放比例，则该页的绘图缩放比例为 3/32" = 1'0"。PageScale 单元格中的值为 0.0938 in.（或 3/32"），DrawingScale 单元格中的值为 1 ft。</span><span class="sxs-lookup"><span data-stu-id="692bc-p103">You can also set the value of the PageScale cell on the **Drawing Scale** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow). The value of the cell is the first of the two numbers in the **Pre-defined scale** box or **Custom scale** box, depending on the drawing scale setting selected under **Drawing scale**. For example, if you select an architectural scale for your drawing, the drawing scale for the page is 3/32" = 1'0". The value in the PageScale cell is 0.0938 in. (or 3/32") and the value in the DrawingScale cell is 1 ft.</span></span>
  
<span data-ttu-id="692bc-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageScale 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="692bc-113">To get a reference to the PageScale cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="692bc-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="692bc-114">Cell name:</span></span>  <br/> |<span data-ttu-id="692bc-115">PageScale</span><span class="sxs-lookup"><span data-stu-id="692bc-115">PageScale</span></span>  <br/> |
   
<span data-ttu-id="692bc-116">若要从某个程序按索引获取对 PageScale 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="692bc-116">To get a reference to the PageScale cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="692bc-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="692bc-117">Section index:</span></span>  <br/> |<span data-ttu-id="692bc-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="692bc-118">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="692bc-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="692bc-119">Row index:</span></span>  <br/> |<span data-ttu-id="692bc-120">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="692bc-120">**visRowPage**</span></span> <br/> |
|<span data-ttu-id="692bc-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="692bc-121">Cell index:</span></span>  <br/> |<span data-ttu-id="692bc-122">**visPageScale**</span><span class="sxs-lookup"><span data-stu-id="692bc-122">**visPageScale**</span></span> <br/> |
   

