---
title: 索引成员 (DAO)
TOCTitle: Index Members
ms:assetid: e261c5fa-ca7d-0d63-1c29-48e9231b39d1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835712(v=office.15)
ms:contentKeyID: 48548290
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 895f29a5dd3e7ed267b96d6a46dc2c8710b4998e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291794"
---
# <a name="index-members-dao"></a><span data-ttu-id="43f62-102">索引成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="43f62-102">Index members (DAO)</span></span>


<span data-ttu-id="43f62-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="43f62-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="43f62-p101">Index 对象指定从数据库表访问的记录的顺序，以及是否可接受重复的记录，以便提供高效的数据访问。对于外部数据库，Index 对象描述为外部表建立的索引（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="43f62-p101">Index objects specify the order of records accessed from database tables and whether or not duplicate records are accepted, providing efficient access to data. For external databases, Index objects describe the indexes established for external tables (Microsoft Access workspaces only).</span></span>

## <a name="methods"></a><span data-ttu-id="43f62-106">方法</span><span class="sxs-lookup"><span data-stu-id="43f62-106">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="43f62-107">名称</span><span class="sxs-lookup"><span data-stu-id="43f62-107">Name</span></span></p></th>
<th><p><span data-ttu-id="43f62-108">说明</span><span class="sxs-lookup"><span data-stu-id="43f62-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43f62-109"><strong><a href="index-createfield-method-dao.md">CreateField</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-109"><strong><a href="index-createfield-method-dao.md">CreateField</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-110">创建一个新的 <strong><a href="field-object-dao.md">Field</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="43f62-110">Creates a new <strong><a href="field-object-dao.md">Field</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43f62-111"><strong><a href="index-createproperty-method-dao.md">CreateProperty</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-111"><strong><a href="index-createproperty-method-dao.md">CreateProperty</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-112">创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="43f62-112">Creates a new user-defined <strong><a href="property-object-dao.md">Property</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="43f62-113">属性</span><span class="sxs-lookup"><span data-stu-id="43f62-113">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="43f62-114">名称</span><span class="sxs-lookup"><span data-stu-id="43f62-114">Name</span></span></p></th>
<th><p><span data-ttu-id="43f62-115">说明</span><span class="sxs-lookup"><span data-stu-id="43f62-115">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43f62-116"><strong><a href="index-clustered-property-dao.md">Clustered</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-116"><strong><a href="index-clustered-property-dao.md">Clustered</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-p102">设置或返回一个值，该值指示某个 <strong>Index</strong> 对象是否代表某个表的聚簇索引（仅适用于 Microsoft Access 工作区）。可读写 <strong>Boolean</strong>。</span><span class="sxs-lookup"><span data-stu-id="43f62-p102">Sets or returns a value that indicates whether an <strong>Index</strong> object represents a clustered index for a table (Microsoft Access workspaces only). Read/write <strong>Boolean</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43f62-119"><strong><a href="index-distinctcount-property-dao.md">DistinctCount</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-119"><strong><a href="index-distinctcount-property-dao.md">DistinctCount</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-120">返回一个值，该值指示 <strong><a href="index-object-dao.md">Index</a></strong> 对象中的、包含在关联表中的唯一值的数目（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="43f62-120">Returns a value that indicates the number of unique values for the <strong><a href="index-object-dao.md">Index</a></strong> object that are included in the associated table (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43f62-121"><strong><a href="index-fields-property-dao.md">Fields</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-121"><strong><a href="index-fields-property-dao.md">Fields</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-122">返回一个 <strong>Fields</strong> 集合，该集合代表指定对象的所有存储的 <strong>Field</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="43f62-122">Returns a <strong>Fields</strong> collection that represents all stored <strong>Field</strong> objects for the specified object.</span></span> <span data-ttu-id="43f62-123">可读/写。</span><span class="sxs-lookup"><span data-stu-id="43f62-123">Read/write.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43f62-124"><strong><a href="index-foreign-property-dao.md">Foreign</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-124"><strong><a href="index-foreign-property-dao.md">Foreign</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-125">返回一个值, 该值指示<strong><a href="index-object-dao.md">Index</a></strong>对象是否表示表中的外键 (仅适用于 Microsoft Access 工作区)。</span><span class="sxs-lookup"><span data-stu-id="43f62-125">Returns a value that indicates whether an <strong><a href="index-object-dao.md">Index</a></strong> object represents a foreign key in a table (Microsoft Access workspaces only).</span></span> <span data-ttu-id="43f62-126">.</span><span class="sxs-lookup"><span data-stu-id="43f62-126"></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43f62-127"><strong><a href="index-ignorenulls-property-dao.md">IgnoreNulls</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-127"><strong><a href="index-ignorenulls-property-dao.md">IgnoreNulls</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-128">设置或返回一个值，该值指示索引字段中包含 Null 值的记录是否具有索引项（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="43f62-128">Sets or returns a value that indicates whether records that have Null values in their index fields have index entries (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43f62-129"><strong><a href="index-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-129"><strong><a href="index-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-p105">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="43f62-p105">Returns or sets the name of the specified object. Read/write <strong>String</strong> if the object has not been appended to a collection. Read-only <strong>String</strong> if the object has been appended to a collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43f62-133"><strong><a href="index-primary-property-dao.md">主</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-133"><strong><a href="index-primary-property-dao.md">Primary</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-134">设置或返回一个值，该值指示 <strong><a href="index-object-dao.md">Index</a></strong> 对象是否代表了对一个表的主键索引（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="43f62-134">Sets or returns a value that indicates whether an <strong><a href="index-object-dao.md">Index</a></strong> object represents a primary key index for a table (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43f62-135"><strong><a href="index-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-135"><strong><a href="index-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-136">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="43f62-136">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object.</span></span> <span data-ttu-id="43f62-137">只读。</span><span class="sxs-lookup"><span data-stu-id="43f62-137">Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43f62-138"><strong><a href="index-required-property-dao.md">Required</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-138"><strong><a href="index-required-property-dao.md">Required</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-139">设置或返回一个值，该值指示 <strong><a href="field-object-dao.md">Field</a></strong> 对象是否需要一个非 Null 值。</span><span class="sxs-lookup"><span data-stu-id="43f62-139">Sets or returns a value that indicates whether a <strong><a href="field-object-dao.md">Field</a></strong> object requires a non-Null value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43f62-140"><strong><a href="index-unique-property-dao.md">独特</a></strong></span><span class="sxs-lookup"><span data-stu-id="43f62-140"><strong><a href="index-unique-property-dao.md">Unique</a></strong></span></span></p></td>
<td><p><span data-ttu-id="43f62-141">设置或返回一个值，该值指示 <strong><a href="index-object-dao.md">Index</a></strong> 对象是否代表一个表的唯一（键）索引（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="43f62-141">Sets or returns a value that indicates whether an <strong><a href="index-object-dao.md">Index</a></strong> object represents a unique (key) index for a table (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>

