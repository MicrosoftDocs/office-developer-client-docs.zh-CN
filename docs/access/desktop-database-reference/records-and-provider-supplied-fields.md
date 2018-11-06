---
title: 记录和提供程序提供的字段
TOCTitle: Records and provider-supplied fields
ms:assetid: cde72d6a-b9b0-9636-581d-68239a3f522d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250022(v=office.15)
ms:contentKeyID: 48547776
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3e01d9dd1dce81911b11b7de8ca8c6ad5a19eaaf
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998320"
---
# <a name="records-and-provider-supplied-fields"></a><span data-ttu-id="1b16e-102">记录和提供程序提供的字段</span><span class="sxs-lookup"><span data-stu-id="1b16e-102">Records and provider-supplied fields</span></span>

<span data-ttu-id="1b16e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1b16e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1b16e-104">打开 [Record](record-object-ado.md) 对象时，它的数据源可以是与打开的 [Connection](recordset-object-ado.md) 对象结合使用的打开的 [Recordset](connection-object-ado.md) 的当前行、绝对 URL 或相对 URL。</span><span class="sxs-lookup"><span data-stu-id="1b16e-104">When a [Record](record-object-ado.md) object is opened, its source can be the current row of an open [Recordset](recordset-object-ado.md), an absolute URL, or a relative URL in conjunction with an open [Connection](connection-object-ado.md) object.</span></span>

<span data-ttu-id="1b16e-105">如果从 **Recordset** 打开 **Record** ，则 **Record** 对象的 [Fields](fields-collection-ado.md) 集合将包含 **Recordset** 的所有字段，还包含基础提供程序添加的所有字段。</span><span class="sxs-lookup"><span data-stu-id="1b16e-105">If the **Record** is opened from a **Recordset**, the **Record** object [Fields](fields-collection-ado.md) collection will contain all the fields from the **Recordset**, plus any fields added by the underlying provider.</span></span>

<span data-ttu-id="1b16e-p101">提供程序可能插入其他字段作为 **Record** 的补充特征。因此， **Record** 可能具有不作为整体的 **Recordset** 中的独特字段，或者有从该 **Recordset** 的其他行派生得到的任何 **Record** 。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p101">The provider may insert additional fields that serve as supplementary characteristics of the **Record**. As a result, a **Record** may have unique fields not in the **Recordset** as a whole or any **Record** derived from another row of the **Recordset**.</span></span>

<span data-ttu-id="1b16e-108">例如， **Recordset**派生自的电子邮件数据源中的所有行可能为，对此类作为从列以及主题。</span><span class="sxs-lookup"><span data-stu-id="1b16e-108">For example, all rows of a **Recordset** derived from an email data source might have columns such as From, To, and Subject.</span></span> <span data-ttu-id="1b16e-109">从 **Recordset** 派生的 **Record** 将有相同的字段。</span><span class="sxs-lookup"><span data-stu-id="1b16e-109">A **Record** derived from that **Recordset** will have the same fields.</span></span> <span data-ttu-id="1b16e-110">但是， **Record** 还可能具有由该 **Record** 表示的针对特定邮件的其他字段，例如"附件"和"抄送"。</span><span class="sxs-lookup"><span data-stu-id="1b16e-110">However, the **Record** may also have other fields unique to the particular message represented by that **Record**, such as Attachment and Cc (carbon copy).</span></span>

<span data-ttu-id="1b16e-111">尽管 **Record** 对象与 **Recordset** 当前行具有相同字段，但它们是不同的，因为 **Record** 和 **Recordset** 对象有不同的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="1b16e-111">Although the **Record** object and current row of the **Recordset** have the same fields, they are different because **Record** and **Recordset** objects have different methods and properties.</span></span>

<span data-ttu-id="1b16e-p103">在 **Record** 和 **Recordset** 上都可以修改这两个对象共有的字段。尽管基础提供程序可能支持将这样的字段设置为 Null，但在 **Record** 对象上无法删除这样的字段。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p103">A field held in common by the **Record** and **Recordset** can be modified on either object. However, the field cannot be deleted on the **Record** object, although the underlying provider may support setting the field to null.</span></span>

