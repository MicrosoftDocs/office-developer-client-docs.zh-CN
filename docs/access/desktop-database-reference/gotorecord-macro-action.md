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
ms.openlocfilehash: 5986b8e891b42ce37cb68d8ce06e7f33feba1b8f
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937727"
---
# <a name="gotorecord-macro-action"></a>GoToRecord 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **GoToRecord** 操作将指定记录设置为打开的表、窗体或查询结果集中的当前记录。

## <a name="setting"></a>设置

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
<td><p>包含您要使成为当前记录的记录的对象的名称。 <strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型为当前数据库中的所有对象。 如果将<strong>对象类型</strong>参数留空，还应将此参数留空。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Record</strong></p></td>
<td><p>要设置为当前记录的记录。请单击<strong>“记录”</strong>框中的<strong>“上一个”</strong>、<strong>“下一个”</strong>、<strong>“第一个”</strong>、<strong>“最后一个”</strong>、<strong>“转至”</strong>或<strong>“新建”</strong>。默认值为<strong>“下一个”</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>Offset</strong></p></td>
<td><p>整数或计算结果为一个整数值的表达式。 一个表达式前面必须有一个等号 (<strong>=</strong>)。 此参数指定要使成为当前记录的记录。 您可以使用两种方式的<strong>偏移量</strong>参数：</p>
<ul>
<li><p>当<strong>记录</strong>参数为<strong>下一个</strong>或<strong>上一步</strong>时，Microsoft Office Access 2007 将移动向前或向后<strong>偏移</strong>参数中指定的记录数。</p></li>
<li><p><strong>转到</strong><strong>记录</strong>参数时，Access 将移动到的记录数等于<strong>偏移量</strong>参数中。 记录号显示在窗口底部的记录编号框。</p></li>
</ul>

> [!NOTE]
> 如果您使用的**第一个**、**最后一个**，或**新建**设置为**记录**参数，则 Access 将忽略**偏移量**参数。 如果输入太大的**偏移量**参数，则 Access 将显示一条错误消息。 不能的**偏移量**参数输入负数。


<p></p>
<ul>
<li><p>当<strong>记录</strong>参数为<strong>下一个</strong>或<strong>上一步</strong>时，Microsoft Office Access 2007 将移动向前或向后<strong>偏移</strong>参数中指定的记录数。</p></li>
<li><p><strong>转到</strong><strong>记录</strong>参数时，Access 将移动到的记录数等于<strong>偏移量</strong>参数中。 记录号显示在窗口底部的记录编号框。</p></li>
</ul></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

如果焦点位于记录中的某个特定控件中，此操作会将焦点留在新记录的相同控件中。

您可以使用**记录**参数的**新**设置移至窗体或表末尾的空白记录，以便您可以输入新的数据。

类似于单击下**主页**选项卡上的**查找**按钮的箭头，然后单击**转到**此操作。 **第一个**、**最后一个**、**下一个**、**上一步**和**新记录**子命令的**转到**命令具有对所选对象作为**第一个**、**最后一个**、**下一个**、**上一步**，相同的影响和**记录**参数的**新**设置。 您还可以使用窗口的底部的导航按钮记录移动。

您可以使用**GoToRecord**操作使隐藏窗体上的当前记录的记录，如果在**对象类型**和**对象名称**参数中指定了隐藏窗体。

要在 Visual Basic for Applications (VBA) 模块中运行 **GoToRecord** 操作，请使用 **DoCmd** 对象的 **GoToRecord** 方法。

