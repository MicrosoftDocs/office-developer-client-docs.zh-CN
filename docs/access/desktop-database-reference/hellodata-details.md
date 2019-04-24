---
title: HelloData 详细信息 (Access desktop database reference)
TOCTitle: HelloData details
ms:assetid: db51e15c-1b5b-c64a-2f84-34dd0e78c6cf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250105(v=office.15)
ms:contentKeyID: 48548103
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 78b04b74d4e2b8d9c215235d6e7ccebed4fa2ef2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291997"
---
# <a name="hellodata-details"></a>HelloData 详细信息


**适用于**：Access 2013、Office 2013

HelloData 应用程序将一步一步地执行典型的 ADO 应用程序的基本操作，即获取、检查、编辑和更新数据。启动该应用程序时，单击第一个按钮“获取数据” ****，从而运行 GetData() 子例程。

## <a name="getdata"></a>GetData

"sConnStr" 将有效的连接字符串放置到模块级变量 *(\_m*) 中。 有关连接字符串的详细信息，请参阅[创建连接字符串](creating-the-connection-string.md)。

使用 Visual Basic **OnError** 语句指定错误处理程序。有关 ADO 中错误处理的详细信息，请参阅[第 6 章：错误处理](chapter-6-error-handling.md)。由于 HelloData 示例创建了一个断开连接的 *Recordset*，因此，将创建一个新的 **Connection** 对象并将 **CursorLocation** 属性设置为 **adUseClient**。这意味着从数据源提取数据后，与数据源的物理连接将被断开，但仍然可以使用 **Recordset** 对象中在本地缓存的数据。

打开连接后，将 SQL 字符串赋给变量 (sSQL)。 然后实例化新的**Recordset**对象 m\_oRecordset1。 在下一行代码中, 通过现有**连接**打开**Recordset** , 并传入。 在下一行代码中, 通过现有**连接**打开**recordset** , 并将 sSQL 作为**Recordset**的源传入。 将最后一个参数中的 **adCmdText** 传递给 **Recordset** 的 **Open** 方法，可以帮助 ADO 确定已作为 **Recordset** 的源传递的 SQL 字符串是命令的文本定义。 此行还设置了与 **Recordset** 关联的 **LockType** 和 **CursorType** 。

下一行代码将 **MarshalOptions** 属性设置为等于 **adMarshalModifiedOnly** 。 **MarshalOptions**指示应将哪些记录封送到中间层 (或 web 服务器)。 有关封送的详细信息，请参阅 COM 文档。 将**adMarshalModifiedOnly**与客户端游标一起使用时 ([CursorLocation](cursorlocation-property-ado.md) = **adUseClient**) 时, 只有在客户端上修改的记录写回到中间层。 将 **MarshalOptions** 设置为 **adMarshalModifiedOnly** 可以提高性能，因为封送的行较少。

下一步，将 **ActiveConnection** 属性设置为等于 **Nothing** ，以断开 **Recordset** 的连接。有关详细信息，请参阅第 5 章"更新和保存数据"中的 [断开和重新连接记录集](disconnecting-and-reconnecting-the-recordset.md)一节。

关闭数据源的连接并销毁现有的 **Connection** 对象，从而释放其耗用的资源。

最后一步是在表单上将 Microsoft DataBound Grid 控件的 **Recordset** 设置为 **DataSource** ，这样，就可以轻松地在表单上显示 **Recordset** 中的数据。

单击第二个按钮“检查数据”****，以便运行 ExamineData 子例程。

## <a name="examinedata"></a>ExamineData

ExamineData 使用 **Recordset** 对象的各种方法和属性来显示有关 **Recordset** 中数据的信息。该子例程通过 **RecordCount** 属性来报告记录数；在 **Recordset** 中循环并在表单的显示文本框中输出 **AbsolutePosition** 属性的值。此外，在该循环中，将第三条记录的 **Bookmark** 属性的值置于 Variant 变量 *vBookmark* 中供以后使用。

该例程使用以前存储的书签变量进行导航，直接回到第三条记录；调用 WalkFields 子例程，以便在  **Recordset** 的 **Fields** 集合中循环，并显示有关该集合中每个 **Field** 的详细信息。

最后，ExamineData 使用 **Recordset** 的 **Filter** 属性进行筛选，以便仅选取 CategoryId 等于 2 的那些记录。在表单的显示网格中，可以立即看到应用此筛选的结果。

有关 ExamineData 子例程中显示的功能的详细信息，请参阅[第 3 章：检查数据](chapter-3-examining-data.md)。

下一步，单击第三个按钮“编辑数据”****，以便运行 EditData 子例程。

## <a name="editdata"></a>EditData

When the code enters the EditData subroutine, the **Recordset** is still filtered on CategoryId equal to 2, so only those items that meet the filter criteria are visible. It first loops through the **Recordset** and increases the price of each visible item in the **Recordset** by 10 percent. The value of the **Price** field is changed by setting the **Value** property for that field equal to a new, valid amount.

请注意， **Recordset** 将与数据源断开连接。在 EditData 中所做的更改只对数据的本地缓存副本有效。有关详细信息，请参阅 [第 4 章：编辑数据](chapter-4-editing-data.md)。

The changes will not be made on the data source until you click the fourth button, **Update Data**. This will run the UpdateData subroutine.

## <a name="updatedata"></a>UpdateData

UpdateData 首先删除已应用于 **Recordset** 的筛选器。 该代码将删除和重置为该窗体上的 Microsoft 绑定的 DataGrid 的**数据源**, 以便在网格中显示未筛选的**Recordset** 。

然后，该代码将查看是否可以使用带有 **adMovePrevious** 参数的 **Supports** 方法在 **Recordset** 中向后移动。

该例程将使用 **MoveFirst** 方法移至第一条记录，并使用 **Field** 对象的 **OriginalValue** 和 **Value** 属性显示相应字段的原始值和当前值。这些属性以及 **UnderlyingValue** 属性（此处未使用）在 [第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)中论述。

下一步，将创建一个新的 **Connection** 对象并使用该对象重新建立与数据源的连接。通过将新的 **Connection** 设置为 **Recordset** 的 **ActiveConnection** ，可以将 **Recordset** 重新连接到数据源。为将更新发送到服务器，该代码将对 **Recordset** 调用 **UpdateBatch** 。

如果批更新成功, 则将模块级标志变量 () 设置为 True。 这将提醒你稍后清除对数据库所做的所有更改。

最后，该代码将移回 **Recordset** 中的第一条记录并显示原始值和当前值。调用 **UpdateBatch** 后，这些值是相同的。

有关更新数据的详细信息，包括在断开 **Recordset** 连接的情况下服务器上的数据发生更改时要执行的操作，请参阅 [第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)。

## <a name="formunload"></a>窗\_体卸载

由于以下\_几个原因, 窗体 Unload 子例程非常重要。 首先, 由于这是一个示例应用程序,\_因此, 窗体卸载会清理在应用程序退出之前对数据库所做的更改。 其次, 该代码演示如何使用**Execute**方法直接从打开的**Connection**对象执行命令。 最后, 它显示了对数据源执行非行返回查询 (更新查询) 的示例。

