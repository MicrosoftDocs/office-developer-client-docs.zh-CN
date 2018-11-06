---
title: OpenForm 宏操作
TOCTitle: OpenForm macro action
ms:assetid: c519a9d7-99d4-4765-ad96-59c3fe1be9e3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823095(v=office.15)
ms:contentKeyID: 48547604
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c1813a80c43eb77f8fb90442ecd6e0336b636191
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998971"
---
# <a name="openform-macro-action"></a>OpenForm 宏操作

**适用于**： Access 2013、 Office 2013

您可以使用**OpenForm**操作窗体视图、 设计视图、 打印预览或数据表视图中打开窗体。 可以选择窗体的数据输入模式和窗口模式，并限制窗体显示的记录。

## <a name="setting"></a>设置

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
<td><p>要打开的窗体名称。 宏生成器窗格的<strong>窗体名称</strong>框在<strong>操作参数</strong>部分中显示当前数据库中的所有窗体。 这是必需参数。 如果您运行包含类库数据库中的<strong>OpenForm</strong>操作的宏，Microsoft Access 首先查找具有此名称在类库数据库，然后在当前数据库的窗体。</p></td>
</tr>
<tr class="even">
<td><p><strong>View</strong></p></td>
<td><p>将在其中打开窗体视图。 单击<strong>窗体</strong>、<strong>设计</strong>、<strong>打印预览</strong>、<strong>数据表</strong>、<strong>数据透视表</strong>，或<strong>数据透视图</strong><strong>视图</strong>框中。 默认值为<strong>窗体</strong>。</p><p><strong>注意</strong>：<STRONG>视图</STRONG>参数设置将覆盖窗体的<STRONG>默认视图</STRONG>和<STRONG>ViewsAllowed</STRONG>属性的设置。 例如，如果窗体<STRONG>ViewsAllowed</STRONG>属性设置为<STRONG>数据表</STRONG>，您可以仍使用<STRONG>OpenForm</STRONG>操作在窗体视图中打开窗体。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Filter Name</strong></p></td>
<td><p>筛选器的限制或排序窗体的记录。 您可以输入现有查询或筛选器已保存为查询的名称。 但是，查询必须包含要打开的窗体中的所有字段，或将它<strong>OutputAllFields</strong>属性设置为<strong>是</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>Where Condition</strong></p></td>
<td><p>关键字的有效 SQL WHERE 子句 (不带有单词其中) 或 Access 使用记录选择的窗体中的表达式的基础表或查询。 如果选择<strong>筛选器名称</strong>参数的筛选器，Access 会将此 WHERE 子句于筛选结果。 打开窗体，并将其记录限制为所指定的另一个窗体上控件的值，请使用以下表达式： <strong>[</strong><em>fieldname</em><strong>] = 的表单 ！ [</strong><em>formname</em><strong>]![</strong><em>其他窗体上的控件名称</em><strong>]</strong> <em>fieldname</em>替换为基础表或查询的要打开的窗体中的字段的名称。 <em>Formname</em>和<em>其他窗体上的控件名称</em>替换为其他表单和包含所需中第一个窗体中，以匹配的记录的值的其他窗体上的控件的名称。</p><p><strong>注意</strong>： <STRONG>Where Condition</STRONG>参数的最大长度为 255 个字符。 如果您需要输入一个更复杂 SQL WHERE 子句多于此，请改用<STRONG>DoCmd</STRONG>对象的<STRONG>OpenForm</STRONG>方法在 Visual Basic for Applications (VBA) 模块。 您可以在 VBA 中输入 SQL WHERE 子句语句的最多为 32,768 个字符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Data Mode</strong></p></td>
<td><p>窗体的数据输入模式。 这仅适用于在窗体视图或数据表视图中打开的窗体。 单击<strong>添加</strong>（用户可以添加新记录，但不能编辑现有记录），<strong>编辑</strong>（用户可以编辑现有记录，并可以添加新记录） 或<strong>只读</strong>（用户只能查看记录）。 默认值为<strong>编辑</strong>。 <strong>备注</strong></p>
<ul>
<li><p><strong>数据模式</strong>参数设置将覆盖窗体的<strong>AllowEdits</strong>、 <strong>AllowDeletions</strong>、 <strong>AllowAdditions</strong>和<strong>DataEntry</strong>属性的设置。 例如，如果窗体的<strong>AllowEdits</strong>属性设置为<strong>No</strong>，您可以仍使用<strong>OpenForm</strong>操作在编辑模式中打开窗体。</p></li>
<li><p>如果将此参数留空，Access 将窗体的<strong>AllowEdits</strong>、 <strong>AllowDeletions</strong>、 <strong>AllowAdditions</strong>和<strong>DataEntry</strong>属性设置的数据输入模式中打开窗体。</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>窗口模式</strong></p></td>
<td><p>打开窗体窗口模式。 依次单击<strong>普通</strong>（由其属性设置模式中打开窗体）、<strong>隐藏</strong>（隐藏窗体）、<strong>图标</strong>（窗体打开最小化为小型的标题栏中，在屏幕底部），或<strong>对话框</strong>（窗体的<strong>模式</strong>和<strong>弹出窗口</strong>属性设置为<strong>是</strong>)。 默认值为<strong>Normal</strong>。</p><p><strong>注意</strong>： 有些<STRONG>窗口模式</STRONG>参数设置不适用时使用选项卡式文档。 若要切换到重叠窗口：</p>
<ol>
<li><p>单击文件选项卡，然后单击<strong>选项</strong>。</p></li>
<li><p>在<strong>“Access 选项”</strong>对话框中，单击<strong>“当前数据库”</strong>。</p></li>
<li><p>在<strong>应用程序选项</strong>部分中，<strong>文档窗口选项</strong>下单击<strong>重叠窗口</strong>。</p></li>
<li><p>单击<strong>“确定”</strong>，然后关闭并重新打开数据库。</p></li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>备注

