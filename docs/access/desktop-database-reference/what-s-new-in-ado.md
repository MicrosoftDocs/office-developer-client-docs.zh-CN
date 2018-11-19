---
title: What's new 中 ActiveX 数据对象 (ADO)
TOCTitle: What's new in ADO
ms:assetid: fd3d0f9c-e9df-d130-13e3-757620e9400c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250297(v=office.15)
ms:contentKeyID: 48548905
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a36695e0d858a630ba91b954bfc9a46136e26403
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025969"
---
# <a name="whats-new-in-ado"></a><span data-ttu-id="f2d6d-102">ADO 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="f2d6d-102">What's new in ADO</span></span>

<span data-ttu-id="f2d6d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f2d6d-103">**Applies to**: Access 2013, Office 2013</span></span> 
 
<span data-ttu-id="f2d6d-p101">ADO 2.5 版中包括以下新功能和增强的文档。此列表涵盖了 ADO、ADO MD 和 ADOX。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-p101">The following new features and enhanced documentation are included in the ADO 2.5 release. This list covers ADO, ADO MD, and ADOX.</span></span>

## <a name="new-features"></a><span data-ttu-id="f2d6d-106">新增功能</span><span class="sxs-lookup"><span data-stu-id="f2d6d-106">New features</span></span>

- <span data-ttu-id="f2d6d-107">**[记录和流](chapter-10-records-and-streams.md)**</span><span class="sxs-lookup"><span data-stu-id="f2d6d-107">**[Records and streams](chapter-10-records-and-streams.md)**</span></span>

  <span data-ttu-id="f2d6d-108">此版本的 ADO 介绍[Record](record-object-ado.md)对象，其中可以表示和管理等目录和文件中的文件系统文件夹和邮件中的电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-108">This release of ADO introduces the [Record](record-object-ado.md) object, which can represent and manage things like directories and files in a file system, and folders and messages in an email system.</span></span> <span data-ttu-id="f2d6d-109">**Record** 还可以表示 [Recordset](recordset-object-ado.md) 中的行，虽然 **Record** 和 **Recordset** 对象具有不同的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-109">A **Record** can also represent a row in a [Recordset](recordset-object-ado.md), although **Record** and **Recordset** objects have different methods and properties.</span></span>

  <span data-ttu-id="f2d6d-110">新增的 [Stream](stream-object-ado.md) 对象为读、写和管理构成文件或消息流的二进制字节流或文本提供了方法。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-110">The new [Stream](stream-object-ado.md) object provides the means to read, write, and manage the binary stream of bytes or text that comprise a file or message stream.</span></span>

- <span data-ttu-id="f2d6d-111">**[URL 使用情况](absolute-and-relative-urls.md)**</span><span class="sxs-lookup"><span data-stu-id="f2d6d-111">**[URL usage](absolute-and-relative-urls.md)**</span></span>

  <span data-ttu-id="f2d6d-p103">此版本还引入了统一资源定位器 (URL) 作为连接字符串和命令文本的替代，以命名数据存储对象。URL 可用于现有的 [Connection](connection-object-ado.md) 和 **Recordset** 对象以及新的 **Record** 和 **Stream** 对象。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-p103">This release also introduces the use of Uniform Resource Locators (URLs), as an alternative to connection strings and command text, to name data store objects. URLs may be used with the existing [Connection](connection-object-ado.md) and **Recordset** objects, as well as with the new **Record** and **Stream** objects.</span></span>

  <span data-ttu-id="f2d6d-p104">在此版本中，ADO 支持 OLE DB 提供程序识别自己的 URL 架构。例如，访问 Windows 2000 文件系统的 [OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)\*\* 即可识别现有的 HTTP 架构。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-p104">With this release, ADO supports OLE DB providers that recognize their own URL schemes. For example, the [OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)*,* which accesses the Windows 2000 file system, recognizes the existing HTTP scheme.</span></span>

