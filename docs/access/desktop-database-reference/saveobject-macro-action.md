---
title: SaveObject 宏操作
TOCTitle: SaveObject macro action
ms:assetid: 85716dfc-f76f-ca47-cc40-f8f88162f85a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196789(v=office.15)
ms:contentKeyID: 48546060
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm116962
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 253067d61a496073692ea4e462b9b0a67f0e26cd
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026293"
---
# <a name="saveobject-macro-action"></a>SaveObject 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **SaveObject** 操作保存指定的 Microsoft Access 对象，如果未指定任何对象，则可以保存活动对象。在某些情况下，还可以用新名称保存活动对象（这与 **"快速访问工具栏"** 上的 **"另存为"** 命令的作用相同）。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**SaveObject** 操作具有下列参数。

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
<td><p>要保存的对象的类型。 单击<strong>表</strong>、<strong>查询</strong>、<strong>窗体</strong>、<strong>报表</strong>、<strong>宏</strong>、<strong>模块</strong>、<strong>数据访问页</strong>、<strong>服务器视图</strong>、<strong>图表</strong>、<strong>存储过程</strong>中，或<strong>对象类型中的<strong>函数</strong></strong>框在宏生成器窗格的<strong>操作参数</strong>部分。 若要选择活动对象，请将此参数留空。 如果此参数中选择的对象类型，您必须在<strong>对象名称</strong>参数中选择现有对象的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要保存的对象的名称。 <strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。 如果将<strong>对象类型</strong>参数留空，您可以将此参数留空保存活动对象，或者，在某些情况下，输入此参数，以保存具有此名称的活动对象中的新名称。 如果输入新名称，该名称必须遵循 Microsoft Access 对象的标准命名约定。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

**SaveObject**操作适用于所有的数据库对象的用户可以直接打开和保存。 指定的对象必须打开**SaveObject**操作已在对象上的任何效果。 此操作具有相同的效果选择一个对象，然后通过单击**快速访问工具栏**上的**保存**保存它。 

**对象类型**参数留空，并在**对象名称**参数中输入新名称具有相同的效果单击**另存为**上的**快速访问工具栏**中，并输入活动对象的新名称。 使用**SaveObject**操作，可以指定对象，以保存并通过宏执行**另存为**命令。

> [!NOTE]
> [!注释] 不能使用 **SaveObject** 操作用新名称保存以下任何一项：
> - 窗体视图或数据表视图中的窗体
> - 打印预览中的报表
> - 模块
> - 数据表视图或打印预览中的服务器视图
> - 页面视图中的数据访问页
> - 数据表视图或打印预览中的表
> - 数据表视图或打印预览中的查询
> - 数据表视图或打印预览中的存储的过程

无论是在当前数据库中运行的宏中执行，还是在类库数据库中运行的宏中执行， **SaveObject** 操作总是将指定对象或活动对象保存在创建该对象的数据库中。

如果活动对象保存使用新名称，但的名称就是此类型的现有对象的名称相同，将会出现一个对话框，询问您是否要覆盖现有对象。 如果已将**SetWarnings**操作**警告**参数设置为**No**，不显示对话框，并自动覆盖旧对象。

若要在 Visual Basic for Applications (VBA) 模块中运行 **SaveObject** 操作，请使用 **DoCmd** 对象的 **Save** 方法。

