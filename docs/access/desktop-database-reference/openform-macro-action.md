---
title: OpenForm 宏操作
TOCTitle: OpenForm macro action
ms:assetid: c519a9d7-99d4-4765-ad96-59c3fe1be9e3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823095(v=office.15)
ms:contentKeyID: 48547604
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cf89b61a65c11f09d5a07e52caeee5ad416c118a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288369"
---
# <a name="openform-macro-action"></a>OpenForm 宏操作

**适用于**：Access 2013、Office 2013

可以使用**OpenForm**操作在 "窗体" 视图、"设计" 视图、"打印预览" 或 "数据表" 视图中打开窗体。 可以选择窗体的数据输入模式和窗口模式，并限制窗体显示的记录。

## <a name="setting"></a>Setting

**OpenForm**操作具有下列参数。

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
<td><p><strong>表单名称</strong></p></td>
<td><p>要打开的窗体的名称。 "宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>窗体名称</strong>" 框中显示了当前数据库中的所有窗体。 这是必需参数。 如果在类库数据库中运行包含<strong>OpenForm</strong>操作的宏, Microsoft Access 将先在该类库数据库中查找具有此名称的窗体, 然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p><strong>View</strong></p></td>
<td><p>将在其中打开表单的视图。 单击 "<strong>视图</strong>" 框中的 "<strong>窗体</strong>、<strong>设计</strong>、<strong>打印预览</strong>、<strong>数据表</strong>、<strong>数据透视表</strong>" 或 "数据<strong>透视图</strong>"。 默认值为<strong>Form</strong>。</p><p><strong>注意</strong>: "<STRONG>查看</STRONG>" 参数设置将覆盖窗体的 "<STRONG>默认</STRONG>视图<STRONG></STRONG> " 和 "已视图" 属性的设置。 例如, 如果将窗体的 "可<STRONG>视图</STRONG>" 属性设置为<STRONG>"数据表</STRONG>", 仍可以使用<STRONG>OpenForm</STRONG>操作在 "窗体" 视图中打开窗体。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Filter Name</strong></p></td>
<td><p>限制或对窗体的记录进行排序的筛选器。 您可以输入现有查询的名称，也可以输入另存为查询的筛选的名称。 但是, 查询必须包含要打开的窗体中的所有字段, 或者将其<strong>输出</strong>所有字段设置为<strong>"是"</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>Where 条件</strong></p></td>
<td><p>Access 用于从窗体的基础表或查询中选择记录的有效 SQL WHERE 子句 (不含 word WHERE) 或表达式。 如果您通过“筛选名称”<strong></strong>参数选择筛选，Access 会将此 WHERE 子句应用于筛选的结果。 若要打开一个窗体并将其记录限制为由另一个窗体上的某个控件的值指定的记录, 请使用以下表达式: <strong>[</strong><em>fieldname</em><strong>] = Forms! [</strong><em>formname</em><strong>]![</strong><em>controlname 在其他窗体上</em>使用<strong>]</strong>将<em>fieldname</em>替换为要打开的窗体的基础表或查询中的字段的名称。 将其他表单<em>上</em>的<em>formname</em>和 controlname 替换为其他窗体的名称, 并将另一个窗体上的控件替换为您希望第一个窗体中的记录与之匹配的值。</p><p><strong>注意</strong>: <STRONG>Where Condition</STRONG>参数的最大长度为255个字符。 如果需要输入更复杂的 SQL WHERE 子句, 请改用 Visual Basic for Applications (VBA) 模块中<STRONG>DoCmd</STRONG>对象的<STRONG>OpenForm</STRONG>方法。 在 VBA 中，可输入长达 32,768 个字符的 SQL WHERE 子句语句。</p></td>
</tr>
<tr class="odd">
<td><p><strong>数据模式</strong></p></td>
<td><p>表单的数据输入模式。 这仅适用于在窗体视图或数据表视图中打开的窗体。 请单击<strong>“添加”</strong>（用户可添加新记录，但不能编辑现有记录）、<strong>“编辑”</strong>（用户可编辑现有记录和添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。 默认值为<strong>“编辑”</strong>。 <strong>Notes</strong></p>
<ul>
<li><p>"<strong>数据模式</strong>" 参数设置将替代表单的 "<strong>允许编辑</strong>"、" <strong></strong>允许删除" <strong></strong> 、"允许添加" 和 "输入" 属性的设置。 <strong></strong> 例如, 如果窗体的<strong>允许</strong>编辑属性设置为 "<strong>否</strong>", 仍可以使用<strong>OpenForm</strong>操作在编辑模式下打开该窗体。</p></li>
<li><p>如果将此参数留空, Access 将打开 "数据输入" 模式中由窗体的<strong>允许编辑、允许</strong>删除<strong></strong>、允许添加<strong></strong>和添加属性设置的窗体。 <strong></strong></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>窗口模式</strong></p></td>
<td><p>打开窗体时所用的窗口模式。 单击 "<strong>普通</strong>" (窗体将在由其属性设置的模式中打开)、"<strong>隐藏</strong>(隐藏窗体)"、"<strong>图标</strong>" (窗体打开时最小化为屏幕底部的小标题栏) 或<strong>对话框</strong>(窗体的<strong>模式</strong>和<strong>弹出菜单)</strong>属性设置为<strong>"是"</strong>)。 默认值为<strong>“普通”</strong>。</p><p><strong>注意</strong>: 使用选项卡式文档时, 某些<STRONG>窗口模式</STRONG>参数设置不适用。 要切换到重叠窗口，请执行下列操作：</p>
<ol>
<li><p>单击 "文件" 选项卡, 然后单击 "<strong>选项</strong>"。</p></li>
<li><p>在<strong>“Access 选项”</strong>对话框中，单击<strong>“当前数据库”</strong>。</p></li>
<li><p>在 "<strong>应用程序选项</strong>" 部分的 "<strong>文档窗口选项</strong>" 下, 单击 "<strong>重叠窗口</strong>"。</p></li>
<li><p>单击<strong>“确定”</strong>，然后关闭并重新打开数据库。</p></li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