- <span data-ttu-id="f2d6d-116">**[文档源提供程序的特殊字段](records-and-provider-supplied-fields.md)**</span><span class="sxs-lookup"><span data-stu-id="f2d6d-116">**[Special fields for document source providers](records-and-provider-supplied-fields.md)**</span></span>

  <span data-ttu-id="f2d6d-117">一个特殊的提供程序，称为*文档源*提供程序类管理文件夹和文档。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-117">A special class of providers, called *document source* providers, manage folders and documents.</span></span> <span data-ttu-id="f2d6d-118">当 **Record** 对象表示文档或 **Recordset** 对象表示文档的文件夹时，文档源提供程序用描述文档特性的唯一字段集来填充这些字段。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-118">When a **Record** object represents a document, or a **Recordset** object represents a folder of documents, the document source provider populates those objects with a unique set of fields that describe characteristics of the document.</span></span> <span data-ttu-id="f2d6d-119">这些字段构成了*资源* **Record**或**Recordset**。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-119">These fields constitute a *resource* **Record** or **Recordset**.</span></span>

## <a name="new-reference-topics"></a><span data-ttu-id="f2d6d-120">新引用主题</span><span class="sxs-lookup"><span data-stu-id="f2d6d-120">New reference topics</span></span>

### <a name="properties"></a><span data-ttu-id="f2d6d-121">属性</span><span class="sxs-lookup"><span data-stu-id="f2d6d-121">Properties</span></span>

<span data-ttu-id="f2d6d-122">此版本中包括以下新属性。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-122">The following new properties are included in this release.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f2d6d-123">属性</span><span class="sxs-lookup"><span data-stu-id="f2d6d-123">Property</span></span></p></th>
<th><p><span data-ttu-id="f2d6d-124">说明</span><span class="sxs-lookup"><span data-stu-id="f2d6d-124">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-125"><a href="charset-property-ado.md">字符集</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-125"><a href="charset-property-ado.md">Charset</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-126">指示文本 <strong>Stream</strong> 对象的内容应当转换为的字符集。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-126">Indicates the character set into which the contents of a text <strong>Stream</strong> object should be translated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-127"><a href="eos-property-ado.md">EOS</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-127"><a href="eos-property-ado.md">EOS</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-128">指示当前位置是否位于流的末尾。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-128">Indicates whether the current position is at the end of the stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-129"><a href="lineseparator-property-ado.md">LineSeparator</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-129"><a href="lineseparator-property-ado.md">LineSeparator</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-130">指示要在文本 <strong>Stream</strong> 对象中用作行分隔符的二进制字符。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-130">Indicates the binary character to be used as the line separator in text <strong>Stream</strong> objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-131"><a href="mode-property-ado.md">Mode</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-131"><a href="mode-property-ado.md">Mode</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-132">指示在 <strong>Connection</strong>、<strong>Record</strong> 或 <strong>Stream</strong> 对象中修改数据的可用权限。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-132">Indicates the available permissions for modifying data in a <strong>Connection</strong>, <strong>Record</strong>, or <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-133"><a href="parenturl-property-ado.md">ParentURL</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-133"><a href="parenturl-property-ado.md">ParentURL</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-134">指示指向当前 <strong>Record</strong> 对象的父 <strong>Record</strong> 的绝对 URL 字符串。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-134">Indicates an absolute URL string that points to the parent <strong>Record</strong> of the current <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-135"><a href="position-property-ado.md">Position</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-135"><a href="position-property-ado.md">Position</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-136">指示 <strong>Stream</strong> 对象中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-136">Indicates the current position within a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-137"><a href="recordtype-property-ado.md">RecordType</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-137"><a href="recordtype-property-ado.md">RecordType</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-138">指示 <strong>Record</strong> 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-138">Indicates the type of <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-139"><a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream">Size</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-139"><a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream">Size</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-140">指示流的大小，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-140">Indicates the size of the stream in number of bytes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-141"><a href="source-property-ado-record.md">Source</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-141"><a href="source-property-ado-record.md">Source</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-142">指示 <strong>Record</strong> 对象所表示的实体。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-142">Indicates the entity represented by the <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-143"><a href="state-property-ado.md">State</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-143"><a href="state-property-ado.md">State</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-144">对所有适用的对象，指示其状态是打开还是关闭。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-144">Indicates for all applicable objects whether the state of the object is open or closed.</span></span> <span data-ttu-id="f2d6d-145">对执行异步方法的所有适用对象，指示其当前状态是正在连接、正在执行还是正在检索。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-145">Indicates for all applicable objects executing an asynchronous method, whether the current state of the object is connecting, executing, or retrieving.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-146"><a href="type-property-ado-stream.md">Type</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-146"><a href="type-property-ado-stream.md">Type</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-147">指示 <strong>Stream</strong> 对象（二进制或文本）中所包含的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-147">Indicates the type of data contained in the <strong>Stream</strong> object (binary or text).</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="methods"></a><span data-ttu-id="f2d6d-148">方法</span><span class="sxs-lookup"><span data-stu-id="f2d6d-148">Methods</span></span>