<span data-ttu-id="1b16e-p104">打开 **Record** 之后，可以通过编程的方式来添加字段。还可以删除已经添加的字段，但无法从原始 **Recordset** 中删除字段。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p104">After the **Record** is opened, you can programmatically add fields. You can also delete fields you have added, but you cannot delete fields from the original **Recordset**.</span></span>

<span data-ttu-id="1b16e-p105">还可以直接从 URL 打开 **Record** 对象。这种情况下，在 **Record** 中可以添加哪些字段将取决于基础提供程序。目前，大多数提供程序都会添加一组字段，用来描述该 **Record** 所表示的实体。如果该实体由字节流组成（如简单文件），则通常可以从 [Record](stream-object-ado.md) 打开 **Stream** 对象。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p105">You may also open the **Record** object directly from a URL. In this case, the fields added to the **Record** depend on the underlying provider. Currently, most providers add a set of fields that describe the entity represented by the **Record**. If the entity consists of a stream of bytes, such as a simple file, then a [Stream](stream-object-ado.md) object can usually be opened from the **Record**.</span></span>

## <a name="special-fields-for-document-source-providers"></a><span data-ttu-id="1b16e-120">文档源提供程序的特殊字段</span><span class="sxs-lookup"><span data-stu-id="1b16e-120">Special Fields for Document Source Providers</span></span>

<span data-ttu-id="1b16e-p106">一种特殊的提供程序（称为*文档源提供程序*）用来管理文件夹和文档。当 **Record** 对象表示文档，或者 **Recordset** 对象表示文档文件夹时，文档源提供程序将以一组用来描述文档特征的独特字段（而不是实际文档本身）来填充这些对象。通常，一个字段会包含对表示该文档的 **Stream** 的引用。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p106">A special class of providers, called *document source providers*, manages folders and documents. When a **Record** object represents a document or a **Recordset** object represents a folder of documents, the document source provider populates those objects with a unique set of fields that describe characteristics of the document instead of the actual document itself. Typically, one field contains a reference to the **Stream** that represents the document.</span></span>

<span data-ttu-id="1b16e-124">这些字段构成了资源 **record** 或 **recordset** ， [附录 A：提供程序](appendix-a-providers.md)中针对支持它们的特定提供程序列出了这些字段。</span><span class="sxs-lookup"><span data-stu-id="1b16e-124">These fields constitute a resource **record** or **recordset** and are listed for the specific providers that support them in [Appendix A: Providers](appendix-a-providers.md).</span></span>

<span data-ttu-id="1b16e-p107">两个常量将对资源 **Record** 或 **Recordset** 的 **Fields** 集合编制索引，以便检索一对常用的字段。 **Field** 对象的 [Value](value-property-ado.md) 属性将返回所需内容。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p107">Two constants index the **Fields** collection of a resource **Record** or **Recordset** to retrieve a pair of commonly used fields. The **Field** object [Value](value-property-ado.md) property returns the desired content.</span></span>

  - <span data-ttu-id="1b16e-p108">用 **adDefaultStream** 常量访问的字段包含与 **Record** 或 **Recordset** 对象关联的默认流。提供程序会将默认流赋给对象。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p108">The field accessed with the **adDefaultStream** constant contains a default stream associated with the **Record** or **Recordset** object. The provider assigns a default stream to an object.</span></span>

  - <span data-ttu-id="1b16e-129">用 **adRecordURL** 常量访问的字段则包含用于标识文档的绝对 URL。</span><span class="sxs-lookup"><span data-stu-id="1b16e-129">The field accessed with the **adRecordURL** constant contains the absolute URL that identifies the document.</span></span>

<span data-ttu-id="1b16e-p109">文档源提供程序不支持 [Record](properties-collection-ado.md) 和 **Field** 对象的 **Properties** 集合。对于这样的对象， **Properties** 集合的内容为 Null。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p109">A document source provider does not support the [Properties](properties-collection-ado.md) collection of **Record** and **Field** objects. The content of the **Properties** collection is null for such objects.</span></span>

