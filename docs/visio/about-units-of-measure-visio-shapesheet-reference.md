---
title: '关于 Visio ShapeSheet 参考 (度量单位) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251828
localization_priority: Normal
ms.assetid: 48f765a8-7485-03c0-3484-d4ec07822600
description: 当您向文本插入域或者建立公式时，常常要指定所键入的值的度量单位。
ms.openlocfilehash: d23c3f30841c81d07c09e57c0802e09edb0fe3c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360450"
---
# <a name="about-units-of-measure-visio-shapesheet-reference"></a>关于 Visio ShapeSheet 参考 (度量单位) 

当您向文本插入域或者建立公式时，常常要指定所键入的值的度量单位。
  
根据您输入的公式所在的单元格的不同，Microsoft Visio 对这个公式求值的结果也会有所不同。 通常，用来表示形状位置、尺寸或角度的单元格需要一个数字单位对，它由一个数字和用来解释该数字的限定单位组成。 很多其他单元格不需要单位，它们求值的结果为字符串、TRUE 或 FALSE，或是索引值。 例如 **，FillForegnd** 单元格中的相同公式表示绘图调色板中的颜色 5 表示 TRUE (并锁定 LockWidth 单元格中形状的宽度) 。 
  
如果在单元格中输入的公式的期望值是个尺寸标记值，则一定要指定度量单位。如果没有指定度量单位，Visio 会为该单元格使用默认单位，如页面单位、绘图单位、类型单位、持续时间单位或者角度单位。
  
## <a name="units-of-measure"></a>度量单位

在 ShapeSheet 公式中指示度量单位时，使用在下表中列出的缩写。
  
|**要指定如下度量单位**|**使用**|**自动常量**|
|:-----|:-----|:-----|
| Centimeters  <br/> | cm  <br/> |**visCentimeters (69)** <br/> |
| 百分百  <br/> | c  <br/> |**visCiceros (54)** <br/> |
| 日期或时间  <br/> | date  <br/> |**visDate (40)** <br/> |
| 学位  <br/> | deg  <br/> |**visDegrees (81)** <br/> |
| Didots  <br/> | d  <br/> |**visDidots (53)** <br/> |
| 已用星期数  <br/> | ew  <br/> |**visElapsedWeek (43)** <br/> |
| 已用天数  <br/> | ed  <br/> |**visElapsedDay (44)** <br/> |
| 已用小时数  <br/> | eh  <br/> |**visElapsedHour (45)** <br/> |
| 已用分钟数  <br/> | em  <br/> |**visElapsedMin (46)** <br/> |
| 已用秒数  <br/> | es  <br/> |**visElapsedSec (47)** <br/> |
| 英尺  <br/> | ft  <br/> |**visFeet (66)** <br/> |
| Inches  <br/> | in  <br/> |**visInches (65)** <br/> |
| 千米  <br/> | km  <br/> |**visKilometers (72)** <br/> |
| 米  <br/> | m  <br/> |**visMeters (71)** <br/> |
| 英里  <br/> | mi  <br/> |**visMiles (68)** <br/> |
| Millimeters  <br/> | mm  <br/> |**visMillimeters (70)** <br/> |
| 分钟  <br/> | '  <br/> |**visMin (84)** <br/> |
| 海里  <br/> | nm  <br/> |**visNautMiles (76)** <br/> |
| Percent  <br/> | %  <br/> |**visPercent (33)** <br/> |
| Picas  <br/> | p  <br/> |**visPicas (51)** <br/> |
| Points  <br/> | pt  <br/> |**visPoints (50)** <br/> |
| Radians  <br/> | rad  <br/> |**visRadians (83)** <br/> |
| 秒  <br/> | "  <br/> |**visSec (85)** <br/> |
| 百年  <br/> | yd  <br/> |**visYards (75)** <br/> |
   
## <a name="compound-units-of-measure"></a>复合度量单位

在公式中，您可以用下表中的缩写表示复合数字的度量单位。 Visio 会简化结果并将它们用复合单位显示出来。
  
例如，如果您输入 45.635°，Visio 显示等价值为 45° 38' 6"。
  
