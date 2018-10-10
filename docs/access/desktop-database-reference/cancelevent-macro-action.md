---
title: CancelEvent 宏操作
TOCTitle: CancelEvent Macro Action
ms:assetid: d9d3ea99-c9fb-2524-c570-e3ee6d20af98
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835110(v=office.15)
ms:contentKeyID: 48548066
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm78430
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 52822d45b30c631dcabe3c38b6722398e96f489f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468080"
---
# <a name="cancelevent-macro-action"></a>CancelEvent 宏操作


**适用于**： Access 2013 |Office 2013


您可以使用**CancelEvent**操作取消导致访问权限才能运行包含此操作的宏的事件。 宏名称是 **BeforeUpdate** 、 **OnOpen** 、 **OnUnload** 或 **OnPrint** 等事件属性的设置。

## <a name="setting"></a>设置

**CancelEvent** 操作不具有任何参数。

## <a name="remarks"></a>说明

在窗体中，通常是在验证宏中将 **CancelEvent** 操作与 **BeforeUpdate** 事件属性搭配使用。当用户在控件或记录中输入数据时，Access 会先运行该宏，然后再将数据添加到数据库中。如果数据不符合该宏中的验证条件， **CancelEvent** 操作将在更新进程开始前将其取消。

此操作通常与 **MessageBox** 操作搭配使用，以指示数据不符合验证条件，并提供有关应输入何种数据类型的帮助信息。

以下事件可由 **CancelEvent** 操作取消。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>ApplyFilter</strong></p></td>
<td><p><strong>Dirty</strong></p></td>
<td><p><strong>MouseDown</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>BeforeDelConfirm</strong></p></td>
<td><p><strong>退出</strong></p></td>
<td><p><strong>NoData</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>BeforeInsert</strong></p></td>
<td><p><strong>Filter</strong></p></td>
<td><p><strong>Open</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>BeforeUpdate</strong></p></td>
<td><p><strong>Format</strong></p></td>
<td><p><strong>Print</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>DblClick</strong></p></td>
<td><p><strong>KeyPress</strong></p></td>
<td><p><strong>卸载</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Delete</strong></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>[!注释] 对 <STRONG>MouseDown</STRONG> 事件应用 <STRONG>CancelEvent</STRONG> 操作时，只能取消右键单击对象时发生的事件。</P>



如果控件的 **OnDblClick** 事件属性设置指定了一个包含 **CancelEvent** 操作的宏，该操作会取消 **DblClick** 事件。

对于可被取消的事件，在对其运行相应的宏后，将会发生该事件的默认行为（即 Access 在事件发生时的通常处理方式）。您可以基于此机制取消默认行为。例如，在双击插入点位于文本框中的某个单词时，Access 通常会选中该单词。您可以在 **DblClick** 事件的宏中取消此默认行为并执行某种其他操作，例如打开一个包含有关文本框中的数据的信息的窗体。对于无法取消的事件，则会在宏运行前发生默认行为。


> [!NOTE]
> <P>[!注释] 如果窗体的 <STRONG>OnUnload</STRONG> 事件属性指定了一个执行 <STRONG>CancelEvent</STRONG> 操作的宏，则无法关闭该窗体。您必须更正导致执行 <STRONG>CancelEvent</STRONG> 操作的条件，或打开该宏并删除 <STRONG>CancelEvent</STRONG> 操作。如果该窗体是一个模式窗体，则无法打开该宏。</P>



要在 Visual Basic for Applications (VBA) 模块中执行 **CancelEvent** 操作，请使用 **DoCmd** 对象的 **CancelEvent** 方法。

## <a name="example"></a>示例

 使用宏验证数据

下面的验证宏会检查在"供应商"窗体中输入的邮政编码。它演示如何使用 **StopMacro** 、 **MessageBox** 、 **CancelEvent** 和 **GoToControl** 操作。其条件表达式检查在窗体的记录中输入的国家/地区和邮政编码。如果邮政编码的格式与国家/地区不符，该宏将显示一个消息框并取消对该记录的保存操作。随后将返回到"邮政编码"控件，以便您更正错误。此宏应附加到"供应商"窗体的 **BeforeUpdate** 属性。

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
<td><p>StopMacro</p></td>
<td><p></p></td>
<td><p>国家/地区为<strong>Null</strong>，如果无法验证邮政编码。</p></td>
</tr>
<tr class="even">
<td><p>[国家/地区]中 (&quot;法国&quot;，&quot;意大利&quot;，&quot;西班牙&quot;) And Len （[邮政编码]） &lt; &gt; 5</p></td>
<td><p>MessageBox</p></td>
<td><p>消息：邮政编码必须为 5 个字符。 

 发嘟嘟声:<strong>是</strong>类型：<strong>信息</strong>标题： 邮政编码错误</p></td>
<td><p>如果邮政编码不是 5 个字符，则显示一条消息。</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p>CancelEvent</p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>GoToControl</p></td>
<td><p>控件名称：邮政编码</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>[国家/地区]中 (&quot;澳大利亚&quot;，&quot;新加坡&quot;) And Len （[邮政编码]） &lt; &gt; 4</p></td>
<td><p>MessageBox</p></td>
<td><p>消息：邮政编码必须为 4 个字符。 

 发嘟嘟声:<strong>是</strong>类型：<strong>信息</strong>标题： 邮政编码错误</p></td>
<td><p>如果邮政编码不是 4 个字符，则显示一条消息。</p></td>
</tr>
<tr class="even">
<td><p>...</p></td>
<td><p>CancelEvent</p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>GoToControl</p></td>
<td><p>控件名称：邮政编码</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>([国家/地区] =&quot;加拿大&quot;)和 ([邮政编码] Not Like&quot;[A-Z] [0-9] [A-Z] [0-9] [A-Z] [0-9]&quot;)</p></td>
<td><p>MessageBox</p></td>
<td><p>消息： 邮政编码不是有效的。 加拿大代码示例： H1J 1c3 发嘟嘟声:<strong>是</strong>类型：<strong>信息</strong>标题： 邮政编码代码错误</p></td>
<td><p>如果邮政编码不符合加拿大格式，则显示一条消息。（加拿大邮政编码示例：H1J 1C3）</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p>CancelEvent</p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
</tbody>
</table>

