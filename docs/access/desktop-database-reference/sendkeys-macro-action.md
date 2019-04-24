---
title: SendKeys 宏操作
TOCTitle: SendKeys macro action
ms:assetid: 3b06fcfc-ea64-c780-b5fc-6fc72853f524
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192656(v=office.15)
ms:contentKeyID: 48544275
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm183441
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: f8c45cdf0d9cf588f61d1b51b728a8a15f6d7e12
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308748"
---
# <a name="sendkeys-macro-action"></a>SendKeys 宏操作

**适用于**：Access 2013、Office 2013

<table>
<thead>
<tr class="header">
<th><img src="media/access-alert-security.gif" title="安全注释" alt="Security note" /><strong>安全说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>避免使用带敏感信息或机密信息的 <strong>SendKeys</strong> 语句或 AutoKeys 宏。恶意用户会截取键击，从而危及计算机和数据的安全性。</td>
</tr>
</tbody>
</table>

可以使用 **SendKeys** 操作直接向 Microsoft Access 或基于 Windows 的活动应用程序发送键击。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**SendKeys** 操作具有下列参数。

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
<td><p><strong>键击</strong></p></td>
<td><p>想让 Access 或其他应用程序处理的键击。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“键击”</strong>框中输入键击。最多可以键入 255 个字符。这是一个必选参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>Wait</strong></p></td>
<td><p>指定在处理完键击之前宏是否应该暂停。请单击<strong>“是”</strong>（暂停）或<strong>“否”</strong>（不暂停）。默认值为<strong>“否”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

Access 处理通过 **SendKeys** 操作接收的键击，就好像您已经直接在 Access 窗口中键入它们一样。

要指定键击，请使用用于 **SendKeys** 语句的语法。

> [!NOTE]
> 如果“键击”**** 参数包含不正确的语法、拼写错误的文本或者其他不适合键击要发送到的窗口的值，则可能发生错误。

可以使用此操作在对话框中输入信息，尤其是在您不想中断宏的执行来手动响应对话框时。有些 Access 操作（例如 **PrintOut** 和 **FindRecord** ）会自动选择某些常用对话框中的选项。可以使用 **SendKeys** 操作选择不常用的对话框中的选项。

> [!NOTE]
> - Because the dialog box suspends the macro, you must put the **SendKeys** action before the action that causes the dialog box to open and set the **Wait** argument to **No**.
> - 键击到达 Access 或其他应用程序的时间难以确定。因此，在有其他方法（如 **FindRecord** 操作）可用来完成需要的任务时，建议您使用其他方法，而不要使用 **SendKeys** 操作来填写对话框中的选项。

如果希望向 Access 或其他基于 Windows 的应用程序发送 255 个以上字符，可以在宏中连续使用多个 **SendKeys** 操作。

使用 **SendKeys** 操作发送键击会触发相应的 **KeyDown** 、 **KeyUp** 和 **KeyPress** 事件。发送非 ANSI 键击（如功能键）不会触发 **KeyPress** 事件。

此操作在 Visual Basic for Applications (VBA) 模块中不可用。请改用 **SendKeys** 语句。

