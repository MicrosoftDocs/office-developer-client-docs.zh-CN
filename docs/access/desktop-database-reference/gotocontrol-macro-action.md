---
title: GoToControl 宏操作
TOCTitle: GoToControl macro action
ms:assetid: caff76dc-7ca8-4f87-8144-89445ed4600d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834370(v=office.15)
ms:contentKeyID: 48547705
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c056f2b0922402ea7cde7cf767969b73f912f572
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292165"
---
# <a name="gotocontrol-macro-action"></a>GoToControl 宏操作

**适用于**：Access 2013、Office 2013

可以使用**GoToControl**操作将焦点移到打开的窗体、窗体数据表、表数据表或查询数据表的当前记录中的指定字段或控件。 当你希望特定字段或控件获得焦点时，可以使用此操作。 然后比较或 **FindRecord** 操作可以使用该字段或控件。 你可以使用此操作以根据特定的条件在表单中导航。 例如，如果用户输入婚姻控件不能在健康保险窗体，焦点可以自动跳过配偶姓名控件并移动到下一个控件。

## <a name="setting"></a>Setting

> [!NOTE]
> 此操作不能用于数据访问页。

**GoToControl** 操作具有以下参数。

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
<td><p><strong>控件名称</strong></p></td>
<td><p>希望获得焦点的字段或控件的名称。 在 "宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>控件名称</strong>" 框中输入字段或控件的名称。 这是必需参数。</p>
<p><strong>注意</strong>: 仅在 "<strong>控件名称</strong>" 参数中输入字段或控件的名称, 而不是完全限定的标识符, 例如 Forms!物料![产品 ID]。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

不能使用**GoToControl**操作将焦点移到隐藏窗体上的控件。

> [!TIP]
> 可以使用**GoToControl**操作移动到子窗体, 它是一种类型的控件。 然后, 可以使用**GoToRecord**操作移动到子窗体中的特定记录。 您还可以通过使用**GoToControl**操作先移到子窗体, 然后再移到子窗体上的控件, 移到子窗体上的控件。

若要在 Visual Basic for Applications (VBA) 模块中运行**gotocontrol**操作, 请使用**DoCmd**对象的**gotocontrol**方法。 您还可以使用 **SetFocus** 方法将焦点移到窗体或其任何子窗体上的控件或打开的表、 查询或窗体数据表中的字段。

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


**使用宏验证数据**

下面的验证宏会检查在"供应商"窗体中输入的邮政编码。 它演示如何使用 **StopMacro** 、 **MessageBox** 、 **CancelEvent** 和 **GoToControl** 操作。 其条件表达式检查在窗体的记录中输入的国家/地区和邮政编码。 如果邮政编码的格式与国家/地区不符，该宏将显示一个消息框并取消对该记录的保存操作。 然后, 该宏将返回到 "邮政编码" 控件, 您可以在其中更正错误。 此宏应附加到“供应商”窗体的 **BeforeUpdate** 属性。

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
<td><p>如果 "国家/地区" 为<strong>空</strong>, 则无法验证邮政编码。</p></td>
</tr>
<tr class="even">
<td><p>国家/地区In (&quot;法国&quot;,&quot;意大利&quot;,&quot;西班牙&quot;) 和 Len ([邮政编码]) &lt; &gt; 5</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: 邮政编码必须为5个字符。 <strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: 邮政编码错误</p></td>
<td><p>如果邮政编码不是5个字符, 则显示一条消息。</p></td>
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
<td><p>消息：邮政编码必须为 4 个字符。 <strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: 邮政编码错误</p></td>
<td><p>如果邮政编码不是4个字符, 则显示一条消息。</p></td>
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
<td><p>([国家/地区&quot;]&quot;= 加拿大)和 ([邮政编码] 不喜欢&quot;[a-z] [0-9] [a-z] [0-9] [a-z] [0-9])&quot;</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: 邮政编码无效。 加拿大代码示例: H1J 1C3<strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: 邮政编码错误</p></td>
<td><p>如果邮政编码对加拿大不正确, 则显示一条消息。 （加拿大邮政编码示例：H1J 1C3）</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p><strong>CancelEvent</strong></p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
</tbody>
</table>

