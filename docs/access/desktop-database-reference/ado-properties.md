---
title: ActiveX 数据对象 (ADO) 属性
TOCTitle: ADO properties
ms:assetid: 04f08f22-6327-c603-229e-d06a9f1c0d83
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248809(v=office.15)
ms:contentKeyID: 48543020
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a0efb40d1b5e4c5d675d8add7cdb7a05760578a9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283231"
---
# <a name="ado-properties"></a><span data-ttu-id="ec269-102">ADO 属性</span><span class="sxs-lookup"><span data-stu-id="ec269-102">ADO properties</span></span>

<span data-ttu-id="ec269-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ec269-103">**Applies to**: Access 2013, Office 2013</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th><span data-ttu-id="ec269-104">属性</span><span class="sxs-lookup"><span data-stu-id="ec269-104">Property</span></span></th>
<th><span data-ttu-id="ec269-105">说明</span><span class="sxs-lookup"><span data-stu-id="ec269-105">Description</span></span></th>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-106"><a href="absolutepage-property-ado.md">AbsolutePage</a></span><span class="sxs-lookup"><span data-stu-id="ec269-106"><a href="absolutepage-property-ado.md">AbsolutePage</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-107">指示当前记录驻留在哪一页。</span><span class="sxs-lookup"><span data-stu-id="ec269-107">Indicates on which page the current record resides.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-108"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span><span class="sxs-lookup"><span data-stu-id="ec269-108"><a href="absoluteposition-property-ado.md">AbsolutePosition</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-109">指示 <strong>Recordset</strong> 对象的当前记录的序号位置。</span><span class="sxs-lookup"><span data-stu-id="ec269-109">Indicates the ordinal position of a <strong>Recordset</strong> object's current record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-110"><a href="activecommand-property-ado.md">ActiveCommand</a></span><span class="sxs-lookup"><span data-stu-id="ec269-110"><a href="activecommand-property-ado.md">ActiveCommand</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-111">指示创建关联的 <strong>Recordset</strong> 对象的 <strong>Command</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ec269-111">Indicates the <strong>Command</strong> object that created the associated <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-112"><a href="activeconnection-property-ado.md">ActiveConnection</a></span><span class="sxs-lookup"><span data-stu-id="ec269-112"><a href="activeconnection-property-ado.md">ActiveConnection</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-113">指示指定的 <strong>Command</strong>、<strong>Recordset</strong> 或 <strong>Record</strong> 对象当前属于哪个 <strong>Connection</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ec269-113">Indicates to which <strong>Connection</strong> object the specified <strong>Command</strong>, <strong>Recordset</strong>, or <strong>Record</strong> object currently belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-114"><a href="actualsize-property-ado.md">ActualSize</a></span><span class="sxs-lookup"><span data-stu-id="ec269-114"><a href="actualsize-property-ado.md">ActualSize</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-115">指示字段值的实际长度。</span><span class="sxs-lookup"><span data-stu-id="ec269-115">Indicates the actual length of a field's value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-116"><a href="attributes-property-ado.md">Attributes</a></span><span class="sxs-lookup"><span data-stu-id="ec269-116"><a href="attributes-property-ado.md">Attributes</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-117">指示对象的一个或多个特征。</span><span class="sxs-lookup"><span data-stu-id="ec269-117">Indicates one or more characteristics of an object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-118"><a href="bof-eof-properties-ado.md">BOF 和 EOF</a></span><span class="sxs-lookup"><span data-stu-id="ec269-118"><a href="bof-eof-properties-ado.md">BOF and EOF</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-119"><strong>BOF</strong> - 指示当前记录位置在 <strong>Recordset</strong> 对象中的第一个记录之前。</span><span class="sxs-lookup"><span data-stu-id="ec269-119"><strong>BOF</strong> — indicates that the current record position is before the first record in a <strong>Recordset</strong> object.</span></span> <span data-ttu-id="ec269-120"><strong>EOF</strong> - 指示当前记录位置在 <strong>Recordset</strong> 对象中的最后一个记录之后。</span><span class="sxs-lookup"><span data-stu-id="ec269-120"><strong>EOF</strong> — indicates that the current record position is after the last record in a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-121"><a href="bookmark-property-ado.md">Bookmark</a></span><span class="sxs-lookup"><span data-stu-id="ec269-121"><a href="bookmark-property-ado.md">Bookmark</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-122">指示在 <strong>Recordset</strong> 对象中唯一标识当前记录的书签，或者将 <strong>Recordset</strong> 对象中的当前记录设置为有效书签标识的记录。</span><span class="sxs-lookup"><span data-stu-id="ec269-122">Indicates a bookmark that uniquely identifies the current record in a <strong>Recordset</strong> object or sets the current record in a <strong>Recordset</strong> object to the record identified by a valid bookmark.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-123"><a href="cachesize-property-ado.md">CacheSize</a></span><span class="sxs-lookup"><span data-stu-id="ec269-123"><a href="cachesize-property-ado.md">CacheSize</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-124">指示本地缓存在内存中的 <strong>Recordset</strong> 对象的记录数。</span><span class="sxs-lookup"><span data-stu-id="ec269-124">Indicates the number of records from a <strong>Recordset</strong> object that are cached locally in memory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-125"><a href="chapter-property-ado.md">第二章</a></span><span class="sxs-lookup"><span data-stu-id="ec269-125"><a href="chapter-property-ado.md">Chapter</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-126">从 <strong>ADORecordsetConstruction</strong> 对象获取（或对它设置）OLE DB <strong>Chapter</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ec269-126">Gets or sets an OLE DB <strong>Chapter</strong> object from/on an <strong>ADORecordsetConstruction</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-127"><a href="charset-property-ado.md">CharSet</a></span><span class="sxs-lookup"><span data-stu-id="ec269-127"><a href="charset-property-ado.md">CharSet</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-128">指示文本 <strong>Stream</strong> 的内容应当转换成哪个字符集。</span><span class="sxs-lookup"><span data-stu-id="ec269-128">Indicates the character set into which the contents of a text <strong>Stream</strong> should be translated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-129"><a href="commandtext-property-ado.md">CommandText</a></span><span class="sxs-lookup"><span data-stu-id="ec269-129"><a href="commandtext-property-ado.md">CommandText</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-130">指示要对提供程序发出的命令的文本。</span><span class="sxs-lookup"><span data-stu-id="ec269-130">Indicates the text of a command to be issued against a provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-131"><a href="commandtimeout-property-ado.md">CommandTimeout</a></span><span class="sxs-lookup"><span data-stu-id="ec269-131"><a href="commandtimeout-property-ado.md">CommandTimeout</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-132">指示在执行命令时要等待多长时间才终止操作尝试并生成错误。</span><span class="sxs-lookup"><span data-stu-id="ec269-132">Indicates how long to wait while executing a command before terminating the attempt and generating an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-133"><a href="commandtype-property-ado.md">CommandType</a></span><span class="sxs-lookup"><span data-stu-id="ec269-133"><a href="commandtype-property-ado.md">CommandType</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-134">指示 <strong>Command</strong> 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="ec269-134">Indicates the type of a <strong>Command</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-135"><a href="connectionstring-property-ado.md">ConnectionString 属性</a></span><span class="sxs-lookup"><span data-stu-id="ec269-135"><a href="connectionstring-property-ado.md">ConnectionString Property</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-136">指示用于建立数据源连接的信息。</span><span class="sxs-lookup"><span data-stu-id="ec269-136">Indicates the information used to establish a connection to a data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-137"><a href="connectiontimeout-property-ado.md">ConnectionTimeout</a></span><span class="sxs-lookup"><span data-stu-id="ec269-137"><a href="connectiontimeout-property-ado.md">ConnectionTimeout</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-138">指示在建立连接时要等待多长时间才终止连接尝试并生成错误。</span><span class="sxs-lookup"><span data-stu-id="ec269-138">Indicates how long to wait while establishing a connection before terminating the attempt and generating an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-139"><a href="count-property-ado.md">Count</a></span><span class="sxs-lookup"><span data-stu-id="ec269-139"><a href="count-property-ado.md">Count</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-140">指示集合中的对象数。</span><span class="sxs-lookup"><span data-stu-id="ec269-140">Indicates the number of objects in a collection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-141"><a href="cursorlocation-property-ado.md">CursorLocation</a></span><span class="sxs-lookup"><span data-stu-id="ec269-141"><a href="cursorlocation-property-ado.md">CursorLocation</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-142">指示游标服务的位置。</span><span class="sxs-lookup"><span data-stu-id="ec269-142">Indicates the location of the cursor service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-143"><a href="cursortype-property-ado.md">CursorType</a></span><span class="sxs-lookup"><span data-stu-id="ec269-143"><a href="cursortype-property-ado.md">CursorType</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-144">指示在 <strong>Recordset</strong> 对象中使用的游标类型。</span><span class="sxs-lookup"><span data-stu-id="ec269-144">Indicates the type of cursor used in a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-145"><a href="datamember-property-ado.md">DataMember</a></span><span class="sxs-lookup"><span data-stu-id="ec269-145"><a href="datamember-property-ado.md">DataMember</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-146">指示将从 <strong>DataSource</strong> 属性所引用的对象中检索的数据成员的名称。</span><span class="sxs-lookup"><span data-stu-id="ec269-146">Indicates the name of the data member that will be retrieved from the object referenced by the <strong>DataSource</strong> property.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-147"><a href="datasource-property-ado.md">DataSource</a></span><span class="sxs-lookup"><span data-stu-id="ec269-147"><a href="datasource-property-ado.md">DataSource</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-148">指示一个对象，其中包含要表示为 <strong>Recordset</strong> 对象的数据。</span><span class="sxs-lookup"><span data-stu-id="ec269-148">Indicates an object that contains data to be represented as a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-149"><a href="defaultdatabase-property-ado.md">DefaultDatabase</a></span><span class="sxs-lookup"><span data-stu-id="ec269-149"><a href="defaultdatabase-property-ado.md">DefaultDatabase</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-150">指示 <strong>Connection</strong> 对象的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="ec269-150">Indicates the default database for a <strong>Connection</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-151"><a href="definedsize-property-ado.md">DefinedSize</a></span><span class="sxs-lookup"><span data-stu-id="ec269-151"><a href="definedsize-property-ado.md">DefinedSize</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-152">指示 <strong>Field</strong> 对象的数据容量。</span><span class="sxs-lookup"><span data-stu-id="ec269-152">Indicates the data capacity of a <strong>Field</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-153"><a href="description-property-ado.md">Description</a></span><span class="sxs-lookup"><span data-stu-id="ec269-153"><a href="description-property-ado.md">Description</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-154">描述 <strong>Error</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ec269-154">Describes an <strong>Error</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-155"><a href="direction-property-ado.md">Direction</a></span><span class="sxs-lookup"><span data-stu-id="ec269-155"><a href="direction-property-ado.md">Direction</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-156">指示 <strong>Parameter</strong> 是否表示输入参数和/或输出参数，或者参数是否是存储过程的返回值。</span><span class="sxs-lookup"><span data-stu-id="ec269-156">Indicates whether the <strong>Parameter</strong> represents an input parameter, an output parameter, or both, or if the parameter is the return value from a stored procedure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-157"><a href="editmode-property-ado.md">EditMode</a></span><span class="sxs-lookup"><span data-stu-id="ec269-157"><a href="editmode-property-ado.md">EditMode</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-158">指示当前记录的编辑状态。</span><span class="sxs-lookup"><span data-stu-id="ec269-158">Indicates the editing status of the current record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-159"><a href="eos-property-ado.md">电源</a></span><span class="sxs-lookup"><span data-stu-id="ec269-159"><a href="eos-property-ado.md">EOS</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-160">指示当前位置是否位于流的末尾。</span><span class="sxs-lookup"><span data-stu-id="ec269-160">Indicates whether the current position is at the end of the stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-161"><a href="filter-property-ado.md">Filter</a></span><span class="sxs-lookup"><span data-stu-id="ec269-161"><a href="filter-property-ado.md">Filter</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-162">指示 <strong>Recordset</strong> 中数据的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="ec269-162">Indicates a filter for data in a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-163"><a href="helpcontext-helpfile-properties-ado.md">HelpContext 和 HelpFile</a></span><span class="sxs-lookup"><span data-stu-id="ec269-163"><a href="helpcontext-helpfile-properties-ado.md">HelpContext and HelpFile</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-164">指示与 <strong>Error</strong> 对象关联的帮助文件和主题。</span><span class="sxs-lookup"><span data-stu-id="ec269-164">Indicates the help file and topic associated with an <strong>Error</strong> object.</span></span> <span data-ttu-id="ec269-165"><strong>HelpContextID</strong> - 返回帮助文件中主题的上下文 ID，返回值的类型为 <strong>Long</strong>。</span><span class="sxs-lookup"><span data-stu-id="ec269-165"><strong>HelpContextID</strong> — returns a context ID, as a <strong>Long</strong> value, for a topic in a Help file.</span></span> <span data-ttu-id="ec269-166"><strong>HelpFile</strong> - 返回一个 <strong>String</strong> 类型的值，作为帮助文件完全解析路径的计算结果。</span><span class="sxs-lookup"><span data-stu-id="ec269-166"><strong>HelpFile</strong> — returns a <strong>String</strong> value that evaluates to a fully resolved path to a Help file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-167"><a href="index-property-ado.md">索引</a></span><span class="sxs-lookup"><span data-stu-id="ec269-167"><a href="index-property-ado.md">Index</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-168">指示当前对 <strong>Recordset</strong> 对象有效的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="ec269-168">Indicates the name of the index currently in effect for a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-169"><a href="isolationlevel-property-ado.md">IsolationLevel</a></span><span class="sxs-lookup"><span data-stu-id="ec269-169"><a href="isolationlevel-property-ado.md">IsolationLevel</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-170">指示 <strong>Connection</strong> 对象的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="ec269-170">Indicates the level of isolation for a <strong>Connection</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-171"><a href="item-property-ado.md">Item</a></span><span class="sxs-lookup"><span data-stu-id="ec269-171"><a href="item-property-ado.md">Item</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-172">按名称或序号指示集合的特定成员。</span><span class="sxs-lookup"><span data-stu-id="ec269-172">Indicates a specific member of a collection, by name or ordinal number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-173"><a href="lineseparator-property-ado.md">LineSeparator</a></span><span class="sxs-lookup"><span data-stu-id="ec269-173"><a href="lineseparator-property-ado.md">LineSeparator</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-174">指示要在文本 <strong>Stream</strong> 对象中用作行分隔符的二进制字符。</span><span class="sxs-lookup"><span data-stu-id="ec269-174">Indicates the binary character to be used as the line separator in text <strong>Stream</strong> objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-175"><a href="locktype-property-ado.md">LockType</a></span><span class="sxs-lookup"><span data-stu-id="ec269-175"><a href="locktype-property-ado.md">LockType</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-176">指示编辑过程中为记录设置的锁定类型。</span><span class="sxs-lookup"><span data-stu-id="ec269-176">Indicates the type of locks placed on records during editing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-177"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span><span class="sxs-lookup"><span data-stu-id="ec269-177"><a href="marshaloptions-property-ado.md">MarshalOptions</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-178">指示哪些记录要封送回服务器。</span><span class="sxs-lookup"><span data-stu-id="ec269-178">Indicates which records are to be marshaled back to the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-179"><a href="maxrecords-property-ado.md">MaxRecords</a></span><span class="sxs-lookup"><span data-stu-id="ec269-179"><a href="maxrecords-property-ado.md">MaxRecords</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-180">指示通过查询返回到 <strong>Recordset</strong> 的最大记录数。</span><span class="sxs-lookup"><span data-stu-id="ec269-180">Indicates the maximum number of records to return to a <strong>Recordset</strong> from a query.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-181"><a href="mode-property-ado.md">Mode</a></span><span class="sxs-lookup"><span data-stu-id="ec269-181"><a href="mode-property-ado.md">Mode</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-182">指示在 <strong>Connection</strong>、<strong>Record</strong> 或 <strong>Stream</strong> 对象中修改数据的可用权限。</span><span class="sxs-lookup"><span data-stu-id="ec269-182">Indicates the available permissions for modifying data in a <strong>Connection</strong>, <strong>Record</strong>, or <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-183"><a href="name-property-ado.md">Name</a></span><span class="sxs-lookup"><span data-stu-id="ec269-183"><a href="name-property-ado.md">Name</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-184">指示对象的名称。</span><span class="sxs-lookup"><span data-stu-id="ec269-184">Indicates the name of an object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-185"><a href="nativeerror-property-ado.md">NativeError</a></span><span class="sxs-lookup"><span data-stu-id="ec269-185"><a href="nativeerror-property-ado.md">NativeError</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-186">指示给定 <strong>Error</strong> 对象特定于提供程序的错误代码。</span><span class="sxs-lookup"><span data-stu-id="ec269-186">Indicates the provider-specific error code for a given <strong>Error</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-187"><a href="number-property-ado.md">Number</a></span><span class="sxs-lookup"><span data-stu-id="ec269-187"><a href="number-property-ado.md">Number</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-188">指示用于唯一标识 <strong>Error</strong> 对象的编号。</span><span class="sxs-lookup"><span data-stu-id="ec269-188">Indicates the number that uniquely identifies an <strong>Error</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-189"><a href="numericscale-property-ado.md">NumericScale</a></span><span class="sxs-lookup"><span data-stu-id="ec269-189"><a href="numericscale-property-ado.md">NumericScale</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-190">指示 <strong>Parameter</strong> 或 <strong>Field</strong> 对象中数值的小数位数。</span><span class="sxs-lookup"><span data-stu-id="ec269-190">Indicates the scale of numeric values in a <strong>Parameter</strong> or <strong>Field</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-191"><a href="originalvalue-property-ado.md">OriginalValue</a></span><span class="sxs-lookup"><span data-stu-id="ec269-191"><a href="originalvalue-property-ado.md">OriginalValue</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-192">指示记录发生任何更改之前的 <strong>Field</strong> 值。</span><span class="sxs-lookup"><span data-stu-id="ec269-192">Indicates the value of a <strong>Field</strong> that existed in the record before any changes were made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-193"><a href="pagecount-property-ado.md">PageCount</a></span><span class="sxs-lookup"><span data-stu-id="ec269-193"><a href="pagecount-property-ado.md">PageCount</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-194">指示 <strong>Recordset</strong> 对象包含的数据页数。</span><span class="sxs-lookup"><span data-stu-id="ec269-194">Indicates how many pages of data the <strong>Recordset</strong> object contains.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-195"><a href="pagesize-property-ado.md">PageSize</a></span><span class="sxs-lookup"><span data-stu-id="ec269-195"><a href="pagesize-property-ado.md">PageSize</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-196">指示由多少记录构成 <strong>Recordset</strong> 中的一页。</span><span class="sxs-lookup"><span data-stu-id="ec269-196">Indicates how many records constitute one page in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-197"><a href="parentrow-property-ado.md">ParentRow</a></span><span class="sxs-lookup"><span data-stu-id="ec269-197"><a href="parentrow-property-ado.md">ParentRow</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-198">在 <strong>ADORecordConstruction</strong> 对象上设置 OLE DB <strong>Row</strong> 对象的容器，以便将行的父项转换为 ADO <strong>Record</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ec269-198">Sets the container of an OLE DB <strong>Row</strong> object on an <strong>ADORecordConstruction</strong> object, so that the parent of the row is turned into an ADO <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-199"><a href="parenturl-property-ado.md">ParentURL</a></span><span class="sxs-lookup"><span data-stu-id="ec269-199"><a href="parenturl-property-ado.md">ParentURL</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-200">指示指向当前 <strong>Record</strong> 对象的父 <strong>Record</strong> 的绝对 URL 字符串。</span><span class="sxs-lookup"><span data-stu-id="ec269-200">Indicates an absolute URL string that points to the parent <strong>Record</strong> of the current <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-201"><a href="position-property-ado.md">Position</a></span><span class="sxs-lookup"><span data-stu-id="ec269-201"><a href="position-property-ado.md">Position</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-202">指示 <strong>Stream</strong> 对象中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="ec269-202">Indicates the current position within a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-203"><a href="precision-property-ado.md">精密</a></span><span class="sxs-lookup"><span data-stu-id="ec269-203"><a href="precision-property-ado.md">Precision</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-204">指示 <strong>Parameter</strong> 对象或数字 <strong>Field</strong> 对象中数值的精度。</span><span class="sxs-lookup"><span data-stu-id="ec269-204">Indicates the degree of precision for numeric values in a <strong>Parameter</strong> object or for numeric <strong>Field</strong> objects.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-205"><a href="prepared-property-ado.md">得</a></span><span class="sxs-lookup"><span data-stu-id="ec269-205"><a href="prepared-property-ado.md">Prepared</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-206">指示是否在执行之前保存命令的已编译版本。</span><span class="sxs-lookup"><span data-stu-id="ec269-206">Indicates whether to save a compiled version of a command before execution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-207"><a href="provider-property-ado.md">Provider</a></span><span class="sxs-lookup"><span data-stu-id="ec269-207"><a href="provider-property-ado.md">Provider</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-208">指示 <strong>Connection</strong> 对象的提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ec269-208">Indicates the name of the provider for a <strong>Connection</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-209"><a href="recordcount-property-ado.md">RecordCount</a></span><span class="sxs-lookup"><span data-stu-id="ec269-209"><a href="recordcount-property-ado.md">RecordCount</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-210">指示 <strong>Recordset</strong> 对象中的记录数。</span><span class="sxs-lookup"><span data-stu-id="ec269-210">Indicates the number of records in a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-211"><a href="recordtype-property-ado.md">RecordType</a></span><span class="sxs-lookup"><span data-stu-id="ec269-211"><a href="recordtype-property-ado.md">RecordType</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-212">指示 <strong>Record</strong> 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="ec269-212">Indicates the type of <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-213"><a href="row-property-ado.md">行</a></span><span class="sxs-lookup"><span data-stu-id="ec269-213"><a href="row-property-ado.md">Row</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-214">从 <strong>ADORecordConstruction</strong> 对象获取（或对它设置）OLE DB <strong>Row</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ec269-214">Gets or sets an OLE DB <strong>Row</strong> object from/on an <strong>ADORecordConstruction</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-215"><a href="rowposition-property-ado.md">RowPosition</a></span><span class="sxs-lookup"><span data-stu-id="ec269-215"><a href="rowposition-property-ado.md">RowPosition</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-216">从 <strong>ADORecordsetConstruction</strong> 对象获取（或对它设置）OLE DB <strong>RowPosition</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ec269-216">Gets or sets an OLE DB <strong>RowPosition</strong> object from/on an <strong>ADORecordsetConstruction</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-217"><a href="rowset-property-ado.md">Rowset</a></span><span class="sxs-lookup"><span data-stu-id="ec269-217"><a href="rowset-property-ado.md">Rowset</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-218">从 <strong>ADORecordsetConstruction</strong> 对象获得（或对它设置）OLE DB <strong>Rowset</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ec269-218">Gets or sets an OLE DB <strong>Rowset</strong> object from/on an <strong>ADORecordsetConstruction</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-219"><a href="size-property-ado.md">Size</a></span><span class="sxs-lookup"><span data-stu-id="ec269-219"><a href="size-property-ado.md">Size</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-220">指示 <strong>Parameter</strong> 对象的最大大小，以字节或字符为单位。</span><span class="sxs-lookup"><span data-stu-id="ec269-220">Indicates the maximum size, in bytes or characters, of a <strong>Parameter</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-221"><a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream">Size (ADO Stream)</a></span><span class="sxs-lookup"><span data-stu-id="ec269-221"><a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream">Size (ADO Stream)</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-222">指示流的总计大小（字节数）。</span><span class="sxs-lookup"><span data-stu-id="ec269-222">Indicates the total size of the stream in number of bytes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-223"><a href="sort-property-ado.md">Sort</a></span><span class="sxs-lookup"><span data-stu-id="ec269-223"><a href="sort-property-ado.md">Sort</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-224">指示一个或多个作为 <strong>Recordset</strong> 的排序依据的字段名称，并指定是按升序还是降序对字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="ec269-224">Indicates one or more field names on which the <strong>Recordset</strong> is sorted, and whether each field is sorted in ascending or descending order.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-225"><a href="source-property-ado-error.md">Source（ADO 错误）</a></span><span class="sxs-lookup"><span data-stu-id="ec269-225"><a href="source-property-ado-error.md">Source (ADO Error)</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-226">指示最初生成错误的对象或应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ec269-226">Indicates the name of the object or application that originally generated an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-227"><a href="source-property-ado-record.md">Source (ADO Record)</a></span><span class="sxs-lookup"><span data-stu-id="ec269-227"><a href="source-property-ado-record.md">Source (ADO Record)</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-228">指示 <strong>Record</strong> 对象所表示的实体。</span><span class="sxs-lookup"><span data-stu-id="ec269-228">Indicates the entity represented by the <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-229"><a href="source-property-ado-recordset.md">Source (ADO Recordset)</a></span><span class="sxs-lookup"><span data-stu-id="ec269-229"><a href="source-property-ado-recordset.md">Source (ADO Recordset)</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-230">指示 <strong>Recordset</strong> 对象中数据的来源</span><span class="sxs-lookup"><span data-stu-id="ec269-230">Indicates the source for the data in a <strong>Recordset</strong> object</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-231"><a href="sqlstate-property-ado.md">SQLState</a></span><span class="sxs-lookup"><span data-stu-id="ec269-231"><a href="sqlstate-property-ado.md">SQLState</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-232">指示给定 <strong>Error</strong> 对象的 SQL 状态。</span><span class="sxs-lookup"><span data-stu-id="ec269-232">Indicates the SQL state for a given <strong>Error</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-233"><a href="state-property-ado.md">State</a></span><span class="sxs-lookup"><span data-stu-id="ec269-233"><a href="state-property-ado.md">State</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-234">对所有适用的对象，指示其状态是打开还是关闭。</span><span class="sxs-lookup"><span data-stu-id="ec269-234">Indicates for all applicable objects whether the state of the object is open or closed.</span></span> <span data-ttu-id="ec269-235">指示对象的当前状态是连接、执行还是检索，针对执行异步方法的所有适用对象</span><span class="sxs-lookup"><span data-stu-id="ec269-235">Indicates for all applicable objects executing an asynchronous method, whether the current state of the object is connecting, executing, or retrieving</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-236"><a href="status-property-ado-field.md">Status (ADO Field)</a></span><span class="sxs-lookup"><span data-stu-id="ec269-236"><a href="status-property-ado-field.md">Status (ADO Field)</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-237">指示 <strong>Field</strong> 对象的状态。</span><span class="sxs-lookup"><span data-stu-id="ec269-237">Indicates the status of a <strong>Field</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-238"><a href="status-property-ado-recordset.md">Status (ADO Recordset)</a></span><span class="sxs-lookup"><span data-stu-id="ec269-238"><a href="status-property-ado-recordset.md">Status (ADO Recordset)</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-239">指示与批更新或其他批量操作相关的当前记录的状态。</span><span class="sxs-lookup"><span data-stu-id="ec269-239">Indicates the status of the current record with respect to batch updates or other bulk operations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-240"><a href="stayinsync-property-ado.md">StayInSync</a></span><span class="sxs-lookup"><span data-stu-id="ec269-240"><a href="stayinsync-property-ado.md">StayInSync</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-241">指示在分层 <strong>Recordset</strong> 对象中，当父行位置更改时，对基础子记录（即<em>章节</em>）的引用是否发生了更改。</span><span class="sxs-lookup"><span data-stu-id="ec269-241">Indicates, in a hierarchical <strong>Recordset</strong> object, whether the reference to the underlying child records (that is, the <em>chapter</em>) changes when the parent row position changes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-242"><a href="type-property-ado.md">Type</a></span><span class="sxs-lookup"><span data-stu-id="ec269-242"><a href="type-property-ado.md">Type</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-243">指示 <strong>Parameter</strong>、<strong>Field</strong> 或 <strong>Property</strong> 对象的操作类型或数据类型。</span><span class="sxs-lookup"><span data-stu-id="ec269-243">Indicates the operational type or data type of a <strong>Parameter</strong>, <strong>Field</strong>, or <strong>Property</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-244"><a href="type-property-ado-stream.md">Type (ADO Stream)</a></span><span class="sxs-lookup"><span data-stu-id="ec269-244"><a href="type-property-ado-stream.md">Type (ADO Stream)</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-245">指示 <strong>Stream</strong> 中包含的数据类型（二进制或文本）。</span><span class="sxs-lookup"><span data-stu-id="ec269-245">Indicates the type of data contained in the <strong>Stream</strong> (binary or text).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-246"><a href="underlyingvalue-property-ado.md">UnderlyingValue</a></span><span class="sxs-lookup"><span data-stu-id="ec269-246"><a href="underlyingvalue-property-ado.md">UnderlyingValue</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-247">指示数据库中 <strong>Field</strong> 对象的当前值。</span><span class="sxs-lookup"><span data-stu-id="ec269-247">Indicates a <strong>Field</strong> object's current value in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec269-248"><a href="value-property-ado.md">值</a></span><span class="sxs-lookup"><span data-stu-id="ec269-248"><a href="value-property-ado.md">Value</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-249">指示赋给 <strong>Field</strong>、<strong>Parameter</strong> 或 <strong>Property</strong> 对象的值。</span><span class="sxs-lookup"><span data-stu-id="ec269-249">Indicates the value assigned to a <strong>Field</strong>, <strong>Parameter</strong>, or <strong>Property</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec269-250"><a href="version-property-ado.md">Version</a></span><span class="sxs-lookup"><span data-stu-id="ec269-250"><a href="version-property-ado.md">Version</a></span></span></p></td>
<td><p><span data-ttu-id="ec269-251">指示 ADO 版本号。</span><span class="sxs-lookup"><span data-stu-id="ec269-251">Indicates the ADO version number.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>
