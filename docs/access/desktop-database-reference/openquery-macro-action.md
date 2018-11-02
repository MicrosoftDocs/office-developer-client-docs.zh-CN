---
title: OpenQuery 宏操作
TOCTitle: OpenQuery macro action
ms:assetid: 64bfce73-aeaf-9a78-895c-492e5da43ded
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195094(v=office.15)
ms:contentKeyID: 48545298
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm89069
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1e5e031b0dc89626a40934cb42f8f54a0eb8d057
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928108"
---
# <a name="openquery-macro-action"></a>OpenQuery 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **OpenQuery** 操作在数据表视图、设计视图或打印预览中打开选择查询或交叉表查询。此操作运行动作查询。您还可以为查询选择数据输入模式。


> [!NOTE]
> <P>[!注释] 此操作仅适用于 Microsoft Access 数据库环境（.mdb 或 .accdb）。如果使用的是 Microsoft Access 项目环境 (.adp)，请参阅 <STRONG>OpenView</STRONG>、 <STRONG>OpenStoredProcedure</STRONG> 或 <STRONG>OpenFunction</STRONG> 操作。</P>



## <a name="setting"></a>设置

**OpenQuery** 操作具有下列参数。

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
<td><p><strong>查询名称</strong></p></td>
<td><p>要打开的查询的名称。 宏生成器窗格的<strong>操作参数</strong>部分的<strong>查询名称</strong>框显示当前数据库中的所有查询。 这是必需的参数。如果您运行包含<strong>OpenQuery</strong>操作类库数据库中的宏，Microsoft Access 首先查找具有此名称在类库数据库，然后在当前数据库的查询。</p></td>
</tr>
<tr class="even">
<td><p><strong>View</strong></p></td>
<td><p>打开查询时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Data Mode</strong></p></td>
<td><p>查询的数据输入模式。此参数仅适用于在数据表视图中打开的查询。请单击<strong>“添加”</strong>（用户可添加新记录，但不能编辑现有记录）、<strong>“编辑”</strong>（用户可编辑现有记录和添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

如果您使用**数据表****视图**参数，Access 将显示在结果集中如果查询选择，交叉表，联合，或传递查询其**ReturnsRecords**属性设置为**是**;和操作、 数据定义或其**ReturnsRecords**属性设置为**不**传递查询是否运行查询。

**OpenQuery** 操作类似于在导航窗格中双击查询，或在导航窗格中右键单击查询并选择视图。通过此操作可以选择其他选项。

**提示**

  - 可以将查询从导航窗格拖动到宏操作行中。 这会自动创建的数据表视图中打开查询**OpenQuery**操作。 打开查询时切换到设计视图中删除查询的**数据模式**参数设置。 此设置不会生效，即使用户返回到数据表视图。

  - 如果不想显示通常在运行动作查询时出现的系统消息（指示查询为动作查询并显示将受到影响的记录数），则可以使用 **SetWarnings** 操作禁止显示这些消息。

要在 Visual Basic for Applications (VBA) 模块中运行 **OpenQuery** 操作，请使用 **DoCmd** 对象的 **OpenQuery** 方法。

