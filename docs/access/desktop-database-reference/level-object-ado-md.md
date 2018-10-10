---
title: Level 对象 (ADO MD)
TOCTitle: Level Object (ADO MD)
ms:assetid: ddbcabce-8777-1068-98a3-be209084f497
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250121(v=office.15)
ms:contentKeyID: 48548160
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 13fce901860768064d450a64c44545f3c3244453
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465882"
---
# <a name="level-object-ado-md"></a>Level 对象 (ADO MD)


**适用于**： Access 2013 |Office 2013

包含一组成员，其中每个成员在层次结构中有相同的等级。

## <a name="remarks"></a>说明

使用 **Level** 对象的集合和属性，可以执行下列操作：

  - 使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Level](uniquename-property-ado-md.md) 。

  - 使用 **Caption** 属性返回在显示 [Level](caption-property-ado-md.md) 时使用的字符串。

  - 使用 **Description** 属性返回描述 [Level](description-property-ado-md.md) 的有意义的字符串。

  - 使用 [Members](member-object-ado-md.md) 集合返回构成 **Level** 的 [Member](members-collection-ado-md.md) 对象。

  - 使用 **Depth** 属性返回来自 [Level](depth-property-ado-md.md) 的根的级别数。

  - 使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Level** 对象的附加信息。

**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CatalogName</p></td>
<td><p>此多维数据集所属的目录的名称。</p></td>
</tr>
<tr class="even">
<td><p>多维数据集名称</p></td>
<td><p>多维数据集的名称。</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>级别的有意义的说明。</p></td>
</tr>
<tr class="even">
<td><p>DimensionUniqueName</p></td>
<td><p><a href="dimension-object-ado-md.md">维度</a>的明确名称。</p></td>
</tr>
<tr class="odd">
<td><p>HierarchyUniqueName</p></td>
<td><p>层次结构的明确名称。</p></td>
</tr>
<tr class="even">
<td><p>LevelCaption</p></td>
<td><p>与级别关联的标签或标题。</p></td>
</tr>
<tr class="odd">
<td><p>LevelCardinality</p></td>
<td><p>级别中的成员数。</p></td>
</tr>
<tr class="even">
<td><p>LevelGUID</p></td>
<td><p>级别的 GUID。</p></td>
</tr>
<tr class="odd">
<td><p>LevelName</p></td>
<td><p>级别的名称。</p></td>
</tr>
<tr class="even">
<td><p>LevelNumber</p></td>
<td><p>层次结构的级别和根之间的距离。</p></td>
</tr>
<tr class="odd">
<td><p>LevelType</p></td>
<td><p>级别的类型。</p></td>
</tr>
<tr class="even">
<td><p>LevelUniqueName</p></td>
<td><p>级别的明确名称。</p></td>
</tr>
<tr class="odd">
<td><p>SchemaName</p></td>
<td><p>此多维数据集所属的架构的名称。</p></td>
</tr>
</tbody>
</table>

