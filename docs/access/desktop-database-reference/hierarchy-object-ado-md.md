---
title: Hierarchy 对象 (ADO MD)
TOCTitle: Hierarchy Object (ADO MD)
ms:assetid: 26e4e690-59ad-fb87-66b0-f3310df42d0c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249031(v=office.15)
ms:contentKeyID: 48543825
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 34513e3188653bdba04add376f06911ce86386bd
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468439"
---
# <a name="hierarchy-object-ado-md"></a>Hierarchy 对象 (ADO MD)


**适用于**： Access 2013 |Office 2013

代表可将某个 [Dimension](dimension-object-ado-md.md) 的成员进行聚合或"汇总"的一种方式。可以在一个或多个层次结构上聚合一个维度。

## <a name="remarks"></a>说明

使用 **Hierarchy** 对象的集合和属性，可以执行下列操作：

  - 使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Hierarchy](uniquename-property-ado-md.md) 。

  - 使用 **Description** 属性返回描述 [Hierarchy](description-property-ado-md.md) 的有意义的字符串。

  - 使用 [Levels](level-object-ado-md.md) 集合返回构成 **Hierarchy** 的 [Level](levels-collection-ado-md.md) 对象。

  - 使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Hierarchy** 对象的附加信息。

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
<td><p>AllMember</p></td>
<td><p>位于此层次结构中最高汇总级别的成员。</p></td>
</tr>
<tr class="even">
<td><p>CatalogName</p></td>
<td><p>此多维数据集所属的目录的名称。</p></td>
</tr>
<tr class="odd">
<td><p>多维数据集名称</p></td>
<td><p>多维数据集的名称。</p></td>
</tr>
<tr class="even">
<td><p>DefaultMember</p></td>
<td><p>此层次结构的默认成员的唯一名称。</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>层次结构的有意义的说明。</p></td>
</tr>
<tr class="even">
<td><p>DimensionType</p></td>
<td><p>此层次结构所属的维的类型。</p></td>
</tr>
<tr class="odd">
<td><p>DimensionUniqueName</p></td>
<td><p>维的明确名称。</p></td>
</tr>
<tr class="even">
<td><p>HierarchyCaption</p></td>
<td><p>与层次结构关联的标签或标题。</p></td>
</tr>
<tr class="odd">
<td><p>HierarchyCardinality</p></td>
<td><p>层次结构中的成员数。</p></td>
</tr>
<tr class="even">
<td><p>HierarchyGUID</p></td>
<td><p>层次结构的 GUID。</p></td>
</tr>
<tr class="odd">
<td><p>HierarchyName</p></td>
<td><p>层次结构的名称。</p></td>
</tr>
<tr class="even">
<td><p>HierarchyUniqueName</p></td>
<td><p>层次结构的明确名称。</p></td>
</tr>
<tr class="odd">
<td><p>SchemaName</p></td>
<td><p>此多维数据集所属的架构的名称。</p></td>
</tr>
</tbody>
</table>

