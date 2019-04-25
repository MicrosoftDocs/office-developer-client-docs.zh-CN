---
title: SetValue 宏操作
TOCTitle: SetValue macro action
ms:assetid: a08be0c1-a053-45f9-b4ae-709fedc58e8b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff820771(v=office.15)
ms:contentKeyID: 48546712
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 6b6f16c22e9265159c73279cfa1b2644adbc0277
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306816"
---
# <a name="setvalue-macro-action"></a>SetValue 宏操作

**适用于**：Access 2013、Office 2013

可以使用**SetValue**操作来设置 Microsoft Access 字段、 控件的值，或表单、表单数据表或报表属性。

> [!NOTE]
> - 不能使用**SetValue**操作来设置可返回一个对象的 Access 属性值。
> - 如果数据库不受信任，则不允许执行此操作。 

## <a name="setting"></a>Setting

**SetValue** 操作具有下列参数。

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
<td><p>字段、 控件或想要设置其值的属性名称。 请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“项目”</strong>框中输入字段、控件或属性名称。 必须使用完整的语法来引用此项目，例如<em>controlname</em>（适用于表单上的控件或从其调用宏的报表）或<strong>Forms</strong>!<em>formname</em>!<em>controlname</em>。 这是必需参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>Expression</strong></p></td>
<td><p>表达式 Access 用于设置此项目的值。 必须始终使用完整的语法来引用表达式中任何对象。 例如，要增加“员工”表单上某个“工资”控件中的值 10%，请使用 Forms!Employees!Salary*1.1。 这是必需参数。</p><p><strong>注释</strong>：不得在此参数表达式前使用等号 （=）。 若使用等号，则 Access 会对表达式求值，然后使用此值作为此参数中的表达式。 如果表达式为一个字符串，将会产生意外结果。</p>
<p>例如，如果此参数键入<strong> = &quot;String1&quot; </strong>，则 Access 首先计算表达式为 String1。 然后使用 String1 作为此参数的表达式，期望在调用宏的表单或报表上找到名为 String1 的控件或属性。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> 在 Access 数据库（.mdb 或 .accdb）中，单击 **“生成”** 按钮，以便使用“表达式生成器”为这些参数中的任意一个选择一个表达式。

## <a name="remarks"></a>说明

此操作可用于设置表单、表单数据表或报表上的字段或控件的值。 此外可以在任意视图中设置几乎所有控件、表单和报表属性值。 若要找出是否可通过使用宏来设置特定属性，以及可以在哪些视图中设置，请参阅在 Visual Basic 编辑器中有关该属性的“帮助”主题。

即使表单不包含绑定字段的控件，也可以在表单基础表中设置字段值。 在**项目**框中使用语法**Forms**\!*formname*\!*fieldname*以设置此类字段的值。 你还可使用语法**Reports**\!*reportname*\!*fieldname*引用到报表基础表中的字段，但是绑定到此字段的报表上必须有一个控件，或者必须在报表上计算控件中引用字段。

如果在表单上设置控件值，**SetValue**操作不会触发控件的表单级别的验证规则，但如果控件是绑定的控件，则会触发基础字段的表级别验证规则。 **SetValue**操作还会触发重新计算，但重新计算不会立即发生。 若触发立即重画并强制完成重新计算，使用**RepaintObject**操作。 使用**SetValue**操作在控件中设置的值还不受在控件或基础字段的**InputMask**属性中设置的输入掩码的影响。

若要更改控件值，可以在由控件的**AfterUpdate**事件属性指定的宏中使用**SetValue**操作。 但是，不能在控件的**BeforeUpdate**事件属性指定的宏中使用**SetValue**操作来变更控件值（虽然可使用**SetValue**操作来变更其他控件的值）。 也可以在表单的**BeforeUpdate**或**AfterUpdate**属性指定的宏中使用**SetValue**操作来变更在当前记录中任何控件的值。

> [!NOTE]
> 不能使用**SetValue**操作来设置以下控件的值：
> - 报表上的绑定控件计算控件。
> - 表单上的计算控件。

> [!TIP]
> 可以使用**SetValue**操作来隐藏或显示“表单”视图中的表单。 在**Item**框中输入**Forms**!*formname***.Visible**，然后在**Expression**框中输入**No**或**Yes**。 设置模式表单的**Visible**属性为**No**，以隐藏表单并使其成为无模式。 将属性设置为**Yes**以显示表单并使其再次成为模式。

在宏中使用**SetValue**操作来变更控件值或添加新数据不会触发**BeforeUpdate**、**BeforeInsert**或**Change**之类的事件，在用户界面的这些控件中更改或输入数据时通常发生此类事件。 如果使用 Visual Basic for Applications (VBA) 模块来设置控件值，也不会发生这些事件。

此操作在 VBA 模块中不可用。 直接在 VBA 中设置值。

## <a name="example"></a>示例

**使用宏来设置控件值**

下列宏从“供应商”表单上的按钮打开“添加产品”表单。 显示如何使用**Echo**、**CloseWindow**、**OpenForm**、 **SetValue**和**GoToControl**操作。 **SetValue**操作将“产品”表单上的 SupplierID 控件设置为“供应商”表单上的当前供应商。 然后**GoToControl**操作会将焦点移动至 CategoryID 字段，在这里开始输入新产品数据。 此宏应附加到“供应商”表单上的“添加产品”按钮。

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
<td><p><strong>Echo On</strong>: <strong>No</strong></p></td>
<td><p>运行宏时停止屏幕更新。</p></td>
</tr>
<tr class="even">
<td><p><strong>CloseWindow</strong></p></td>
<td><p><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></p></td>
<td><p>关闭“产品列表”表单。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OpenForm</strong></p></td>
<td><p><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></p></td>
<td><p>打开“产品”表单。</p></td>
</tr>
<tr class="even">
<td><p><strong>SetValue</strong></p></td>
<td><p><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</p></td>
<td><p>在“供应商”表单上将 SupplierID 控件设置为当前供应商。</p></td>
</tr>
<tr class="odd">
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>Control Name</strong>: CategoryID</p></td>
<td><p>转到 CategoryID 控件。</p></td>
</tr>
</tbody>
</table>

