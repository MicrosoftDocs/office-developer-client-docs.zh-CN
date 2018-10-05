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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389349"
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

ShapeSheet 分为*部分*的控制某个特定方面的形状的行为或外观，例如，及其几何图形或格式设置。 每个部分包含*单元格*包含一个或多个*行*。 每个单元格包含公式，其 （通常名为单元格的值） 的结果和可选的错误信息。 公式可能必需或可选的具体取决于特定单元格。 单元格的数据 （例如，其公式或值） 可能是本地定义或者，更频繁地继承自中形状的主控形状或样式的等效单元格。 
  
以下示例显示了 ShapeSheet 窗口中的公式栏 ![编辑栏](media/callout1_ZA01036259.gif)、内容 ![section](media/callout2_ZA01036260.gif)、单元格 ![单元格](media/callout3_ZA01036261.gif)和行 ![row](media/callout4_ZA01036262.gif) 。 
  
![ShapeSheet 窗口](media/ShpSheetRef_CA_02a_ZA07645861.gif)
  
时绘制形状，Visio 将记录作为集合的水平和垂直位置与线段连接的形状。 这些位置 （称为顶点） 记录在 X 和 Y 单元格的形状的**geometry**内容中。 下面的示例中所示，当您单击形状的 ShapeSheet 窗口的**geometry**内容中的 X 和 Y 单元格时，您将看到黑色界定框中，突出显示在绘图窗口中的形状的顶点。 
  
![突出显示在绘图窗口中的形状的顶点的黑色界定框](media/ShpSheetRef_CA_01_ZA07645860.gif)
  
## <a name="editing-an-object-in-the-shapesheet-window"></a>在 ShapeSheet 窗口中编辑对象

当 ShapeSheet 窗口处于活动状态时，功能区将改为显示在该窗口中工作时特定的选项。选择一个 ShapeSheet 单元格后，将会出现一个公式栏，您可以用它输入和编辑对象的公式。或者，您可以直接在该单元格中工作。
  
在 ShapeSheet 窗口中，您可以添加节到形状的工作表添加到绘图页上的形状的新特征。 例如，您可以添加**Connection** points 创建的连接。 当不再需要一节时，您可以将其删除。 
  
您还可以添加行于节保存附加公式或更改形状的外观。 例如，您可以将行添加到**geometry**内容添加到形状的一段。 同样，您可以删除不再需要的行。 
  
您可以在单元格中显示公式或者值。在输入新公式、编辑现有公式或查看单元格中公式的相互关系时，显示公式。值是 Visio 对单元格的公式求值后得到的结果。您可以显示单元格中的值以便查看求值结果。
  
## <a name="additional-shapesheet-references"></a>其他 ShapeSheet 引用

有关特定内容、 行或单元格 ShapeSheet 中的详细信息，此[ShapeSheet 参考](reference-visio-shapesheet.md)中查看相应文章。
  
有关以编程方式访问 ShapeSheet 电子表格的详细信息，请参阅“Microsoft Visio 自动化参考”。
  

