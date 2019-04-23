---
title: ADO MD 对象 (Access desktop database reference)
TOCTitle: ADO MD objects
ms:assetid: 13501e44-70b6-1036-a8b7-c276f187e4f4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248907(v=office.15)
ms:contentKeyID: 48543366
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a2d3acf1b236e23522da0143d577bbcbeacbb4b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283294"
---
# <a name="ado-md-objects"></a>ADO MD 对象

**适用于**：Access 2013、Office 2013

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th>Object</th>
<th>说明</th>
</tr>
<tr class="odd">
<td><p><a href="axis-object-ado-md.md">Axis</a></p></td>
<td><p>代表单元格集的位置轴或筛选轴，包含一维或多维的选定成员。</p></td>
</tr>
<tr class="even">
<td><p><a href="catalog-object-ado-md.md">Catalog</a></p></td>
<td><p>包含特定于多维数据提供程序 (MDP) 的多维架构信息（即，多维数据集和基础维、层次结构、级别和成员）。</p></td>
</tr>
<tr class="odd">
<td><p><a href="cell-object-ado-md.md">Cell</a></p></td>
<td><p>代表处于坐标轴交点的数据，包含在单元格集内。</p></td>
</tr>
<tr class="even">
<td><p><a href="cellset-object-ado-md.md">Cellset</a></p></td>
<td><p>代表多维查询的结果。 它是从多维数据集或其他单元格集中选择的单元格的集合。</p></td>
</tr>
<tr class="odd">
<td><p><a href="cubedef-object-ado-md.md">CubeDef</a></p></td>
<td><p>代表多维架构中的多维数据集，包含一组相关的维度。</p></td>
</tr>
<tr class="even">
<td><p><a href="dimension-object-ado-md.md">Dimension</a></p></td>
<td><p>代表多维数据集的维度之一，包含一个或多个成员层次结构。</p></td>
</tr>
<tr class="odd">
<td><p><a href="hierarchy-object-ado-md.md">Hierarchy</a></p></td>
<td><p>表示可将维度的成员进行聚合或&quot;汇总的一种方式。&quot;可以在一个或多个层次结构上聚合一个维度。</p></td>
</tr>
<tr class="even">
<td><p><a href="level-object-ado-md.md">Level</a></p></td>
<td><p>包含一组成员，其中每个成员在层次结构中有相同的等级。</p></td>
</tr>
<tr class="odd">
<td><p><a href="member-object-ado-md.md">Member</a></p></td>
<td><p>代表多维数据集中某个级别的某个成员、某个级别的某个成员的子级，或者单元格集的轴上某个位置的某个成员。</p></td>
</tr>
<tr class="even">
<td><p><a href="position-object-ado-md.md">Position</a></p></td>
<td><p>代表由一个成员或不同维度的多个成员组成的成员集，该成员集定义了轴上的某个点。</p></td>
</tr>
</tbody>
</table>

<br/>

此外，**Catalog** 对象连接到 ADO **Connection** 对象，后者包含在标准 ADO 库中：

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Object</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="connection-object-ado.md">Connection</a></p></td>
<td><p>代表指向数据源的打开的连接。</p></td>
</tr>
</tbody>
</table>

<br/>

很多 ADO MD 对象可包含在相应的集合中。例如，[CubeDef](cubedef-object-ado-md.md) 对象可包含在 **Catalog** 的 [CubeDefs](cubedefs-collection-ado-md.md) 集合中。有关详细信息，请参阅 [ADO MD 集合](ado-md-collections.md)。

