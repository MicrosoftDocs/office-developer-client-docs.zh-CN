---
title: SetMenuItem 宏操作
TOCTitle: SetMenuItem Macro Action
ms:assetid: 503b3635-e721-1b99-3249-626e5dccdb8a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193803(v=office.15)
ms:contentKeyID: 48544789
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm16614
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d7a7de3d627dacfa0ca014a80ea037d0728220d1
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873563"
---
# <a name="setmenuitem-macro-action"></a>SetMenuItem 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **SetMenuItem** 操作设置 **"加载项"** 选项卡上的自定义菜单或全局菜单上的菜单项的状态（已启用或已禁用、已选择或未选择）。


> [!NOTE]
> <P><STRONG>SetMenuItem</STRONG>操作仅适用于使用菜单宏创建的自定义和全局菜单。 仅为与早期版本兼容的 Microsoft Access 包含<STRONG>SetMenuItem</STRONG>操作。 不适用于命令栏功能。 但是，您可以使用在 Visual Basic for Applications (VBA) 模块禁用或启用并选择或取消选择快捷菜单上的项目中<STRONG>启用</STRONG>和<STRONG>状态</STRONG>属性或自定义或全局菜单。</P>



## <a name="setting"></a>设置

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
<td><p>包含您要为其设置的状态的命令的菜单的索引。 输入从 0，需菜单自定义或全局菜单中的索引的整数值。 在宏生成器窗格的<strong>操作参数</strong>部分的<strong>菜单索引</strong>框中输入的索引值。 索引是相对于菜单宏自定义或全局菜单 （此菜单<strong>AddMenu</strong>操作在菜单宏，从 0 开始计数的位置） 中的菜单上的位置。 菜单的显示可能有所不同，因为您可以在菜单宏中使用条件表达式，隐藏或显示自定义菜单项。 这是必需参数。 如果您选择菜单与此参数，并将<strong>命令索引</strong>和<strong>子命令索引</strong>参数留空，您可以启用或禁用菜单名称本身。 但是，不能选择或取消选择菜单名称 （访问忽略菜单名为<strong>标志</strong>参数<strong>检查</strong>和<strong>取消选中</strong>设置）。</p></td>
</tr>
<tr class="even">
<td><p><strong>命令索引</strong></p></td>
<td><p>您要为其设置的状态命令的索引。 输入所需的命令通过<strong>菜单索引</strong>参数选定的菜单中的索引为 0，启动一个整数值。 索引是宏的相对于定义自定义或全局菜单 （宏组中，从 0 开始计数中该命令的位置） 的所选的菜单宏组中的命令的位置。 菜单的显示可能有所不同，因为您可以在菜单的宏组中使用条件表达式可隐藏或显示自定义菜单命令。</p></td>
</tr>
<tr class="odd">
<td><p><strong>子命令索引</strong></p></td>
<td><p>您要为其设置的状态的子命令索引。 这仅适用于所需的命令具有子菜单。 输入所需子<strong>命令索引</strong>参数选择子菜单中的索引为 0，启动一个整数值。 索引是宏的相对于定义自定义或全局菜单 （从 0 开始计数的宏组中的此子命令位置） 所选子菜单宏组中的子命令的位置。</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>要将命令或子命令设置成的状态。请单击<strong>“变灰”</strong>（禁用命令 - 命令显示为灰色）、<strong>“变实”</strong>（启用该命令）、<strong>“选取”</strong>（在命令旁放置一个选中标记 - 通常指示已选中该命令或已切换到该命令）或<strong>“不选取”</strong>（删除选中标记）。默认值为<strong>“变实”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

**SetMenuItem** 操作仅适用于自定义菜单或全局菜单。如果活动窗口没有自定义菜单或全局菜单，则运行包含 **SetMenuItem** 操作的宏会导致运行时错误。

可以使用此操作设置菜单命令和子命令的状态，但不能设置子命令的子命令的状态。

要在 Visual Basic for Applications (VBA) 模块中运行 **SetMenuItem** 操作，请使用 **DoCmd** 对象的 **SetMenuItem** 方法。

