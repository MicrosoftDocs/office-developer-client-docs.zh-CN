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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281713"
---
# <a name="ado-dynamic-properties"></a><span data-ttu-id="ec1ee-102">ADO 动态属性</span><span class="sxs-lookup"><span data-stu-id="ec1ee-102">ADO dynamic properties</span></span>

<span data-ttu-id="ec1ee-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ec1ee-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ec1ee-p101">可以将动态属性添加到 [Connection](properties-collection-ado.md)、[Command](connection-object-ado.md) 或 [Recordset](command-object-ado.md) 对象的 [Properties](recordset-object-ado.md) 集合中。这些属性的源是数据提供程序（例如 [OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md)）或服务提供程序（例如 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md)）。有关特定动态属性的详细信息，请参考相应的数据提供程序或服务提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-p101">Dynamic properties can be added to the [Properties](properties-collection-ado.md) collections of the [Connection](connection-object-ado.md), [Command](command-object-ado.md), or [Recordset](recordset-object-ado.md) objects. The source for these properties is either a data provider, such as the [OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md), or a service provider, such as the [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md). Refer to the appropriate data provider or service provider documentation for more information about a specific dynamic property.</span></span>

<span data-ttu-id="ec1ee-107">[ADO 动态属性索引](ado-dynamic-property-index.md)为每个标准 OLE DB 提供程序动态属性提供 ADO 和 OLE DB 名称之间的交叉引用。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-107">The [ADO Dynamic Property Index](ado-dynamic-property-index.md) provides a cross-reference between the ADO and OLE DB names for each standard OLE DB provider dynamic property.</span></span>

<span data-ttu-id="ec1ee-p102">以下动态属性需要特别注意，上述数据源文档也记录了这些属性。下面列出的 ADO 帮助主题列出了 ADO 提供的特殊功能。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-p102">The following dynamic properties are of special interest, and are also documented in the sources mentioned above. Special functionality with ADO is documented in the ADO help topics listed below.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th><span data-ttu-id="ec1ee-110">动态属性</span><span class="sxs-lookup"><span data-stu-id="ec1ee-110">Dynamic property</span></span></th>
<th><span data-ttu-id="ec1ee-111">说明</span><span class="sxs-lookup"><span data-stu-id="ec1ee-111">Description</span></span></th>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec1ee-112"><a href="optimize-property-dynamic-ado.md">优化</a></span><span class="sxs-lookup"><span data-stu-id="ec1ee-112"><a href="optimize-property-dynamic-ado.md">Optimize</a></span></span></p></td>
<td><p><span data-ttu-id="ec1ee-113">指定是否应当创建此字段的索引。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-113">Specifies whether an index should be created on this field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec1ee-114"><a href="prompt-property-dynamic-ado.md">Prompt</a></span><span class="sxs-lookup"><span data-stu-id="ec1ee-114"><a href="prompt-property-dynamic-ado.md">Prompt</a></span></span></p></td>
<td><p><span data-ttu-id="ec1ee-115">指定 OLE DB 提供程序是否应当提示用户输入初始化信息。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-115">Specifies whether the OLE DB provider should prompt the user for initialization information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec1ee-116"><a href="reshape-name-property-dynamic-ado.md">Reshape Name</a></span><span class="sxs-lookup"><span data-stu-id="ec1ee-116"><a href="reshape-name-property-dynamic-ado.md">Reshape Name</a></span></span></p></td>
<td><p><span data-ttu-id="ec1ee-117">指定 <strong>Recordset</strong> 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-117">Specifies a name for the <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec1ee-118"><a href="resync-command-property-dynamic-ado.md">Resync Command</a></span><span class="sxs-lookup"><span data-stu-id="ec1ee-118"><a href="resync-command-property-dynamic-ado.md">Resync Command</a></span></span></p></td>
<td><p><span data-ttu-id="ec1ee-119">指定一个用户提供的命令字符串，<strong>Resync</strong> 方法会发出此命令字符串以刷新 <strong>Unique Table</strong> 动态属性中指定的表中的数据。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-119">Specifies a user-supplied command string that the <strong>Resync</strong> method issues to refresh the data in the table named in the <strong>Unique Table</strong> dynamic property.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec1ee-120"><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Table、Unique Schema 和 Unique Catalog</a></span><span class="sxs-lookup"><span data-stu-id="ec1ee-120"><a href="unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md">Unique Table, Unique Schema, Unique Catalog</a></span></span></p></td>
<td><p><span data-ttu-id="ec1ee-121"><strong>Unique table</strong> -指定允许在其上进行更新、插入和删除的基表的名称。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-121"><strong>Unique Table</strong> — specifies the name of the base table upon which updates, insertions, and deletions are allowed.</span></span><br/><br/><span data-ttu-id="ec1ee-122"><strong>Unique schema</strong> -指定表所有者的架构或名称。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-122"><strong>Unique Schema</strong> — specifies the schema, or name of the owner of the table.</span></span><br/><br/><span data-ttu-id="ec1ee-123"><strong>Unique catalog</strong> -指定包含该表的数据库的目录或名称。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-123"><strong>Unique Catalog</strong> — specifies the catalog, or name of the database containing the table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec1ee-124"><a href="update-resync-property-dynamic-ado.md">Update Resync</a></span><span class="sxs-lookup"><span data-stu-id="ec1ee-124"><a href="update-resync-property-dynamic-ado.md">Update Resync</a></span></span></p></td>
<td><p><span data-ttu-id="ec1ee-125">指定 <strong>UpdateBatch</strong> 方法后面是否跟随隐式的 <strong>Resync</strong> 方法操作，如果跟随，则指定该操作的范围。</span><span class="sxs-lookup"><span data-stu-id="ec1ee-125">Specifies whether the <strong>UpdateBatch</strong> method is followed by an implicit <strong>Resync</strong> method operation, and if so, the scope of that operation.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