<span data-ttu-id="1b16e-p110">文档源提供程序可能添加特定于提供程序的属性（如 **Datasource Type** ），以标识它是否是文档源提供程序。有关如何确定提供程序类型的详细信息，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p110">A document source provider may add a provider-specific property such as **Datasource Type** to identify whether it is a document source provider. For more information about how to determine your type of provider, see your provider documentation.</span></span>

## <a name="resource-recordset-columns"></a><span data-ttu-id="1b16e-134">资源记录集列</span><span class="sxs-lookup"><span data-stu-id="1b16e-134">Resource Recordset Columns</span></span>

<span data-ttu-id="1b16e-135">*资源记录集*由以下列组成。</span><span class="sxs-lookup"><span data-stu-id="1b16e-135">A *resource recordset* consists of the following columns.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1b16e-136">列名称</span><span class="sxs-lookup"><span data-stu-id="1b16e-136">Column name</span></span></p></th>
<th><p><span data-ttu-id="1b16e-137">类型</span><span class="sxs-lookup"><span data-stu-id="1b16e-137">Type</span></span></p></th>
<th><p><span data-ttu-id="1b16e-138">说明</span><span class="sxs-lookup"><span data-stu-id="1b16e-138">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b16e-139">RESOURCE_PARSENAME</span><span class="sxs-lookup"><span data-stu-id="1b16e-139">RESOURCE_PARSENAME</span></span></p></td>
<td><p><span data-ttu-id="1b16e-140">AdVarWChar</span><span class="sxs-lookup"><span data-stu-id="1b16e-140">AdVarWChar</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p111">只读。指示资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p111">Read-only. Indicates the URL of the resource.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b16e-143">RESOURCE_PARENTNAME</span><span class="sxs-lookup"><span data-stu-id="1b16e-143">RESOURCE_PARENTNAME</span></span></p></td>
<td><p><span data-ttu-id="1b16e-144">AdVarWChar</span><span class="sxs-lookup"><span data-stu-id="1b16e-144">AdVarWChar</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p112">只读。指示父记录的绝对 URL。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p112">Read-only. Indicates the absolute URL of the parent record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b16e-147">RESOURCE_ABSOLUTEPARSENAME</span><span class="sxs-lookup"><span data-stu-id="1b16e-147">RESOURCE_ABSOLUTEPARSENAME</span></span></p></td>
<td><p><span data-ttu-id="1b16e-148">AdVarWChar</span><span class="sxs-lookup"><span data-stu-id="1b16e-148">AdVarWChar</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p113">只读。指示资源的绝对 URL，它是 PARENTNAME 和 PARSENAME 的串联。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p113">Read-only. Indicates the absolute URL of the resource, which is the concatenation of PARENTNAME and PARSENAME.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b16e-151">RESOURCE_ISHIDDEN</span><span class="sxs-lookup"><span data-stu-id="1b16e-151">RESOURCE_ISHIDDEN</span></span></p></td>
<td><p><span data-ttu-id="1b16e-152">AdBoolean</span><span class="sxs-lookup"><span data-stu-id="1b16e-152">AdBoolean</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p114">如果资源是隐藏的，则为 True。除非创建行集的命令显式选择 RESOURCE_ISHIDDEN 为 True 的行，否则没有返回行。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p114">True if the resource is hidden. No rows will be returned unless the command that creates the rowset explicitly selects rows where RESOURCE_ISHIDDEN is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b16e-155">RESOURCE_ISREADONLY</span><span class="sxs-lookup"><span data-stu-id="1b16e-155">RESOURCE_ISREADONLY</span></span></p></td>
<td><p><span data-ttu-id="1b16e-156">AdBoolean</span><span class="sxs-lookup"><span data-stu-id="1b16e-156">AdBoolean</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p115">如果资源是只读的，则为 True。请尝试用 DBBINDFLAG_WRITE 打开此资源，使用 DB_E_READONLY 将失败。即使当资源只是为了进行读取而已经打开时，也可以编辑此属性。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p115">True if the resource is read-only. Attempts to open this resource with DBBINDFLAG_WRITE and will fail with DB_E_READONLY. This property may be edited even when the resource has only been opened for reading.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b16e-160">RESOURCE_CONTENTTYPE</span><span class="sxs-lookup"><span data-stu-id="1b16e-160">RESOURCE_CONTENTTYPE</span></span></p></td>
<td><p><span data-ttu-id="1b16e-161">AdVarWChar</span><span class="sxs-lookup"><span data-stu-id="1b16e-161">AdVarWChar</span></span></p></td>
<td><p><span data-ttu-id="1b16e-162">指示文档的可能使用 — 例如，律师的简短。</span><span class="sxs-lookup"><span data-stu-id="1b16e-162">Indicates the likely use of the document — for example, a lawyer's brief.</span></span> <span data-ttu-id="1b16e-163">这可能对应于用来创建文档的 Office 模板。&quot;&quot;</span><span class="sxs-lookup"><span data-stu-id="1b16e-163">This may correspond to the Office template used to create the document.&quot;&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b16e-164">RESOURCE_CONTENTCLASS</span><span class="sxs-lookup"><span data-stu-id="1b16e-164">RESOURCE_CONTENTCLASS</span></span></p></td>
<td><p><span data-ttu-id="1b16e-165">AdVarWChar</span><span class="sxs-lookup"><span data-stu-id="1b16e-165">AdVarWChar</span></span></p></td>
<td><p><span data-ttu-id="1b16e-166">指示文档，如指示格式的 MIME 类型&quot;text/html&quot;。</span><span class="sxs-lookup"><span data-stu-id="1b16e-166">Indicates the MIME type of the document, indicating the format such as &quot;text/html&quot;.'</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b16e-167">RESOURCE_CONTENTLANGUAGE</span><span class="sxs-lookup"><span data-stu-id="1b16e-167">RESOURCE_CONTENTLANGUAGE</span></span></p></td>
<td><p><span data-ttu-id="1b16e-168">AdVarWChar</span><span class="sxs-lookup"><span data-stu-id="1b16e-168">AdVarWChar</span></span></p></td>
<td><p><span data-ttu-id="1b16e-169">指示存储内容所用的语言。</span><span class="sxs-lookup"><span data-stu-id="1b16e-169">Indicates the language in which the content is stored.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b16e-170">RESOURCE_CREATIONTIME</span><span class="sxs-lookup"><span data-stu-id="1b16e-170">RESOURCE_CREATIONTIME</span></span></p></td>
<td><p><span data-ttu-id="1b16e-171">adFileTime</span><span class="sxs-lookup"><span data-stu-id="1b16e-171">adFileTime</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p117">只读。指示 FILETIME 结构，其中包含资源的创建时间。该时间以通用协调时间 (UTC) 格式报告。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p117">Read-only. Indicates a FILETIME structure containing the time the resource was created. The time is reported in Coordinated Universal Time (UTC) format.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b16e-175">RESOURCE_LASTACCESSTIME</span><span class="sxs-lookup"><span data-stu-id="1b16e-175">RESOURCE_LASTACCESSTIME</span></span></p></td>
<td><p><span data-ttu-id="1b16e-176">AdFileTime</span><span class="sxs-lookup"><span data-stu-id="1b16e-176">AdFileTime</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p118">只读。指示 FILETIME 结构，其中包含最后一次访问资源的时间。该时间采用 UTC 格式。如果提供程序不支持此时间成员，则 FILETIME 成员为零。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p118">Read-only. Indicates a FILETIME structure containing the time that the resource was last accessed. The time is in UTC format. The FILETIME members are zero if the provider does not support this time member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b16e-181">RESOURCE_LASTWRITETIME</span><span class="sxs-lookup"><span data-stu-id="1b16e-181">RESOURCE_LASTWRITETIME</span></span></p></td>
<td><p><span data-ttu-id="1b16e-182">AdFileTime</span><span class="sxs-lookup"><span data-stu-id="1b16e-182">AdFileTime</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p119">只读。指示 FILETIME 结构，其中包含最后一次写入资源的时间。该时间采用 UTC 格式。如果提供程序不支持此时间成员，则 FILETIME 成员为零。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p119">Read-only. Indicates a FILETIME structure containing the time that the resource was last written. The time is in UTC format. The FILETIME members are zero if the provider does not support this time member.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b16e-187">RESOURCE_STREAMSIZE</span><span class="sxs-lookup"><span data-stu-id="1b16e-187">RESOURCE_STREAMSIZE</span></span></p></td>
<td><p><span data-ttu-id="1b16e-188">asUnsignedBigInt</span><span class="sxs-lookup"><span data-stu-id="1b16e-188">asUnsignedBigInt</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p120">只读。指示资源的默认流的大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p120">Read-only. Indicates the size of the resource's default stream, in bytes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b16e-191">RESOURCE_ISCOLLECTION</span><span class="sxs-lookup"><span data-stu-id="1b16e-191">RESOURCE_ISCOLLECTION</span></span></p></td>
<td><p><span data-ttu-id="1b16e-192">AdBoolean</span><span class="sxs-lookup"><span data-stu-id="1b16e-192">AdBoolean</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p121">只读。如果资源是集合（如目录），则为 True。如果资源是简单文件，则为 False。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p121">Read-only. True if the resource is a collection, such as a directory. False if the resource is a simple file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b16e-196">RESOURCE_ISSTRUCTUREDDOCUMENT</span><span class="sxs-lookup"><span data-stu-id="1b16e-196">RESOURCE_ISSTRUCTUREDDOCUMENT</span></span></p></td>
<td><p><span data-ttu-id="1b16e-197">AdBoolean</span><span class="sxs-lookup"><span data-stu-id="1b16e-197">AdBoolean</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p122">如果资源是结构化文档，则为 True。如果资源不是结构化文档，则为 False。它可以是集合或简单文件。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p122">True if the resource is a structured document. False if the resource is not a structured document. It could be a collection or a simple file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b16e-201">DEFAULT_DOCUMENT</span><span class="sxs-lookup"><span data-stu-id="1b16e-201">DEFAULT_DOCUMENT</span></span></p></td>
<td><p><span data-ttu-id="1b16e-202">AdVarWChar</span><span class="sxs-lookup"><span data-stu-id="1b16e-202">AdVarWChar</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p123">只读。指示此资源包含一个指向文件夹中的默认简单文档或指向结构化文档的 URL。从资源请求默认流时使用该属性。对于简单文件，此属性为空。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p123">Read-only. Indicates that this resource contains a URL to the default simple document of a folder or a structured document. Used when the default stream is requested from a resource. This property is blank for a simple file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b16e-207">CHAPTERED_CHILDREN</span><span class="sxs-lookup"><span data-stu-id="1b16e-207">CHAPTERED_CHILDREN</span></span></p></td>
<td><p><span data-ttu-id="1b16e-208">AdChapter</span><span class="sxs-lookup"><span data-stu-id="1b16e-208">AdChapter</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p124">只读。可选。指示包含子资源的行集的章节（<em>OLE DB Provider for Internet Publishing</em> 不使用此列）。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p124">Read-only. Optional. Indicates the chapter of the rowset containing the children of the resource. (The <em>OLE DB Provider for Internet Publishing</em> does not use this column.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b16e-213">RESOURCE_DISPLAYNAME</span><span class="sxs-lookup"><span data-stu-id="1b16e-213">RESOURCE_DISPLAYNAME</span></span></p></td>
<td><p><span data-ttu-id="1b16e-214">AdVarWChar</span><span class="sxs-lookup"><span data-stu-id="1b16e-214">AdVarWChar</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p125">只读。指示资源的显示名。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p125">Read-only. Indicates the display name of the resource.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b16e-217">RESOURCE_ISROOT</span><span class="sxs-lookup"><span data-stu-id="1b16e-217">RESOURCE_ISROOT</span></span></p></td>
<td><p><span data-ttu-id="1b16e-218">AdBoolean</span><span class="sxs-lookup"><span data-stu-id="1b16e-218">AdBoolean</span></span></p></td>
<td><p><span data-ttu-id="1b16e-p126">只读。如果资源是集合或结构化文档的根，则为 True。</span><span class="sxs-lookup"><span data-stu-id="1b16e-p126">Read-only. True if the resource is the root of a collection or structured document.</span></span></p></td>
</tr>
</tbody>
</table>

