---
title: SetValue 宏操作
TOCTitle: SetValue macro action
ms:assetid: a08be0c1-a053-45f9-b4ae-709fedc58e8b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff820771(v=office.15)
ms:contentKeyID: 48546712
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1ec96fd588e4b20b6c2ebe0ef25f488841aa4d70
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998873"
---
# <a name="setvalue-macro-action"></a>SetValue 宏操作

**适用于**： Access 2013、 Office 2013

您可以使用**SetValue**操作设置窗体、 窗体数据表或报表上的 Microsoft Access 字段、 控件或属性的值。

> [!NOTE]
> - 您不能使用**SetValue**操作设置返回一个 object 访问属性的值。
> - [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**SetValue**操作具有下列参数。

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
<td><p><strong>Item</strong></p></td>
<td><p>字段、 控件或想要设置其值属性的名称。 在宏生成器窗格的<strong>操作参数</strong>部分的<strong>项目</strong>框中输入字段、 控件或属性名称。 您必须使用完整的语法引用此项目，如<em>controlname</em> （对于控件在窗体或报表从中调用宏） 或<strong>表单</strong>！<em>formname</em>！<em>控件名称</em>。 这是必需参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>Expression</strong></p></td>
<td><p>Access 使用设置此项的值的表达式。 始终必须使用完整的语法来引用该表达式中的任何对象。 例如，若要增加 10 %employees 窗体上的薪金控件中的值，请使用表单 ！员工 ！Salary * 1.1。 这是必需参数。</p><p><strong>注意</strong>： 不应在此参数中使用的表达式前等号 （=）。 否则，Access 计算了表达式，然后使用此值作为此参数中的表达式。 如果表达式是一个字符串，这可能会产生意外的结果。</p>
<p>例如，如果您键入<strong>= &quot;String1&quot;</strong>用于此参数，Access 将首先计算表达式作为 String1。 然后使用 String1 为此参数，应找到控件或窗体或报表调用宏上的名为 String1 属性中的表达式。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> 在 Access 数据库 （.mdb 或.accdb），单击**生成**按钮以使用表达式生成器创建的上述参数的表达式。

## <a name="remarks"></a>备注

您可以使用此操作设置字段或窗体、 窗体数据表或报表上的控件的值。 您还可以在任何视图中设置几乎所有控件、 窗体和报表属性的值。 了解特定属性是否可通过使用宏设置和哪些视图它可以是在设置，请参阅在 Visual Basic 编辑器中的属性的帮助主题。

即使窗体不包含控件绑定到的字段，还可以在窗体基础表中设置字段的值。 使用语法**Forms**\!*formname*\!*fieldname*在**项**中设置此类的字段的值。 您还可以参考到报表的基础表中的字段通过使用**报告**的语法\!*reportname*\!*fieldname*，但必须绑定到此字段中，在报表上的控件或字段必须引用到在报表上的计算的控件。

如果设置窗体上控件的值， **SetValue**操作不会触发该控件的窗体级有效性规则，但如果控件绑定的控件，它会触发基础字段的表级有效性规则。 **SetValue**操作还将触发重新计算，但重新计算不会立即发生。 若要触发立即重画并强制结束重新计算，请使用**RepaintObject**操作。 可以使用**SetValue**操作设置控件中的值还不受输入掩码在控件的设置或基础字段的**InputMask**属性。

若要更改控件的值，可以在宏中指定控件的**AfterUpdate**事件属性使用**SetValue**操作。 但是，不能在宏中指定控件的**BeforeUpdate**事件属性使用**SetValue**操作，更改控件的值 （尽管可以使用**SetValue**操作来更改其他控件的值）。 您可以在宏中指定窗体的**BeforeUpdate**或**AfterUpdate**属性使用**SetValue**操作更改当前记录中任何控件的值。

> [!NOTE]
> 不能使用**SetValue**操作设置以下控件的值：
> - 绑定控件和报表上的计算的控件。
> - 在窗体上的计算的控件。

> [!TIP]
> 您可以使用**SetValue**操作隐藏或显示窗体中窗体视图。 输入**表单**！*formname ***。可见** 中**项**框和**无**或******表达式**框中。 模式窗体的**Visible**属性设置为**否**将隐藏窗体，并使其无模式。 将属性设置为**是**的形式显示，并使其在再次时模式。

更改的值或控件中添加新数据，在宏中使用**SetValue**操作不会触发如**BeforeUpdate**、 **BeforeInsert**，或**更改**时更改或输入数据，这些控件中所发生的事件用户界面。 如果您通过使用 Visual Basic for Applications (VBA) 模块中设置控件的值还不发生这些事件。

此操作不能在 VBA 模块中使用。 直接在 VBA 中设置的值。

## <a name="example"></a>示例

**通过使用宏设置控件的值**

下面的宏 Suppliers 窗体上的按钮打开添加产品窗体。 它演示如何使用**回声**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作。 **SetValue**操作供应商窗体上将产品窗体上的 SupplierID 控件设置为当前供应商。 然后， **GoToControl**操作将焦点移到 CategoryID 字段中，您可以开始新产品的输入数据。 这个宏应附加到 Suppliers 窗体上的添加产品按钮。

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
<td><p>在 Suppliers 窗体上将 SupplierID 控件设置为当前供应商。</p></td>
</tr>
<tr class="odd">
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： CategoryID</p></td>
<td><p>转到 CategoryID 控件。</p></td>
</tr>
</tbody>
</table>

