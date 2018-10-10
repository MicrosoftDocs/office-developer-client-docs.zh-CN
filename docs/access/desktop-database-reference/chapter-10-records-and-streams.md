---
title: 第 10 章：记录和流
TOCTitle: 'Chapter 10: Records and Streams'
ms:assetid: 74862096-2273-3b61-f89c-06554ccf42cd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249477(v=office.15)
ms:contentKeyID: 48545663
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4cdc7bbbaad7242ddbe2c4992395e6c4e0477504
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467146"
---
# <a name="chapter-10-records-and-streams"></a><span data-ttu-id="48115-102">第 10 章：记录和流</span><span class="sxs-lookup"><span data-stu-id="48115-102">Chapter 10: Records and Streams</span></span>


<span data-ttu-id="48115-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="48115-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="48115-p101">ADO 目前提供了 [Recordset](recordset-object-ado.md) 对象作为访问数据源（如关系数据库）中的信息的主要方式。但是，某些提供程序支持 [Record](record-object-ado.md) 和 [Stream](stream-object-ado.md) 对象作为替代或补充对象，使用这些对象可以操作提供程序提供的数据。有关 **Record** 行为的细节，请参阅提供程序的文档。</span><span class="sxs-lookup"><span data-stu-id="48115-p101">ADO currently provides the[Recordset](recordset-object-ado.md) object as the primary means of accessing information in data sources, such as relational databases. However, some providers support the [Record](record-object-ado.md) and [Stream](stream-object-ado.md) objects as alternative or complementary objects with which data from providers can be manipulated. For specifics on **Record** behavior, see your provider's documentation.</span></span>

## <a name="records"></a><span data-ttu-id="48115-107">记录</span><span class="sxs-lookup"><span data-stu-id="48115-107">Records</span></span>

<span data-ttu-id="48115-p102">**Record** 对象本质上是单行的 **Recordset**。但是，与 **Recordsets** 相比，**Records** 的功能有限，并且它们有不同的属性和方法。**Record** 对象中数据的源可以是从提供程序返回一行数据的命令。如果使用 **Record** 对象而不是 **Recordset** 对象从返回一行数据的查询接收结果，则可以避免实例化更复杂的 **Recordset** 对象所需的开销。</span><span class="sxs-lookup"><span data-stu-id="48115-p102">**Record** objects essentially function as one-row **Recordset**s. However, **Records** have limited functionality compared to **Recordsets** and they have different properties and methods.The source for the data in a **Record** object can be a command which returns one row of data from the provider. Using **Record** objects rather than **Recordset** objects to receive the results from a query that returns one row of data eliminates the overhead of instantiating the more complex **Recordset** object.</span></span>

<span data-ttu-id="48115-p103">**Record** 对象可以用于另一个用途，特别是对于除传统关系数据库以外的其他数据源的提供程序，例如 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。很多必须处理的信息不是作为数据库中的表，而是作为电子邮件系统中的邮件和现代文件系统中的文件而存在。 **Record** 和 **Stream** 对象使您能够方便地访问在非关系数据库的数据源中存储的信息。</span><span class="sxs-lookup"><span data-stu-id="48115-p103">**Record** objects can serve another purpose, particularly with providers for data sources other than traditional relational databases, such as the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md). Much of the information that must be processed exists, not as tables in databases, but as messages in electronic mail systems and files in modern file systems. The **Record** and **Stream** objects facilitate access to information stored in sources other than relational databases.</span></span>

<span data-ttu-id="48115-p104">**Record** 对象可以表示和管理数据（例如，文件系统或文件夹中的目录和文件以及电子邮件系统中的邮件）。对于这些用途， **Record** 的源可以是打开的 **Recordset** 的当前行、绝对 URL 或与打开的 [Connection](connection-object-ado.md) 对象结合的相对 URL。</span><span class="sxs-lookup"><span data-stu-id="48115-p104">The **Record** object can represent and manage data such as directories and files in a file system or folders and messages in an e-mail system. For these purposes, the source for the **Record** can be the current row of an open **Recordset**, an absolute URL, or a relative URL in conjunction with an open [Connection](connection-object-ado.md) object.</span></span>

