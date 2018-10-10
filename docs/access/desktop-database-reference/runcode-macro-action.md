---
title: RunCode 宏操作
TOCTitle: RunCode Macro Action
ms:assetid: cb0625be-4b5d-4927-9b0e-59a6e411b5bb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834373(v=office.15)
ms:contentKeyID: 48547706
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm98700
f1_categories:
- Office.Version=v15
ms.openlocfilehash: c13f6fed20bebb40f4a8cacc3deedd7467ff55e4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465583"
---
# <a name="runcode-macro-action"></a>RunCode 宏操作


**适用于**： Access 2013 |Office 2013

可以使用 **RunCode** 操作调用 Visual Basic for Applications (VBA) Function 过程。

## <a name="setting"></a>设置

**RunCode** 操作具有以下参数。

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
<td><p><strong>函数名称</strong></p></td>
<td><p>要调用的 VBA Function 过程的名称。请将所有函数参数放在括号中。在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“函数名称”</strong>框中输入函数名称。这是一个必选参数。</p>

> [!NOTE]
> <P>在 Microsoft Access 数据库（.mdb 或 .accdb）中，单击<STRONG>“生成”</STRONG>按钮，以便使用表达式生成器为此参数选择一个函数。在表达式生成器中的列表中单击所需的函数。</P>


<p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

用户定义的 Function 过程都存储在 Microsoft Access 模块中。

即使 Function 过程不具有任何参数，括号也是必需的，如下面的示例所示：

`TestFunction()`

**函数名称**参数中的函数名称不与用于事件属性设置的用户定义的函数名称，不同开头等号 (**=**)。

Access 会忽略函数的返回值。


> [!NOTE]
> <P>[!注释] 如果函数名称与模块名称相同，则不能通过宏调用 Function 过程。</P>




> [!TIP]
> <P>[!提示] 要运行用 Visual Basic 编写的 Sub 过程或事件过程，请创建一个调用 Sub 过程或事件过程的 Function 过程。然后使用 <STRONG>RunCode</STRONG> 操作运行该 Function 过程。</P>



如果您使用**RunCode**操作调用的函数，访问查找函数使用数据库标准模块中的**函数名称**参数指定的名称。 但是，当运行此操作的窗体或报表上的菜单命令或在窗体或报表上的事件的响应，访问首先查找函数在窗体或报表的类模块，然后在标准模块。 Access 不搜索显示在导航窗格中的**函数名称**参数指定的函数**模块**区域中的类模块。

此操作不能在 VBA 模块中使用。然而，可以直接在 VBA 中运行所需的 Function 过程。

