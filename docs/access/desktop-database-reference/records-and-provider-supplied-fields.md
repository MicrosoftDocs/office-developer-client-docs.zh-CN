---
title: 记录和提供程序提供的字段
TOCTitle: Records and provider-supplied fields
ms:assetid: cde72d6a-b9b0-9636-581d-68239a3f522d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250022(v=office.15)
ms:contentKeyID: 48547776
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ebbfeb303bb575928f09858db5d3a34cf2171ce0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300754"
---
# <a name="records-and-provider-supplied-fields"></a>记录和提供程序提供的字段

**适用于**：Access 2013、Office 2013

打开 [Record](record-object-ado.md) 对象时，它的数据源可以是与打开的 [Connection](connection-object-ado.md) 对象结合使用的打开的 [Recordset](recordset-object-ado.md) 的当前行、绝对 URL 或相对 URL。

如果从 **Recordset** 打开 **Record**，则 **Record** 对象的 [Fields](fields-collection-ado.md) 集合将包含 **Recordset** 的所有字段，还包含基础提供程序添加的所有字段。

提供程序可能插入其他字段作为 **Record** 的补充特征。因此，**Record** 可能具有不作为整体的 **Recordset** 中的独特字段，或者有从该 **Recordset** 的其他行派生得到的任何 **Record**。

例如, 从电子邮件数据源派生的**Recordset**的所有行都可能包含 from、To 和 Subject 等列。 从 **Recordset** 派生的 **Record** 将有相同的字段。 但是，**Record** 还可能具有由该 **Record** 表示的针对特定邮件的其他字段，例如“附件”和“抄送”。

尽管 **Record** 对象与 **Recordset** 当前行具有相同字段，但它们是不同的，因为 **Record** 和 **Recordset** 对象有不同的方法和属性。

在 **Record** 和 **Recordset** 上都可以修改这两个对象共有的字段。尽管基础提供程序可能支持将这样的字段设置为 Null，但在 **Record** 对象上无法删除这样的字段。

打开 **Record** 之后，可以通过编程的方式来添加字段。还可以删除已经添加的字段，但无法从原始 **Recordset** 中删除字段。

还可以直接从 URL 打开 **Record** 对象。这种情况下，在 **Record** 中可以添加哪些字段将取决于基础提供程序。目前，大多数提供程序都会添加一组字段，用来描述该 **Record** 所表示的实体。如果该实体由字节流组成（如简单文件），则通常可以从 [Record](stream-object-ado.md) 打开 **Stream** 对象。

## <a name="special-fields-for-document-source-providers"></a>文档源提供程序的特殊字段

一种特殊的提供程序（称为*文档源提供程序*）用来管理文件夹和文档。当 **Record** 对象表示文档，或者 **Recordset** 对象表示文档文件夹时，文档源提供程序将以一组用来描述文档特征的独特字段（而不是实际文档本身）来填充这些对象。通常，一个字段会包含对表示该文档的 **Stream** 的引用。

这些字段构成了资源 **record** 或 **recordset**，[附录 A：提供程序](appendix-a-providers.md)中针对支持它们的特定提供程序列出了这些字段。

两个常量将对资源 **Record** 或 **Recordset** 的 **Fields** 集合编制索引，以便检索一对常用的字段。 **Field** 对象的 [Value](value-property-ado.md) 属性将返回所需内容。

  - 用 **adDefaultStream** 常量访问的字段包含与 **Record** 或 **Recordset** 对象关联的默认流。提供程序会将默认流赋给对象。

  - 用 **adRecordURL** 常量访问的字段则包含用于标识文档的绝对 URL。

文档源提供程序不支持 [Record](properties-collection-ado.md) 和 **Field** 对象的 **Properties** 集合。对于这样的对象， **Properties** 集合的内容为 Null。

文档源提供程序可能添加特定于提供程序的属性（如 **Datasource Type** ），以标识它是否是文档源提供程序。有关如何确定提供程序类型的详细信息，请参阅提供程序文档。

## <a name="resource-recordset-columns"></a>资源记录集列

