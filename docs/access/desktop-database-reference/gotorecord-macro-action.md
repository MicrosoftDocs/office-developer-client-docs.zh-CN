---
title: GoToRecord 宏操作
TOCTitle: GoToRecord macro action
ms:assetid: 76f936de-739b-63be-9b28-5b0e111408e6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196037(v=office.15)
ms:contentKeyID: 48545712
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm58124
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7534ae84b57d14450009865ea330a4c54d4cfb44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292137"
---
# <a name="gotorecord-macro-action"></a>GoToRecord 宏操作


**适用于**：Access 2013、Office 2013

可以使用 **GoToRecord** 操作将指定记录设置为打开的表、窗体或查询结果集中的当前记录。

## <a name="setting"></a>Setting

**GoToRecord** 操作具有下列参数。

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
<td><p>要设置为当前记录的记录所在的数据库对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“服务器视图”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。如果将此参数留空，则会选择活动对象。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要设置为当前记录的记录所在的对象的名称。“对象名称”<strong></strong>框显示属于“对象类型”<strong></strong>参数所选类型的当前数据库中的所有对象。如果将“对象类型”<strong></strong>参数留空，则也要将此参数留空。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Record</strong></p></td>
<td><p>要设置为当前记录的记录。请单击<strong>“记录”</strong>框中的<strong>“上一个”</strong>、<strong>“下一个”</strong>、<strong>“第一个”</strong>、<strong>“最后一个”</strong>、<strong>“转至”</strong>或<strong>“新建”</strong>。默认值为<strong>“下一个”</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>Offset</strong></p></td>
<td><p>一个整数或求值结果为整数的表达式。 表达式的前面必须有等号 (<strong>=</strong>)。 此参数指定要设置为当前记录的记录。 “偏移量”<strong></strong>参数有两种用法：</p>
<ul>
<li><p>当“记录”<strong></strong>参数为<strong>“下一个”</strong>或<strong>“上一个”</strong>时，Microsoft Office Access 2007 会向前或向后移动“偏移量”<strong></strong>参数指定的记录数。</p></li>
<li><p>当“记录”<strong></strong>参数为<strong>“转至”</strong>时，Access 会移到编号等于“偏移量”<strong></strong>参数的记录。记录编号显示在窗口底部的记录编号框中。</p>
<p><strong>注意</strong>: 如果使用<strong>Record</strong>参数的<strong>第一个</strong>、<strong>最后一个</strong>或<strong>新</strong>设置, Access 将忽略<strong>Offset</strong>参数。 如果输入的“偏移量”<strong></strong>参数过大，Access 将显示一条错误消息。 不能为“偏移量”<strong></strong>参数输入负数。</p></li>
<li><p>当“记录”<strong></strong>参数为<strong>“下一个”</strong>或<strong>“上一个”</strong>时，Microsoft Office Access 2007 会向前或向后移动“偏移量”<strong></strong>参数指定的记录数。</p></li>
<li><p>当“记录”<strong></strong>参数为<strong>“转至”</strong>时，Access 会移到编号等于“偏移量”<strong></strong>参数的记录。记录编号显示在窗口底部的记录编号框中。</p></li>
</ul>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

如果焦点位于记录中的某个特定控件中，此操作会将焦点留在新记录的相同控件中。

You can use the **New** setting for the **Record** argument to move to the blank record at the end of a form or table so you can enter new data.

This action is similar to clicking the arrow below the **Find** button on the **Home** tab and then clicking **Go To**. The **First**, **Last**, **Next**, **Previous**, and **New Record** subcommands of the **Go To** command have the same effect on the selected object as the **First**, **Last**, **Next**, **Previous**, and **New** settings for the **Record** argument. You can also move to records by using the navigation buttons at the bottom of the window.

You can use the **GoToRecord** action to make a record on a hidden form the current record if you specify the hidden form in the **Object Type** and **Object Name** arguments.

要在 Visual Basic for Applications (VBA) 模块中运行 **GoToRecord** 操作，请使用 **DoCmd** 对象的 **GoToRecord** 方法。

