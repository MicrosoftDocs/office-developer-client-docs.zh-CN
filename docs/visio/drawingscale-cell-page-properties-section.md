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
ms.openlocfilehash: 8a3a5f93ff096e42ba3c13b671b46bf1cf97df82
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413316"
---
# <a name="drawingscale-cell-page-properties-section"></a>DrawingScale 单元格（“Page Properties”内容）

代表当前绘图比例中绘图单位的值。页面的绘图比例是 PageScale 单元格中显示的页面单位与 DrawingScale 单元格中显示的绘图单位之比。
  
您可以设置 DrawingScale 单元格，以便通过程序更改页上标尺的单位。 下面是一个通过程序将度量单位由英寸改为厘米的示例。 在这个例子中，使用 **ConvertResult** 方法以不同的单位保持相同的距离。 
  
```vb
Public Sub SetActivePageMeasurementToCM() 
Dim dsCell As Visio.Cell 
Set dsCell = ActivePage.PageSheet.Cells("DrawingScale") 
 dsCell.Result(visCentimeters) = _ 
 Application.ConvertResult _ 
 (dsCell.ResultIU,visInches,visCentimeters) 
End Sub 
```

您可以通过检查 DrawingScale 单元格的 **Units** 属性来确定绘图中的度量系统。 运行上述宏后, 在 Visual Basic 编辑器的 "即时" 窗口中执行以下语句将返回*True* 。 
  
```vb
debug.print ActivePage.PageSheet.Cells("DrawingScale").Units = _ 
 visCentimeters 
```

## <a name="remarks"></a>说明

此单元格对应于 **“页面设置”** 对话框（单击 **“开始”** 选项卡上的 **“页面设置”** 箭头）中的设置。 
  
DrawingScale 单元格中公式的单位决定了绘图窗口中标尺所使用的度量单位。如果您不想同时更改绘图比例，可执行以下操作之一：
  
- 保留 DrawingScale 单元格中表示的距离，但是以其他单位表示。
    
- 更改 PageScale 单元格中表示的距离，但与更改 DrawingScale 的幅度保持一致。
    
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DrawingScale 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |DrawingScale  <br/> |
   
若要从某个程序按索引获取对 DrawingScale 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPage** <br/> |
|单元格索引：  <br/> |**visPageDrawingScale** <br/> |
   

