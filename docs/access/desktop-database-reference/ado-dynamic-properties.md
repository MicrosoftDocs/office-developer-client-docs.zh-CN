---
title: ADO 动态属性
TOCTitle: ADO dynamic properties
ms:assetid: a908bc52-2cb0-89c7-a997-2cde93477e4d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249782(v=office.15)
ms:contentKeyID: 48546915
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fae0df2a4cc5c9de585d2b101e9fa31cb6a0a545
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28714519"
---
# <a name="ado-dynamic-properties"></a>ADO 动态属性

**适用于**： Access 2013、 Office 2013

可以将动态属性添加到 [Connection](properties-collection-ado.md)、[Command](connection-object-ado.md) 或 [Recordset](command-object-ado.md) 对象的 [Properties](recordset-object-ado.md) 集合中。这些属性的源是数据提供程序（例如 [OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md)）或服务提供程序（例如 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md)）。有关特定动态属性的详细信息，请参考相应的数据提供程序或服务提供程序文档。

[ADO 动态属性索引](ado-dynamic-property-index.md)为每个标准 OLE DB 提供程序动态属性提供 ADO 和 OLE DB 名称之间的交叉引用。

以下动态属性需要特别注意，上述数据源文档也记录了这些属性。下面列出的 ADO 帮助主题列出了 ADO 提供的特殊功能。

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th>动态属性</th>
<th>说明</th>
</tr>
<tr class="odd">
<td><p><a href="optimize-property-dynamic-ado.md">优化</a></p></td>
<td><p>指定是否应当创建此字段的索引。</p></td>
</tr>
<tr class="even">
<td><p><a href="prompt-property-dynamic-ado.md">Prompt</a></p></td>
<td><p>指定 OLE DB 提供程序是否应当提示用户输入初始化信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="reshape-name-property-dynamic-ado.md">Reshape Name</a></p></td>
<td><p>指定 <strong>Recordset</strong> 对象的名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="resync-command-property-dynamic-ado.md">Resync Command</a></p></td>
<td><p>指定一个用户提供的命令字符串，<strong>Resync</strong> 方法会发出此命令字符串以刷新 <strong>Unique Table</strong> 动态属性中指定的表中的数据。</p></td>
</tr>
<tr class="odd">
<td><p><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Table、 Unique Schema、 Unique Catalog</a></p></td>
<td><p><strong>Unique Table</strong> -指定在其允许更新、 插入和删除的基表的名称。<br/><br/><strong>Unique Schema</strong> -指定架构或表的所有者的名称。<br/><br/><strong>Unique Catalog</strong> -指定目录或包含表的数据库的名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="update-resync-property-dynamic-ado.md">Update Resync</a></p></td>
<td><p>指定是否在 <strong>UpdateBatch</strong> 方法后跟一个隐式 <strong>Resync</strong> 方法操作，如果是，还要指定该操作的范围。</p></td>
</tr>
</tbody>
</table>

<br/>

