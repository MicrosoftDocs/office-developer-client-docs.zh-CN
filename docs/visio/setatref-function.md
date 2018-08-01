---
title: SETATREF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60113
localization_priority: Normal
ms.assetid: 1ecfdb05-2533-470a-006b-e554026944d8
description: 重定向更新中的用户界面 (UI) 或自动化操作产生到另一个单元格的值。
ms.openlocfilehash: 69a9cb93ae3fbd807ef4f306be386f5389a6cfeb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781240"
---
# <a name="setatref-function"></a>SETATREF 函数

重定向更新中的用户界面 (UI) 或自动化操作产生到另一个单元格的值。 
  
## <a name="syntax"></a>语法

SETATREF (* **参考 （英文）* * * [，* * *set_expression* * * [，* * *ignore_eval* * *]]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _参考 （英文）_ <br/> |必需  <br/> |**字符串** <br/> |表示对重定向更新的单元格的引用。  <br/> |
| _set_expression_ <br/> |可选  <br/> |**字符串** <br/> |分配给_引用_一个表达式。  <br/> |
| _ignore_eval_ <br/> |可选  <br/> |**Boolean** <br/> |如果为 TRUE，则 SETATREF 函数计算为 (0) 零;如果为 FALSE （默认值） SETATREF 函数计算为_reference_的值。  <br/> |
   
## <a name="remarks"></a>说明

当用户操作在绘图窗口中或自动化方法，使 Microsoft Visio 更新包含 SETATREF 公式的单元格时，值改为重定向到 SETATREF 公式 （_引用_） 引用的单元格。 中包含 SETATREF 函数的单元格的公式保持不变。
  
如果省略_set_expression_ ，设置在用户界面或通过使用自动化的值分配给引用的单元格;否则， _set_expression_的某一部分的内容分配给引用的单元格。 这样，要修改或转换之前要分配给引用的单元格的新值。 
  
SETATREF 函数有两个相关函数： 
  
- SETATREFEXPR 函数，可用来表示_set_expression_中的新值。 例如， _set_expression_的 SETATREFEXPR （）-2 中的。 无法用于减去从 SETATREFEXPR 结果的 2 英寸。 
    
- SETATREFEVAL 函数，您可以使用它来指示应计算并由其结果替换_set_expression_的。 
    
SETATREF 函数用于可以更改的绘图窗口中的用户操作的单元格。 支持以下单元格：
  
- “ShapeTransform”内容 — Width、Height、Angle、PinX 和 PinY 单元格
    
- “Text Transform”内容 — TxtWidth、TxtHeight、TxtAngle、TxtPinX 和 TxtPinY 单元格
    
- “1-D Endpoints”内容 — BeginX、BeginY、EndX 和 EndY 单元格
    
- “Controls”内容 — Controls.X 和 Controls.Y 单元格
    
- “Shape Data”内容
    
SETATREF 更改单元格值的变化的位置，因为它会影响事件触发。 如果单元格包含 SETATREF，则**FormulaChanged**和**CellChanged**事件触发 SETATREF，不包含 SETATREF 的单元格引用单元格。 如果还包含 SETATREF 的单元格包含 SETATREFEXPR，还会包含 SETATREF，因为函数参数已更改的单元格的触发**FormulaChanged**事件。 
  
对于 SETATREF 函数，还请注意以下一些要点：
  
- SETATREF 函数最多可链接 10 个对其他 SETATREF 函数的引用。 
    
- 除 SETATREF 函数以外，单元格可包含其他表达式，包括在一个单元格中可多次出现 SETATREF。
    
- 如果形状被粘附，Visio 将延续同一工作表中的 SETATREF 引用链并将粘附公式放在引用的单元格中。 
    
- 自动化识别 SETATREF 函数并延续引用单元格链。 
    
- 与 GUARD 类似，SETATREF 不能避免在 ShapeSheet 中使用 SETF 函数时单元格发生更改。
    
## <a name="example1"></a>示例 1

假设某个形状具有自定义属性 Width，且“Shape Transform”内容中的 Width 单元格包含以下公式：
  
=SETATREF(Prop.Width)
  
如果用户更改在 UI 中的形状的宽度，将新值分配给 Prop.Width 单元格，而不应用于在 ShapeTransform 部分中; Width 单元格Width 单元格中的公式保持不变。 您还可以使用形状数据设置形状的宽度。
  
## <a name="example2"></a>示例 2

Visio 解决方案通常具有含分级关系的形状，要求子形状随父形状的移动而移动。下面的示例向您演示了如何使用 ShapeSheet 中的 SETATREF 函数管理这种关系。 
  
以下公式包含在子形状的“Shape Transform”内容中。我们还定义了用户单元格 User.DeltaX 和 User.DeltaY，用来跟踪父形状的偏移尺寸。这样，子形状会随父形状的移动而移动，并且在移动子形状时仍然保持分级关系。
  
PinX =SETATREF(User.DeltaX, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinX)) + ParentShape!PinX
  
PinY =SETATREF(User.DeltaY, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinY)) + ParentShape!PinY
  
当使用用户界面移动子形状时，新的 PinX 和 PinY 值设置为 SETATREFEXPR 函数中的参数。 SETATREF 函数计算括在 SETATREFEVAL 的公式，并将 PinX 和 PinY 替换为其结果，然后生成公式分配给用户的单元格引用中的 SETATREF function—User.DeltaX 和 User.DeltaY。 最后，SETATREF （User.DeltaX 或 User.DeltaY） 返回的值添加到 ParentShape 计算子形状的 pin 位置的 pin 位置。
  

