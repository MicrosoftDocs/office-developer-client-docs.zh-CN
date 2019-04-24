---
title: Echo 宏操作 (Access desktop database reference)
TOCTitle: Echo macro action
ms:assetid: 38dfb2cf-8db5-44b3-91fa-e490932b940b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192516(v=office.15)
ms:contentKeyID: 48544227
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7d536ed47c780b7f9f1675a9879e86aeff80b67f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293621"
---
# <a name="echo-macro-action"></a>Echo 宏操作

**适用于**：Access 2013、Office 2013

可以使用**echo**操作指定是否打开回响。 例如, 可以使用此操作在宏运行时隐藏或显示其结果。

## <a name="setting"></a>Setting

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。

**Echo**操作具有下列参数。

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
<td><p><strong>打开回响</strong></p></td>
<td><p>在 "宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>回响</strong>" 框中, 单击<strong>"是</strong>(打开回响)" 或 "否 (关闭回响)" 框中的 "<strong>否</strong>"。 默认值为 <strong>"是"</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>状态栏文字</strong></p></td>
<td><p>关闭回响时显示在状态栏中的文本。 例如, 当回响关闭时, 状态栏可以显示&quot;宏正在运行。&quot;</p></td>
</tr>
</tbody>
</table>


当宏运行时, 屏幕更新通常会显示不重要的有关宏功能的信息。 当您将 "**打开回响**" 参数设置为 "**否**" 时, 宏将运行, 而不更新屏幕。 当宏完成时, Access 会自动打开回响, 并重新绘制窗口。 "打开**回响**" 参数的 "**无**" 设置不会影响宏或其结果的功能。

**Echo**操作不会禁止显示模式对话框 (如错误消息) 或弹出式窗体 (如属性表)。 您可以使用对话框和弹出窗体来收集或显示信息, 即使关闭了回响也是如此。 若要禁止显示除错误消息框和要求用户输入信息的对话框以外的所有消息或对话框, 请使用**SetWarnings**操作。

您可以在宏中多次运行**Echo**操作。 这使您可以在宏运行时更改状态栏文本。

如果关闭了回响, 则可以使用**DisplayHourglassPointer**操作将鼠标指针更改为沙漏图标 (或为 "忙碌" 设置的任何鼠标指针图标), 以提供宏运行的可视指示。

若要在 Visual Basic for Applications (VBA) 模块中运行**echo**操作, 请使用**DoCmd**对象的**echo**方法。

## <a name="examples"></a>示例

### <a name="set-the-value-of-a-control-by-using-a-macro"></a>使用宏设置控件的值

以下宏将从 "供应商" 窗体上的按钮中打开 "添加产品" 窗体。 它显示了**Echo**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作的使用。 **SetValue**操作将 "产品" 窗体上的 "供应商 ID" 控件设置为 "供应商" 窗体上的当前供应商。 然后, **GoToControl**操作将焦点移到 "类别 ID" 字段, 在其中可以开始为新产品输入数据。 此宏应附加到 "供应商" 窗体上的 "添加产品" 按钮。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作</p></th>
<th><p>参数：设置</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Echo</strong></p></td>
<td><p><strong>打开回响</strong>:<strong>否</strong></p></td>
<td><p>在宏运行时停止屏幕更新。</p></td>
</tr>
<tr class="even">
<td><p><strong>CloseWindow</strong></p></td>
<td><p><strong>对象类型</strong>: <strong>FormObject 名称</strong>: 产品列表是否<strong>保存</strong>:<strong>否</strong></p></td>
<td><p>关闭 "产品列表" 表单。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OpenForm</strong></p></td>
<td><p><strong>表单名称</strong>: 产品<strong>视图</strong>: <strong>FormData 模式</strong>: <strong>AddWindow 模式</strong>: <strong>Normal</strong></p></td>
<td><p>打开 "产品" 窗体。</p></td>
</tr>
<tr class="even">
<td><p><strong>SetValue</strong></p></td>
<td><p><strong>项</strong>: [Forms]![Products]!id<strong>表达式</strong>: 供应商 id</p></td>
<td><p>将 "供应商 ID" 控件设置为 "供应商" 窗体上的当前供应商。</p></td>
</tr>
<tr class="odd">
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>: 类别 id</p></td>
<td><p>转到 "类别 ID" 控件。</p></td>
</tr>
</tbody>
</table>


### <a name="synchronize-forms-by-using-a-macro"></a>使用宏同步窗体

以下宏将打开 "供应商" 窗体右下角的 "产品列表" 窗体, 显示当前供应商的产品。 它演示了如何使用**Echo**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**和**MoveAndSizeWindow**操作。 它还演示了如何使用带有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式。 此宏应附加到 "供应商" 窗体上的 "查看产品" 按钮。

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>条件</p></th>
<th><p>操作</p></th>
<th><p>参数：设置</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>Echo</strong></p></td>
<td><p><strong>打开回响</strong>:<strong>否</strong></p></td>
<td><p>在宏运行时停止屏幕更新。</p></td>
</tr>
<tr class="even">
<td><p>IsNull ([供应商 ID])</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: 移动到要查看其产品的供应商记录, 然后再次单击 "查看产品" 按钮。 <strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: 选择供应商</p></td>
<td><p>如果 "供应商" 窗体上没有当前供应商, 则显示一条消息。</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>: 公司名称</p></td>
<td><p>将焦点移到 "公司名称" 控件。</p></td>
</tr>
<tr class="even">
<td><p>...</p></td>
<td><p><strong>StopMacro</strong></p></td>
<td><p></p></td>
<td><p>停止宏。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>OpenForm</strong></p></td>
<td><p><strong>表单名称</strong>: 产品列表<strong>视图</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where 条件</strong>: [供应商 ID] = [Forms]![供应商]!id<strong>数据模式</strong>:<strong>读取 OnlyWindow 模式</strong>:<strong>普通</strong></p></td>
<td><p>打开 "产品列表" 表单并显示当前供应商的产品。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><strong>MoveAndSizeWindow</strong></p></td>
<td><p><strong>右侧</strong>: 0.7799&quot; <strong></strong>: 1。8&quot;</p></td>
<td><p>将 "产品列表" 窗体放置在 "供应商" 窗体的右下角。</p></td>
</tr>
</tbody>
</table>

