---
title: OpenFunction 宏操作
TOCTitle: OpenFunction macro action
ms:assetid: 0446dbb9-c342-9225-27ba-b8a6892030e1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844833(v=office.15)
ms:contentKeyID: 48543005
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm89179
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 2a9a96b22669889cf4dc51984fc3d3c9f7623428
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930222"
---
# <a name="openfunction-macro-action"></a>OpenFunction 宏操作


**适用于**： Access 2013、 Office 2013

在 Access 项目中，可以使用 **OpenFunction** 操作在数据表视图、内嵌函数设计视图、SQL 文本编辑器视图（针对用户定义的标量或表函数）或打印预览中打开用户定义的函数。当在数据表视图中打开用户定义的函数时，此操作会运行该函数。您还可以为用户定义的函数选择数据输入模式，以及限制用户定义的函数所显示的记录。


> [!NOTE]
> <P>[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</P>



## <a name="setting"></a>设置

**OpenFunction** 操作具有下列参数。

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
<td><p>要打开的用户定义函数的名称。 宏生成器窗格的<strong>函数名称</strong>框在<strong>操作参数</strong>部分显示当前数据库中的所有用户定义的函数。 这是必需的参数。如果您运行包含类库数据库中的<strong>功能</strong>操作的宏，Microsoft Access 首先查找具有此名称在类库数据库，然后在当前数据库中的函数。</p></td>
</tr>
<tr class="even">
<td><p><strong>View</strong></p></td>
<td><p>打开用户定义的函数时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Data Mode</strong></p></td>
<td><p>用户定义的函数的数据输入模式。此参数仅适用于在数据表视图中打开的用户定义的函数。请单击<strong>“添加”</strong>（用户可添加新记录，但不能查看或编辑现有记录）、<strong>“编辑”</strong>（用户可查看或编辑现有记录以及添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

此操作类似于在导航窗格中双击用户定义的函数，或在导航窗格中右键单击该函数并选择视图。

打开的用户定义的函数时切换到设计视图中删除用户定义函数的**数据模式**参数设置。 此设置不起作用，即使用户返回到数据表视图。

**提示**

  - 您可以在导航窗格中选择用户定义的函数并将其拖至宏操作行。这样会自动创建在数据表视图中打开该用户定义的函数的 **OpenFunction** 操作。

  - 通常，当用户定义的函数运行时，会显示一些系统消息（指明运行的是用户定义的函数并显示将受到影响的记录数）。如果不想显示这些系统消息，可以使用 **SetWarning** 操作来禁止其显示。

要在 Visual Basic for Applications (VBA) 模块中运行 **OpenFunction** 操作，请使用 **DoCmd** 对象的 **OpenFunction** 方法。