<span data-ttu-id="f2d6d-149">此版本中包括以下新方法。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-149">The following new methods are included in this release.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f2d6d-150">方法</span><span class="sxs-lookup"><span data-stu-id="f2d6d-150">Method</span></span></p></th>
<th><p><span data-ttu-id="f2d6d-151">说明</span><span class="sxs-lookup"><span data-stu-id="f2d6d-151">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-152"><a href="copyrecord-method-ado.md">CopyRecord</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-152"><a href="copyrecord-method-ado.md">CopyRecord</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-153">用于将文件或目录及其内容复制到其他位置。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-153">Copies a file or directory, and its contents, to another location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-154"><a href="copyto-method-ado.md">CopyTo</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-154"><a href="copyto-method-ado.md">CopyTo</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-155"><strong>Stream</strong> <strong>对象</strong>中的指定的数量的字符或字节 （取决于<strong>类型</strong>） 复制到另一个<strong>Stream</strong>对象。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-155">Copies the specified number of characters or bytes (depending on <strong>Type</strong>) in the <strong>Stream</strong> <strong>object</strong> to another <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-156"><a href="deleterecord-method-ado.md">DeleteRecord</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-156"><a href="deleterecord-method-ado.md">DeleteRecord</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-157">用于删除文件或目录及其所有子目录。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-157">Deletes a file or directory, and all its subdirectories.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-158"><a href="flush-method-ado.md">刷新</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-158"><a href="flush-method-ado.md">Flush</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-159">用于将保留在 ADO 缓冲区中的 <strong>Stream</strong> 对象的内容强制转移到 <strong>Stream</strong> 对象所关联的基础对象中。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-159">Forces the contents of the <strong>Stream</strong> object remaining in the ADO buffer to the underlying object with which the <strong>Stream</strong> object is associated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-160"><a href="getchildren-method-ado.md">GetChildren</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-160"><a href="getchildren-method-ado.md">GetChildren</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-161">用于返回一个 <strong>Recordset</strong>，其行表示此 <strong>Record</strong> 所表示的目录中的文件和子目录。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-161">Returns a <strong>Recordset</strong> whose rows represent the files and subdirectories in the directory represented by this <strong>Record.</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-162"><a href="loadfromfile-method-ado.md">LoadFromFile</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-162"><a href="loadfromfile-method-ado.md">LoadFromFile</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-163">用于将现有文件的内容加载到 <strong>Stream</strong> 对象中。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-163">Loads the contents of an existing file into a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-164"><a href="moverecord-method-ado.md">MoveRecord</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-164"><a href="moverecord-method-ado.md">MoveRecord</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-165">用于将文件（或目录及其内容）移动到其他位置。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-165">Moves a file, or a directory and its contents, to another location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-166"><a href="open-method-ado-record.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-166"><a href="open-method-ado-record.md">Open</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-167">用于打开现有的 <strong>Record</strong> 对象，或创建新的文件或目录。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-167">Opens an existing <strong>Record</strong> object, or creates a new file or directory.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-168"><a href="open-method-ado-stream.md">Open</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-168"><a href="open-method-ado-stream.md">Open</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-169">用于打开 <strong>Stream</strong> 对象，以操作二进制数据流或文本数据流。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-169">Opens a <strong>Stream</strong> object to manipulate streams of binary or text data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-170"><a href="read-method-ado.md">Read</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-170"><a href="read-method-ado.md">Read</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-171">可从二进制 <strong>Stream</strong> 对象读取指定数量的字节。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-171">Reads a specified number of bytes from a binary <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-172"><a href="readtext-method-ado.md">ReadText</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-172"><a href="readtext-method-ado.md">ReadText</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-173">可从文本 <strong>Stream</strong> 对象读取指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-173">Reads specified number of characters from a text <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-174"><a href="savetofile-method-ado.md">SaveToFile</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-174"><a href="savetofile-method-ado.md">SaveToFile</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-175">可将 <strong>Stream</strong> 的二进制内容保存到文件。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-175">Saves the binary contents of a <strong>Stream</strong> to a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-176"><a href="seteos-method-ado.md">SetEOS</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-176"><a href="seteos-method-ado.md">SetEOS</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-177">用于设置流的结束位置。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-177">Sets the position that is the end of the stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-178"><a href="skipline-method-ado.md">SkipLine</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-178"><a href="skipline-method-ado.md">SkipLine</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-179">用于在读取文本 <strong>Stream</strong> 对象时跳过一整行。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-179">Skips one entire line when reading a text <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2d6d-180"><a href="write-method-ado.md">Write</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-180"><a href="write-method-ado.md">Write</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-181">用于将二进制数据写入 <strong>Stream</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-181">Writes binary data to a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2d6d-182"><a href="writetext-method-ado.md">WriteText</a></span><span class="sxs-lookup"><span data-stu-id="f2d6d-182"><a href="writetext-method-ado.md">WriteText</a></span></span></p></td>
<td><p><span data-ttu-id="f2d6d-183">用于将指定的文本字符串写入 <strong>Stream</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-183">Writes a specified text string to a <strong>Stream</strong> object.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="new-and-enhanced-documentation"></a><span data-ttu-id="f2d6d-184">新增和增强文档</span><span class="sxs-lookup"><span data-stu-id="f2d6d-184">New and enhanced documentation</span></span>

