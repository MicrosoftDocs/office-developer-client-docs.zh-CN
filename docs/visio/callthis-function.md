---
title: CALLTHIS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251403
localization_priority: Normal
ms.assetid: 461abfc1-d2cc-2354-1c2f-395c9e351a78
description: 调用 Microsoft Visual Basic for Applications (VBA) 中的过程。
ms.openlocfilehash: 7e0f0bafa39d6c1eb1fd39535506981c937ce8a1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413813"
---
# <a name="callthis-function"></a>CALLTHIS 函数

调用 Microsoft Visual Basic for Applications (VBA) 中的过程。
  
## <a name="syntax"></a>语法

CALLTHIS (" ** *procedure* ** "，[" ** *project* ** "]，[ ** *arg1* **， ** *arg2* **,...])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _procedure_ <br/> |必需  <br/> |**String** <br/> | 要调用的过程的名称。  <br/> |
| _project_ <br/> |可选  <br/> |**字符串** <br/> |包含该过程的项目。  <br/> |
| _arg_ <br/> |可选  <br/> |**Number、String、Date 或 Currency** <br/> |作为参数传递给过程。  <br/> |
   
## <a name="remarks"></a>备注

在 VBA 项目中  *，过程*  定义如下： 
  
过程 (*vsoShape* As Visio。形状 [arg1 As type， arg2 As type...])  
  
其中  *vsoShape*  是包含要求值 CALLTHIS 公式的 **Shape** 对象的引用  _，arg1_、  *arg2*  ...是该公式中指定的参数。 
  
请注意  *，vsoShape*  与传递给 C++ 成员过程的"this"参数非常类似;因此，名称为"CALLTHIS"。 实际上，包含包含 CALLTHIS 的公式的单元格可以读取为"调用此过程，并传递对形状的引用"。 
  
如果 _指定了 project，Microsoft_ Visio所有打开的文档中扫描包含项目的文档 _，并_ 调用该项目中的过程。 如果 _省略 project_ 或空 ("") ，Visio假定 _过程_ 位于包含正在求值 CALLTHIS 公式的文档的 VBA 项目中。 
  
_arg1 、_ _arg2..._ 中的数字以外部单位传递。 例如，如果您传递一个 3 cm 高的形状的 Height 单元格中的数值，则会传递 3。 若要用不同的单位进行传递，则应使用 FORMATEX 函数或通过增加一个空的数值-单位对（例如，0 ft + Height），来明确规定单位。 
  
CALLTHIS 函数中的第二个逗号是可选的。 它对应于添加到过程中的附加参数的数值。 如果不使用任何其他参数，但不要添加第二个逗号;使用  `(vsoShape as Visio.Shape)` CALLTHIS ("，) 。 例如，如果要添加两个附加参数，请使用 CALLTHIS("",,,)。 
  
CALLTHIS 函数始终计算为 0，并且对  _过程的_ 调用在重新计算过程完成后的空闲时间内发生。  _Procedure_ 可以返回一个数值，但 Visio 将忽略该值。  _Procedure_ 返回一个值，Visio通过设置文档中其他单元格（而不是调用 _procedure_ 的单元格）的公式或结果来识别该值，除非您要覆盖 CALLTHIS 公式。
  
CALLTHIS 函数不同于 RUNADDON 函数，文档的项目不需要引用另一个项目便可调用到该项目中。 
  
> [!NOTE]
>  在 Visio 实例对公式中的 CALLTHIS 函数求值时所调用的 VBA 代码不应关闭包含使用该函数的单元格的文档，因为这样会导致应用程序出错，并且 Visio 将终止。 
  
如果您需要关闭包含使用 CALLTHIS 函数的单元格的文档，则请使用下列方法之一： 
  
- 从非 VBA 的代码关闭文档。
    
- 从正在关闭的项目之外的其他项目关闭文档。
    
- 将关闭窗口的窗口消息张贴到文档中，而不是关闭该文档。
    
有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。 
  
## <a name="example-1"></a>示例 1

CALLTHIS("p",,FORMATEX(Height,"#.00 u",,"cm"))
  
调用位于模块中的名为 p 的过程，并传递以厘米为单位的高度数值，如 7.62 cm。
  
## <a name="example-2"></a>示例 2

CALLTHIS("q",,0 cm+Height,Width)
  
调用位于模块中的名为 q 的过程，并传递以厘米为单位的单元格高度和以内部单位表示的宽度。
  
## <a name="example-3"></a>示例 3

请使用  *ThisDocument*  类模块中的以下过程。 
  
在形状的 EventDblClick 单元格中使用以下任一语法来调用前面的过程。
  
CALLTHIS ("ThisDocument.A"，) 
  
CALLTHIS ("ThisDocument.B"，"Click") 
  
CALLTHIS("ThisDocument.C",,"Click", " OK.")
  

