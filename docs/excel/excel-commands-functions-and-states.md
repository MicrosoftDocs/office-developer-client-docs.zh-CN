---
title: Excel 命令、函数和状态
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- '[excel 2007] 的状态、 命令 [Excel 2007]、 工作表函数 [Excel 2007]、 宏工作表函数 [Excel 2007]、 Excel 状态'
localization_priority: Normal
ms.assetid: 20f19aa4-f184-47be-bcdd-7ded78778974
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 60977216663fb2492f425a9b7c855b77815f0e7b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773671"
---
# <a name="excel-commands-functions-and-states"></a>Excel 命令、函数和状态

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 能识别两种非常不同类型的新增功能： 命令和函数。
  
## <a name="commands"></a>命令

在 Excel 中，命令具有以下特征：
  
- 他们在用户执行的相同方式执行操作。
    
- 它们可以执行任何操作的用户可以执行 (使用的接口的限制到的 subject) 更改 Excel 设置、 打开、 关闭和编辑文档，如启动重新计算，等等。
    
- 他们可以设置某些发生了已捕获的事件发生时调用。
    
- 他们可以显示对话框，并与用户交互。
    
- 它们可以链接来控制对象，以便他们对该对象，例如单击鼠标左键执行某些操作时调用。
    
- 会永远不会调用 Excel 重新计算过程中。
    
- 他们不能调用函数过程中重新计算。
    
## <a name="functions"></a>函数

在 Excel 中的功能执行以下操作：
  
- 他们通常采用参数并始终返回结果。
    
- 它们可以输入到一个或多个单元格中 Excel 公式的一部分。
    
- 它们可在定义的名称定义。
    
- 它们可在条件格式限制和阈值表达式。
    
- 它们可通过命令调用。
    
- 他们不能调用命令。
    
Excel 将用户定义的工作表函数和旨在配合使用宏工作表上的用户定义函数进一步区别。 Excel 不会限制仅对宏工作表上使用的用户定义的宏工作表函数： 这些功能可以使用任意位置可正常工作表函数。
  
### <a name="worksheet-functions"></a>工作表函数

以下是 true 的 Excel 工作表函数：
  
- 他们无法访问宏工作表信息函数。
    
- 他们无法获取未计算的单元格的值。
    
- 他们可以编写并注册为 Excel 2007 中的线程安全启动。
    
### <a name="macro-sheet-functions"></a>宏工作表函数

以下是 true 的 Excel 宏工作表函数：
  
- 他们可以访问宏工作表信息函数。
    
- 它们可以获取包括调用单元格的值的未计算单元格的值。
    
- 它们不被视为线程安全 Excel 2007 中启动。
    
Excel 如何处理用户定义函数 (UDF)，它还允许函数执行，并重新计算的方式，注册功能时，是所有确定该函数。 如果函数注册为工作表函数，但试图执行一些只有宏工作表函数可以执行操作，则操作将失败。 从 Excel 2007 中，如果尝试调用宏工作表函数注册为线程安全的工作表函数，同样，则操作将失败。
  
Excel 视为 Microsoft Visual Basic for Applications (VBA) Udf 宏工作表的等价函数，他们可以访问工作区信息和未计算的单元格的值，并且它们不会考虑如线程在 Excel 2007 中的安全启动。
  
## <a name="excel-states"></a>Excel 状态

Excel 中可以许多状态之一在任何给定时间，具体取决于用户、 外部进程、 发生了已捕获的事件运行宏或如**自动保存**定时的 Excel 内部管理事件的操作。
  
用户体验的状态如下所示：
  
- **准备状态：** 正在运行任何命令或宏。 要不显示的任何对话框。 正在编辑没有单元格，并且用户不剪切/复制和粘贴操作过程。 没有嵌入的对象具有焦点。 
    
- **编辑模式：** 用户开始输入的有效字符单元格中键入未锁定或未受保护，或者已对一个或多个未锁定或未受保护的单元格按**F2** 。 
    
- **剪切/复制和粘贴模式：** 用户具有剪切或复制单元格区域和具有不尚未粘贴，或具有粘贴它们使用选择性粘贴对话框，允许多个粘贴操作。 
    
- **点模式：** 用户正在编辑公式，则选择其地址会添加到正在编辑的公式的单元格。 
    
用户可以通过按**ESC**键，Excel 返回其准备状态清除编辑、 点和剪切/复制模式。 其他事件可以清除这些状态，如下所示： 
  
- 用户打开一个内置对话框。
    
- 用户启动的重新计算。
    
- 用户运行命令。
    
- Excel 执行**自动保存**操作。 
    
- 捕获 timer 事件。
    
最后一个示例是重要性以外接程序的开发人员。 您应考虑的常用的 timer 事件捕获其中的 Excel 的普通可用性影响被设置和执行。 这是外接程序的功能的重要组成部分，应将用户提供为挂起，以便他们可以剪切/复制并粘贴通常时需轻松访问方法。
  
## <a name="see-also"></a>另请参阅



[Excel Programming Concepts](excel-programming-concepts.md)
  
[在长时间的操作中允许用户中断](permitting-user-breaks-in-lengthy-operations.md)