|**要指定单位**|**使用如下缩写**|**自动常量**|
|:-----|:-----|:-----|
| Cicero 和 didot  <br/> | EROERO/DIDOT  <br/> |**visCicerosAndDidots (52)** <br/> |
| 度、分和秒  <br/> | °  <br/> |**visDegreeMinSec (82)** <br/> |
| 英尺和英寸  <br/> | 英尺/英寸  <br/> |**visFeetAndInches (67)** <br/> |
| 十二点活字和磅  <br/> | PICAPOINTS  <br/> |**visPicasAndPoints (49)** <br/> |
   
## <a name="fractional-units-of-measure"></a>分数度量单位

可以在 **DrawingScale** 单元格中指定分数度量单位，以影响绘图窗口中Visio标尺细分线的数量。 默认情况下，Visio 在绘制其标尺时将距离十等分。 如果在 **DrawingScale** 单元格中使用分数度量单位，Visio将距离划分为以下值： 
  
- *visInchFrac* 和 *visMileFrac* 的第八位 
    
- *visFeetAndInches 的第十二位* 
    
分数度量单位对除 DrawingScale 单元格以外的单元格没有影响。
  
|**要指定分数单位**|**使用如下缩写**|**自动常量**|
|:-----|:-----|:-----|
| 分数英寸  <br/> | IN_F  <br/> |**visInchFrac (73)** <br/> |
| 分数英里  <br/> | MI_F  <br/> |**visMileFrac (74)** <br/> |
| 英尺和英寸  <br/> | 英尺/英寸  <br/> |**visFeetAndInches (67)** <br/> |
   
## <a name="multidimensional-units-of-measure"></a>多维度量单位

在公式中，您可以用下表中的缩写表示多维数字的度量单位。Visio 会简化结果并将它们用多维单位显示出来。
  
|**要指定多维单位**|**使用如下缩写**|**自动常量**|
|:-----|:-----|:-----|
| 百分百  <br/> | 一些  <br/> |**visAcre (36)** <br/> |
| Centimeters  <br/> | SQ. CM.、SQ CM、CM.^2、CM^2  <br/> |**visCentimeters (69)** <br/> |
| 英尺  <br/> | SQ. FT.、SQ FT、FT.^2、FT^2  <br/> |**visFeet (66)** <br/> |
| 百年  <br/> | HECTARES、HECTARE、HA.、HA  <br/> |**visHectare (37)** <br/> |
| Inches  <br/> | SQ. IN.、SQ IN、IN.^2、IN^2  <br/> |**visInches (65)** <br/> |
| 千米  <br/> | SQ. KM.、SQ KM、KM.^2、KM ^2  <br/> |**visKilometers (72)** <br/> |
| 米  <br/> | SQ. M.、SQ M、M.^2、M ^2  <br/> |**visMeters (71)** <br/> |
| 英里  <br/> | SQ. MI.、SQ MI、MI.^2、MI ^2  <br/> |**visMiles (68)** <br/> |
| Millimeters  <br/> | SQ. MM.、SQ MM、MM.^2、MM ^2  <br/> |**visMillimeters (70)** <br/> |
| 百年  <br/> | SQ. YD.、SQ YD、YD.^2、YD^2  <br/> |**visYards (75)** <br/> |
   
## <a name="universal-strings"></a>通用字符串

在 Visio 的本地化版本中，可识别的字符串集随语言而变化。如果您希望程序可以使用多种语言，则将通用字符串用于度量单位。
  
|**适用对象**|**使用**|
|:-----|:-----|
| Centimeters  <br/> | CM  <br/> |
| 百分百  <br/> | C  <br/> |
| Cicero 和 didot  <br/> | EROERO/DIDOT  <br/> |
| 日期或时间  <br/> | DATE  <br/> |
| 学位  <br/> | DEG  <br/> |
| 度、分和秒  <br/> | °  <br/> |
| Didots  <br/> | D  <br/> |
| 已用星期数  <br/> | EW  <br/> |
| 已用天数  <br/> | ED  <br/> |
| 已用小时数  <br/> | EH  <br/> |
| 已用分钟数  <br/> | EM  <br/> |
| 已用秒数  <br/> | ES  <br/> |
| 英尺  <br/> | FT  <br/> |
| 英尺和英寸  <br/> | 英尺/英寸  <br/> |
| Inches  <br/> | IN  <br/> |
| 分数英寸  <br/> | IN_F  <br/> |
| 千米  <br/> | KM  <br/> |
| 米  <br/> | M  <br/> |
| 英里  <br/> | MI  <br/> |
| 分数英里  <br/> | MI_F  <br/> |
| Millimeters  <br/> | MM  <br/> |
| 分钟  <br/> | '  <br/> |
| 海里  <br/> | NM  <br/> |
| Percent  <br/> | %  <br/> |
| Picas  <br/> | P  <br/> |
| 十二点活字和磅  <br/> | PICAPOINTS  <br/> |
| Points  <br/> | PT  <br/> |
| Radians  <br/> | RAD  <br/> |
| 秒  <br/> | "  <br/> |
| 百年  <br/> | YD  <br/> |
   
