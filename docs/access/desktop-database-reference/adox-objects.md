---
title: ADOX 对象 (Access desktop database reference)
TOCTitle: ADOX objects
ms:assetid: d7db1aed-251b-888b-bc44-f61caeeac403
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250087(v=office.15)
ms:contentKeyID: 48548018
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d5051a9842645ac8f93be26bf6309dd05da7ec24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280299"
---
# <a name="adox-objects"></a><span data-ttu-id="efc50-102">ADOX 对象</span><span class="sxs-lookup"><span data-stu-id="efc50-102">ADOX objects</span></span>

<span data-ttu-id="efc50-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="efc50-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="efc50-104">每个对象可包含在其对应的集合中。</span><span class="sxs-lookup"><span data-stu-id="efc50-104">Each object can be contained in its corresponding collection.</span></span> <span data-ttu-id="efc50-105">例如， **Table** 对象可包含在 [Tables](tables-collection-adox.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="efc50-105">For example, a **Table** object can be contained in a [Tables](tables-collection-adox.md) collection.</span></span> <span data-ttu-id="efc50-106">有关详细信息, 请参阅[ADOX 集合](adox-collections.md)或特定集合主题。</span><span class="sxs-lookup"><span data-stu-id="efc50-106">For more information, see [ADOX collections](adox-collections.md) or a specific collection topic.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="efc50-107">Object</span><span class="sxs-lookup"><span data-stu-id="efc50-107">Object</span></span></p></th>
<th><p><span data-ttu-id="efc50-108">说明</span><span class="sxs-lookup"><span data-stu-id="efc50-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efc50-109"><a href="catalog-object-adox.md">Catalog</a></span><span class="sxs-lookup"><span data-stu-id="efc50-109"><a href="catalog-object-adox.md">Catalog</a></span></span></p></td>
<td><p><span data-ttu-id="efc50-110">包含描述数据源架构目录的集合。</span><span class="sxs-lookup"><span data-stu-id="efc50-110">Contains collections that describe the schema catalog of a data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efc50-111"><a href="column-object-adox.md">列</a></span><span class="sxs-lookup"><span data-stu-id="efc50-111"><a href="column-object-adox.md">Column</a></span></span></p></td>
<td><p><span data-ttu-id="efc50-112">代表表、索引或键中的列。</span><span class="sxs-lookup"><span data-stu-id="efc50-112">Represents a column from a table, index, or key.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efc50-113"><a href="group-object-adox.md">组</a></span><span class="sxs-lookup"><span data-stu-id="efc50-113"><a href="group-object-adox.md">Group</a></span></span></p></td>
<td><p><span data-ttu-id="efc50-114">代表在受保护的数据库中有访问权限的组帐户。</span><span class="sxs-lookup"><span data-stu-id="efc50-114">Represents a group account that has access permissions within a secured database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efc50-115"><a href="index-object-adox.md">索引</a></span><span class="sxs-lookup"><span data-stu-id="efc50-115"><a href="index-object-adox.md">Index</a></span></span></p></td>
<td><p><span data-ttu-id="efc50-116">代表数据库表中的索引。</span><span class="sxs-lookup"><span data-stu-id="efc50-116">Represents an index from a database table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efc50-117"><a href="key-object-adox.md">Key</a></span><span class="sxs-lookup"><span data-stu-id="efc50-117"><a href="key-object-adox.md">Key</a></span></span></p></td>
<td><p><span data-ttu-id="efc50-118">代表数据库表中的主键、外键或唯一键字段。</span><span class="sxs-lookup"><span data-stu-id="efc50-118">Represents a primary, foreign, or unique key field from a database table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efc50-119"><a href="procedure-object-adox.md">步骤</a></span><span class="sxs-lookup"><span data-stu-id="efc50-119"><a href="procedure-object-adox.md">Procedure</a></span></span></p></td>
<td><p><span data-ttu-id="efc50-120">代表存储过程。</span><span class="sxs-lookup"><span data-stu-id="efc50-120">Represents a stored procedure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efc50-121"><a href="table-object-adox.md">Table</a></span><span class="sxs-lookup"><span data-stu-id="efc50-121"><a href="table-object-adox.md">Table</a></span></span></p></td>
<td><p><span data-ttu-id="efc50-122">代表数据库表，包括列、索引和键。</span><span class="sxs-lookup"><span data-stu-id="efc50-122">Represents a database table, including columns, indexes, and keys.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efc50-123"><a href="user-object-adox.md">用户</a></span><span class="sxs-lookup"><span data-stu-id="efc50-123"><a href="user-object-adox.md">User</a></span></span></p></td>
<td><p><span data-ttu-id="efc50-124">代表在受保护的数据库中有访问权限的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="efc50-124">Represents a user account that has access permissions within a secured database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efc50-125"><a href="view-object-adox.md">View</a></span><span class="sxs-lookup"><span data-stu-id="efc50-125"><a href="view-object-adox.md">View</a></span></span></p></td>
<td><p><span data-ttu-id="efc50-126">表示经过筛选的记录集或虚拟表。</span><span class="sxs-lookup"><span data-stu-id="efc50-126">Represents a filtered set of records or a virtual table.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>