此操作类似于在导航窗格中双击窗体, 或者右键单击导航窗格中的窗体, 然后选择视图。

窗体可以是模式的 (在用户可以执行任何其他操作之前, 必须将其关闭或隐藏) 或无模式 (用户可以在窗体处于打开状态时移动到其他窗口)。 它还可以是弹出式窗体 (用于收集或显示在所有其他 Access 窗口顶部的信息的窗体)。 您在设计窗体时设置了**Modal**和**PopUp**属性。 如果对 "**窗口模式**" 参数使用 "**常规**", 则该窗体将以这些属性设置指定的模式打开。 如果将**对话框**用于**窗口模式**参数, 则这些属性都设置为 **"是"**。 作为隐藏或图标打开的窗体将返回到显示或还原时其属性设置所指定的模式。

打开 "**窗口模式**" 参数设置为 "**对话框**" 的窗体时, Access 将挂起宏, 直到窗体关闭或隐藏。 您可以通过使用**SetValue**操作将窗体的**Visible**属性设置为 "**否**" 来隐藏窗体。

> [!TIP]
> 您可以在导航窗格中选择窗体并将其拖动到宏操作行。 这会自动创建一个在 "窗体" 视图中打开窗体的**OpenForm**操作。

应用的筛选和 WHERE 条件将成为窗体的**filter**属性的设置。

## <a name="examples"></a>示例

**使用宏设置控件的值**

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


以下宏将打开 "供应商" 窗体右下角的 "产品列表" 窗体, 显示当前供应商的产品。 它演示了如何使用**Echo**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**和**MoveAndSizeWindow**操作。 它还演示了如何使用带有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式。 此宏应附加到 "供应商" 窗体上的 "查看产品" 按钮。

**使用宏同步窗体**

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
<td><p>IsNull ([供应商 id])</p></td>
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
<td><p><strong>表单名称</strong>: 产品列表<strong>视图</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where 条件</strong>: [供应商 id] = [Forms]![供应商]!id<strong>数据模式</strong>:<strong>读取 OnlyWindow 模式</strong>:<strong>普通</strong></p></td>
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

