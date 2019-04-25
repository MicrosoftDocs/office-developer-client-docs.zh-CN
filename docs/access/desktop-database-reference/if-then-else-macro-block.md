---
title: If...Then...Else 宏程序块
TOCTitle: If...Then...Else macro block
ms:assetid: 0c4a4b7a-4fdb-9dbc-a94e-939a2ff1c0e5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845158(v=office.15)
ms:contentKeyID: 48543188
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: fb6cbd6cc925a3e4841d9e7d6d77332cc36c7a03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291892"
---
# <a name="ifthenelse-macro-block"></a>If...Then...Else 宏程序块


**适用于**：Access 2013、Office 2013

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

对于 **If** 和 **Else If**，以下参数是必需的。

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
<td><p>要测试的条件。 它必须是一个计算结果为 True 或 False 的表达式。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

当您选择 **If** 宏程序块时，会出现一个文本框，可在其中输入代表要测试的条件的表达式。此外，还会出现一个可插入宏操作的组合框，它下面会自动显示文本"End If"。If 和 End If 括起一个区域，可在其中输入操作组或块。仅当您输入的表达式为 True 时，该块才会执行。

To evaluate a different expression when the first expression is false, you can click **Add Else If** to insert an optional **Else If** block. You must enter an expression that evaluates to True or False. In this case, the block executes only if the expression is True and the first expression is False.

您可以根据需要向 If 块中添加任意多个 **Else If** 块。

You can click **Add Else** to insert an optional **Else** block. In this case, the actions that you insert below the **Else** form the **Else** block, which executes only when the actions above do not. You can add a single **Else** block to an **If** block.

在下面的代码示例中，如果 \[Status\] 的值大于 0，将执行第一个块中的宏操作。 如果 \[Status\] 的值不大于 0，则计算 **Else If** 之后的表达式。 如果 \[Status\] 的值等于 0，将执行 **Else If** 块中的宏操作。 最后，如果第一个块和第二个块都不执行，则执行 **Else** 块中的操作。

```vb
    If [Status] > 0 Then 
     Insert macro actions here ... 
    Else If [Status] = 0 
     Insert macro actions here ... 
    Else 
     Insert macro actions here ... 
    End If
```

您可以嵌套 **If** 块。 如果要在第一个表达式为 True 时计算另一个表达式，则应考虑在 **If** 块中嵌套一个 **If** 块。 在下面的代码示例中，仅当 \[Status\] 的值既大于 0 *又*大于 100 时，才会执行内部 **If** 块。

```vb
    If [Status] > 0 Then 
     Insert macro actions here ... 
     If [Status] > 100 
     Insert macro actions here ... 
     EndifEnd If
```
