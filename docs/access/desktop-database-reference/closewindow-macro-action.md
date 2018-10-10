---
title: CloseWindow 宏操作
TOCTitle: CloseWindow Macro Action
ms:assetid: ba96bc26-7f3f-fd3d-8d3a-e18bfe90cdf0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822510(v=office.15)
ms:contentKeyID: 48547377
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm64319
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1d80ac5b545f07d3bd39f69f16c4578e49439cdf
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465579"
---
# <a name="closewindow-macro-action"></a>CloseWindow 宏操作


**适用于**： Access 2013 |Office 2013

您可以使用**CloseWindow**操作关闭指定的访问文档选项卡或活动文档选项卡，如果未指定。

## <a name="setting"></a>设置

**CloseWindow** 操作具有下列参数。

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
<td><p><strong>对象类型</strong></p></td>
<td><p>要关闭其文档选项卡的数据库对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要选择活动的文档选项卡，请将此参数留空。 

</p>

> [!NOTE]
> <P>如果您正在关闭模块在 Visual Basic 编辑器中，您必须在<STRONG>对象类型</STRONG>参数中使用<STRONG>模块</STRONG>。</P>


<p></p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要关闭的对象的名称。 <strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。 单击要关闭的对象。 如果将<strong>对象类型</strong>参数留空，还应将此参数留空。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Save</strong></p></td>
<td><p>关闭对象时是否保存对其所做的更改。单击<strong>“是”</strong>（保存对象）、<strong>“否”</strong>（关闭对象但不保存）或<strong>“提示”</strong>（提示用户是否保存对象）。默认值为<strong>“提示”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

**CloseWindow** 操作适用于用户可显式打开或关闭的所有数据库对象。此操作等效于选择某个对象，然后通过右键单击该对象的文档选项卡并单击快捷菜单上的 **"关闭"** 来关闭该对象，也等效于单击对象的 **"关闭"** 按钮。

如果**保存**参数设置为**提示**并执行**CloseWindow**操作之前不起作用已经保存了对象，一个对话框，提示用户宏关闭之前保存的对象。 如果已将**SetWarnings**操作**警告**参数设置为**No**，不显示对话框，并自动保存的对象。

若要在 Visual Basic for Applications (VBA) 模块中运行 **CloseWindow** 操作，请使用 **DoCmd** 对象的 **CloseWindow** 方法。

