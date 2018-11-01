---
title: SetWarnings 宏操作
TOCTitle: SetWarnings Macro Action
ms:assetid: ff95b919-b1ee-c0a0-851d-71894851bb1d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837313(v=office.15)
ms:contentKeyID: 48548965
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm165020
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1a1081ac8778c143270e4e2536c53bb47982af92
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885512"
---
# <a name="setwarnings-macro-action"></a>SetWarnings 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **SetWarnings** 操作打开或者关闭系统消息。


> [!NOTE]
> <P>[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</P>



## <a name="setting"></a>设置

**SetWarnings** 操作具有以下参数。

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
<td><p><strong>打开警告</strong></p></td>
<td><p>指定是否显示系统消息。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“打开警告”</strong>框中单击<strong>“是”</strong>（打开系统消息）或<strong>“否”</strong>（关闭系统消息）。默认值为<strong>“否”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

可以使用此操作防止模式警告框和消息框使宏停止执行。不过，始终都会显示错误消息。另外，Microsoft Access 除了不显示只需选择一个按钮（例如， **"确定"**、 **"取消"**、 **"是"** 或 **"否"**）的对话框外，会显示任何需要输入的对话框，例如任何需要您输入文本或者选择多个选项之一的对话框。

执行此操作与**警告**参数设置为**否**时显示警告或消息框中，按 ENTER 的效果相同。 通常，响应警告或消息是选择**确定**或**是**按钮。

在宏执行完后，Access 会自动打开系统消息的显示。

通常，此操作将与 **Echo** 操作一起使用，后者将一直隐藏宏的执行结果，直到宏执行完。也可以使用 **SetWarnings** 操作来隐藏警告框和消息框。


> [!WARNING]
> <P>[!警告] 虽然 <STRONG>SetWarnings</STRONG> 操作可以简化与宏之间的交互，但对于关闭系统消息必须要谨慎。在一些情况下，如果出现某条警告消息，您将不希望再继续执行宏。除非您对所有宏操作的执行结果有把握，否则应该避免使用此操作。</P>



要在 Visual Basic for Applications (VBA) 模块中运行 **SetWarnings** 操作，请使用 **DoCmd** 对象的 **SetWarnings** 方法。

