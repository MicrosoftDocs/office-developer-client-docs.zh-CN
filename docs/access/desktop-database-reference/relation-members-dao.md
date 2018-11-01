---
title: Relation Members (DAO)
TOCTitle: Relation Members
ms:assetid: 9ee36e7d-3825-1de8-65fb-64bbcada847c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198338(v=office.15)
ms:contentKeyID: 48546670
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2d6aceacf462898628b0aee9e406860def9474c2
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25889915"
---
# <a name="relation-members-dao"></a><span data-ttu-id="1681b-102">Relation Members (DAO)</span><span class="sxs-lookup"><span data-stu-id="1681b-102">Relation Members (DAO)</span></span>


<span data-ttu-id="1681b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1681b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1681b-104">Relation 对象表示表或查询中的字段之间的关系（仅适用于 Microsoft Access 数据库引擎数据库）。</span><span class="sxs-lookup"><span data-stu-id="1681b-104">A Relation object represents a relationship between fields in tables or queries (Microsoft Access database engine databases only).</span></span>

## <a name="methods"></a><span data-ttu-id="1681b-105">方法</span><span class="sxs-lookup"><span data-stu-id="1681b-105">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1681b-106">名称</span><span class="sxs-lookup"><span data-stu-id="1681b-106">Name</span></span></p></th>
<th><p><span data-ttu-id="1681b-107">说明</span><span class="sxs-lookup"><span data-stu-id="1681b-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1681b-108"><strong><a href="relation-createfield-method-dao.md">CreateField</a></strong></span><span class="sxs-lookup"><span data-stu-id="1681b-108"><strong><a href="relation-createfield-method-dao.md">CreateField</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1681b-109">创建一个新的 <strong><a href="field-object-dao.md">Field</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1681b-109">Creates a new <strong><a href="field-object-dao.md">Field</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="1681b-110">属性</span><span class="sxs-lookup"><span data-stu-id="1681b-110">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1681b-111">名称</span><span class="sxs-lookup"><span data-stu-id="1681b-111">Name</span></span></p></th>
<th><p><span data-ttu-id="1681b-112">说明</span><span class="sxs-lookup"><span data-stu-id="1681b-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1681b-113"><strong><a href="relation-attributes-property-dao.md">Attributes</a></strong></span><span class="sxs-lookup"><span data-stu-id="1681b-113"><strong><a href="relation-attributes-property-dao.md">Attributes</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1681b-p101">设置或返回一个值，该值指示 <strong>Relation</strong> 对象的一个或多个特征。可读写 <strong>Long</strong>。</span><span class="sxs-lookup"><span data-stu-id="1681b-p101">Sets or returns a value that indicates one or more characteristics of a <strong>Relation</strong> object. Read/write <strong>Long</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1681b-116"><strong><a href="relation-fields-property-dao.md">字段</a></strong></span><span class="sxs-lookup"><span data-stu-id="1681b-116"><strong><a href="relation-fields-property-dao.md">Fields</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1681b-p102">返回一个 <strong>Fields</strong> 集合，该集合表示指定对象的所有存储 <strong>Field</strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="1681b-p102">Returns a <strong>Fields</strong> collection that represents all stored <strong>Field</strong> objects for the specified object. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1681b-119"><strong><a href="relation-foreigntable-property-dao.md">ForeignTable</a></strong></span><span class="sxs-lookup"><span data-stu-id="1681b-119"><strong><a href="relation-foreigntable-property-dao.md">ForeignTable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1681b-p103">设置或返回某个关系中的外表的名称（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1681b-p103">Sets or returns the name of the foreign table in a relationship (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1681b-122"><strong><a href="relation-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="1681b-122"><strong><a href="relation-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1681b-p104">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="1681b-p104">Returns or sets the name of the specified object. Read/write <strong>String</strong> if the object has not been appended to a collection. Read-only <strong>String</strong> if the object has been appended to a collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1681b-126"><strong><a href="relation-partialreplica-property-dao.md">PartialReplica</a></strong></span><span class="sxs-lookup"><span data-stu-id="1681b-126"><strong><a href="relation-partialreplica-property-dao.md">PartialReplica</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1681b-p105">设置或返回 <strong>Relation</strong> 对象的值，用于指示从完全副本填充部分副本时是否应当考虑关系。（仅适用于 Microsoft Access 数据库引擎数据库）。可读写 <strong>Boolean</strong>。</span><span class="sxs-lookup"><span data-stu-id="1681b-p105">Sets or returns a value on a <strong>Relation</strong> object indicating whether that relation should be considered when populating a partial replica from a full replica. (Microsoft Access database engine databases only). Read/write <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1681b-130"><strong><a href="relation-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="1681b-130"><strong><a href="relation-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1681b-p106">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</span><span class="sxs-lookup"><span data-stu-id="1681b-p106">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1681b-133"><strong><a href="relation-table-property-dao.md">表</a></strong></span><span class="sxs-lookup"><span data-stu-id="1681b-133"><strong><a href="relation-table-property-dao.md">Table</a></strong></span></span></p></td>
<td><p><span data-ttu-id="1681b-p107">指示 <strong><a href="relation-object-dao.md">Relation</a></strong> 对象的主表的名称。该属性应当等同于 <strong><a href="connection-name-property-dao.md">TableDef</a></strong> 或 <strong><a href="tabledef-object-dao.md">QueryDef</a></strong> 对象的 <strong><a href="querydef-object-dao.md">Name</a></strong> 属性设置（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1681b-p107">Indicates the name of a <strong><a href="relation-object-dao.md">Relation</a></strong> object's primary table. This should be equal to the <strong><a href="connection-name-property-dao.md">Name</a></strong> property setting of a <strong><a href="tabledef-object-dao.md">TableDef</a></strong> or <strong><a href="querydef-object-dao.md">QueryDef</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>

