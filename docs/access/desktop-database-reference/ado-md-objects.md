---
title: ADO MD 对象 （访问桌面数据库参考 （英文）
TOCTitle: ADO MD objects
ms:assetid: 13501e44-70b6-1036-a8b7-c276f187e4f4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248907(v=office.15)
ms:contentKeyID: 48543366
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a2d3acf1b236e23522da0143d577bbcbeacbb4b7
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726209"
---
# <a name="ado-md-objects"></a><span data-ttu-id="eae86-102">ADO MD 对象</span><span class="sxs-lookup"><span data-stu-id="eae86-102">ADO MD objects</span></span>

<span data-ttu-id="eae86-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="eae86-103">**Applies to**: Access 2013, Office 2013</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th><span data-ttu-id="eae86-104">对象</span><span class="sxs-lookup"><span data-stu-id="eae86-104">Object</span></span></th>
<th><span data-ttu-id="eae86-105">说明</span><span class="sxs-lookup"><span data-stu-id="eae86-105">Description</span></span></th>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae86-106"><a href="axis-object-ado-md.md">Axis</a></span><span class="sxs-lookup"><span data-stu-id="eae86-106"><a href="axis-object-ado-md.md">Axis</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-107">代表单元格集的位置轴或筛选轴，包含一维或多维的选定成员。</span><span class="sxs-lookup"><span data-stu-id="eae86-107">Represents a positional or filter axis of a cellset, containing selected members of one or more dimensions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae86-108"><a href="catalog-object-ado-md.md">Catalog</a></span><span class="sxs-lookup"><span data-stu-id="eae86-108"><a href="catalog-object-ado-md.md">Catalog</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-109">包含特定于多维数据提供程序 (MDP) 的多维架构信息（即，多维数据集和基础维、层次结构、级别和成员）。</span><span class="sxs-lookup"><span data-stu-id="eae86-109">Contains multidimensional schema information (that is, cubes and underlying dimensions, hierarchies, levels, and members) specific to a multidimensional data provider (MDP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae86-110"><a href="cell-object-ado-md.md">Cell</a></span><span class="sxs-lookup"><span data-stu-id="eae86-110"><a href="cell-object-ado-md.md">Cell</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-111">代表处于坐标轴交点的数据，包含在单元格集内。</span><span class="sxs-lookup"><span data-stu-id="eae86-111">Represents the data at the intersection of axis coordinates, contained in a cellset.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae86-112"><a href="cellset-object-ado-md.md">Cellset</a></span><span class="sxs-lookup"><span data-stu-id="eae86-112"><a href="cellset-object-ado-md.md">Cellset</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-p101">代表多维查询的结果。它是从多维数据集或其他单元格集中选择的单元格的集合。</span><span class="sxs-lookup"><span data-stu-id="eae86-p101">Represents the results of a multidimensional query. It is a collection of cells selected from cubes or other cellsets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae86-115"><a href="cubedef-object-ado-md.md">CubeDef</a></span><span class="sxs-lookup"><span data-stu-id="eae86-115"><a href="cubedef-object-ado-md.md">CubeDef</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-116">代表多维架构中的多维数据集，包含一组相关的维度。</span><span class="sxs-lookup"><span data-stu-id="eae86-116">Represents a cube from a multidimensional schema, containing a set of related dimensions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae86-117"><a href="dimension-object-ado-md.md">Dimension</a></span><span class="sxs-lookup"><span data-stu-id="eae86-117"><a href="dimension-object-ado-md.md">Dimension</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-118">代表多维数据集的维度之一，包含一个或多个成员层次结构。</span><span class="sxs-lookup"><span data-stu-id="eae86-118">Represents one of the dimensions of a multidimensional cube, containing one or more hierarchies of members.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae86-119"><a href="hierarchy-object-ado-md.md">Hierarchy</a></span><span class="sxs-lookup"><span data-stu-id="eae86-119"><a href="hierarchy-object-ado-md.md">Hierarchy</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-120">代表一个方式在其中可聚合的维度成员或&quot;上卷得到。&quot;一个或多个层次结构可以聚合一个维度。</span><span class="sxs-lookup"><span data-stu-id="eae86-120">Represents one way in which the members of a dimension can be aggregated or &quot;rolled up.&quot; A dimension can be aggregated along one or more hierarchies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae86-121"><a href="level-object-ado-md.md">Level</a></span><span class="sxs-lookup"><span data-stu-id="eae86-121"><a href="level-object-ado-md.md">Level</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-122">包含一组成员，其中每个成员在层次结构中有相同的等级。</span><span class="sxs-lookup"><span data-stu-id="eae86-122">Contains a set of members, each of which has the same rank within a hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eae86-123"><a href="member-object-ado-md.md">成员</a></span><span class="sxs-lookup"><span data-stu-id="eae86-123"><a href="member-object-ado-md.md">Member</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-124">代表多维数据集中某个级别的某个成员、某个级别的某个成员的子级，或者单元格集的轴上某个位置的某个成员。</span><span class="sxs-lookup"><span data-stu-id="eae86-124">Represents a member of a level in a cube, the children of a member of a level, or a member of a position along an axis of a cellset.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eae86-125"><a href="position-object-ado-md.md">Position</a></span><span class="sxs-lookup"><span data-stu-id="eae86-125"><a href="position-object-ado-md.md">Position</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-126">表示由一个成员或不同维度的多个成员组成的成员集，该成员集定义了轴上的某个点。</span><span class="sxs-lookup"><span data-stu-id="eae86-126">Represents a set of one or more members of different dimensions that defines a point along an axis.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="eae86-127">此外， **Catalog** 对象连接到 ADO **Connection** 对象，后者包含在标准 ADO 库中：</span><span class="sxs-lookup"><span data-stu-id="eae86-127">Also, the **Catalog** object is connected to an ADO **Connection** object, which is included with the standard ADO library:</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="eae86-128">对象</span><span class="sxs-lookup"><span data-stu-id="eae86-128">Object</span></span></p></th>
<th><p><span data-ttu-id="eae86-129">说明</span><span class="sxs-lookup"><span data-stu-id="eae86-129">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eae86-130"><a href="connection-object-ado.md">Connection</a></span><span class="sxs-lookup"><span data-stu-id="eae86-130"><a href="connection-object-ado.md">Connection</a></span></span></p></td>
<td><p><span data-ttu-id="eae86-131">表示指向数据源的打开的连接。</span><span class="sxs-lookup"><span data-stu-id="eae86-131">Represents an open connection to a data source.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="eae86-p102">很多 ADO MD 对象可包含在相应的集合中。例如，[CubeDef](cubedef-object-ado-md.md) 对象可包含在 [Catalog](cubedefs-collection-ado-md.md) 的 **CubeDefs** 集合中。有关详细信息，请参阅 [ADO MD 集合](ado-md-collections.md)。</span><span class="sxs-lookup"><span data-stu-id="eae86-p102">Many ADO MD objects can be contained in a corresponding collection. For example, a [CubeDef](cubedef-object-ado-md.md) object can be contained in a [CubeDefs](cubedefs-collection-ado-md.md) collection of a **Catalog**. For more information, see [ADO MD Collections](ado-md-collections.md).</span></span>

