---
title: ActiveX 数据对象 (ADO) 中的新增功能
TOCTitle: What's new in ADO
ms:assetid: fd3d0f9c-e9df-d130-13e3-757620e9400c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250297(v=office.15)
ms:contentKeyID: 48548905
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 593daf08da1b4ce435d17f2a6deedfa3e89dbd32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302609"
---
# <a name="whats-new-in-ado"></a>ADO 中的新增功能

**适用于**：Access 2013、Office 2013 
 
ADO 2.5 版中包括以下新功能和增强的文档。 此列表涵盖了 ADO、ADO MD 和 ADOX。

## <a name="new-features"></a>新增功能

- **[记录和流](chapter-10-records-and-streams.md)**

  此版本的 ADO 引入了[Record](record-object-ado.md)对象, 该对象可以表示和管理文件系统中的目录和文件等内容, 以及电子邮件系统中的文件夹和邮件。 **Record** 还可以表示 [Recordset](recordset-object-ado.md) 中的行，虽然 **Record** 和 **Recordset** 对象具有不同的方法和属性。

  新增的 [Stream](stream-object-ado.md) 对象为读、写和管理构成文件或消息流的二进制字节流或文本提供了方法。

- **[URL 用法](absolute-and-relative-urls.md)**

  此版本还引入了统一资源定位器 (URL) 作为连接字符串和命令文本的替代，以命名数据存储对象。URL 可用于现有的 [Connection](connection-object-ado.md) 和 **Recordset** 对象以及新的 **Record** 和 **Stream** 对象。

  在此版本中，ADO 支持 OLE DB 提供程序识别自己的 URL 架构。例如，访问 Windows 2000 文件系统的 [OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)** 即可识别现有的 HTTP 架构。

- **[文档源提供程序的特殊字段](records-and-provider-supplied-fields.md)**

  提供程序的特殊类，称为*文档源*提供程序，用于管理文件夹和文档。 当 **Record** 对象表示文档或 **Recordset** 对象表示文档的文件夹时，文档源提供程序用描述文档特性的唯一字段集来填充这些字段。 这些字段构成了一个*资源***记录**或**记录集**。

## <a name="new-reference-topics"></a>新的参考主题

### <a name="properties"></a>属性

此版本中包括以下新属性。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>属性</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="charset-property-ado.md">Charset</a></p></td>
<td><p>指示文本 <strong>Stream</strong> 对象的内容应当转换为的字符集。</p></td>
</tr>
<tr class="even">
<td><p><a href="eos-property-ado.md">电源</a></p></td>
<td><p>指示当前位置是否位于流的末尾。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lineseparator-property-ado.md">LineSeparator</a></p></td>
<td><p>指示要在文本 <strong>Stream</strong> 对象中用作行分隔符的二进制字符。</p></td>
</tr>
<tr class="even">
<td><p><a href="mode-property-ado.md">Mode</a></p></td>
<td><p>指示在 <strong>Connection</strong>、<strong>Record</strong> 或 <strong>Stream</strong> 对象中修改数据的可用权限。</p></td>
</tr>
<tr class="odd">
<td><p><a href="parenturl-property-ado.md">ParentURL</a></p></td>
<td><p>指示指向当前 <strong>Record</strong> 对象的父 <strong>Record</strong> 的绝对 URL 字符串。</p></td>
</tr>
<tr class="even">
<td><p><a href="position-property-ado.md">Position</a></p></td>
<td><p>指示 <strong>Stream</strong> 对象中的当前位置。</p></td>
</tr>
<tr class="odd">
<td><p><a href="recordtype-property-ado.md">RecordType</a></p></td>
<td><p>指示 <strong>Record</strong> 对象的类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream">Size</a></p></td>
<td><p>指示流的大小，以字节为单位。</p></td>
</tr>
<tr class="odd">
<td><p><a href="source-property-ado-record.md">Source</a></p></td>
<td><p>指示 <strong>Record</strong> 对象所表示的实体。</p></td>
</tr>
<tr class="even">
<td><p><a href="state-property-ado.md">State</a></p></td>
<td><p>对所有适用的对象，指示其状态是打开还是关闭。 指示执行异步方法的所有适用对象，无论对象的当前状态是正在连接、执行还是检索。</p></td>
</tr>
<tr class="odd">
<td><p><a href="type-property-ado-stream.md">Type</a></p></td>
<td><p>指示 <strong>Stream</strong> 对象（二进制或文本）中所包含的数据类型。</p></td>
</tr>
</tbody>
</table>

