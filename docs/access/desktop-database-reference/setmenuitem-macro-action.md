---
title: SetMenuItem 宏操作
TOCTitle: SetMenuItem macro action
ms:assetid: 503b3635-e721-1b99-3249-626e5dccdb8a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193803(v=office.15)
ms:contentKeyID: 48544789
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm16614
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: fe61a3368813ba3420920909f818beee2029d993
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308678"
---
# <a name="setmenuitem-macro-action"></a>SetMenuItem 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **SetMenuItem** 操作设置 **"加载项"** 选项卡上的自定义菜单或全局菜单上的菜单项的状态（已启用或已禁用、已选择或未选择）。

> [!NOTE]
> The **SetMenuItem** action works only with custom and global menus created by using menu macros. The **SetMenuItem** action is included in Microsoft Access only for compatibility with previous versions. It does not work with the command bar functionality. However, you can use the **Enabled** and **State** properties in a Visual Basic for Applications (VBA) module to disable or enable and select or unselect items on shortcut menus or custom or global menus.

## <a name="setting"></a>Setting

**SetMenuItem** 操作具有下列参数。

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
<td><p><strong>菜单索引</strong></p></td>
<td><p>包含要设置其状态的命令的菜单的索引。 在自定义或全局菜单中，为所需菜单的索引输入 Integer 数据类型的值（从 0 开始）。 请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“菜单索引”</strong>框中输入索引值。 该索引相对于菜单在自定义菜单或全局菜单的菜单宏中的位置（此菜单的 <strong>AddMenu</strong> 操作在菜单宏中的位置，从 0 开始计数）。 由于您可以在菜单宏中使用条件表达式来隐藏或显示自定义菜单项，因此菜单的显示可能会稍有不同。 这是一个必选参数。 如果您选择带有此参数的菜单并将“命令索引”<strong></strong>和“子命令索引”<strong></strong>参数留空，则您可以启用或禁用菜单名称本身。 但您无法选择或取消选择菜单名称（Access 将忽略菜单名称的“标志”<strong></strong>参数的“选取”<strong></strong>和“不选取”<strong></strong>设置）。</p></td>
</tr>
<tr class="even">
<td><p><strong>命令索引</strong></p></td>
<td><p>要设置其状态的命令的索引。请在通过“菜单索引”<strong></strong>参数选择的菜单中输入所需命令索引的整数值（从 0 开始）。索引相对于命令在为自定义或全局菜单定义选择的菜单的宏组中位置（此命令的宏在宏组中的位置，从 0 开始计数）。由于您可以在菜单的宏组中使用条件表达式来隐藏或显示自定义菜单命令，因此菜单的显示可能会稍有不同。</p></td>
</tr>
<tr class="odd">
<td><p><strong>子命令索引</strong></p></td>
<td><p>要设置其状态的子命令的索引。仅当所需的命令有子菜单时，此参数才适用。在通过“命令索引”<strong></strong>参数选择的子菜单中，输入所需子命令索引的整数值（从 0 开始）。索引相对于子命令在为自定义或全局菜单定义选择的子菜单的宏组中的位置（此子命令的宏在宏组中的位置，从 0 开始计数）。</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>要将命令或子命令设置成的状态。请单击<strong>“变灰”</strong>（禁用命令 - 命令显示为灰色）、<strong>“变实”</strong>（启用该命令）、<strong>“选取”</strong>（在命令旁放置一个选中标记 - 通常指示已选中该命令或已切换到该命令）或<strong>“不选取”</strong>（删除选中标记）。默认值为<strong>“变实”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

**SetMenuItem** 操作仅适用于自定义菜单或全局菜单。如果活动窗口没有自定义菜单或全局菜单，则运行包含 **SetMenuItem** 操作的宏会导致运行时错误。

可以使用此操作设置菜单命令和子命令的状态，但不能设置子命令的子命令的状态。

要在 Visual Basic for Applications (VBA) 模块中运行 **SetMenuItem** 操作，请使用 **DoCmd** 对象的 **SetMenuItem** 方法。

