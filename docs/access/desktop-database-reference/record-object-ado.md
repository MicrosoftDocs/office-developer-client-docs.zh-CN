---
title: Record 对象 (ADO)
TOCTitle: Record Object (ADO)
ms:assetid: 817aaf13-78d4-1134-aa94-997e92077c22
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249557(v=office.15)
ms:contentKeyID: 48545952
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 806b2292b12bededd299a0ef628601589afe0ce9
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603138"
---
# <a name="record-object-ado"></a>Record 对象 (ADO)


**适用于**： Access 2013 |Office 2013

代表 [Recordset](recordset-object-ado.md) 或数据提供程序中的行，或由半结构化数据提供程序返回的对象，如文件或目录。

## <a name="remarks"></a>说明

**Record** 对象代表一个数据行，与单行 **Recordset** 在概念上有些相同之处。例如，取决于提供程序的功能，当执行仅选择一行的 SQL 查询时，可以直接从提供程序（而不是从单行 **Recordset** ）返回 **Record** 对象。也可以直接从 **Recordset** 对象获得 **Record** 对象，还可以直接从提供程序（例如 Microsoft Exchange OLE DB provider）向半结构化数据返回 **Record** 。

可以通过 **Record** 对象的 [Fields](fields-collection-ado.md) 集合来查看与 **Record** 对象关联的字段。ADO 允许包含对象值的列包括 **Recordset** 、 **SafeArray** 以及 **Record** 对象的 **Fields** 集合中的标量值。

如果 **Record** 对象代表 **Recordset** 中的行，则可以通过 **Source** 属性返回到该初始 [Recordset](source-property-ado-record.md) 。

**Record** 对象还可以供 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md) 等半结构化数据提供程序用来为树状结构命名空间建模。树中的每个节点就是一个具有关联列的 **Record** 对象。这些列可以代表该节点的属性和其他相关信息。 **Record** 对象可以表示树结构中的叶节点和非叶节点。非叶节点包含其他节点作为内容，而叶节点没有这类内容。叶节点通常包含二进制数据流，而非叶节可能还包含与其关联的默认二进制流。 **Record** 对象的属性确定节点的类型。

**Record** 还表示一种替代方式，用来导航按分级结构组织的数据。可以将 **Record** 对象创建为表示大型树结构中的特定子树的根，也可以打开新 **Record** 对象以表示子节点。

可通过绝对 URL 来唯一标识某个资源（例如，文件或目录）。 使用绝对 URL 打开 [Record](connection-object-ado.md) 对象时，会隐式创建 **Connection** 对象，并将其设置为该 **Record** 对象。 通过 **ActiveConnection** 属性可以将 **Connection** 对象显式设置为 [Record](activeconnection-property-ado.md) 对象。 文件和目录的**Connection**对象通过访问定义**记录**操作可能会发生的*上下文*。

**Record** 对象的数据修改和导航方法也接受相对 URL，相对 URL 使用绝对 URL 或 **Connection** 对象上下文作为起始点来定位资源。

<<<<<<< 标头

> [!NOTE]
> <P>[!注释] 使用 HTTP 架构的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对 URL 和相对 URL</A>。</P>
=======
> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。
>>>>>>> master



**Connection** 对象与每个 **Record** 对象关联。因此，通过调用 **Connection** 对象事务处理方法，可以使 **Record** 对象操作成为事务处理的一部分。

**Record** 对象不支持 ADO 事件，因此不会响应通知。

使用 **Record** 对象的方法和属性，可以执行下列操作：

  - 使用 **ActiveConnection** 属性设置或返回关联的 [Connection](activeconnection-property-ado.md) 对象。

  - 使用 [Mode](mode-property-ado.md) 属性指示访问权限。

  - 使用 **ParentURL** 属性返回包含 [Record](parenturl-property-ado.md) 所代表的资源的目录的 URL（如果有）。

  - 使用 **Source** 属性指示派生 **Record** 的绝对 URL、相对 URL 或 [Recordset](source-property-ado-record.md) 。

  - 使用 **State** 属性指示 [Record](state-property-ado.md) 的当前状态。

  - 使用 [RecordType](recordtype-property-ado.md) 属性指示 **Record** 的类型，包括*简单*、*集合*或*结构化文档*。

  - 使用 [Cancel](cancel-method-ado.md) 方法中止异步操作的执行。

  - 使用 **Close** 方法取消 [Record](close-method-ado.md) 与数据源的关联。

  - 使用 **CopyRecord** 方法将 [Record](copyrecord-method-ado.md) 所表示的文件或目录复制到其他位置。

  - 使用 **DeleteRecord** 方法删除 [Record](deleterecord-method-ado.md) 所表示的文件或目录和子目录。

  - 使用 **GetChildren** 方法打开一个 **Recordset** ，其中包含代表由 [Record](getchildren-method-ado.md) 所表示的实体的子目录和文件的行。

  - 使用 **MoveRecord** 方法将 [Record](moverecord-method-ado.md) 所表示的文件或目录和子目录移动（重命名）到其他位置。

  - 使用 **Open** 方法将 [Record](open-method-ado-record.md) 与现有数据源关联，或者创建新文件或目录。

