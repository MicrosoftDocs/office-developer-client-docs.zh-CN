---
title: RunMacro 宏操作
TOCTitle: RunMacro macro action
ms:assetid: 25966f20-8160-0821-b88a-ed08b7786fdc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191868(v=office.15)
ms:contentKeyID: 48543787
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm43195
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: d9e86fb7d60af94d6ecde71b2a857a3cc5b9bcb8
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712335"
---
# <a name="runmacro-macro-action"></a>RunMacro 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **RunMacro** 操作运行宏。宏可以包括在宏组中。

可以使用此操作：

- 从另一个宏内运行某个宏。

- 基于某个条件运行宏。

- 将宏附加到自定义菜单命令中。

## <a name="setting"></a>设置

**RunMacro** 操作具有下列参数。

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
<td><p><strong>宏名</strong></p></td>
<td><p>要运行的宏的名称。 宏生成器窗格的<strong>宏名称</strong>框在<strong>操作参数</strong>部分中显示当前数据库中的所有宏 （和宏组）。 如果宏组中的宏，它是否列出在列表中的宏组名称下为<em>macrogroupname</em>。<em>macroname</em>。 这是必需参数。 如果在类库数据库中运行包含 <strong>RunMacro</strong> 操作的宏，Microsoft Access 将在该类库数据库中查找具有此名称的宏，而不会在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p><strong>重复次数</strong></p></td>
<td><p>宏将运行最大次数。 如果将此参数留空 （和<strong>重复表达式</strong>参数也是空），宏将运行一次。</p></td>
</tr>
<tr class="odd">
<td><p><strong>重复表达式</strong></p></td>
<td><p>计算结果为<strong>“True”</strong>(–1) 或<strong>“False”</strong>(0) 的表达式。如果表达式的计算结果为<strong>“False”</strong>，宏将停止运行。宏每次运行时都会计算该表达式。</p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a>说明

如果您输入宏组名为**宏名称**参数，Access 将运行宏组中的第一个宏。

此操作类似于单击 **"数据库工具"** 选项卡上的 **"运行宏"**，选择宏，然后单击 **"确定"**。但是，此命令仅运行一次宏，而 **RunMacro** 操作则可以将宏运行任意次。

> [!TIP]
> 您可以使用的**重复次数**和**重复表达式**参数确定宏将运行的次数：
> - 如果将这两个参数均留空，宏将运行一次。
> - 如果您的**重复次数**输入号码，但保留**重复表达式**为空，宏将运行指定的次数。
> - 如果您将**重复次数**保留为空，但为**重复表达式**输入一个表达式，宏将运行，直到该表达式的计算结果为**False**。
> - 如果为这两个参数，则宏将运行的次数指定在**重复次数**或直到**重复表达式**计算结果为**False**，输入值前进哪个事件首先发生。

在运行包含 **RunMacro** 操作的宏并且该宏执行到 **RunMacro** 操作时，Access 将运行被调用的宏。在被调用的宏运行完后，Access 将继续运行原来的宏并运行下一个操作。

> [!NOTE]
> - 可以调用同一个宏组或者另一个宏组中的宏。
> - 可以嵌套宏。也就是说，您可以运行宏 A，宏 A 继而调用宏 B，依此类推。在每种情况下，当被调用的宏运行完后，Access 将继续运行调用它的宏并运行该宏中的下一个操作。

要在 Visual Basic for Applications (VBA) 模块中运行 **RunMacro** 操作，请使用 **DoCmd** 对象的 **RunMacro** 方法。

