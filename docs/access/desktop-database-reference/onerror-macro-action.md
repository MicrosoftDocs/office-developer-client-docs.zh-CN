---
title: OnError 宏操作
TOCTitle: OnError macro action
ms:assetid: 5c6073c4-2c0f-0ed2-83b0-477636e2d81c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194562(v=office.15)
ms:contentKeyID: 48545088
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm62274
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a2288d64241f3289505a8b0fafb98062830b0e97
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288453"
---
# <a name="onerror-macro-action"></a>OnError 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **OnError** 操作指定在宏中发生错误时应出现的情况。

## <a name="setting"></a>Setting

**OnError** 操作具有下列参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>转到</p></td>
<td><p>指定在遇到错误时所应发生的一般行为。请单击下拉箭头，然后单击下列设置之一：</p>
<div class="tableSection">
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Setting</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Next</strong></p></td>
<td><p>Microsoft Office Access 2007 在 <strong>MacroError</strong> 对象中记录错误的详细信息，但不会停止该宏。该宏将继续执行下一操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>宏名</strong></p></td>
<td><p>Access 停止当前的宏并运行在“宏名”<strong></strong>参数中命名的宏。</p></td>
</tr>
<tr class="odd">
<td><p><strong>失败</strong></p></td>
<td><p>Access 停止当前的宏并显示一条错误消息。</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>宏名</p></td>
<td><p>如果 "转到" 参数设置为 "宏名", 请键入要用于错误处理的宏的名称。 键入的名称必须与当前宏的 "<strong>宏名称</strong>" 列中的名称相匹配;不能输入一个不同的宏对象的名称。 在下面的示例中, <strong>ErrorHandler</strong>宏包含在与<strong>OnError</strong>操作相同的宏对象中。 如果 "转到" 参数设置为 "<strong>下一个</strong>" 或 "<strong>失败</strong>", 则此参数必须为空。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

- **OnError** 操作通常放在宏的开头，但您也可以将该操作放在宏中比较靠后的位置。该操作建立的规则会在其每次运行时生效。

- If you set the Go to argument to **Fail**, Access behaves the same way it would if there were no **OnError** action in the macro. That is, if an error is encountered, Access stops the macro and displays a standard error message. The main use for the **Fail** setting is to turn off any error handling that you established earlier in a macro.

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