## <a name="implicit-units-of-measure"></a>隐式度量单位

当 Visio 分析和存储数字单位对时，它可以使用显式单位或隐式单位。用显式单位表示的数字总是按最初输入的度量单位显示。用隐式单位表示的数字总是转换为以适合于单元格的绘图、页面或角度单位表示的等价值。
  
例如，假设您在单元格 A 和单元格 B 中分别用显式单位和隐式单位输入 1 英寸的等价值，单元格 A 和 B 都使用绘图单位。然后，您将页面的默认单位改为厘米。单元格 A 仍然显示 1 in.，因为它使用不随默认值变化的显式单位。而单元格 B 现在显示 2.54 cm，它使用默认单位的等价值。
  
要隐式输入单位，应使用以下语法。
  
```vb
number  [unit , flag ]
```

|||
|:-----|:-----|
| _number_ <br/> |原始值，如 3.7、1.7E-4 或 5 1/2。  <br/> |
| _unit_ <br/> |最初表示  _数字_ 的单位。  <br/> |
| _flag_ <br/> |显示隐式值单位时使用的度量系统。其值请参见下表。  <br/> |
   
参数  _标志是_ 下列字母之一 (大写或小写) 指示显示隐式值单位时应该使用的度量系统。 
  
|**_标志_**|**度量系统**|**示例**|
|:-----|:-----|:-----|
| a、A  <br/> | Angular  <br/> | =5[deg，A]  <br/> |
| d、D  <br/> | Drawing  <br/> | =5[in，D]  <br/> |
| e、E  <br/> | 期限  <br/> | =5[eh，E]  <br/> |
| p、P  <br/> | Page  <br/> | =5[in，P]  <br/> |
| t、T  <br/> | 类型  <br/> | =5[pt，T]  <br/> |
   
另外，您可以对隐式绘图、页面、文本、角度和时间单位分别使用隐式单位 DL、DP、DT、DA、DE。 这些单位假设关联值是内部单位。 例如，如果当前度量系统是厘米，则  *=2 DL*  将被解释为 2 个内部单位 (英寸) 显示为 5.08 cm。 
  
使用上述隐式语法，该表达式（=2 DL）等价于 2[in,d]。隐式语法使您能够选择如何解释这个值，这样您也可以指定 2[ft,d]，它会被解释为 2 英尺并显示为 60.96 cm。隐式单位 DL、DP、DT、DA 和 DE 是通用的，没有本地化的对应单位。
  
## <a name="default-units-of-measure"></a>默认度量单位

以下是默认度量单位及其在用户界面中的等价设置。
  
|**默认度量单位**|**用户界面等价设置**|
|:-----|:-----|
|**visDrawingUnits** <br/> |页面中 DrawingScale 单元格的单位或者包含该单元格的主控形状的单位。  <br/> |
|**visPageUnits** <br/> |在 **“页面设置”** 对话框的 **“页面属性”** 选项卡上的 **“度量单位”** 框中选定的单位（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）。  <br/> |
|**visTypeUnits** <br/> |在"选项 **Visio"** 对话框的"高级"选项卡上的"显示"下的"文本"框中 (单击"文件"选项卡，然后单击"选项") 。    <br/> |
|**visAngleUnits** <br/> |在 **“Visio 选项”** 对话框的 **“高级”** 选项卡上的 **“显示”** 下方的 **“角度”** 框中选定的单位。  <br/> |
|**visDurationUnits** <br/> |在 **“Visio 选项”** 对话框的 **“高级”** 选项卡上的 **“显示”** 下方的 **“持续时间”** 框中选定的单位。  <br/> |
   

