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
description: 将用户界面中的操作产生的更新值 (UI) 自动化重定向到另一个单元格。
ms.openlocfilehash: c4f5fe94aba90ce0a69983d6637a5399b6e42707
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416802"
---
# <a name="setatref-function"></a>SETATREF 函数

将用户界面中的操作产生的更新值 (UI) 自动化重定向到另一个单元格。 
  
## <a name="syntax"></a>语法

SETATREF (** *reference* ** [， ** *set_expression* ** [， ** *ignore_eval* ** ]]])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _reference_ <br/> |必需  <br/> |**String** <br/> |表示对重定向更新的单元格的引用。  <br/> |
| _set_expression_ <br/> |可选  <br/> |**字符串** <br/> |分配给引用 的  _表达式_。  <br/> |
| _ignore_eval_ <br/> |可选  <br/> |**Boolean** <br/> |如果为 TRUE，则 SETATREF 函数的 (为 0) 零;如果为 FALSE (SETATREF) 计算结果为引用  _的值的默认值_。  <br/> |
   
## <a name="remarks"></a>备注

当绘图窗口中的用户操作或自动化方法导致 Microsoft Visio 更新包含 SETATREF 公式的单元格时，值会重定向到 SETATREF 公式 (引用的单元格) 。  含有 SETATREF 函数的单元格中的公式将保持不变。
  
如果  _set_expression，_ 则 UI 中或通过使用自动化设置的值将分配给引用的单元格;否则，  _将set_expression分配给_ 引用的单元格。 这样，可以在将新值赋给引用的单元格之前对其进行修改或转换。 
  
SETATREF 函数有两个相关函数： 
  
- SETATREFEXPR 函数，可用于表示 set_expression _。_ 例如，一个  _set_expression_ SETATREFEXPR () -2 in。 可用于从 SETATREFEXPR 结果中减去 2 英寸。 
    
- SETATREFEVAL 函数，可用于指示应计算set_expression部分内容，并替换为其结果。 
    
SETATREF 函数设计用于绘图窗口中用户操作可更改的单元格。 该函数支持以下单元格：
  
- “ShapeTransform”内容 — Width、Height、Angle、PinX 和 PinY 单元格
    
- “Text Transform”内容 — TxtWidth、TxtHeight、TxtAngle、TxtPinX 和 TxtPinY 单元格
    
- “1-D Endpoints”内容 — BeginX、BeginY、EndX 和 EndY 单元格
    
- “Controls”内容 — Controls.X 和 Controls.Y 单元格
    
- “Shape Data”内容
    
由于 SETATREF 会更改单元格值发生变化的位置，因此它会影响事件触发。 如果某个单元格包含 SETATREF，则 **FormulaChanged** 和 **CellChanged** 事件将为 SETATREF 所引用的单元格而触发，而不会为包含 SETATREF 的单元格而触发。 如果包含 SETATREF 的单元格还包含 SETATREFEXPR，FormulaChanged 事件也会为包含 SETATREF 的单元格触发，因为函数参数已更改。  
  
对于 SETATREF 函数，还请注意以下一些要点：
  
- SETATREF 函数最多可链接 10 个对其他 SETATREF 函数的引用。 
    
- 除 SETATREF 函数以外，单元格可包含其他表达式，包括在一个单元格中可多次出现 SETATREF。
    
- 如果形状被粘附，Visio 将延续同一工作表中的 SETATREF 引用链并将粘附公式放在引用的单元格中。 
    
- 自动化识别 SETATREF 函数并延续引用单元格链。 
    
- 与 GUARD 类似，SETATREF 不能避免在 ShapeSheet 中使用 SETF 函数时单元格发生更改。
    
## <a name="example1"></a>示例 1

假设某个形状具有自定义属性 Width，且“Shape Transform”内容中的 Width 单元格包含以下公式：
  
=SETATREF (Prop.Width) 
  
如果用户在 UI 中更改形状的宽度，则新值将分配给 Prop.Width 单元格，而不是 ShapeTransform 内容中的 Width 单元格;Width 单元格中的公式保持不变。 您还可以使用形状数据设置形状的宽度。
  
## <a name="example2"></a>示例 2

Visio 解决方案通常具有含分级关系的形状，要求子形状随父形状的移动而移动。下面的示例向您演示了如何使用 ShapeSheet 中的 SETATREF 函数管理这种关系。 
  
以下公式包含在子形状的“Shape Transform”内容中。我们还定义了用户单元格 User.DeltaX 和 User.DeltaY，用来跟踪父形状的偏移尺寸。这样，子形状会随父形状的移动而移动，并且在移动子形状时仍然保持分级关系。
  
PinX =SETATREF(User.DeltaX, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinX)) + ParentShape!PinX
  
PinY =SETATREF(User.DeltaY, SETATREFEVAL(SETATREFEXPR() - ParentShape!PinY)) + ParentShape!PinY
  
当使用 UI 移动子形状时，新的 PinX 和 PinY 值被设置为 SETATREFEXPR 函数中的参数。 SETATREF 函数计算包含在 SETATREFEVAL 中的公式，并将 PinX 和 PinY 替换为其结果，然后将生成的公式分配给 SETATREF 函数中引用的用户单元格 User.DeltaX 和 User.DeltaY。 最后，SETATREF（User.DeltaX 或 User.DeltaY）所返回的值被添加到父形状的旋转中心点位置，以计算子形状的旋转中心点位置。
  

