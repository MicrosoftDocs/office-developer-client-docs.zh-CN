---
title: OpenStoredProcedure 宏操作
TOCTitle: OpenStoredProcedure Macro Action
ms:assetid: b14dbb82-7c8a-0ace-e251-46599551a490
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822003(v=office.15)
ms:contentKeyID: 48547142
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm187628
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 52d7d6c54913511ab593ee77d374ed55984ed40b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25883251"
---
# <a name="openstoredprocedure-macro-action"></a>OpenStoredProcedure 宏操作


**适用于**： Access 2013、 Office 2013

在 Microsoft Access 项目中，可以使用 **OpenStoredProcedure** 操作在数据表视图、存储过程设计视图或打印预览中打开存储过程。如果在数据表视图中打开命名的存储过程，此操作将运行该存储过程。您可以为存储过程选择数据输入模式，以及限制存储过程显示的记录。


> [!NOTE]
> <P>[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</P>



## <a name="setting"></a>设置

**OpenStoredProcedure** 操作具有下列参数。

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
<td><p><strong>过程名称</strong></p></td>
<td><p>要打开的存储过程的名称。 在<strong>操作参数</strong>部分的宏生成器窗格<strong>过程名称框</strong>中显示当前数据库中的所有存储的过程。 这是必需参数。 如果在类库数据库中运行包含 <strong>OpenStoredProcedure</strong> 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的存储过程，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p><strong>View</strong></p></td>
<td><p>打开存储过程时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Data Mode</strong></p></td>
<td><p>存储过程的数据输入模式。此参数仅适用于在数据表视图中打开的存储过程。请单击<strong>“添加”</strong>（用户可添加新记录，但不能查看或编辑现有记录）、<strong>“编辑”</strong>（用户可查看或编辑现有记录以及添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

此操作类似于在导航窗格中双击存储过程，或者在导航窗格中右键单击存储过程，然后选择所需的命令。

存储的过程处于打开状态时切换到设计视图中删除存储过程的**数据模式**参数设置。 此设置不起作用，即使用户返回到数据表视图。


> [!TIP]
> <P></P>
> <UL>
> <LI>
> <P>可以将存储的过程从导航窗格拖动到宏操作行中。 这会自动创建的数据表视图中打开的存储的过程<STRONG>OpenStoredProcedure</STRONG>操作。</P>
> <LI>
> <P>
> 						通常，当运行存储过程时，会显示一些系统消息（指明运行的是存储过程并显示将受影响的记录数），如果不想显示这些消息，可以使用 <STRONG>SetWarning</STRONG> 操作来禁止其显示。
</P></LI></UL>
<P></P>



要在 Visual Basic for Applications (VBA) 模块中运行 **OpenStoredProcedure** 操作，请使用 **DoCmd** 对象的 **OpenStoredProcedure** 方法。

