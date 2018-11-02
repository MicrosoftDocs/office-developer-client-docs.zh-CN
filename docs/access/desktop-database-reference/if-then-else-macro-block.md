---
title: If...Then...Else 宏程序块
TOCTitle: If...Then...Else macro block
ms:assetid: 0c4a4b7a-4fdb-9dbc-a94e-939a2ff1c0e5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845158(v=office.15)
ms:contentKeyID: 48543188
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c671ced7d3de2ce461af3bcf0a5d832e092bbf17
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922935"
---
# <a name="ifthenelse-macro-block"></a>If...Then...Else 宏程序块


**适用于**： Access 2013、 Office 2013

可以使用 **If** 宏程序块，根据表达式的值有条件地执行一组操作。

```vb
    If expression Then 
     Insert macro actions here ... 
    Else If expression 
     Insert macro actions here ... 
    Else 
     Insert macro actions here ... 
    End If
```

## <a name="setting"></a>设置

**如果**和**Else If**，以下参数是必需的。

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
<td><p><strong>Expression</strong></p></td>
<td><p>您要测试的条件。 它必须是表达式的计算结果为 True 或 False。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

当您选择 **If** 宏程序块时，会出现一个文本框，可在其中输入代表要测试的条件的表达式。此外，还会出现一个可插入宏操作的组合框，它下面会自动显示文本"End If"。If 和 End If 括起一个区域，可在其中输入操作组或块。仅当您输入的表达式为 True 时，该块才会执行。

表达式进行求值不同的第一个表达式为 false 时，您可以单击**添加 Else If**插入一个可选的**Else If**块。 您必须输入表达式，其计算结果 True 或 False。 在这种情况下，阻止执行仅当表达式为 True 且的第一个表达式为 False。

您可以根据需要向 If 块中添加任意多个 **Else If** 块。

您可以单击**添加其他人**要插入可选的**Else**块。 在这种情况下， **Else**下方插入操作窗体的**Else**块中，仅当上述操作不会执行。 您可以向**If**块添加单个**Else**块。

下面的代码示例中的第一个块中的宏操作执行如果的值\[状态\]大于 0。 如果值\[状态\]不大于 0，计算**Else If**遵循的表达式。 如果执行**Else If**块中的宏操作的值\[状态\]等于 0。 最后，如果第一个块和第二个块都不执行，则执行 **Else** 块中的操作。

```vb
    If [Status] > 0 Then 
     Insert macro actions here ... 
    Else If [Status] = 0 
     Insert macro actions here ... 
    Else 
     Insert macro actions here ... 
    End If
```

您可以嵌套 **If** 块。 如果要在第一个表达式为 True 时计算另一个表达式，则应考虑在 **If** 块中嵌套一个 **If** 块。 在下面的代码示例中，内部**If**块仅时，会执行的值\[状态\]同时大于 0*和*大于 100。

```vb
    If [Status] > 0 Then 
     Insert macro actions here ... 
     If [Status] > 100 
     Insert macro actions here ... 
     EndifEnd If
```
