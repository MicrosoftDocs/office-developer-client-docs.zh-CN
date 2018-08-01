---
title: 关于公式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251823
localization_priority: Normal
ms.assetid: ec0de3e1-21dc-c5d6-2c2a-d5fef80d89bd
description: 控制形状动作的关键是编写定义所需行为的公式。您可以编辑某个单元格的公式来更改单元格的值，并因此改变某个特定形状的行为。例如，更改“Shape Transform”内容的 Height 单元格所包含的公式可以改变形状的高度。
ms.openlocfilehash: 7df5ffe4d3dc32bcd5209bde353c39a92c7d422b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779597"
---
# <a name="about-formulas"></a>关于公式

控制形状动作的关键是编写定义所需行为的公式。您可以编辑某个单元格的公式来更改单元格的值，并因此改变某个特定形状的行为。例如，更改“Shape Transform”内容的 Height 单元格所包含的公式可以改变形状的高度。
  
Microsoft Visio 公式在很多方面都类似于典型的电子表格公式。Visio 将单元格中的所有内容（甚至是数值或简单的单元格引用）都看作公式。
  
单元格中的公式可以从主控形状或样式中的等价单元格继承，也可以进行局部定义。Visio 会对公式求值，然后将结果转化为适合于单元格的值和单位。在 ShapeSheet 窗口中，您可以将单元格内容显示为公式或值。
  
## <a name="elements-of-a-formula"></a>公式的元素

公式总是以一个自动插入的等号开始。公式可以包含以下任何元素：
  
- 数字
    
- 坐标
    
- 布尔值
    
- 运算符
    
- 函数
    
- 字符串
    
- 单元格引用
    
- 度量单位
    
## <a name="default-formulas"></a>默认的公式

创建形状时，默认情况下 Visio 会为它创建公式。若要查看这些默认公式，请绘制一个简单的形状（如矩形、椭圆或直线），然后打开它的 ShapeSheet 窗口（在[“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“显示 ShapeSheet”**）。
  
## <a name="inherited-formulas"></a>继承的公式

Visio 将尽可能继承公式。实例总是从其文档模具上的主控形状继承公式并从与绘图一起存储的样式定义继承格式，而不是在实例中制作每个公式的本地副本。这种行为产生多个较小的文件，但仍然允许对主控形状的公式或样式定义所做的更改传播到所有实例。
  
单元格中的黑色文本指示继承的公式。
  
## <a name="local-formulas"></a>局部公式

当您为实例编写局部公式时，您就用局部替换值替代了单元格中的继承的公式。由于该实例使用局部替换值阻止了单元格继承公式，因此将来在主控形状或样式中对此单元格的更改不会影响该实例。
  
应用样式会删除相关单元格中的所有局部公式，除非使用 GUARD 函数进行保护。
  
蓝色文本指示局部公式，它或者是 ShapeSheet 窗口中编辑公式的结果，或者是因对形状作出改动而使 Visio 重新设置该单元格的公式的结果。
  
## <a name="automatic-updates-to-formulas"></a>自动更新公式

 Visio 在您改变绘图中的某个形状时会自动更新某些单元格。这意味着在某些情况下您输入的公式可能被替换。例如，如果您拖动角手柄调整形状的大小时，Visio 会重置 PinX、PinY、Width 和 Height 单元格中的公式。 
  
如有必要，可以使用 GUARD 函数防止对公式进行改动。
  

