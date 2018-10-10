---
title: Dimension 对象 (ADO MD)
TOCTitle: Dimension Object (ADO MD)
ms:assetid: 12f43cfc-c74e-a2e8-7f6e-75fc68472c4b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248902(v=office.15)
ms:contentKeyID: 48543355
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 15ae89905c9ca82c4c41701c4ed713c02722e322
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465571"
---
# <a name="dimension-object-ado-md"></a>Dimension 对象 (ADO MD)


**适用于**： Access 2013 |Office 2013

代表多维数据集的维度之一，包含一个或多个成员层次结构。

## <a name="remarks"></a>说明

使用 **Dimension** 对象的集合和属性，可以执行下列操作：

  - 使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Dimension](uniquename-property-ado-md.md) 。

  - 使用 **Description** 属性返回描述 [Dimension](description-property-ado-md.md) 的有意义的字符串。

  - 使用 [Hierarchies](hierarchy-object-ado-md.md) 集合返回构成 **Dimension** 的 [Hierarchy](hierarchies-collection-ado-md.md) 对象。

  - 使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Dimension** 对象的附加信息。

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
<td><p>DefaultHierarchy</p></td>
<td><p>默认层次结构的唯一名称。</p></td>
</tr>
<tr class="even">
<td><p>说明</p></td>
<td><p>多维数据集的有意义的说明。</p></td>
</tr>
<tr class="odd">
<td><p>DimensionCaption</p></td>
<td><p>与维关联的标签或标题。</p></td>
</tr>
<tr class="even">
<td><p>DimensionCardinality</p></td>
<td><p>维中的成员数。</p></td>
</tr>
<tr class="odd">
<td><p>DimensionGUID</p></td>
<td><p>维的 GUID。</p></td>
</tr>
<tr class="even">
<td><p>维度</p></td>
<td><p>维的名称。</p></td>
</tr>
<tr class="odd">
<td><p>DimensionOrdinal</p></td>
<td><p>构成多维数据集的维组中维的序号。</p></td>
</tr>
<tr class="even">
<td><p>DimensionType</p></td>
<td><p>维类型。</p></td>
</tr>
<tr class="odd">
<td><p>DimensionUniqueName</p></td>
<td><p>维的明确名称。</p></td>
</tr>
<tr class="even">
<td><p>SchemaName</p></td>
<td><p>此多维数据集所属的架构的名称。</p></td>
</tr>
</tbody>
</table>

