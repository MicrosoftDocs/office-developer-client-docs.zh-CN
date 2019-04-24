---
title: RunCode 宏操作
TOCTitle: RunCode macro action
ms:assetid: cb0625be-4b5d-4927-9b0e-59a6e411b5bb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834373(v=office.15)
ms:contentKeyID: 48547706
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm98700
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 646c1393cc798c1f827e6ceaebf46bfe7c87bcbd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306830"
---
# <a name="runcode-macro-action"></a>RunCode 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **RunCode** 操作调用 Visual Basic for Applications (VBA) Function 过程。

## <a name="setting"></a>Setting

**RunCode** 操作具有以下参数。

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
<td><p><strong>函数名称</strong></p></td>
<td><p>要调用的 VBA Function 过程的名称。请将所有函数参数放在括号中。在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“函数名称”</strong>框中输入函数名称。这是一个必选参数。</p><p><strong>注意</strong>: 在 Access 数据库 (.mdb 或 .accdb) 中, 单击 "<strong>生成</strong>" 按钮以使用表达式生成器选择此参数的函数。 在表达式生成器中的列表中单击所需的函数。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

用户定义的 Function 过程都存储在 Microsoft Access 模块中。

即使 Function 过程不具有任何参数，括号也是必需的，如下面的示例所示：

`TestFunction()`

与用于事件属性设置的用户定义的函数名称不同,**函数名称**参数中的函数名称不以等号**=** 开头。

Access 会忽略函数的返回值。

> [!NOTE]
> 如果函数名称与模块名称相同，则不能通过宏调用 Function 过程。

> [!TIP]
> [!提示] 要运行用 Visual Basic 编写的 Sub 过程或事件过程，请创建一个调用 Sub 过程或事件过程的 Function 过程。然后使用 **RunCode** 操作运行该 Function 过程。

If you use the **RunCode** action to call a function, Access looks for the function with the name specified by the **Function Name** argument in the standard modules for the database. However, when this action runs in response to clicking a menu command on a form or report or in response to an event on a form or report, Access first looks for the function in the form's or report's class module and then in the standard modules. Access doesn't search the class modules that appear in the **Modules** area of the Navigation Pane for the function specified by the **Function Name** argument.

此操作不能在 VBA 模块中使用。然而，可以直接在 VBA 中运行所需的 Function 过程。

