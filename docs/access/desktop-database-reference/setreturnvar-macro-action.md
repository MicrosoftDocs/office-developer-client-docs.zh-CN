---
title: SetReturnVar 宏操作
TOCTitle: SetReturnVar macro action
ms:assetid: 53719857-00bb-4f33-b5d2-93aff92d736e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193989(v=office.15)
ms:contentKeyID: 48544870
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0e0c849fc507d535807bc088e667acd74410ddd8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308671"
---
# <a name="setreturnvar-macro-action"></a>SetReturnVar 宏操作

**适用于**：Access 2013、Office 2013

**SetReturnVar**操作将创建一个返回变量并将其设置为特定值。

> [!NOTE]
> **SetReturnVar**操作仅适用于数据宏。

## <a name="setting"></a>Setting

**SetReturnVar**操作具有下列参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>是</p></td>
<td><p>一个用于指定变量名称的字符串。</p></td>
</tr>
<tr class="even">
<td><p>表达式</p></td>
<td><p>是</p></td>
<td><p>一个用于设置该临时变量的值的表达式。 该表达式不能以等号 (=) 开头。 可以单击 "<strong>生成</strong>" 按钮以使用<strong>表达式生成器</strong>设置此参数。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

**SetReturnVar**操作用于创建**ReturnVar**, 它是一个变量, 可供使用**RunDataMacro**操作调用数据宏的宏使用。

一旦**ReturnVar**由**SetReturnVar**操作创建, 调用宏便可以在表达式中使用它。 例如, 如果您创建了一个名为**UpdateSuccess**的**ReturnVar** , 则可以使用以下语法来使用变量:

```vb
    =[ReturnVars]![UpdateSuccess]
```

**SetReturnVar**操作只能在已命名的数据宏中使用。 它在附加到数据宏事件的数据宏中不可用。

## <a name="example"></a>示例

下面的示例演示如何使用 SetReturnVar 操作从已命名的数据宏中返回值。 名为**CurrentServiceRequest**的 ReturnVar 返回给宏或 Visual Basic for Applications (VBA) 子例程, 该子例程称为已命名的数据宏。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    RunDataMacro
        Macro Name tblServiceRequests.dmGetCurrentServiceRequest
    
    Parameters
        prmAssignedTo =[ID]
    
    SetProperty
        Control Name txtCurrentSR
        Property Value
        Value =[ReturnVars]![CurrentServiceRequest]
```
