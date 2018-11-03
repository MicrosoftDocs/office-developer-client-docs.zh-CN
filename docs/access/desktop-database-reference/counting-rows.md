---
title: 对行 （访问桌面数据库引用） 进行计数
TOCTitle: Counting rows
ms:assetid: ff684c5e-7f41-0dae-beea-f5c71f79bd84
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250312(v=office.15)
ms:contentKeyID: 48548963
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 39468086e7c78a89b13b6021c7f07853c487c6e5
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945304"
---
# <a name="counting-rows"></a><span data-ttu-id="fbe07-102">对行进行计数</span><span class="sxs-lookup"><span data-stu-id="fbe07-102">Counting rows</span></span>


<span data-ttu-id="fbe07-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fbe07-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fbe07-p101">**RecordCount** 属性返回一个 **长整型** 值，该值指示 **Recordset** 中的记录数。使用 **RecordCount** 属性可以确定 **Recordset** 对象中的记录数。如果 ADO 无法确定记录数，或者如果提供程序或游标类型不支持 **RecordCount** ，该属性将返回 -1。针对已关闭 **Recordset** 读取 **RecordCount** 属性会产生错误。</span><span class="sxs-lookup"><span data-stu-id="fbe07-p101">The **RecordCount** property returns a **Long** value that indicates the number of records in the **Recordset**. Use the **RecordCount** property to find out how many records are in a **Recordset** object. The property returns -1 when ADO cannot determine the number of records or if the provider or cursor type does not support **RecordCount**. Reading the **RecordCount** property on a closed **Recordset** causes an error.</span></span>

<span data-ttu-id="fbe07-p102">**RecordCount** 属性取决于提供程序功能和游标类型。对于仅向前型游标， **RecordCount** 属性将返回 -1，对于静态或键集游标将返回实际计数，对于动态游标将返回 -1 或实际计数（具体情况取决于数据源）。</span><span class="sxs-lookup"><span data-stu-id="fbe07-p102">The **RecordCount** property depends on the capabilities of the provider and the type of cursor. The **RecordCount** property will return -1 for a forward-only cursor, the actual count for a static or keyset cursor, and either -1 or the actual count for a dynamic cursor, depending on the data source.</span></span>

<span data-ttu-id="fbe07-110">该示例因为打开的仅向前型游标， **Recordset**中[检查数据](chapter-3-examining-data.md)引入将返回-1。</span><span class="sxs-lookup"><span data-stu-id="fbe07-110">The sample **Recordset** introduced in [Examining Data](chapter-3-examining-data.md) would return –1 because a forward-only cursor was opened.</span></span> <span data-ttu-id="fbe07-111">为了使用 **RecordCount** 属性，您需要用更复杂的游标（静态游标或键集游标）来打开 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="fbe07-111">In order to use the **RecordCount** property, you would need to open the **Recordset** with a more sophisticated cursor (static or keyset).</span></span>

<span data-ttu-id="fbe07-p104">在某些情况下，如果不首先从数据源提取所有的记录，提供程序或游标可能无法提供 **RecordCount** 值。若要强制进行此类提取，请在调用 **RecordCount** 之前调用 **Recordset** 的 **MoveLast** 方法。</span><span class="sxs-lookup"><span data-stu-id="fbe07-p104">In certain cases, your provider or cursor might be unable to provide the **RecordCount** value without first fetching all records from the data source. To force this type of fetch, call the **Recordset** **MoveLast** method before calling **RecordCount**.</span></span>

<span data-ttu-id="fbe07-114">如果用以下代码替换调用 **Recordset** **Open** 方法的代码行：</span><span class="sxs-lookup"><span data-stu-id="fbe07-114">If you were to replace the line of code that calls the **Recordset** **Open** method with the following:</span></span>

```vb 
 
oRs.Open sSQL, sCnStr, adOpenStatic, adLockOptimistic, adCmdText 
```

<span data-ttu-id="fbe07-p105">您就能够使用 **RecordCount** 属性，因为静态游标和 [Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md) 支持 **RecordCount** 。例如，以下代码将在调试窗口中显示该命令返回的记录数，假定游标支持 **RecordCount** 属性：</span><span class="sxs-lookup"><span data-stu-id="fbe07-p105">you would be able to use the **RecordCount** property because static cursors with the [Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md) support **RecordCount**. For example, the following code would print out the number of records returned by the command to the debug window, assuming the cursor supports the **RecordCount** property:</span></span>

```vb 
 
Debug.Print oRs.RecordCount ' Output: 4 
```

<span data-ttu-id="fbe07-117">此后，将假设使用这些功能更强大（但比较昂贵）的游标和锁定类型设置。</span><span class="sxs-lookup"><span data-stu-id="fbe07-117">From this point forward, assume that these more capable (but more expensive) cursor and lock type settings are used.</span></span>