*资源记录集*由以下列组成。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>列名</p></th>
<th><p>类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RESOURCE_PARSENAME</p></td>
<td><p>AdVarWChar</p></td>
<td><p>只读。指示资源的 URL。</p></td>
</tr>
<tr class="even">
<td><p>RESOURCE_PARENTNAME</p></td>
<td><p>AdVarWChar</p></td>
<td><p>只读。指示父记录的绝对 URL。</p></td>
</tr>
<tr class="odd">
<td><p>RESOURCE_ABSOLUTEPARSENAME</p></td>
<td><p>AdVarWChar</p></td>
<td><p>只读。指示资源的绝对 URL，它是 PARENTNAME 和 PARSENAME 的串联。</p></td>
</tr>
<tr class="even">
<td><p>RESOURCE_ISHIDDEN</p></td>
<td><p>AdBoolean</p></td>
<td><p>如果资源是隐藏的，则为 True。除非创建行集的命令显式选择 RESOURCE_ISHIDDEN 为 True 的行，否则没有返回行。</p></td>
</tr>
<tr class="odd">
<td><p>RESOURCE_ISREADONLY</p></td>
<td><p>AdBoolean</p></td>
<td><p>如果资源是只读的，则为 True。请尝试用 DBBINDFLAG_WRITE 打开此资源，使用 DB_E_READONLY 将失败。即使当资源只是为了进行读取而已经打开时，也可以编辑此属性。</p></td>
</tr>
<tr class="even">
<td><p>RESOURCE_CONTENTTYPE</p></td>
<td><p>AdVarWChar</p></td>
<td><p>指示文档的可能用法，例如，律师的简介。 这可能与用于创建文档的 Office 模板相对应。&quot;&quot;</p></td>
</tr>
<tr class="odd">
<td><p>RESOURCE_CONTENTCLASS</p></td>
<td><p>AdVarWChar</p></td>
<td><p>指示文档的 MIME 类型, 指示格式 (如&quot;text/html&quot;)。</p></td>
</tr>
<tr class="even">
<td><p>RESOURCE_CONTENTLANGUAGE</p></td>
<td><p>AdVarWChar</p></td>
<td><p>指示存储内容所用的语言。</p></td>
</tr>
<tr class="odd">
<td><p>RESOURCE_CREATIONTIME</p></td>
<td><p>adFileTime</p></td>
<td><p>只读。指示 FILETIME 结构，其中包含资源的创建时间。该时间以通用协调时间 (UTC) 格式报告。</p></td>
</tr>
<tr class="even">
<td><p>RESOURCE_LASTACCESSTIME</p></td>
<td><p>AdFileTime</p></td>
<td><p>只读。指示 FILETIME 结构，其中包含最后一次访问资源的时间。该时间采用 UTC 格式。如果提供程序不支持此时间成员，则 FILETIME 成员为零。</p></td>
</tr>
<tr class="odd">
<td><p>RESOURCE_LASTWRITETIME</p></td>
<td><p>AdFileTime</p></td>
<td><p>只读。指示 FILETIME 结构，其中包含最后一次写入资源的时间。该时间采用 UTC 格式。如果提供程序不支持此时间成员，则 FILETIME 成员为零。</p></td>
</tr>
<tr class="even">
<td><p>RESOURCE_STREAMSIZE</p></td>
<td><p>asUnsignedBigInt</p></td>
<td><p>只读。指示资源的默认流的大小（字节）。</p></td>
</tr>
<tr class="odd">
<td><p>RESOURCE_ISCOLLECTION</p></td>
<td><p>AdBoolean</p></td>
<td><p>只读。如果资源是集合（如目录），则为 True。如果资源是简单文件，则为 False。</p></td>
</tr>
<tr class="even">
<td><p>RESOURCE_ISSTRUCTUREDDOCUMENT</p></td>
<td><p>AdBoolean</p></td>
<td><p>如果资源是结构化文档，则为 True。如果资源不是结构化文档，则为 False。它可以是集合或简单文件。</p></td>
</tr>
<tr class="odd">
<td><p>DEFAULT_DOCUMENT</p></td>
<td><p>AdVarWChar</p></td>
<td><p>只读。指示此资源包含一个指向文件夹中的默认简单文档或指向结构化文档的 URL。从资源请求默认流时使用该属性。对于简单文件，此属性为空。</p></td>
</tr>
<tr class="even">
<td><p>CHAPTERED_CHILDREN</p></td>
<td><p>AdChapter</p></td>
<td><p>只读。可选。指示包含子资源的行集的章节（<em>OLE DB Provider for Internet Publishing</em> 不使用此列）。</p></td>
</tr>
<tr class="odd">
<td><p>RESOURCE_DISPLAYNAME</p></td>
<td><p>AdVarWChar</p></td>
<td><p>只读。指示资源的显示名。</p></td>
</tr>
<tr class="even">
<td><p>RESOURCE_ISROOT</p></td>
<td><p>AdBoolean</p></td>
<td><p>只读。如果资源是集合或结构化文档的根，则为 True。</p></td>
</tr>
</tbody>
</table>

