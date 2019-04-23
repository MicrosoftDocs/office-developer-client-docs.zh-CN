---
title: MessageBox 宏操作
TOCTitle: MessageBox macro action
ms:assetid: 326a0e68-38fb-4f81-b319-5a70caa5aec4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192304(v=office.15)
ms:contentKeyID: 48544077
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1175e3903e54fd3420be43dfd9e3652d9990468b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289154"
---
# <a name="messagebox-macro-action"></a>MessageBox 宏操作

**适用于**：Access 2013、Office 2013

可以使用**MessageBox**操作显示包含警告或信息性消息的消息框。 例如, 可以将**MessageBox**操作与验证宏一起使用。 当控件或记录未通过宏的有效性验证条件时, 消息框会显示一条错误消息, 并提供有关应输入的数据类型的说明。

## <a name="setting"></a>Setting

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
<td><p>消息框中的文本。 在 "宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>消息</strong>" 框中输入消息文本。 最长可键入255个字符或输入一个表达式 (前面加上等号)。</p></td>
</tr>
<tr class="even">
<td><p><strong>Beep</strong></p></td>
<td><p>指定在显示消息时, 计算机的扬声器是否发出嘟嘟声。 单击<strong>"是"</strong> (发出蜂鸣音) 或 "<strong>否</strong>" (不发出嘟嘟声)。 默认值为 <strong>"是"</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>消息框的类型。 每种类型都有一个不同的图标。 单击 "<strong>无</strong>、<strong>紧急</strong>、<strong>警告？</strong>、<strong>警告!</strong>" 或 "<strong>信息</strong>"。 默认值为 "<strong>无</strong>"。</p></td>
</tr>
<tr class="even">
<td><p><strong>Title</strong></p></td>
<td><p>消息框标题栏中显示的文本。 例如, 您可以让标题栏显示&quot;"客户 ID" 验证&quot;。 如果将此参数留空, &quot;则会&quot;显示 Microsoft Access。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以使用**MessageBox**操作创建类似于 Microsoft Access 所显示的内置错误消息的格式化错误消息。 **MessageBox**操作允许您在三个部分中为 message 参数提供一条消息。 使用 "@" 字符分隔各部分。

下面的示例显示一个带有分节消息的格式化消息框。 邮件中文本的第一部分显示为加粗标题。 第二部分在标题下方显示为纯文本。 第三部分以纯文本的形式显示在第二部分的下方, 中间有一个空行。

在**Message**参数中键入以下字符串:

**错误按钮\!@This 按钮不起作用。 @Try 其他按钮。**

不能在 Visual Basic for Applications (VBA) 模块中运行**MessageBox**操作。 改为使用**MsgBox**函数。

## <a name="examples"></a>示例

**使用宏同步窗体**

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


**使用宏验证数据**

下面的验证宏会检查在"供应商"窗体中输入的邮政编码。 它演示如何使用 **StopMacro** 、 **MessageBox** 、 **CancelEvent** 和 **GoToControl** 操作。 其条件表达式检查在窗体的记录中输入的国家/地区和邮政编码。 如果邮政编码的格式不是正确的国家/地区, 宏将显示一个消息框, 并取消保存该记录。 然后, 它将返回到 "邮政编码" 控件, 您可以在其中更正错误。 此宏应附加到“供应商”窗体的 **BeforeUpdate** 属性。

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
<td><p>IsNull ([国家/地区])</p></td>
<td><p><strong>StopMacro</strong></p></td>
<td><p></p></td>
<td><p>如果 "国家/地区" 为<strong>Null</strong>, 则无法验证邮政编码。</p></td>
</tr>
<tr class="even">
<td><p>国家/地区In (&quot;法国&quot;,&quot;意大利&quot;,&quot;西班牙&quot;) 和 Len ([邮政编码]) &lt; &gt; 5</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: 邮政编码必须为5个字符。 <strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: 邮政编码错误</p></td>
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
<td><p><strong>控件名称</strong>: 邮政编码</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>国家/地区In (&quot;澳大利亚&quot;,&quot;新加坡&quot;) 和 Len ([邮政编码]) &lt; &gt; 4</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: 邮政编码必须为4个字符。 <strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: 邮政编码错误</p></td>
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
<td><p><strong>控件名称</strong>: 邮政编码</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>([国家/地区&quot;]&quot;= 加拿大)和 ([邮政编码] 不喜欢&quot;[a-z] [0-9] [a-z] [0-9] [a-z] [0-9]&quot;)</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: 邮政编码无效。 加拿大代码示例: H1J 1C3<strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: 邮政编码错误</p></td>
<td><p>如果邮政编码不符合加拿大格式，则显示一条消息。 （加拿大邮政编码示例：H1J 1C3）</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p><strong>CancelEvent</strong></p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
</tbody>
</table>

