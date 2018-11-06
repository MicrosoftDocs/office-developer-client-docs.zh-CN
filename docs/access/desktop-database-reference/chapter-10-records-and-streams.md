---
title: 第 10 章： 记录和流
TOCTitle: 'Chapter 10: Records and streams'
ms:assetid: 74862096-2273-3b61-f89c-06554ccf42cd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249477(v=office.15)
ms:contentKeyID: 48545663
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 96350229bce2ecc25ff035f2e5949f080f0fa10f
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997726"
---
# <a name="chapter-10-records-and-streams"></a>第 10 章： 记录和流

**适用于**： Access 2013、 Office 2013

ADO 目前提供了 [Recordset](recordset-object-ado.md) 对象作为访问数据源（如关系数据库）中的信息的主要方式。但是，某些提供程序支持 [Record](record-object-ado.md) 和 [Stream](stream-object-ado.md) 对象作为替代或补充对象，使用这些对象可以操作提供程序提供的数据。有关 **Record** 行为的细节，请参阅提供程序的文档。

## <a name="records"></a>记录

**Record** 对象本质上是单行的 **Recordset**。但是，与 **Recordsets** 相比，**Records** 的功能有限，并且它们有不同的属性和方法。**Record** 对象中数据的源可以是从提供程序返回一行数据的命令。如果使用 **Record** 对象而不是 **Recordset** 对象从返回一行数据的查询接收结果，则可以避免实例化更复杂的 **Recordset** 对象所需的开销。

**Record** 对象可以用于另一个用途，特别是对于除传统关系数据库以外的其他数据源的提供程序，例如 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。很多必须处理的信息不是作为数据库中的表，而是作为电子邮件系统中的邮件和现代文件系统中的文件而存在。 **Record** 和 **Stream** 对象使您能够方便地访问在非关系数据库的数据源中存储的信息。

**Record**对象可以表示和管理电子邮件系统中文件系统或文件夹和消息中的数据，例如目录和文件。 对于这些用途， **Record** 的源可以是打开的 **Recordset** 的当前行、绝对 URL 或与打开的 [Connection](connection-object-ado.md) 对象结合的相对 URL。

通常， **Recordset** 可以用来表示层次结构中的容器或父对象（如文件夹或目录）。而 **Record** 可以用来返回有关父容器中一个节点（如文件或文档）的特定信息。用 **Records** 来表示此类信息的主要原因是这些数据源是异构的。这意味着，每个 **Record** 都可能有不同的字段集合和字段数。而包含来自数据库的行的传统 **Recordsets** 是同构的，这意味着每个行都有相同的字段数和字段类型。

有关使用 **Record** 对象来处理提供程序（如 Internet Publishing Provider）所提供的这类异构数据的详细信息，请参阅 [使用 ADO for Internet Publishing](using-ado-for-internet-publishing.md)。

## <a name="streams"></a>流

**Stream** 对象提供用于读取、写入和管理字节流的方法。此字节流可能是文本或二进制，并且大小只受系统资源限制。通常，ADO **Stream** 对象用于以下用途：

- 若要包含由文件或邮件组成的文本或字节，通常需要与 Microsoft OLE DB Provider for Internet Publishing 等提供程序一起使用。有关 **Stream** 对象这种用法的详细信息，请参阅 [使用 ADO for Internet Publishing](using-ado-for-internet-publishing.md)。

可以对如下项打开 **Stream** 对象：

- 用 URL 指定的简单文件。

- 包含 **Stream** 对象的 **Record** 或 **Recordset** 的字段。

- 表示目录或复合文件的 **Record** 或 **Recordset** 对象的默认流。

- 包含简单文件的 URL 的资源字段。

- 根本没有特定数据源。在这种情况下，将在内存中打开 **Stream** 对象。可以将数据写入其中，然后保存到另一个 **Stream** 或文件中。

- **Recordset** 中的 BLOB 字段。

本章包含以下主题：

- [流和持久化](streams-and-persistence.md)
- [记录和提供程序提供的字段](records-and-provider-supplied-fields.md)
- [绝对和相对 Url](absolute-and-relative-urls.md)
- [使用 ADO for Internet publishing (ADO)](using-ado-for-internet-publishing.md)