此操作类似于双击在导航窗格中，窗体或右键单击导航窗格中的窗体，然后选择视图。

窗体可以是的模式 （它必须关闭或隐藏然后用户可以执行任何其他操作） 或无模式 （用户可以在窗体打开时移动到其他 windows 中）。 也可以是弹出式窗体 （用于收集或显示信息的所有其他访问窗体之上的窗体）。 设计表单时，您可以设置的**Modal**和**PopUp**属性。 如果您使用**普通****窗口模式**参数，通过这些属性设置指定的模式中打开窗体。 如果您使用**窗口模式**参数**对话框**，这些属性都设置为**是**。 打开作为隐藏或图标的窗体返回到显示或将其还原时，其属性设置所指定的模式。

当您打开窗体**窗口模式**参数设置为**对话框**时，Access 将挂起宏，直到窗体被关闭或隐藏。 您可以通过使用**SetValue**操作将其**Visible**属性设置为**否**隐藏窗体。

> [!TIP]
> 您可以在导航窗格中选择一个窗体，并将它拖到宏操作行。 这会自动创建窗体视图中打开该窗体**OpenForm**操作。

筛选和 WHERE 条件将成为窗体的**Filter**属性的设置。

## <a name="examples"></a>示例

**通过使用宏设置控件的值**

下面的宏 Suppliers 窗体上的按钮打开添加产品窗体。 它演示如何使用**回声**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作。 **SetValue**操作供应商窗体上将产品窗体上的供应商 ID 控件设置为当前供应商。 然后， **GoToControl**操作将焦点移到类别 ID 字段中，您可以开始新产品的输入数据。 这个宏应附加到 Suppliers 窗体上的添加产品按钮。

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
<th><p>注释</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Echo</strong></p></td>
<td><p><strong>打开回响</strong>：<strong>否</strong></p></td>
<td><p>停止屏幕更新时运行宏。</p></td>
</tr>
<tr class="even">
<td><p><strong>CloseWindow</strong></p></td>
<td><p><strong>对象类型</strong>： <strong>FormObject 名称</strong>： 产品列表<strong>保存</strong>：<strong>否</strong></p></td>
<td><p>关闭产品列表窗体。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OpenForm</strong></p></td>
<td><p><strong>窗体名称</strong>： 产品<strong>视图</strong>： <strong>FormData 模式</strong>： <strong>AddWindow 模式</strong>：<strong>普通</strong></p></td>
<td><p>打开产品窗体。</p></td>
</tr>
<tr class="even">
<td><p><strong>SetValue</strong></p></td>
<td><p><strong>项目</strong>: [窗体] ！[产品] ！[SupplierID]<strong>表达式</strong>： 供应商 Id</p></td>
<td><p>在 Suppliers 窗体上将供应商 ID 控件设置为当前供应商。</p></td>
</tr>
<tr class="odd">
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： CategoryID</p></td>
<td><p>转到类别 ID 控件。</p></td>
</tr>
</tbody>
</table>


下面的宏将在显示当前供应商的产品 Suppliers 窗体的右下角中打开产品列表窗体。 它演示如何使用**回声**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**，和**MoveAndSizeWindow**操作。 它还会显示具有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式使用。 这个宏应附加到 Suppliers 窗体上的查看产品按钮。

**通过使用宏同步处理窗体**

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
<th><p>注释</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>Echo</strong></p></td>
<td><p><strong>打开回响</strong>：<strong>否</strong></p></td>
<td><p>停止屏幕更新时运行宏。</p></td>
</tr>
<tr class="even">
<td><p>IsNull([SupplierID])</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>： 移动到您要查看其的产品然后再次单击查看产品按钮的供应商记录。 <strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>NoneTitle</strong>： 选择一个供应商</p></td>
<td><p>如果 Suppliers 窗体上没有当前供应商，显示一条消息。</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： 公司名称</p></td>
<td><p>将焦点移到公司名称控件。</p></td>
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
<td><p><strong>窗体名称</strong>： 产品列表<strong>视图</strong>： <strong>DatasheetFilter 名称</strong>： <strong>Where 条件</strong>: [SupplierID] = [窗体] ！[供应商] ！[SupplierID]<strong>数据模式</strong>：<strong>读取 OnlyWindow 模式</strong>：<strong>普通</strong></p></td>
<td><p>打开产品列表窗体并显示当前供应商的产品。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><strong>MoveAndSizeWindow</strong></p></td>
<td><p><strong>右</strong>： 0.7799&quot; <strong>下</strong>： 1.8&quot;</p></td>
<td><p>产品列表表单 Suppliers 窗体的右下角的位置。</p></td>
</tr>
</tbody>
</table>

