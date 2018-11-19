---
title: MessageBox 宏操作
TOCTitle: MessageBox macro action
ms:assetid: 326a0e68-38fb-4f81-b319-5a70caa5aec4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192304(v=office.15)
ms:contentKeyID: 48544077
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 14f3cd56323b68f54228e01413f984542c7f3c1a
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944513"
---
# <a name="messagebox-macro-action"></a>MessageBox 宏操作

**适用于**： Access 2013、 Office 2013

您可以使用**MessageBox**操作显示包含警告或信息性消息一个消息框。 例如，您可以使用验证宏使用**MessageBox**操作。 当控件或记录失败时在宏中的有效性验证条件时，一个消息框可以显示一条错误消息，并提供有关应输入的数据类型的说明。

## <a name="setting"></a>设置

**MessageBox**操作具有下列参数。

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
<td><p><strong>Message</strong></p></td>
<td><p>邮件框中的文本。 在宏生成器窗格的<strong>操作参数</strong>部分的<strong>消息</strong>框中输入消息文本。 您可以键入最多 255 个字符，或输入一个表达式 （前面带有等号）。</p></td>
</tr>
<tr class="even">
<td><p><strong>Beep</strong></p></td>
<td><p>指定是否计算机的扬声器发出嘟嘟声显示消息时。 单击<strong>是</strong>（发出嘟嘟声） 或<strong>否</strong>（不发出嘟嘟声）。 默认值为 <strong>"是"</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>消息框中的类型。 每种类型有不同的图标。 单击<strong>无</strong><strong>关键</strong><strong>警告？</strong>，<strong>警告 ！</strong>，或<strong>信息</strong>。 默认值为<strong>None</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>Title</strong></p></td>
<td><p>在消息框标题栏中显示的文本。 例如，您可以标题栏中显示&quot;客户 ID 验证&quot;。 如果您将此参数留空， &quot;Microsoft Access&quot;显示。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>备注

**MessageBox**操作可用于创建带格式的错误消息类似于由 Microsoft Access 显示内置的错误消息。 **MessageBox**操作允许您提供三个部分的消息参数中的邮件。 分隔各节与"@"字符。

下面的示例显示一个带有分段消息的格式化的消息框。 第一节的消息中的文本显示为加粗的标题。 第二部分显示为纯文本标题的下面。 第三部分显示为纯文本下方第二部分，使用它们之间的一个空行。

在**消息**参数中键入以下字符串：

**错误按钮\!@This 按钮不 work.@Try 另一个。**

不能在 Visual Basic for Applications (VBA) 模块中运行的**MessageBox**操作。 请改用**MsgBox**函数。

## <a name="examples"></a>示例

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


**通过使用宏验证数据**

下面的验证宏会检查在"供应商"窗体中输入的邮政编码。 它演示如何使用 **StopMacro** 、 **MessageBox** 、 **CancelEvent** 和 **GoToControl** 操作。 其条件表达式检查在窗体的记录中输入的国家/地区和邮政编码。 如果邮政编码不是以适当的国家/地区的格式，宏将显示一个消息框，并取消保存记录。 它然后返回到 PostalCode 控件中，您可以在其中更正错误。 此宏应附加到"供应商"窗体的 **BeforeUpdate** 属性。

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
<td><p>IsNull([CountryRegion])</p></td>
<td><p><strong>StopMacro</strong></p></td>
<td><p></p></td>
<td><p>国家/地区为<strong>Null</strong>，如果无法验证邮政编码。</p></td>
</tr>
<tr class="even">
<td><p>[国家/地区]中 (&quot;法国&quot;，&quot;意大利&quot;，&quot;西班牙&quot;) 和 Len([PostalCode]) &lt; &gt; 5</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>： 邮政编码必须为 5 个字符。 <strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政编码错误</p></td>
<td><p>如果邮政编码不是 5 个字符，则显示一条消息。</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p><strong>CancelEvent</strong></p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： 邮政编码</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>[国家/地区]中 (&quot;澳大利亚&quot;，&quot;新加坡&quot;) 和 Len([PostalCode]) &lt; &gt; 4</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>： 邮政编码必须为 4 个字符。 <strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政编码错误</p></td>
<td><p>如果邮政编码不是 4 个字符，则显示一条消息。</p></td>
</tr>
<tr class="even">
<td><p>...</p></td>
<td><p><strong>CancelEvent</strong></p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： 邮政编码</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>([国家/地区] =&quot;加拿大&quot;)和 ([邮政编码] Not Like&quot;[A-Z] [0-9] [A-Z] [0-9] [A-Z] [0-9]&quot;)</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>： 邮政编码无效。 加拿大代码示例： H1J 1c3<strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政代码错误</p></td>
<td><p>如果邮政编码不符合加拿大格式，则显示一条消息。（加拿大邮政编码示例：H1J 1C3）</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p><strong>CancelEvent</strong></p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
</tbody>
</table>