- <span data-ttu-id="f2d6d-185">**[代码示例主题](ado-code-examples.md)**</span><span class="sxs-lookup"><span data-stu-id="f2d6d-185">**[Code example topics](ado-code-examples.md)**</span></span>

  <span data-ttu-id="f2d6d-186">示例已扩展以包含在 Microsoft Visual c + + 和 Microsoft Visual J + + 中编写的代码示例。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-186">The examples have been expanded to contain code examples written in Microsoft Visual C++ and Microsoft Visual J++.</span></span> <span data-ttu-id="f2d6d-187">您可以将这些示例复制并粘贴到自己的编辑器中。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-187">You can copy and paste these code examples into your editor.</span></span>

- <span data-ttu-id="f2d6d-188">**[提供程序主题](appendix-a-providers.md)**</span><span class="sxs-lookup"><span data-stu-id="f2d6d-188">**[Provider topics](appendix-a-providers.md)**</span></span>

  <span data-ttu-id="f2d6d-189">包括一个新的主题，阐述了如何在 [OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md) 中使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-189">A new topic is included that explains how to use ADO with the [OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span>

- <span data-ttu-id="f2d6d-190">**[用 ADO 编程](appendix-c-programming-with-ado.md)**</span><span class="sxs-lookup"><span data-stu-id="f2d6d-190">**[Programming with ADO](appendix-c-programming-with-ado.md)**</span></span>

  <span data-ttu-id="f2d6d-191">这是一个新的部分，包含在各种编程语言中使用 ADO 的提示和技巧。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-191">This new section contains tips and tricks for using ADO with various programming languages.</span></span> <span data-ttu-id="f2d6d-192">它包含 Visual c + + Extensions for ADO 和 ADO/WFC，以及特定于使用 Microsoft Visual Basic、 Microsoft Visual Basic Scripting Edition、 Microsoft JScript、 Microsoft Visual c + + 中，开发人员的新信息的现有语法索引或Microsoft Visual J + + 中。</span><span class="sxs-lookup"><span data-stu-id="f2d6d-192">It contains the existing syntax indexes for the Visual C++ Extensions for ADO and ADO/WFC, as well as new information specific to developers using Microsoft Visual Basic, Microsoft Visual Basic Scripting Edition, Microsoft JScript, Microsoft Visual C++, or Microsoft Visual J++.</span></span>

