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
description: 在 Microsoft Visual Basic for Applications (VBA) 项目执行加载项或宏。
ms.openlocfilehash: 31ac32c742827311d8aaee4547024ad97d2c48e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781212"
---
# <a name="runaddon-function"></a>RUNADDON 函数

在 Microsoft Visual Basic for Applications (VBA) 项目执行加载项或宏。 
  
## <a name="syntax"></a>语法

RUNADDON （"*字符串*"） 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _string_ <br/> |必需  <br/> |**字符串** <br/> | **Addons** 集合中的加载项或 VBA 项目中的宏的名称。  <br/> |
   
## <a name="remarks"></a>说明

如果包含 RUNADDON 函数调用的文档项目 （或另一个项目，如果它引用） 不具有一个名为_字符串_的宏 （不带任何参数的过程），Microsoft Visio 将运行名为_字符串_的加载项。 如果找不到名为_字符串_没有加载项，Visio 将不执行任何操作，并不报告任何错误。 （您可以使用**TraceFlags**属性要监视的过程和 Visio 尝试运行的加载项。） 
  
当标准模块中调用过程时，建议您前缀与包含 (例如， *moduleName.procName*)，该过程的模块名称的字符串，因为多个模块可以具有相同名称的过程。 
  
在项目中调用过程以外的其他项目的文档的包含 RUNADDON 函数调用，使用语法*projName.modName.procName* （必须具有显式设置引用*projName* VBA 项目中）。 
  
> [!NOTE]
>  从 Visio 2002 开始，RUNADDON 函数无法执行含有任意 VBA 代码的字符串。对于以前传递到 RUNADDON 函数的代码，可以将这些代码移到从该 RUNADDON 函数调用的某个文档的 VBA 项目的过程中。 
  
有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。 
  
在 Visio 的早期版本中，此函数以 _RUNADDON 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。 
  
## <a name="example-1"></a>示例 1

RUNADDON("Calendar.exe")
  
启动名为 Calendar.exe 的加载项。
  
## <a name="example-2"></a>示例 2

RUNADDON("Array Shapes")
  
启动名为 Array Shapes 的（实现 VSL 功能的）加载项。
  
## <a name="example-3"></a>示例 3

RUNADDON("ThisDocument.ReportStatistics")
  
在包含此函数调用的文档项目中，调用 **ThisDocument** 模块中的 ReportStatistics 宏。 
  
> [!NOTE]
>  若要调用 **ThisDocument** 模块中的宏，必须如示例所示，使用“ThisDocument”作为字符串的前缀。 
  
## <a name="example-4"></a>示例 4

RUNADDON (" *ModuleName* 。ReportStatistics") 
  
调用*ModuleName*中包含此函数调用的文档项目中的 ReportStatistics 宏。 
  

