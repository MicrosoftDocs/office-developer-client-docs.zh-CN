---
title: 关系成员 (DAO)
TOCTitle: Relation Members
ms:assetid: 9ee36e7d-3825-1de8-65fb-64bbcada847c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198338(v=office.15)
ms:contentKeyID: 48546670
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 84e18afe4a11e53d68397efad71ac6136c779143
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307035"
---
# <a name="relation-members-dao"></a><span data-ttu-id="bee11-102">关系成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bee11-102">Relation members (DAO)</span></span>


<span data-ttu-id="bee11-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bee11-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bee11-104">Relation 对象表示表或查询中的字段之间的关系（仅适用于 Microsoft Access 数据库引擎数据库）。</span><span class="sxs-lookup"><span data-stu-id="bee11-104">A Relation object represents a relationship between fields in tables or queries (Microsoft Access database engine databases only).</span></span>

## <a name="methods"></a><span data-ttu-id="bee11-105">方法</span><span class="sxs-lookup"><span data-stu-id="bee11-105">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bee11-106">名称</span><span class="sxs-lookup"><span data-stu-id="bee11-106">Name</span></span></p></th>
<th><p><span data-ttu-id="bee11-107">说明</span><span class="sxs-lookup"><span data-stu-id="bee11-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bee11-108"><strong><a href="relation-createfield-method-dao.md">CreateField</a></strong></span><span class="sxs-lookup"><span data-stu-id="bee11-108"><strong><a href="relation-createfield-method-dao.md">CreateField</a></strong></span></span></p></td>
<td><p><span data-ttu-id="bee11-109">创建一个新的 <strong><a href="field-object-dao.md">Field</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="bee11-109">Creates a new <strong><a href="field-object-dao.md">Field</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="bee11-110">属性</span><span class="sxs-lookup"><span data-stu-id="bee11-110">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bee11-111">名称</span><span class="sxs-lookup"><span data-stu-id="bee11-111">Name</span></span></p></th>
<th><p><span data-ttu-id="bee11-112">说明</span><span class="sxs-lookup"><span data-stu-id="bee11-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bee11-113"><strong><a href="relation-attributes-property-dao.md">Attributes</a></strong></span><span class="sxs-lookup"><span data-stu-id="bee11-113"><strong><a href="relation-attributes-property-dao.md">Attributes</a></strong></span></span></p></td>
<td><p><span data-ttu-id="bee11-114">设置或返回一个值，该值指示 <strong>Relation</strong> 对象的一个或多个特征。</span><span class="sxs-lookup"><span data-stu-id="bee11-114">Sets or returns a value that indicates one or more characteristics of a <strong>Relation</strong> object.</span></span> <span data-ttu-id="bee11-115">可读写 <strong>Long</strong>。</span><span class="sxs-lookup"><span data-stu-id="bee11-115">Read/write <strong>Long</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee11-116"><strong><a href="relation-fields-property-dao.md">Fields</a></strong></span><span class="sxs-lookup"><span data-stu-id="bee11-116"><strong><a href="relation-fields-property-dao.md">Fields</a></strong></span></span></p></td>
<td><p><span data-ttu-id="bee11-117">返回一个 <strong>Fields</strong> 集合，该集合表示指定对象的所有存储 <strong>Field</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="bee11-117">Returns a <strong>Fields</strong> collection that represents all stored <strong>Field</strong> objects for the specified object.</span></span> <span data-ttu-id="bee11-118">只读。</span><span class="sxs-lookup"><span data-stu-id="bee11-118">Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bee11-119"><strong><a href="relation-foreigntable-property-dao.md">ForeignTable</a></strong></span><span class="sxs-lookup"><span data-stu-id="bee11-119"><strong><a href="relation-foreigntable-property-dao.md">ForeignTable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="bee11-120">设置或返回关系中外表的名称 (仅适用于 Microsoft Access 工作区)。</span><span class="sxs-lookup"><span data-stu-id="bee11-120">Sets or returns the name of the foreign table in a relationship (Microsoft Access workspaces only).</span></span> <span data-ttu-id="bee11-121">.</span><span class="sxs-lookup"><span data-stu-id="bee11-121"></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee11-122"><strong><a href="relation-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="bee11-122"><strong><a href="relation-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="bee11-p104">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="bee11-p104">Returns or sets the name of the specified object. Read/write <strong>String</strong> if the object has not been appended to a collection. Read-only <strong>String</strong> if the object has been appended to a collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bee11-126"><strong><a href="relation-partialreplica-property-dao.md">PartialReplica</a></strong></span><span class="sxs-lookup"><span data-stu-id="bee11-126"><strong><a href="relation-partialreplica-property-dao.md">PartialReplica</a></strong></span></span></p></td>
<td><p><span data-ttu-id="bee11-p105">设置或返回 <strong>Relation</strong> 对象的值，用于指示从完全副本填充部分副本时是否应当考虑关系。（仅适用于 Microsoft Access 数据库引擎数据库）。可读写 <strong>Boolean</strong>。</span><span class="sxs-lookup"><span data-stu-id="bee11-p105">Sets or returns a value on a <strong>Relation</strong> object indicating whether that relation should be considered when populating a partial replica from a full replica. (Microsoft Access database engine databases only). Read/write <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee11-130"><strong><a href="relation-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="bee11-130"><strong><a href="relation-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="bee11-131">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="bee11-131">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object.</span></span> <span data-ttu-id="bee11-132">只读。</span><span class="sxs-lookup"><span data-stu-id="bee11-132">Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bee11-133"><strong><a href="relation-table-property-dao.md">Table</a></strong></span><span class="sxs-lookup"><span data-stu-id="bee11-133"><strong><a href="relation-table-property-dao.md">Table</a></strong></span></span></p></td>
<td><p><span data-ttu-id="bee11-p107">指示 <strong><a href="relation-object-dao.md">Relation</a></strong> 对象的主表的名称。该属性应当等同于 <strong><a href="connection-name-property-dao.md">TableDef</a></strong> 或 <strong><a href="tabledef-object-dao.md">QueryDef</a></strong> 对象的 <strong><a href="querydef-object-dao.md">Name</a></strong> 属性设置（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="bee11-p107">Indicates the name of a <strong><a href="relation-object-dao.md">Relation</a></strong> object's primary table. This should be equal to the <strong><a href="connection-name-property-dao.md">Name</a></strong> property setting of a <strong><a href="tabledef-object-dao.md">TableDef</a></strong> or <strong><a href="querydef-object-dao.md">QueryDef</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>

