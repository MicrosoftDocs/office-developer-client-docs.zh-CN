---
title: CloseWindow 宏操作
TOCTitle: CloseWindow macro action
ms:assetid: ba96bc26-7f3f-fd3d-8d3a-e18bfe90cdf0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822510(v=office.15)
ms:contentKeyID: 48547377
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm64319
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 4397846abdc0d10b6bfa0e6a1eb5c0c435fc862a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296288"
---
# <a name="closewindow-macro-action"></a>CloseWindow 宏操作


**适用于**：Access 2013、Office 2013

您可以使用**CloseWindow**操作关闭指定的 Access 文档选项卡或活动文档选项卡 (如果未指定)。

## <a name="setting"></a>Setting

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
<td><p>要关闭其文档选项卡的数据库对象的类型。 请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。 要选择活动的文档选项卡，请将此参数留空。</p>

> [!NOTE]
> 如果要在 Visual Basic 编辑器中关闭模块，则必须在“对象类型”**** 参数中使用 **“模块”**。


<p></p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要关闭的对象的名称。<strong>“对象名称”</strong>框会显示数据库中属于“对象类型”<strong></strong>参数所选的类型的所有对象。单击该对象可将其关闭。如果将“对象类型”<strong></strong>参数留空，则也要将此参数留空。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Save</strong></p></td>
<td><p>关闭对象时是否保存对其所做的更改。单击<strong>“是”</strong>（保存对象）、<strong>“否”</strong>（关闭对象但不保存）或<strong>“提示”</strong>（提示用户是否保存对象）。默认值为<strong>“提示”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

**CloseWindow** 操作适用于用户可显式打开或关闭的所有数据库对象。此操作等效于选择某个对象，然后通过右键单击该对象的文档选项卡并单击快捷菜单上的 **"关闭"** 来关闭该对象，也等效于单击对象的 **"关闭"** 按钮。

If the **Save** argument is set to **Prompt** and the object hasn't already been saved before the **CloseWindow** action is carried out, a dialog box prompts the user to save the object before the macro closes it. If you have set the **Warnings On** argument of the **SetWarnings** action to **No**, the dialog box is not displayed and the object is automatically saved.

若要在 Visual Basic for Applications (VBA) 模块中运行 **CloseWindow** 操作，请使用 **DoCmd** 对象的 **CloseWindow** 方法。