<span data-ttu-id="48115-p105">通常， **Recordset** 可以用来表示层次结构中的容器或父对象（如文件夹或目录）。而 **Record** 可以用来返回有关父容器中一个节点（如文件或文档）的特定信息。用 **Records** 来表示此类信息的主要原因是这些数据源是异构的。这意味着，每个 **Record** 都可能有不同的字段集合和字段数。而包含来自数据库的行的传统 **Recordsets** 是同构的，这意味着每个行都有相同的字段数和字段类型。</span><span class="sxs-lookup"><span data-stu-id="48115-p105">Typically, a **Recordset** can be used to represent a container or parent in a hierarchy such as a folder or directory. A **Record** can be used to return specific information about one node in the parent container, such as a file or document. The primary reason **Records** are used to represent this type of information is that these sources of data are heterogenous. This means that each **Record** may have a different set and number of fields. Traditional **Recordsets** containing rows from a database are homogenous, which means that each row has the same number and type of fields.</span></span>

<span data-ttu-id="48115-121">有关使用 **Record** 对象来处理提供程序（如 Internet Publishing Provider）所提供的这类异构数据的详细信息，请参阅 [使用 ADO for Internet Publishing](using-ado-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="48115-121">For more information about using the **Record** object for processing this heterogeneous data from providers such as the Internet Publishing Provider, see [Using ADO for Internet Publishing](using-ado-for-internet-publishing.md).</span></span>

## <a name="streams"></a><span data-ttu-id="48115-122">流</span><span class="sxs-lookup"><span data-stu-id="48115-122">Streams</span></span>

<span data-ttu-id="48115-p106">**Stream** 对象提供用于读取、写入和管理字节流的方法。此字节流可能是文本或二进制，并且大小只受系统资源限制。通常，ADO **Stream** 对象用于以下用途：</span><span class="sxs-lookup"><span data-stu-id="48115-p106">The **Stream** object provides the means to read, write, and manage a stream of bytes. This byte stream may be text or binary and is limited in size only by system resources. Typically, ADO **Stream** objects are used for the following purposes:</span></span>

  - <span data-ttu-id="48115-p107">若要包含由文件或邮件组成的文本或字节，通常需要与 Microsoft OLE DB Provider for Internet Publishing 等提供程序一起使用。有关 **Stream** 对象这种用法的详细信息，请参阅 [使用 ADO for Internet Publishing](using-ado-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="48115-p107">To contain the text or bytes that comprise a file or message, typically used with providers such as the Microsoft OLE DB Provider for Internet Publishing. For more information about this use of **Stream** objects, see [Using ADO for Internet Publishing](using-ado-for-internet-publishing.md).</span></span>

<span data-ttu-id="48115-128">可以对如下项打开 **Stream** 对象：</span><span class="sxs-lookup"><span data-stu-id="48115-128">A **Stream** object can be opened on:</span></span>

  - <span data-ttu-id="48115-129">用 URL 指定的简单文件。</span><span class="sxs-lookup"><span data-stu-id="48115-129">A simple file specified with a URL.</span></span>

  - <span data-ttu-id="48115-130">包含 **Stream** 对象的 **Record** 或 **Recordset** 的字段。</span><span class="sxs-lookup"><span data-stu-id="48115-130">A field of a **Record** or **Recordset** containing a **Stream** object.</span></span>

  - <span data-ttu-id="48115-131">表示目录或复合文件的 **Record** 或 **Recordset** 对象的默认流。</span><span class="sxs-lookup"><span data-stu-id="48115-131">The default stream of a **Record** or **Recordset** object representing a directory or compound file.</span></span>

  - <span data-ttu-id="48115-132">包含简单文件的 URL 的资源字段。</span><span class="sxs-lookup"><span data-stu-id="48115-132">A resource field containing the URL of a simple file.</span></span>

  - <span data-ttu-id="48115-p108">根本没有特定数据源。在这种情况下，将在内存中打开 **Stream** 对象。可以将数据写入其中，然后保存到另一个 **Stream** 或文件中。</span><span class="sxs-lookup"><span data-stu-id="48115-p108">No particular source at all. In this case, a **Stream** object is opened in memory. Data can be written to it and then saved in another **Stream** or file.</span></span>

  - <span data-ttu-id="48115-136">**Recordset** 中的 BLOB 字段。</span><span class="sxs-lookup"><span data-stu-id="48115-136">A BLOB field in a **Recordset**.</span></span>

