---
title: RUNADDON 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251492
localization_priority: Normal
ms.assetid: 122c1d30-3cb9-7e7d-b4cc-e93ab8e4da4f
description: 在 Microsoft VBA Visual Basic for Applications (项目中执行加载项) 宏。
ms.openlocfilehash: 280f6eaf1e5db045d8c1d22965df00960d188112
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432007"
---
# <a name="runaddon-function"></a>RUNADDON 函数

在 Microsoft VBA Visual Basic for Applications (项目中执行加载项) 宏。 
  
## <a name="syntax"></a>语法

RUNADDON (" *string*  ")  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _string_ <br/> |必需  <br/> |**String** <br/> | **Addons** 集合中的加载项或 VBA 项目中的宏的名称。  <br/> |
   
## <a name="remarks"></a>备注

如果包含 RUNADDON 函数的文档的项目调用 (或引用它的另一个项目（如果引用了) ）没有宏 (则没有参数) named _string_ 的过程，Microsoft Visio 将运行名为 的 _加载项字符串_。 如果找不到加载项命名 _的字符串_，则Visio不执行任何操作，并且不会报告错误。  (可以使用 **TraceFlags** 属性监视尝试运行的过程Visio加载项。)  
  
在标准模块中调用过程时，建议您在字符串前面添加包含过程 (（例如  *moduleName.procName*) ）的模块名称作为前缀，因为多个模块可以具有同名的过程。 
  
若要在包含 RUNADDON 函数调用的文档项目外的项目中调用过程，请使用  *语法 projName.modName.procName*  (您必须在 VBA 项目) 中显式设置对  *projName*  的引用。 
  
> [!NOTE]
>  从 Visio 2002 开始，RUNADDON 函数无法执行含有任意 VBA 代码的字符串。对于以前传递到 RUNADDON 函数的代码，可以将这些代码移到从该 RUNADDON 函数调用的某个文档的 VBA 项目的过程中。 
  
有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。 
  
在 Visio 的早期版本中，此函数以 _RUNADDON 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。 
  
## <a name="example-1"></a>示例 1

RUNADDON ("Calendar.exe") 
  
启动名为 Calendar.exe 的Calendar.exe。
  
## <a name="example-2"></a>示例 2

RUNADDON("Array Shapes")
  
启动名为 Array Shapes 的（实现 VSL 功能的）加载项。
  
## <a name="example-3"></a>示例 3

RUNADDON ("ThisDocument.ReportStatistics") 
  
在包含此函数调用的文档项目中，调用 **ThisDocument** 模块中的 ReportStatistics 宏。 
  
> [!NOTE]
>  若要调用 **ThisDocument** 模块中的宏，必须如示例所示，使用“ThisDocument”作为字符串的前缀。 
  
## <a name="example-4"></a>示例 4

RUNADDON (" *ModuleName*  .ReportStatistics")  
  
调用包含此函数调用的文档项目中  *ModuleName*  中的 ReportStatistics 宏。 
  

