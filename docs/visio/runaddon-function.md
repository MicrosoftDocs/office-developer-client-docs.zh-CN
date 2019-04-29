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
description: 在 Microsoft Visual Basic for Applications (VBA) 项目中执行加载项或宏。
ms.openlocfilehash: 280f6eaf1e5db045d8c1d22965df00960d188112
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432007"
---
# <a name="runaddon-function"></a>RUNADDON 函数

在 Microsoft Visual Basic for Applications (VBA) 项目中执行加载项或宏。 
  
## <a name="syntax"></a>语法

RUNADDON (" *string* ") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _string_ <br/> |必需  <br/> |**String** <br/> | **Addons** 集合中的加载项或 VBA 项目中的宏的名称。  <br/> |
   
## <a name="remarks"></a>说明

如果包含 RUNADDON 函数调用的文档项目 (或引用的其他项目) 没有名为_string_的宏 (没有参数的过程), Microsoft Visio 将运行加载项的名为_string_。 如果找不到任何附加的命名_字符串_, Visio 不会执行任何操作, 并且报告不会出错。 (可以使用**TraceFlags**属性监视 Visio 尝试运行的过程和加载项。) 
  
在标准模块中调用过程时, 建议使用包含过程的模块名称为字符串加上前缀 (例如, *procName*), 因为不止一个模块可以有同名的过程。 
  
若要调用包含 RUNADDON 函数调用的文档项目之外的项目中的过程, 请使用语法*projName* (您必须显式设置对 VBA 项目中的*projName*的引用)。 
  
> [!NOTE]
>  从 Visio 2002 开始，RUNADDON 函数无法执行含有任意 VBA 代码的字符串。对于以前传递到 RUNADDON 函数的代码，可以将这些代码移到从该 RUNADDON 函数调用的某个文档的 VBA 项目的过程中。 
  
有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。 
  
在 Visio 的早期版本中，此函数以 _RUNADDON 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。 
  
## <a name="example-1"></a>示例 1

RUNADDON ("Calendar")
  
启动名为 "share.exe" 的加载项。
  
## <a name="example-2"></a>示例 2

RUNADDON("Array Shapes")
  
启动名为 Array Shapes 的（实现 VSL 功能的）加载项。
  
## <a name="example-3"></a>示例 3

RUNADDON ("ThisDocument")
  
在包含此函数调用的文档项目中，调用 **ThisDocument** 模块中的 ReportStatistics 宏。 
  
> [!NOTE]
>  若要调用 **ThisDocument** 模块中的宏，必须如示例所示，使用“ThisDocument”作为字符串的前缀。 
  
## <a name="example-4"></a>示例 4

RUNADDON (" *ModuleName* 。ReportStatistics ") 
  
在包含此函数调用的 document 项目中调用*ModuleName*中的 ReportStatistics 宏。 
  

