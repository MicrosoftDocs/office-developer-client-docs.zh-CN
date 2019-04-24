---
title: StopMacro 宏操作
TOCTitle: StopMacro macro action
ms:assetid: 6bbf9026-4536-43f2-aa43-3f2ecea01005
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195473(v=office.15)
ms:contentKeyID: 48545455
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fe319e0f7a811d3bcd3b2fc18c4a3d951187fbe8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308496"
---
# <a name="stopmacro-macro-action"></a>StopMacro 宏操作

**适用于**：Access 2013、Office 2013

您可以使用**StopMacro**操作来停止当前正在运行的宏。

## <a name="setting"></a>Setting

**StopMacro**操作不具有任何参数。

## <a name="remarks"></a>注解

通常在条件导致需要停止宏时使用此操作。 可以在宏中包含此操作的操作行中使用条件表达式。 当表达式的计算结果为**True** (– 1) 时, Microsoft Access 将停止宏。

例如, 您可以创建一个宏, 打开一个窗体, 该窗体显示在自定义对话框中输入的日期的每日订单总数。 您可以使用条件表达式, 以确保对话框上的 "**排序日期**" 控件包含有效的日期。 如果不是这样, 则**MessageBox**操作可以显示一条错误消息, 并且**StopMacro**操作可以停止宏。

如果宏已经使用**echo**或**SetWarnings**操作关闭了回响或系统消息的显示, 则**StopMacro**操作会自动将其重新打开。

此操作在 Visual Basic for Applications (VBA) 模块中不可用。

## <a name="example"></a>示例

下面的宏演示如何使用 **OnError** 操作。 在此示例中， **OnError** 操作指定 Access 在发生错误时运行名为 ErrorHandler 的自定义错误处理宏。 发生错误时, 将调用 CatchErrors submacro。 如果错误号为 2102, 则显示一条特定消息, 并停止宏的执行。 否则, 将显示描述错误的消息, 并暂停宏, 以便您可以执行其他故障排除。 ErrorHandler 宏会显示一个引用 **MacroError** 对象的消息框，以显示有关该错误的信息。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    /* MACRO: mcrThrowErrors                                  */
    /* PURPOSE: Error handling using macros in Access 2010    */
    
    OnError
        Go to Macro Name
        Macro Name CatchErrors
    
    OpenForm 
        Form Name frmSamples
        View Form
        Filter Name
        Where Condition
        Data Mode
        Window Mode Normal
    
    MessageBox 
        Message This message appears after the OpenForm action
        Beep Yes
        Type None
        Title
    
    
    /* SUBMACRO: CatchErrors                                   */
    
    SubMacro: CatchErrors
        If [MacroError].[Number]=2101 Then
            MessageBox
                Message Cannot find the specified form!
                Beep Yes
                Type Critical
                Title
            StopMacro
    
        Else
            MessageBox
                Message =[MacroErro].[Description]
                Beep Yes
                Type None
                Title Unhandled Error
    
            SingleStep
        End If
    
    End SubMacro
```
