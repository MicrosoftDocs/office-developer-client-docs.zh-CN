---
title: 关于 ShapeSheet 电子表格
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251822
localization_priority: Normal
ms.assetid: f403890d-4a3a-bacc-53d7-1b9920b23639
description: Microsoft Visio 中的每个元素（每个文档、绘图页、样式、形状、组合、组合中的形状或对象、主控形状、来自其他程序的对象、参考线以及辅助点）都具有用来保存与该对象有关的信息的 ShapeSheet 电子表格。此电子表格包含诸如高度、宽度、角度、颜色以及其他决定形状的外观和行为的属性信息。
ms.openlocfilehash: 37b2ae10b1f511197af5ccf739de91edb74e7819
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345153"
---
# <a name="about-the-shapesheet-spreadsheet"></a>关于 ShapeSheet 电子表格

Microsoft Visio 中的每个元素（每个文档、绘图页、样式、形状、组合、组合中的形状或对象、主控形状、来自其他程序的对象、参考线以及辅助点）都具有用来保存与该对象有关的信息的 ShapeSheet 电子表格。此电子表格包含诸如高度、宽度、角度、颜色以及其他决定形状的外观和行为的属性信息。
  
作为一名形状开发人员，您需要精确控制所创建的形状的外观和行为。您可以通过在形状的 ShapeSheet 中编辑它来改变其默认行为并增强其功能，可通过 ShapeSheet 窗口或以编程的方式访问该电子表格。
  
## <a name="viewing-an-object-in-a-shapesheet-window"></a>在 ShapeSheet 窗口中查看对象

Visio 绘图窗口和 ShapeSheet 窗口只不过是同一形状的不同视图。
  
- 当您在绘图窗口中查看一个形状时，您看到的是根据其 ShapeSheet 中的公式显示的图形外观和行为。
    
- 当您在 ShapeSheet 窗口中查看一个形状时，您将看到决定其在绘图页上的外观和行为的基本公式。
    
您可以同时查看 ShapeSheet 窗口和绘图窗口，并且当您在 ShapeSheet 窗口中操作单元格时，可以看到绘图窗口中的形状发生相应变化，反之亦然。例如，当您使用指针移动形状时，“Shape Transform”内容中形状的 PinX 和 PinY 公式会发生改变，以反映形状在绘图页上的新位置。
  
## <a name="structure-of-the-shapesheet-window"></a>ShapeSheet 窗口的结构

ShapeSheet 分为*几个部分*, 这些部分控制形状的行为或外观的特定方面, 例如其几何图形或格式。 每个部分都包含一个或多个包含*单元格*的*行*。 每个单元格可以包含一个公式、公式的结果（通常称为单元格值）和可选的错误信息。 根据特定单元格的需要，公式可能是必选的，也可能是可选的。 一个单元格的数据（如其公式或值）可以进行局部定义，也可以从形状的主控形状或样式中的等价单元格继承，而后者更为常见一些。 
  
下面的示例显示了编辑栏 ![编辑栏](media/callout1_ZA01036259.gif)、节 ![section](media/callout2_ZA01036260.gif)、单元格 ![单元](media/callout3_ZA01036261.gif)以及行 ![row](media/callout4_ZA01036262.gif) 在 ShapeSheet 窗口中。 
  
![ShapeSheet 窗口](media/ShpSheetRef_CA_02a_ZA07645861.gif)
  
当您绘制形状时，Visio 将形状记录为与线段连接的水平位置和垂直位置的集合。 这些位置 (称为顶点) 记录在形状的 " **Geometry** " 内容的 X 和 Y 单元格中。 如以下示例所示, 当您单击形状的 ShapeSheet 窗口的 "**几何图形**" 部分中的 X 和 Y 单元格时, 您将看到一个黑色的框突出显示绘图窗口中形状上的顶点。 
  
![黑色带边框的框突出显示绘图窗口中形状上的顶点](media/ShpSheetRef_CA_01_ZA07645860.gif)
  
## <a name="editing-an-object-in-the-shapesheet-window"></a>在 ShapeSheet 窗口中编辑对象

当 ShapeSheet 窗口处于活动状态时，功能区将改为显示在该窗口中工作时特定的选项。选择一个 ShapeSheet 单元格后，将会出现一个公式栏，您可以用它输入和编辑对象的公式。或者，您可以直接在该单元格中工作。
  
在 ShapeSheet 窗口中，您可以向形状的工作表添加内容，以便为绘图页上的形状添加新特征。 例如, 可以添加 "**连接点**" 部分来创建连接。 当您不再需要某个内容时，可以删除它。 
  
还可以向内容添加行，以便保存附加公式或更改形状的外观。 例如, 您可以向 " **Geometry** " 内容中添加行, 以向形状添加线段。 同样，您也可以删除不再需要的行。 
  
您可以在单元格中显示公式或者值。在输入新公式、编辑现有公式或查看单元格中公式的相互关系时，显示公式。值是 Visio 对单元格的公式求值后得到的结果。您可以显示单元格中的值以便查看求值结果。
  
## <a name="additional-shapesheet-references"></a>其他 ShapeSheet 引用

有关 shapesheet 中特定的节、行或单元格的详细信息, 请参阅此[ShapeSheet 引用](reference-visio-shapesheet.md)中的相应文章。
  
有关以编程方式访问 ShapeSheet 电子表格的详细信息，请参阅“Microsoft Visio 自动化参考”。
  

