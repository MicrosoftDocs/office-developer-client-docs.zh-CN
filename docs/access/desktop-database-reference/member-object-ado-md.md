---
title: Member 对象 (ADO MD)
TOCTitle: Member Object (ADO MD)
ms:assetid: d80c024a-07dc-7a35-f8f2-b4d5b19d89e4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250088(v=office.15)
ms:contentKeyID: 48548025
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: caa3bd6e36c26864e263653cc63a85d35d2d1232
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467956"
---
# <a name="member-object-ado-md"></a>Member 对象 (ADO MD)


**适用于**： Access 2013 |Office 2013

代表多维数据集中某个级别的某个成员、某个级别的某个成员的子级，或者单元格集的轴上某个位置的某个成员。

## <a name="remarks"></a>说明

每个 **Member** 的属性各有不同，具体取决于所使用的上下文。 **CubeDef** 中的 [Level](level-object-ado-md.md) 的 [Member](cubedef-object-ado-md.md) 具有一个 [Children](children-property-ado-md.md) 属性，该属性返回层次结构中比当前 **Member** 低一个级别的 **Members** 。对于 **Position** 的 [Member](position-object-ado-md.md) ， **Children** 集合始终为空。另外， [Type](type-property-ado-md.md) 属性仅应用于 **Level** 的 **Members** 。

**Position** 的 **Member** 有两个属性 - [DrilledDown](drilleddown-property-ado-md.md) 和 [ParentSameAsPrev](parentsameasprev-property-ado-md.md)，它们在显示 [Cellset](cellset-object-ado-md.md) 时很有用。如果在 **Level** 的 **Member** 上访问这些属性，将发生错误。

使用 **Level** 的 **Member** 对象的集合和属性，可以执行下列操作：

  - 使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Member](uniquename-property-ado-md.md) 。

  - 使用 **Caption** 属性返回在显示 [Member](caption-property-ado-md.md) 时使用的字符串。

  - 使用 **Description** 属性返回描述度量或公式 [Member](description-property-ado-md.md) 的有意义的字符串。

  - 使用 **Type** 属性确定 [Member](type-property-ado-md.md) 的性质。

  - 使用 **LevelDepth** 和 **LevelName** 属性获取有关 [Member](leveldepth-property-ado-md.md) 的 [Level](levelname-property-ado-md.md) 的信息。

  - 使用 **Parent** 和 [Children](hierarchy-object-ado-md.md) 属性获取 [Hierarchy](parent-property-ado-md.md) 中的相关 [Members](children-property-ado-md.md) 。

  - 使用 **ChildCount** 属性对 [Member](childcount-property-ado-md.md) 的子级进行计数。

  - 使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Level** 对象的附加信息。

使用沿 **Axis** 的 **Position** 的 [Member](axis-object-ado-md.md) 的集合和属性，可以执行下列操作：

  - 使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Member](uniquename-property-ado-md.md) 。

  - 使用 **Caption** 属性返回在显示 [Member](caption-property-ado-md.md) 时使用的字符串。

  - 使用 **Description** 属性返回描述度量或公式 [Member](description-property-ado-md.md) 的有意义的字符串。

  - 使用 **LevelDepth** 和 **LevelName** 属性获取有关 [Member](leveldepth-property-ado-md.md) 的 [Level](levelname-property-ado-md.md) 的信息。

  - 使用 **ChildCount** 属性对 [Member](childcount-property-ado-md.md) 的子级进行计数。

  - 使用 [DrilledDown](drilleddown-property-ado-md.md) 属性确定此 **Member** 在 **Axis** 上是否至少有一个直接子级。

  - 使用 [ParentSameAsPrev](parentsameasprev-property-ado-md.md) 属性确定此 **Member** 的父级是否与直接父级 **Member** 的父级相同。

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
<td><p>ChildrenCardinality</p></td>
<td><p>成员具有的子级数目。</p></td>
</tr>
<tr class="odd">
<td><p>多维数据集名称</p></td>
<td><p>多维数据集的名称。</p></td>
</tr>
<tr class="even">
<td><p>Description</p></td>
<td><p>成员的有意义的说明。</p></td>
</tr>
<tr class="odd">
<td><p>DimensionUniqueName</p></td>
<td><p><a href="dimension-object-ado-md.md">维度</a>的明确名称。</p></td>
</tr>
<tr class="even">
<td><p>HierarchyUniqueName</p></td>
<td><p>层次结构的明确名称。</p></td>
</tr>
<tr class="odd">
<td><p>LevelNumber</p></td>
<td><p>层次结构的级别和根之间的距离。</p></td>
</tr>
<tr class="even">
<td><p>LevelUniqueName</p></td>
<td><p>级别的明确名称。</p></td>
</tr>
<tr class="odd">
<td><p>MemberCaption</p></td>
<td><p>与成员关联的标签或标题。</p></td>
</tr>
<tr class="even">
<td><p>MemberGUID</p></td>
<td><p>成员的 GUID。</p></td>
</tr>
<tr class="odd">
<td><p>成员名称</p></td>
<td><p>成员的名称。</p></td>
</tr>
<tr class="even">
<td><p>MemberOrdinal</p></td>
<td><p>成员的序号。</p></td>
</tr>
<tr class="odd">
<td><p>MemberType</p></td>
<td><p>成员的类型。</p></td>
</tr>
<tr class="even">
<td><p>成员的唯一名称</p></td>
<td><p>成员的明确名称。</p></td>
</tr>
<tr class="odd">
<td><p>ParentCount</p></td>
<td><p>此成员具有的父级数目。</p></td>
</tr>
<tr class="even">
<td><p>ParentLevel</p></td>
<td><p>成员父级的级别号。</p></td>
</tr>
<tr class="odd">
<td><p>ParentUniqueName</p></td>
<td><p>成员父级的明确名称。</p></td>
</tr>
<tr class="even">
<td><p>SchemaName</p></td>
<td><p>此多维数据集所属的架构的名称。</p></td>
</tr>
</tbody>
</table>

