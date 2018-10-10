---
title: OpenView 宏操作
TOCTitle: OpenView Macro Action
ms:assetid: 4d3b7e6d-4b81-4fbe-7222-24d745350321
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193569(v=office.15)
ms:contentKeyID: 48544726
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm50135
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ad607f852f5af21bc2979bd635286b86d18489a5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466784"
---
# <a name="openview-macro-action"></a>OpenView 宏操作


**适用于**： Access 2013 |Office 2013

在 Microsoft Access 项目中，可以使用 **OpenView** 操作在数据表视图、设计视图或打印预览中打开视图。如果在数据表视图中打开命名视图，此操作将运行该视图。您可以为视图选择数据输入模式，以及限制视图显示的记录。


> [!NOTE]
> <P>[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</P>



## <a name="setting"></a>设置

**OpenView** 操作具有下列参数。

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
<td><p><strong>视图名称</strong></p></td>
<td><p>要打开的视图的名称。 宏生成器窗格的<strong>操作参数</strong>部分的<strong>视图名称</strong>框显示当前数据库中的所有视图。 这是必需参数。 如果在类库数据库中运行包含 <strong>OpenView</strong> 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的视图，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p><strong>View</strong></p></td>
<td><p>打开视图时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Data Mode</strong></p></td>
<td><p>视图的数据输入模式。此参数仅适用于在数据表视图中打开的视图。请单击<strong>“添加”</strong>（用户可添加新记录，但不能查看或编辑现有记录）、<strong>“编辑”</strong>（用户可查看或编辑现有记录以及添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

此操作类似于在导航窗格中双击视图，或者在导航窗格中右键单击视图，然后单击所需的命令。

**提示**

  - 您可以将视图从导航窗格拖至某个宏操作行。这会自动创建在数据表视图中打开该视图的 **OpenView** 操作。

  - 通常，当视图运行时，会显示一些系统消息（指明运行的是视图并显示将受到影响的记录数）。如果不想显示这些系统消息，可以使用 **SetWarning** 操作禁止其显示。

要在 Visual Basic for Applications (VBA) 模块中运行 **OpenView** 操作，请使用 **DoCmd** 对象的 **OpenView** 方法。

