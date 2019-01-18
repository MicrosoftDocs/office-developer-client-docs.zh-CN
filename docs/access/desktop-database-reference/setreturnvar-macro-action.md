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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708156"
---
# <a name="setreturnvar-macro-action"></a>SetReturnVar 宏操作

**适用于**： Access 2013、 Office 2013

**SetReturnVar**操作创建返回变量，并将其设置为特定值。

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
<th><p>是否必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名称</p></td>
<td><p>是</p></td>
<td><p>一个用于指定变量名称的字符串。</p></td>
</tr>
<tr class="even">
<td><p>表达式</p></td>
<td><p>是</p></td>
<td><p>一个表达式，用于设置为临时变量的值。 不在表达式前面放等号 （=）。 您可以单击<strong>生成</strong>按钮以使用<strong>表达式生成器</strong>设置此参数。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>备注

**SetReturnVar**操作用于创建**ReturnVar**，这是可供使用**RunDataMacro**操作调用的数据宏的宏的变量。

**SetReturnVar**操作创建**ReturnVar**后，调用宏可以使用它在表达式中。 例如，如果您创建名为**UpdateSuccess** **ReturnVar** ，您可以使用该变量使用以下语法：

```vb
    =[ReturnVars]![UpdateSuccess]
```

**SetReturnVar**操作可仅在命名的数据宏。 不适用于数据宏附加到的数据宏事件。

## <a name="example"></a>示例

下面的示例演示如何使用 SetReturnVar 操作从已命名的数据宏返回值。 名为**CurrentServiceRequest** ReturnVar 调用已命名的数据宏的 Applications (VBA) 子例程返回到宏或 Visual Basic。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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
