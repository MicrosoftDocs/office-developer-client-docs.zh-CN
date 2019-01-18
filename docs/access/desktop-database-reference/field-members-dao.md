---
title: 域成员 (DAO)
TOCTitle: Field Members
ms:assetid: 4b6a587f-1fd0-37fb-db7d-75b587a8dc60
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193511(v=office.15)
ms:contentKeyID: 48544689
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1a0e448662384572163fca074e554a5e30be30a7
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703599"
---
# <a name="field-members-dao"></a><span data-ttu-id="79c6b-102">域成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="79c6b-102">Field members (DAO)</span></span>


<span data-ttu-id="79c6b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="79c6b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="79c6b-104">Field 对象代表具有普通数据类型和普通属性集的数据列。</span><span class="sxs-lookup"><span data-stu-id="79c6b-104">A Field object represents a column of data with a common data type and a common set of properties.</span></span>

## <a name="methods"></a><span data-ttu-id="79c6b-105">方法</span><span class="sxs-lookup"><span data-stu-id="79c6b-105">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="79c6b-106">名称</span><span class="sxs-lookup"><span data-stu-id="79c6b-106">Name</span></span></p></th>
<th><p><span data-ttu-id="79c6b-107">说明</span><span class="sxs-lookup"><span data-stu-id="79c6b-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-108"><strong><a href="field-appendchunk-method-dao.md">AppendChunk</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-108"><strong><a href="field-appendchunk-method-dao.md">AppendChunk</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-109">将字符串表达式中的数据追加到 <strong><a href="field-object-dao.md">Recordset</a></strong> 中的"备注"或"长二进制"型 <strong><a href="recordset-object-dao.md">Field</a></strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="79c6b-109">Appends data from a string expression to a Memo or Long Binary <strong><a href="field-object-dao.md">Field</a></strong> object in a <strong><a href="recordset-object-dao.md">Recordset</a></strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-110"><strong><a href="field-createproperty-method-dao.md">CreateProperty</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-110"><strong><a href="field-createproperty-method-dao.md">CreateProperty</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-111">创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="79c6b-111">Creates a new user-defined <strong><a href="property-object-dao.md">Property</a></strong> object (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-112"><strong><a href="field-getchunk-method-dao.md">GetChunk</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-112"><strong><a href="field-getchunk-method-dao.md">GetChunk</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-113">返回 <strong><strong>Recordset</strong></strong> 对象的 <strong><a href="field-object-dao.md">Fields</a></strong> 集合中的 <a href="fields-collection-dao.md">Memo</a> 或 <strong>Long Binary</strong> <strong><a href="recordset-object-dao.md">Field</a></strong> 对象的全部或一部分内容。</span><span class="sxs-lookup"><span data-stu-id="79c6b-113">Returns all or a portion of the contents of a <strong>Memo</strong> or <strong>Long Binary</strong> <strong><a href="field-object-dao.md">Field</a></strong> object in the <strong><a href="fields-collection-dao.md">Fields</a></strong> collection of a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="79c6b-114">属性</span><span class="sxs-lookup"><span data-stu-id="79c6b-114">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="79c6b-115">名称</span><span class="sxs-lookup"><span data-stu-id="79c6b-115">Name</span></span></p></th>
<th><p><span data-ttu-id="79c6b-116">说明</span><span class="sxs-lookup"><span data-stu-id="79c6b-116">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-117"><strong><a href="field-allowzerolength-property-dao.md">AllowZeroLength</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-117"><strong><a href="field-allowzerolength-property-dao.md">AllowZeroLength</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-118">设置或返回一个值，指示是否为零长度字符串 (&quot;&quot;) 是<strong><a href="field-object-dao.md">Field</a></strong>对象的<strong><a href="field-value-property-dao.md">Value</a></strong>属性的有效设置与文本或备注数据类型 （仅限 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="79c6b-118">Sets or returns a value that indicates whether a zero-length string (&quot;&quot;) is a valid setting for the <strong><a href="field-value-property-dao.md">Value</a></strong> property of the <strong><a href="field-object-dao.md">Field</a></strong> object with a Text or Memo data type (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-119"><strong><a href="field-attributes-property-dao.md">Attributes</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-119"><strong><a href="field-attributes-property-dao.md">Attributes</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p101">设置或返回 <strong><a href="field-object-dao.md">Field</a></strong> 对象的一个或多个特征。 <strong>Long</strong> 类型，可读写。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p101">Sets or returns a value that indicates one or more characteristics of a <strong><a href="field-object-dao.md">Field</a></strong> object. Read/write <strong>Long</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-122"><strong><a href="field-collatingorder-property-dao.md">CollatingOrder</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-122"><strong><a href="field-collatingorder-property-dao.md">CollatingOrder</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p102">返回一个值，该值指定用于字符串比较或排序的文本中排序次序的序列（仅适用于 Microsoft Access 工作区）。只读 <strong>Long</strong>。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p102">Returns a value that specifies the sequence of the sort order in text for string comparison or sorting (Microsoft Access workspaces only). Read-only <strong>Long</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-125"><strong><a href="field-dataupdatable-property-dao.md">DataUpdatable</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-125"><strong><a href="field-dataupdatable-property-dao.md">DataUpdatable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-126">返回一个值，该值指示是否可更新 <strong><a href="field-object-dao.md">Field</a></strong> 对象所代表的字段中的数据。</span><span class="sxs-lookup"><span data-stu-id="79c6b-126">Returns a value that indicates whether the data in the field represented by a <strong><a href="field-object-dao.md">Field</a></strong> object is updatable.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-127"><strong><a href="field-defaultvalue-property-dao.md">DefaultValue</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-127"><strong><a href="field-defaultvalue-property-dao.md">DefaultValue</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p103">设置或返回 <strong><a href="field-object-dao.md">Field</a></strong> 对象的默认值。对于尚未追加到 <a href="fields-collection-dao.md"><strong>Fields</strong></a> 集合的 <strong>Field</strong> 对象，该属性是可读写的（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p103">Sets or returns the default value of a <strong><a href="field-object-dao.md">Field</a></strong> object. For a <strong>Field</strong> object not yet appended to the <strong><a href="fields-collection-dao.md">Fields</a></strong> collection, this property is read/write (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-130"><strong><a href="field-fieldsize-property-dao.md">字段大小</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-130"><strong><a href="field-fieldsize-property-dao.md">FieldSize</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-131">返回 <strong><a href="field-object-dao.md">Recordset</a></strong> 对象的 <strong><a href="fields-collection-dao.md">Fields</a></strong> 集合中"备注"或"长二进制"类型 <strong><a href="recordset-object-dao.md">Field</a></strong> 对象的数据库（而不是内存）中使用的字节数。</span><span class="sxs-lookup"><span data-stu-id="79c6b-131">Returns the number of bytes used in the database (rather than in memory) of a Memo or Long Binary <strong><a href="field-object-dao.md">Field</a></strong> object in the <strong><a href="fields-collection-dao.md">Fields</a></strong> collection of a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-132"><strong><a href="field-foreignname-property-dao.md">ForeignName</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-132"><strong><a href="field-foreignname-property-dao.md">ForeignName</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-133">设置或返回一个值，该值指定某个外表中的 <strong><a href="field-object-dao.md">Field</a></strong> 对象的名称，而该外表对应于某个关系的主表中的字段（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="79c6b-133">Sets or returns a value that specifies the name of the <strong><a href="field-object-dao.md">Field</a></strong> object in a foreign table that corresponds to a field in a primary table for a relationship (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-134"><strong><a href="field-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-134"><strong><a href="field-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p104">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p104">Returns or sets the name of the specified object. Read/write <strong>String</strong> if the object has not been appended to a collection. Read-only <strong>String</strong> if the object has been appended to a collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-138"><strong><a href="field-ordinalposition-property-dao.md">OrdinalPosition</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-138"><strong><a href="field-ordinalposition-property-dao.md">OrdinalPosition</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p105">设置或返回 <strong><a href="field-object-dao.md">Field</a></strong> 对象在 <strong><a href="fields-collection-dao.md">Fields</a></strong> 集合中的相对位置。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p105">Sets or returns the relative position of a <strong><a href="field-object-dao.md">Field</a></strong> object within a <strong><a href="fields-collection-dao.md">Fields</a></strong> collection. .</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-141"><strong><a href="field-originalvalue-property-dao.md">OriginalValue</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-141"><strong><a href="field-originalvalue-property-dao.md">OriginalValue</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-142"><strong><a href="workspacetypeenum-enumeration-dao.md">WorkspaceTypeEnum</a></strong>值之一。</span><span class="sxs-lookup"><span data-stu-id="79c6b-142">One of the <strong><a href="workspacetypeenum-enumeration-dao.md">WorkspaceTypeEnum</a></strong> values.</span></span></p>
<td><p><span data-ttu-id="79c6b-143"><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="79c6b-143"><strong>NOTE</strong>: ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="79c6b-144">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="79c6b-144">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="79c6b-145">返回数据库中的 <strong>Field</strong> 的值，该值在上一次批更新开始时已经存在（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="79c6b-145">Returns the value of a <strong>Field</strong> in the database that existed when the last batch update began (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-146"><strong><a href="field-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-146"><strong><a href="field-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p107">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p107">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object. Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-149"><strong><a href="field-required-property-dao.md">Required</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-149"><strong><a href="field-required-property-dao.md">Required</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-150">设置或返回一个值，该值指示 <strong><a href="field-object-dao.md">Field</a></strong> 对象是否需要一个非 Null 值。</span><span class="sxs-lookup"><span data-stu-id="79c6b-150">Sets or returns a value that indicates whether a <strong><a href="field-object-dao.md">Field</a></strong> object requires a non-Null value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-151"><strong><a href="field-fieldsize-property-dao.md">Size</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-151"><strong><a href="field-fieldsize-property-dao.md">Size</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-152">返回 <strong><a href="field-object-dao.md">Recordset</a></strong> 对象的 <strong><a href="fields-collection-dao.md">Fields</a></strong> 集合中"备注"或"长二进制"类型 <strong><a href="recordset-object-dao.md">Field</a></strong> 对象的数据库（而不是内存）中使用的字节数。</span><span class="sxs-lookup"><span data-stu-id="79c6b-152">Returns the number of bytes used in the database (rather than in memory) of a Memo or Long Binary <strong><a href="field-object-dao.md">Field</a></strong> object in the <strong><a href="fields-collection-dao.md">Fields</a></strong> collection of a <strong><a href="recordset-object-dao.md">Recordset</a></strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-153"><strong><a href="field-sourcefield-property-dao.md">SourceField</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-153"><strong><a href="field-sourcefield-property-dao.md">SourceField</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p108">返回一个值，该值指示作为 <strong>Field</strong> 对象的原始数据源的字段的名称。只读 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p108">Returns a value that indicates the name of the field that is the original source of the data for a <strong>Field</strong> object. Read-only <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-156"><strong><a href="field-sourcetable-property-dao.md">SourceTable</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-156"><strong><a href="field-sourcetable-property-dao.md">SourceTable</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p109">返回一个值，该值指示作为 <strong>Field</strong> 对象的原始数据源的表的名称。只读 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p109">Returns a value that indicates the name of the table that is the original source of the data for a <strong>Field</strong> object. Read-only <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-159"><strong><a href="field-type-property-dao.md">Type</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-159"><strong><a href="field-type-property-dao.md">Type</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p110">设置或返回一个值，该值指示对象的操作类型或数据类型。可读写 <strong>Integer</strong>。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p110">Sets or returns a value that indicates the operational type or data type of an object. Read/write <strong>Integer</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-162"><strong><a href="field-validateonset-property-dao.md">ValidateOnSet</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-162"><strong><a href="field-validateonset-property-dao.md">ValidateOnSet</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-163">设置或返回一个值，该值指定当设置 <strong><a href="field-object-dao.md">Field</a></strong> 对象的 <strong><a href="field-value-property-dao.md">Value</a></strong> 属性时是否立即验证该对象的值（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="79c6b-163">Sets or returns a value that specifies whether or not the value of a <strong><a href="field-object-dao.md">Field</a></strong> object is immediately validated when the object's <strong><a href="field-value-property-dao.md">Value</a></strong> property is set (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-164"><strong><a href="field-validationrule-property-dao.md">ValidationRule</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-164"><strong><a href="field-validationrule-property-dao.md">ValidationRule</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p111">设置或返回一个值，当字段中的数据发生更改或被添加到表中时，该值将会验证该数据（仅适用于 Microsoft Access 工作区）。可读写 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p111">Sets or returns a value that validates the data in a field as it's changed or added to a table (Microsoft Access workspaces only). Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-167"><strong><a href="field-validationtext-property-dao.md">ValidationText</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-167"><strong><a href="field-validationtext-property-dao.md">ValidationText</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p112">设置或返回一个值，该值指定当 <strong>Field</strong> 对象的值不符合 <strong>ValidationRule</strong> 属性设置所指定的验证规则时应用程序显示的消息文本（仅适用于 Microsoft Access 工作区）。可读写 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p112">Sets or returns a value that specifies the text of the message that your application displays if the value of a <strong>Field</strong> object doesn't satisfy the validation rule specified by the <strong>ValidationRule</strong> property setting (Microsoft Access workspaces only). Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c6b-170"><strong><a href="field-value-property-dao.md">Value</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-170"><strong><a href="field-value-property-dao.md">Value</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-p113">设置或返回对象的值。可读/写 <strong>Variant</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="79c6b-p113">Sets or returns the value of an object. Read/write <strong>Variant</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c6b-173"><strong><a href="field-visiblevalue-property-dao.md">VisibleValue</a></strong></span><span class="sxs-lookup"><span data-stu-id="79c6b-173"><strong><a href="field-visiblevalue-property-dao.md">VisibleValue</a></strong></span></span></p></td>
<td><p><span data-ttu-id="79c6b-174"><strong><a href="workspacetypeenum-enumeration-dao.md">WorkspaceTypeEnum</a></strong>值之一。</span><span class="sxs-lookup"><span data-stu-id="79c6b-174">One of the <strong><a href="workspacetypeenum-enumeration-dao.md">WorkspaceTypeEnum</a></strong> values.</span></span></p>
<td><p><span data-ttu-id="79c6b-175"><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="79c6b-175"><strong>NOTE</strong>: ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="79c6b-176">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="79c6b-176">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></p>
<p><span data-ttu-id="79c6b-177">返回数据库中现有的一个值，批更新冲突确定该值比 <strong>OriginalValue</strong> 属性新（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="79c6b-177">Returns a value currently in the database that is newer than the <strong>OriginalValue</strong> property as determined by a batch update conflict (ODBCDirect workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>

