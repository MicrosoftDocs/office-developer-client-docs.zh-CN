---
title: StopMacro Macro Action
TOCTitle: StopMacro Macro Action
ms:assetid: 6bbf9026-4536-43f2-aa43-3f2ecea01005
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195473(v=office.15)
ms:contentKeyID: 48545455
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a918fd128456450c21b5a36e74b7266df661cb75
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467236"
---
# <a name="stopmacro-macro-action"></a>StopMacro Macro Action

**适用于**： Access 2013 |Office 2013

您可以使用**StopMacro**操作停止当前正在运行的宏。

## <a name="setting"></a>设置

**StopMacro**操作不具有任何参数。

## <a name="remarks"></a>说明

通常，当条件进行所需停止宏，可使用此操作。 可以在宏中包含此操作的操作行中使用条件表达式。 当在表达式计算结果为**True** (– 1) 时，Microsoft Access 将停止宏。

例如，您可能会创建的宏，打开一个窗体显示每日的顺序总计的自定义对话框中输入的日期。 您可以使用的条件表达式以确保对话框上的**订单日期**控件包含有效的日期。 如果没有， **MessageBox**操作可以显示一条错误消息和**StopMacro**操作可以停止宏。

如果宏已经使用**Echo**或**SetWarnings**操作回响或系统消息的显示， **StopMacro**操作会自动将它们再打开。

此操作在 Visual Basic for Applications (VBA) 模块中不可用。

## <a name="example"></a>示例

下面的宏演示如何使用 **OnError** 操作。 在此示例中， **OnError** 操作指定 Access 在发生错误时运行名为 ErrorHandler 的自定义错误处理宏。 发生错误时，调用 CatchErrors submacro。 如果错误号，2102年显示特定的邮件和暂停宏执行。 否则为显示一条描述错误消息，并将暂停该宏，以便您可以执行其他故障排除。 ErrorHandler 宏会显示一个引用 **MacroError** 对象的消息框，以显示有关该错误的信息。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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
