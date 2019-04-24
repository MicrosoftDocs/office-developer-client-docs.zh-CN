---
title: Record 对象 (ADO)
TOCTitle: Record object (ADO)
ms:assetid: 817aaf13-78d4-1134-aa94-997e92077c22
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249557(v=office.15)
ms:contentKeyID: 48545952
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 96ddc7fc1a93543f0eea2b42a3d423ec25a00636
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300901"
---
# <a name="record-object-ado"></a><span data-ttu-id="dd77b-102">Record 对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="dd77b-102">Record object (ADO)</span></span>


<span data-ttu-id="dd77b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="dd77b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="dd77b-104">代表 [Recordset](recordset-object-ado.md) 或数据提供程序中的行，或由半结构化数据提供程序返回的对象，如文件或目录。</span><span class="sxs-lookup"><span data-stu-id="dd77b-104">Represents a row from a [Recordset](recordset-object-ado.md) or the data provider, or an object returned by a semi-structured data provider, such as a file or directory.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd77b-105">注解</span><span class="sxs-lookup"><span data-stu-id="dd77b-105">Remarks</span></span>

<span data-ttu-id="dd77b-p101">**Record** 对象代表一个数据行，与单行 **Recordset** 在概念上有些相同之处。例如，取决于提供程序的功能，当执行仅选择一行的 SQL 查询时，可以直接从提供程序（而不是从单行 **Recordset**）返回 **Record** 对象。也可以直接从 **Recordset** 对象获得 **Record** 对象，还可以直接从提供程序（例如 Microsoft Exchange OLE DB provider）向半结构化数据返回 **Record**。</span><span class="sxs-lookup"><span data-stu-id="dd77b-p101">A **Record** object represents one row of data, and has some conceptual similarities with a one-row **Recordset**. Depending upon the capabilities of your provider, **Record** objects may be returned directly from your provider instead of a one-row **Recordset**, for example when an SQL query that selects only one row is executed. Or, a **Record** object can be obtained directly from a **Recordset** object. Or, a **Record** can be returned directly from a provider to semi-structured data, such as the Microsoft Exchange OLE DB provider.</span></span>

<span data-ttu-id="dd77b-p102">可以通过 **Record** 对象的 [Fields](fields-collection-ado.md) 集合来查看与 **Record** 对象关联的字段。ADO 允许包含对象值的列包括 **Recordset** 、 **SafeArray** 以及 **Record** 对象的 **Fields** 集合中的标量值。</span><span class="sxs-lookup"><span data-stu-id="dd77b-p102">You can view the fields associated with the **Record** object by way of the [Fields](fields-collection-ado.md) collection on the **Record** object. ADO allows object-valued columns including **Recordset**, **SafeArray**, and scalar values in the **Fields** collection of **Record** objects.</span></span>

<span data-ttu-id="dd77b-112">如果 **Record** 对象代表 **Recordset** 中的行，则可以通过 **Source** 属性返回到该初始 [Recordset](source-property-ado-record.md) 。</span><span class="sxs-lookup"><span data-stu-id="dd77b-112">If the **Record** object represents a row in a **Recordset**, then it is possible to return to that original **Recordset** with the [Source](source-property-ado-record.md) property.</span></span>

<span data-ttu-id="dd77b-p103">**Record** 对象还可以供 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md) 等半结构化数据提供程序用来为树状结构命名空间建模。树中的每个节点就是一个具有关联列的 **Record** 对象。这些列可以代表该节点的属性和其他相关信息。 **Record** 对象可以表示树结构中的叶节点和非叶节点。非叶节点包含其他节点作为内容，而叶节点没有这类内容。叶节点通常包含二进制数据流，而非叶节可能还包含与其关联的默认二进制流。 **Record** 对象的属性确定节点的类型。</span><span class="sxs-lookup"><span data-stu-id="dd77b-p103">The **Record** object can also be used by semi-structured data providers such as the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md), to model tree-structured namespaces. Each node in the tree is a **Record** object with associated columns. The columns can represent the attributes of that node and other relevant information. The **Record** object can represent both a leaf node and a non-leaf node in the tree structure. Non-leaf nodes have other nodes as their contents while leaf nodes do not have such contents. Leaf nodes typically contain binary streams of data while non-leaf nodes may also have a default binary stream associated with them. Properties on the **Record** object identify the type of node.</span></span>

