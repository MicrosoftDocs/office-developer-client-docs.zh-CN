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
description: 调用的过程中 Microsoft Visual Basic for Applications (VBA) 项目。
ms.openlocfilehash: 04065384453e55b745daa89273fb4c23b32fb90c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779809"
---
# <a name="callthis-function"></a>CALLTHIS 函数

调用的过程中 Microsoft Visual Basic for Applications (VBA) 项目。
  
## <a name="syntax"></a>语法

CALLTHIS ("* **过程** *"，["* **项目** *"]，[* * *arg1* * *，* * *arg2* * *，...]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _过程_ <br/> |必需  <br/> |**字符串** <br/> | 要调用的过程的名称。  <br/> |
| _项目_ <br/> |可选  <br/> |**字符串** <br/> |包含该过程的项目。  <br/> |
| _arg_ <br/> |可选  <br/> |**Number、String、Date 或 Currency** <br/> |作为参数传递给过程。  <br/> |
   
## <a name="remarks"></a>注解

在 VBA 项目中，定义*过程*如下： 
  
过程 (*vsoShape*作为 Visio.Shape [arg1 键入，arg2 为类型...]) 
  
其中*vsoShape*是引用包含计算的 CALLTHIS 公式的**Shape**对象和_arg1_， *arg2* ...是中的公式指定的参数。 
  
请注意该*vsoShape*非常类似的"此"参数传递到 c + + 成员过程;因此名称"CALLTHIS。" 如"调用此过程，并将它传递到我的形状的引用。"生效，可以读取包含包括 CALLTHIS 公式的单元格 
  
如果指定_项目_，则 Microsoft Visio 将扫描所有打开的文档的一个包含_项目_和呼叫_过程_中的项目。 如果_项目_被省略或 null ("")，Visio 假定_过程_中的文档包含在进行计算的 CALLTHIS 公式的 VBA 项目。 
  
_Arg1_中的号码，在外部单元传递_arg2..._ 。 例如，如果传递从 3 cm 高一个形状的 Height 单元格中的值，3 传递。 若要通过其他单位表示与一个号码，使用 FORMATEX 函数或明确强制通过添加一个 null 的数字单位对，例如，0 ft + 高度的单位。 
  
CALLTHIS 函数中的第二个逗号是可选的。 对应于添加到过程的其他参数的数目。 如果您不使用任何其他参数，除非`(vsoShape as Visio.Shape)`，不要添加第二个逗号;使用 CALLTHIS("",)。 如果您添加两个附加参数，例如，使用 CALLTHIS("",,,)。 
  
CALLTHIS 函数始终计算结果为 0，并对_过程_调用期间空闲时间重新计算过程完成后发生。  _过程_可以返回一个值，但 Visio 会将其忽略。  _过程_将返回一个值，Visio 可以识别文档中设置的公式或另一个单元格的结果，但不是单元格调用_过程_，除非您想要覆盖 CALLTHIS 公式。
  
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

在*ThisDocument*类模块中使用以下过程。 
  
在形状的 EventDblClick 单元格中使用以下任一语法来调用前面的过程。
  
CALLTHIS("ThisDocument.A",)
  
CALLTHIS("ThisDocument.B",,"Click")
  
CALLTHIS("ThisDocument.C",,"Click", " OK.")
  

