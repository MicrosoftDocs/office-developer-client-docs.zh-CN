---
title: 回声宏操作 （访问桌面数据库参考 （英文）
TOCTitle: Echo macro action
ms:assetid: 38dfb2cf-8db5-44b3-91fa-e490932b940b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192516(v=office.15)
ms:contentKeyID: 48544227
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 947e3569d52558cc154ea751ecce204d02cbf7ec
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921542"
---
# <a name="echo-macro-action"></a>Echo 宏操作


**适用于**： Access 2013、 Office 2013

**Echo**操作可用于指定是否打开回响。 例如，您可以使用此操作可隐藏或运行时显示的宏的结果。

## <a name="setting"></a>设置


> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。



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
<td><p>单击<strong>是</strong>（打开回响） 或<strong>无</strong>（关闭回响） 的<strong>回声</strong>框中的<strong>操作参数</strong>部分的宏生成器窗格中。 默认值为 <strong>"是"</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>状态栏文字</strong></p></td>
<td><p>要关闭回声时在状态栏中显示的文本。 例如，当回声处于关闭状态，可以显示状态栏&quot;会在运行宏。&quot;</p></td>
</tr>
</tbody>
</table>


时运行一个宏，更新显示信息通常已为宏的功能不必需的屏幕。 时将**打开回响**参数设置为**No**，宏将运行但没有更新屏幕。 宏执行完，Access 将自动打开回声和重画窗口。 **打开回响**参数的**无**设置不会影响宏或其结果的功能。

**Echo**操作不会禁止显示模式对话框，例如错误消息或弹出式窗体，如属性表。 您可以使用对话框和弹出式窗体来收集或显示的信息，即使关闭回响。 若要取消所有邮件或对话框框除的错误消息框和要求用户输入信息的对话框，请使用**SetWarnings**操作。

您可以在宏中多次运行**Echo**操作。 这样，您可以在宏运行时更改状态栏文本。

如果关闭回声，您可以使用**DisplayHourglassPointer**操作将鼠标指针更改为沙漏图标 （或已设置为"忙碌"的任何鼠标指针图标） 提供直观的指示运行宏。

若要在 Visual Basic for Applications (VBA) 模块中运行**Echo**操作，请使用**DoCmd**对象的**回声**方法。

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


**通过使用宏同步处理窗体**

下面的宏将在显示当前供应商的产品 Suppliers 窗体的右下角中打开产品列表窗体。 它演示如何使用**回声**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**，和**MoveAndSizeWindow**操作。 它还会显示具有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式使用。 这个宏应附加到 Suppliers 窗体上的查看产品按钮。

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
<td><p>IsNull ([供应商 ID])</p></td>
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
<td><p><strong>窗体名称</strong>： 产品列表<strong>视图</strong>： <strong>DatasheetFilter 名称</strong>： <strong>Where 条件</strong>: [供应商 ID] = [窗体] ！[供应商] ！[SupplierID]<strong>数据模式</strong>：<strong>读取 OnlyWindow 模式</strong>：<strong>普通</strong></p></td>
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

