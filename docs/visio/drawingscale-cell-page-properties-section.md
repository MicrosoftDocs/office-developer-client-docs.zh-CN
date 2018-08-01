---
title: DrawingScale 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm265
localization_priority: Normal
ms.assetid: bc447f22-a188-2c61-e33c-df0d401a4725
description: 代表当前绘图比例中绘图单位的值。页面的绘图比例是 PageScale 单元格中显示的页面单位与 DrawingScale 单元格中显示的绘图单位之比。
ms.openlocfilehash: cdd3222f5e56c34ac8947c9ef5a653cfe19fbd0f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780133"
---
# <a name="drawingscale-cell-page-properties-section"></a><span data-ttu-id="12f5a-104">DrawingScale 单元格（“Page Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="12f5a-104">DrawingScale Cell (Page Properties Section)</span></span>

<span data-ttu-id="12f5a-p102">代表当前绘图比例中绘图单位的值。页面的绘图比例是 PageScale 单元格中显示的页面单位与 DrawingScale 单元格中显示的绘图单位之比。</span><span class="sxs-lookup"><span data-stu-id="12f5a-p102">Represents the value of the drawing unit in the current drawing scale. The drawing scale for the page is the ratio of the page unit shown in the PageScale cell to the drawing unit shown in the DrawingScale cell.</span></span>
  
<span data-ttu-id="12f5a-p103">您可以设置 DrawingScale 单元格，以便通过程序更改页上标尺的单位。下面是一个通过程序将度量单位由英寸改为厘米的示例。在这个例子中，使用 **ConvertResult** 方法以不同的单位保持相同的距离。</span><span class="sxs-lookup"><span data-stu-id="12f5a-p103">You can set the DrawingScale cell to change the units of a page's rulers from a program. Here is an example of changing the measurement units from inches to centimeters from a program. In this case, we use the **ConvertResult** method to keep the distance the same but express it in different units.</span></span> 
  
```vb
Public Sub SetActivePageMeasurementToCM() 
Dim dsCell As Visio.Cell 
Set dsCell = ActivePage.PageSheet.Cells("DrawingScale") 
 dsCell.Result(visCentimeters) = _ 
 Application.ConvertResult _ 
 (dsCell.ResultIU,visInches,visCentimeters) 
End Sub 
```

<span data-ttu-id="12f5a-110">您可以通过检查 DrawingScale 单元格的**单位**属性确定在绘图中的度量系统。</span><span class="sxs-lookup"><span data-stu-id="12f5a-110">You can determine the measurement system in a drawing by examining the **Units** property of the DrawingScale cell.</span></span> <span data-ttu-id="12f5a-111">在 Visual Basic 编辑器即时中执行以下语句在运行上述宏之后窗口将返回*True* 。</span><span class="sxs-lookup"><span data-stu-id="12f5a-111">After running the above macro the following statement executed in the Visual Basic Editor Immediate window will return  *True*  .</span></span> 
  
```vb
debug.print ActivePage.PageSheet.Cells("DrawingScale").Units = _ 
 visCentimeters 
```

## <a name="remarks"></a><span data-ttu-id="12f5a-112">说明</span><span class="sxs-lookup"><span data-stu-id="12f5a-112">Remarks</span></span>

<span data-ttu-id="12f5a-113">此单元格对应于 **“页面设置”** 对话框（单击 **“开始”** 选项卡上的 **“页面设置”** 箭头）中的设置。</span><span class="sxs-lookup"><span data-stu-id="12f5a-113">This cell corresponds to the settings in the **Page Setup** dialog box (click the **Page Setup** arrow on the **Home** tab).</span></span> 
  
<span data-ttu-id="12f5a-p105">DrawingScale 单元格中公式的单位决定了绘图窗口中标尺所使用的度量单位。如果您不想同时更改绘图比例，可执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="12f5a-p105">The units of the formula in the DrawingScale cell determine the measurement units used by the rulers in the drawing window. If you do not want to also change the drawing's scale, you can do one of the following:</span></span>
  
- <span data-ttu-id="12f5a-116">保留 DrawingScale 单元格中表示的距离，但是以其他单位表示。</span><span class="sxs-lookup"><span data-stu-id="12f5a-116">Keep the distance expressed in the DrawingScale cell the same but express it in different units.</span></span>
    
- <span data-ttu-id="12f5a-117">更改 PageScale 单元格中表示的距离，但与更改 DrawingScale 的幅度保持一致。</span><span class="sxs-lookup"><span data-stu-id="12f5a-117">Change the distance expressed in the PageScale cell by the same factor that you change DrawingScale.</span></span>
    
<span data-ttu-id="12f5a-118">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DrawingScale 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="12f5a-118">To get a reference to the DrawingScale cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="12f5a-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="12f5a-119">Cell name:</span></span>  <br/> |<span data-ttu-id="12f5a-120">DrawingScale</span><span class="sxs-lookup"><span data-stu-id="12f5a-120">DrawingScale</span></span>  <br/> |
   
<span data-ttu-id="12f5a-121">若要从某个程序按索引获取对 DrawingScale 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="12f5a-121">To get a reference to the DrawingScale cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="12f5a-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="12f5a-122">Section index:</span></span>  <br/> |<span data-ttu-id="12f5a-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="12f5a-123">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="12f5a-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="12f5a-124">Row index:</span></span>  <br/> |<span data-ttu-id="12f5a-125">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="12f5a-125">**visRowPage**</span></span> <br/> |
|<span data-ttu-id="12f5a-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="12f5a-126">Cell index:</span></span>  <br/> |<span data-ttu-id="12f5a-127">**visPageDrawingScale**</span><span class="sxs-lookup"><span data-stu-id="12f5a-127">**visPageDrawingScale**</span></span> <br/> |
   