<span data-ttu-id="dd77b-p104">**Record** 还表示一种替代方式，用来导航按分级结构组织的数据。可以将 **Record** 对象创建为表示大型树结构中的特定子树的根，也可以打开新 **Record** 对象以表示子节点。</span><span class="sxs-lookup"><span data-stu-id="dd77b-p104">The **Record** object also represents an alternative way for navigating hierarchically organized data. A **Record** object may be created to represent the root of a specific sub-tree in a large tree structure and new **Record** objects may be opened to represent child nodes.</span></span>

<span data-ttu-id="dd77b-p105">可通过绝对 URL 来唯一标识某个资源（例如，文件或目录）。使用绝对 URL 打开 **Record** 对象时，会隐式创建 [Connection](connection-object-ado.md) 对象，并将其设置为该 **Record** 对象。通过 [ActiveConnection](activeconnection-property-ado.md) 属性可以将 **Connection** 对象显式设置为 **Record** 对象。可通过 **Connection** 对象访问的文件和目录指定 **Record** 操作可以在哪些*上下文*中发生。</span><span class="sxs-lookup"><span data-stu-id="dd77b-p105">A resource (for example, a file or directory) can be uniquely identified by an absolute URL. A [Connection](connection-object-ado.md) object is implicitly created and set to the **Record** object when the **Record** is opened with an absolute URL. A **Connection** object may explicitly be set to the **Record** object via the [ActiveConnection](activeconnection-property-ado.md) property. The files and directories accessible via the **Connection** object define the *context* in which **Record** operations may occur.</span></span>

<span data-ttu-id="dd77b-126">**Record** 对象的数据修改和导航方法也接受相对 URL，相对 URL 使用绝对 URL 或 **Connection** 对象上下文作为起始点来定位资源。</span><span class="sxs-lookup"><span data-stu-id="dd77b-126">Data modification and navigation methods on the **Record** object also accept a relative URL, which locates a resource using an absolute URL or the **Connection** object context as a starting point.</span></span>

> [!NOTE]
> <span data-ttu-id="dd77b-127">[!注释] 使用 http 方案的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="dd77b-127">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="dd77b-128">有关详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="dd77b-128">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>



<span data-ttu-id="dd77b-p107">**Connection** 对象与每个 **Record** 对象关联。因此，通过调用 **Connection** 对象事务处理方法，可以使 **Record** 对象操作成为事务处理的一部分。</span><span class="sxs-lookup"><span data-stu-id="dd77b-p107">A **Connection** object is associated with each **Record** object. Therefore, **Record** object operations can be part of a transaction by invoking **Connection** object transaction methods.</span></span>

<span data-ttu-id="dd77b-131">**Record** 对象不支持 ADO 事件，因此不会响应通知。</span><span class="sxs-lookup"><span data-stu-id="dd77b-131">The **Record** object does not support ADO events, and therefore will not respond to notifications.</span></span>

