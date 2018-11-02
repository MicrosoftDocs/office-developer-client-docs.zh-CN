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
ms.openlocfilehash: 38dc9491a03d2bfa043bddec84efd7fc12c5d08a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919120"
---
# <a name="onerror-macro-action"></a>OnError 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **OnError** 操作指定在宏中发生错误时应出现的情况。

## <a name="setting"></a>设置

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
<td><p>转至</p></td>
<td><p>指定在遇到错误时所应发生的一般行为。请单击下拉箭头，然后单击下列设置之一：</p>
<div class="tableSection">
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>设置</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>下一步</strong></p></td>
<td><p>Microsoft Office Access 2007 在 <strong>MacroError</strong> 对象中记录错误的详细信息，但不会停止该宏。该宏将继续执行下一操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>宏名</strong></p></td>
<td><p>Access 停止当前的宏并运行宏的名为<strong>宏名称</strong>参数中。</p></td>
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
<td><p>如果将转到参数设置为宏名，键入要用于错误处理的宏的名称。 键入的名称必须与当前的宏;<strong>宏名称</strong>列中的名称相匹配不能输入不同宏对象的名称。 在下面的示例中， <strong>ErrorHandler</strong>宏包含在相同<strong>OnError</strong>操作的宏对象。 必须将此参数留空将转到参数设置为<strong>下一步</strong>或<strong>失败</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

- **OnError** 操作通常放在宏的开头，但您也可以将该操作放在宏中比较靠后的位置。该操作建立的规则会在其每次运行时生效。

- 如果您将转到设置为**失败**参数时，访问同样的行为方式如果没有在宏中没有**OnError**操作。 也就是说，如果遇到错误，Access 将停止宏，并显示标准错误消息。 对于**失败**设置的主要用途是关闭之前在宏中建立的任何错误处理。

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