### <a name="methods"></a>方法

此版本中包括以下新方法。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>方法</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="copyrecord-method-ado.md">CopyRecord</a></p></td>
<td><p>用于将文件或目录及其内容复制到其他位置。</p></td>
</tr>
<tr class="even">
<td><p><a href="copyto-method-ado.md">CopyTo</a></p></td>
<td><p>将<strong>stream</strong> <strong>对象</strong>中指定数量的字符或字节 (取决于<strong>类型</strong>) 复制到另一个<strong>stream</strong>对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="deleterecord-method-ado.md">DeleteRecord</a></p></td>
<td><p>用于删除文件或目录及其所有子目录。</p></td>
</tr>
<tr class="even">
<td><p><a href="flush-method-ado.md">对齐</a></p></td>
<td><p>用于将保留在 ADO 缓冲区中的 <strong>Stream</strong> 对象的内容强制转移到 <strong>Stream</strong> 对象所关联的基础对象中。</p></td>
</tr>
<tr class="odd">
<td><p><a href="getchildren-method-ado.md">GetChildren</a></p></td>
<td><p>用于返回一个 <strong>Recordset</strong>，其行表示此 <strong>Record</strong> 所表示的目录中的文件和子目录。</p></td>
</tr>
<tr class="even">
<td><p><a href="loadfromfile-method-ado.md">LoadFromFile</a></p></td>
<td><p>用于将现有文件的内容加载到 <strong>Stream</strong> 对象中。</p></td>
</tr>
<tr class="odd">
<td><p><a href="moverecord-method-ado.md">MoveRecord</a></p></td>
<td><p>用于将文件（或目录及其内容）移动到其他位置。</p></td>
</tr>
<tr class="even">
<td><p><a href="open-method-ado-record.md">Open</a></p></td>
<td><p>用于打开现有的 <strong>Record</strong> 对象，或创建新的文件或目录。</p></td>
</tr>
<tr class="odd">
<td><p><a href="open-method-ado-stream.md">Open</a></p></td>
<td><p>用于打开 <strong>Stream</strong> 对象，以操作二进制数据流或文本数据流。</p></td>
</tr>
<tr class="even">
<td><p><a href="read-method-ado.md">Read</a></p></td>
<td><p>可从二进制 <strong>Stream</strong> 对象读取指定数量的字节。</p></td>
</tr>
<tr class="odd">
<td><p><a href="readtext-method-ado.md">ReadText</a></p></td>
<td><p>可从文本 <strong>Stream</strong> 对象读取指定数量的字符。</p></td>
</tr>
<tr class="even">
<td><p><a href="savetofile-method-ado.md">SaveToFile</a></p></td>
<td><p>可将 <strong>Stream</strong> 的二进制内容保存到文件。</p></td>
</tr>
<tr class="odd">
<td><p><a href="seteos-method-ado.md">SetEOS</a></p></td>
<td><p>用于设置流的结束位置。</p></td>
</tr>
<tr class="even">
<td><p><a href="skipline-method-ado.md">SkipLine</a></p></td>
<td><p>用于在读取文本 <strong>Stream</strong> 对象时跳过一整行。</p></td>
</tr>
<tr class="odd">
<td><p><a href="write-method-ado.md">Write</a></p></td>
<td><p>用于将二进制数据写入 <strong>Stream</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="writetext-method-ado.md">WriteText</a></p></td>
<td><p>用于将指定的文本字符串写入 <strong>Stream</strong> 对象。</p></td>
</tr>
</tbody>
</table>


## <a name="new-and-enhanced-documentation"></a>新文档和增强文档

- **[代码示例主题](ado-code-examples.md)**

  示例已扩展为包含在 microsoft visual c + + 和 microsoft visual j + + 中编写的代码示例。 您可以将这些示例复制并粘贴到自己的编辑器中。

- **[提供程序主题](appendix-a-providers.md)**

  包括一个新的主题，阐述了如何在 [OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md) 中使用 ADO。

- **[用 ADO 编程](appendix-c-programming-with-ado.md)**

  这是一个新的部分，包含在各种编程语言中使用 ADO 的提示和技巧。 它包含 Visual c + + 扩展的现有语法索引, 用于 ado 和 ADO/WFC, 以及特定于使用 microsoft visual basic、microsoft visual basic 脚本编写版、microsoft JScript、microsoft visual c + + 或的开发人员的新信息。Microsoft Visual j + +。