<span data-ttu-id="dd77b-132">使用 **Record** 对象的方法和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="dd77b-132">With the methods and properties of a **Record** object, you can do the following:</span></span>

  - <span data-ttu-id="dd77b-133">使用 [ActiveConnection](activeconnection-property-ado.md) 属性设置或返回关联的 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="dd77b-133">Set or return the associated **Connection** object with the [ActiveConnection](activeconnection-property-ado.md) property.</span></span>

  - <span data-ttu-id="dd77b-134">使用 [Mode](mode-property-ado.md) 属性指示访问权限。</span><span class="sxs-lookup"><span data-stu-id="dd77b-134">Indicate access permissions with the [Mode](mode-property-ado.md) property.</span></span>

  - <span data-ttu-id="dd77b-135">使用 [ParentURL](parenturl-property-ado.md) 属性返回包含 **Record** 所代表的资源的目录的 URL（如果有）。</span><span class="sxs-lookup"><span data-stu-id="dd77b-135">Return the URL of the directory, if any, that contains the resource represented by the **Record** with the [ParentURL](parenturl-property-ado.md) property.</span></span>

  - <span data-ttu-id="dd77b-136">使用 [Source](source-property-ado-record.md) 属性指示派生 **Record** 的绝对 URL、相对 URL 或 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="dd77b-136">Indicate the absolute URL, relative URL, or **Recordset** from which the **Record** is derived with the [Source](source-property-ado-record.md) property.</span></span>

  - <span data-ttu-id="dd77b-137">使用 [State](state-property-ado.md) 属性指示 **Record** 的当前状态。</span><span class="sxs-lookup"><span data-stu-id="dd77b-137">Indicate the current status of the **Record** with the [State](state-property-ado.md) property.</span></span>

  - <span data-ttu-id="dd77b-138">使用 [RecordType](recordtype-property-ado.md) 属性指示 **Record** 的类型，包括*简单*、*集合*或*结构化文档*。</span><span class="sxs-lookup"><span data-stu-id="dd77b-138">Indicate the type of **Record** — *simple*, *collection*, or *structured document* — with the [RecordType](recordtype-property-ado.md) property.</span></span>

  - <span data-ttu-id="dd77b-139">使用 [Cancel](cancel-method-ado.md) 方法中止异步操作的执行。</span><span class="sxs-lookup"><span data-stu-id="dd77b-139">Halt execution of an asynchronous operation with the [Cancel](cancel-method-ado.md) method.</span></span>

  - <span data-ttu-id="dd77b-140">使用 [Close](close-method-ado.md) 方法取消 **Record** 与数据源的关联。</span><span class="sxs-lookup"><span data-stu-id="dd77b-140">Disassociate the **Record** from a data source with the [Close](close-method-ado.md) method.</span></span>

  - <span data-ttu-id="dd77b-141">使用 [CopyRecord](copyrecord-method-ado.md) 方法将 **Record** 所表示的文件或目录复制到其他位置。</span><span class="sxs-lookup"><span data-stu-id="dd77b-141">Copy the file or directory represented by a **Record** to another location with the [CopyRecord](copyrecord-method-ado.md) method.</span></span>

  - <span data-ttu-id="dd77b-142">使用 [DeleteRecord](deleterecord-method-ado.md) 方法删除 **Record** 所表示的文件或目录和子目录。</span><span class="sxs-lookup"><span data-stu-id="dd77b-142">Delete the file, or directory and subdirectories, represented by a **Record** with the [DeleteRecord](deleterecord-method-ado.md) method.</span></span>

  - <span data-ttu-id="dd77b-143">使用 [GetChildren](getchildren-method-ado.md) 方法打开一个 **Recordset**，其中包含代表由 **Record** 所表示的实体的子目录和文件的行。</span><span class="sxs-lookup"><span data-stu-id="dd77b-143">Open a **Recordset** containing rows that represent the subdirectories and files of the entity represented by the **Record** with the [GetChildren](getchildren-method-ado.md) method.</span></span>

  - <span data-ttu-id="dd77b-144">使用 [MoveRecord](moverecord-method-ado.md) 方法将 **Record** 所表示的文件或目录和子目录移动（重命名）到其他位置。</span><span class="sxs-lookup"><span data-stu-id="dd77b-144">Move (rename) the file, or directory and subdirectories, represented by a **Record** to another location with the [MoveRecord](moverecord-method-ado.md) method.</span></span>

  - <span data-ttu-id="dd77b-145">使用 [Open](open-method-ado-record.md) 方法将 **Record** 与现有数据源关联，或者创建新文件或目录。</span><span class="sxs-lookup"><span data-stu-id="dd77b-145">Associate the **Record** with an existing data source, or create a new file or directory with the [Open](open-method-ado-record.md) method.</span></span>

