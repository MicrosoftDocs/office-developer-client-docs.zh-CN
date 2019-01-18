---
title: CubeDef 对象 (ADO MD)
TOCTitle: CubeDef object (ADO MD)
ms:assetid: 199235b7-3d98-f655-27bc-94f66e994e06
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248941(v=office.15)
ms:contentKeyID: 48543502
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c82c95a430da76694fe26300e877e86f86a2eb4b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28719902"
---
# <a name="cubedef-object-ado-md"></a>CubeDef 对象 (ADO MD)


**适用于**： Access 2013、 Office 2013

代表多维架构中的多维数据集，包含一组相关的维度。

## <a name="remarks"></a>说明

使用 **CubeDef** 对象的集合和属性，可以执行下列操作：

  - 使用 **Name** 属性标识 [CubeDef](name-property-ado-md.md) 。

  - 使用 [Description](description-property-ado-md.md) 属性返回描述多维数据集的字符串。

  - 使用 [Dimensions](dimensions-collection-ado-md.md) 集合返回构成多维数据集的维。

  - 使用标准 ADO **Properties** 集合获取有关 [CubeDef](properties-collection-ado.md) 的附加信息。

**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CatalogName</p></td>
<td><p>此多维数据集所属的目录的名称。</p></td>
</tr>
<tr class="even">
<td><p>CreatedOn</p></td>
<td><p>多维数据集的创建日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p>CubeGUID</p></td>
<td><p>多维数据集 GUID。</p></td>
</tr>
<tr class="even">
<td><p>多维数据集名称</p></td>
<td><p>多维数据集的名称。</p></td>
</tr>
<tr class="odd">
<td><p>CubeType</p></td>
<td><p>多维数据集的类型。</p></td>
</tr>
<tr class="even">
<td><p>DataUpdatedBy</p></td>
<td><p>执行上一次数据更新的用户的用户 ID。</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>多维数据集的有意义的说明。</p></td>
</tr>
<tr class="even">
<td><p>LastSchemaUpdate</p></td>
<td><p>上次更新架构的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p>SchemaName</p></td>
<td><p>此多维数据集所属的架构的名称。</p></td>
</tr>
<tr class="even">
<td><p>SchemaUpdatedBy</p></td>
<td><p>执行上一次架构更新的用户的用户 ID。</p></td>
</tr>
</tbody>
</table>

