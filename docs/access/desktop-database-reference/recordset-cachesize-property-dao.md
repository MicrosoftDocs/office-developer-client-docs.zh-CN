---
title: Recordset.CacheSize 属性 (DAO)
TOCTitle: CacheSize Property
ms:assetid: 8632f5fb-6e5d-5a3e-1bd7-81e1270e9531
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196807(v=office.15)
ms:contentKeyID: 48546079
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e3a337226d0b710394469649c0846d92b079b2ed
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924825"
---
# <a name="recordsetcachesize-property-dao"></a><span data-ttu-id="bc28c-102">Recordset.CacheSize 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bc28c-102">Recordset.CacheSize property (DAO)</span></span>


<span data-ttu-id="bc28c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bc28c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bc28c-p101">设置或返回从 ODBC 数据源中检索的、需要本地缓存的记录数。可读/写 **Long** 类型。</span><span class="sxs-lookup"><span data-stu-id="bc28c-p101">Sets or returns the number of records retrieved from an ODBC data source that will be cached locally. Read/write **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="bc28c-106">语法</span><span class="sxs-lookup"><span data-stu-id="bc28c-106">Syntax</span></span>

<span data-ttu-id="bc28c-107">*表达式*。CacheSize</span><span class="sxs-lookup"><span data-stu-id="bc28c-107">*expression* .CacheSize</span></span>

<span data-ttu-id="bc28c-108">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bc28c-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc28c-109">注解</span><span class="sxs-lookup"><span data-stu-id="bc28c-109">Remarks</span></span>

<span data-ttu-id="bc28c-p102">**CacheSize** 属性值必须介于 5 和 1200 之间，但不得超过可用内存允许的大小。典型值为 100。设置为 0 时将关闭缓存。</span><span class="sxs-lookup"><span data-stu-id="bc28c-p102">The value of the **CacheSize** property must be between 5 and 1200, but not greater than available memory will allow. A typical value is 100. A setting of 0 turns off caching.</span></span>

<span data-ttu-id="bc28c-p103">如果使用 **Recordset** 对象从远程服务器检索数据，数据缓存可以提高性能。缓存是内存中的一个位置，用于保存最近从服务器检索的数据；如果用户在应用程序正在运行时再次请求数据，缓存将发挥作用。用户请求数据时，Microsoft Access 数据库引擎将首先检查所请求数据的缓存，而不是从服务器检索此数据（从服务器检索会花费较长时间）。缓存只保存来自 ODBC 数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="bc28c-p103">Data caching improves performance if you use **Recordset** objects to retrieve data from a remote server. A cache is a space in local memory that holds the data most recently retrieved from the server; this is useful if users request the data again while the application is running. When users request data, the Microsoft Access database engine checks the cache for the requested data first rather than retrieving it from the server, which takes more time. The cache only saves data that comes from an ODBC data source.</span></span>

<span data-ttu-id="bc28c-p104">任何 Microsoft Access 数据库引擎连接的 ODBC 数据源（例如链接表）都可以有一个本地缓存。若要创建缓存，请从远程数据源打开 **Recordset** 对象，设置 **CacheSize** 和 **[CacheStart](recordset-cachestart-property-dao.md)** 属性，然后使用 **[FillCache](recordset-fillcache-method-dao.md)** 方法，或者使用 **Move** 方法遍历记录。</span><span class="sxs-lookup"><span data-stu-id="bc28c-p104">Any Microsoft Access database engine-connected ODBC data source, such as a linked table, can have a local cache. To create the cache, open a **Recordset** object from the remote data source, set the **CacheSize** and **[CacheStart](recordset-cachestart-property-dao.md)** properties, and then use the **[FillCache](recordset-fillcache-method-dao.md)** method, or step through the records by using the **Move** methods.</span></span>

<span data-ttu-id="bc28c-p105">可以将 **CacheSize** 属性设置基于应用程序可同时处理的记录数。例如，如果将 **Recordset** 对象用作要在屏幕上显示的数据的源，可以将其 **CacheSize** 属性设置为 20，以同时显示 20 条记录。</span><span class="sxs-lookup"><span data-stu-id="bc28c-p105">You can base the **CacheSize** property setting on the number of records your application can handle at one time. For example, if you're using a **Recordset** object as the source of the data to be displayed on screen, you could set its **CacheSize** property to 20 to display 20 records at one time.</span></span>

<span data-ttu-id="bc28c-121">Microsoft Access 数据库引擎从缓存中请求位于缓存范围内的记录，同时从服务器中请求位于缓存范围以外的记录。</span><span class="sxs-lookup"><span data-stu-id="bc28c-121">The Microsoft Access database engine requests records within the cache range from the cache, and it requests records outside the cache range from the server.</span></span>

<span data-ttu-id="bc28c-122">从缓存中检索的记录并不能反映其他用户对源数据所做的并发更改。</span><span class="sxs-lookup"><span data-stu-id="bc28c-122">Records retrieved from the cache don't reflect concurrent changes that other users made to the source data.</span></span>

<span data-ttu-id="bc28c-123">若要强制更新所有缓存的数据，请将 **Recordset** 对象的 **CacheSize** 属性设置为 0，再将它重置为最初请求的缓存的大小，然后使用 **FillCache** 方法。</span><span class="sxs-lookup"><span data-stu-id="bc28c-123">To force an update of all the cached data, set the **CacheSize** property of the **Recordset** object to 0, re-set it to the size of the cache you originally requested, and then use the **FillCache** method.</span></span>

## <a name="example"></a><span data-ttu-id="bc28c-124">示例</span><span class="sxs-lookup"><span data-stu-id="bc28c-124">Example</span></span>

<span data-ttu-id="bc28c-p106">以下示例使用 **CreateTableDef** 和 **FillCache** 方法以及 **CacheSize**、 **CacheStart** 和 **SourceTableName** 属性两次枚举链接表中的记录，再使用存有 50 条记录的缓存两次枚举这些记录，然后通过链接表显示未缓存运行和缓存运行的性能统计。</span><span class="sxs-lookup"><span data-stu-id="bc28c-p106">This example uses the **CreateTableDef** and **FillCache** methods and the **CacheSize**, **CacheStart** and **SourceTableName** properties to enumerate the records in a linked table twice. Then it enumerates the records twice with a 50-record cache. The example then displays the performance statistics for the uncached and cached runs through the linked table.</span></span>

```vb
    Sub ClientServerX3() 
     
     Dim dbsCurrent As Database 
     Dim tdfRoyalties As TableDef 
     Dim rstRemote As Recordset 
     Dim sngStart As Single 
     Dim sngEnd As Single 
     Dim sngNoCache As Single 
     Dim sngCache As Single 
     Dim intLoop As Integer 
     Dim strTemp As String 
     Dim intRecords As Integer 
     
     ' Open a database to which a linked table can be 
     ' appended. 
     Set dbsCurrent = OpenDatabase("DB1.mdb") 
     
     ' Create a linked table that connects to a Microsoft SQL 
     ' Server database. 
     Set tdfRoyalties = _ 
     dbsCurrent.CreateTableDef("Royalties") 
     ' Note: The DSN referenced below must be set to 
     ' use Microsoft Windows NT Authentication Mode to 
     ' authorize user access to the Microsoft SQL Server. 
     tdfRoyalties.Connect = _ 
     "ODBC;DATABASE=pubs;DSN=Publishers" 
     tdfRoyalties.SourceTableName = "roysched" 
     dbsCurrent.TableDefs.Append tdfRoyalties 
     Set rstRemote = _ 
     dbsCurrent.OpenRecordset("Royalties") 
     
     With rstRemote 
     ' Enumerate the Recordset object twice and record 
     ' the elapsed time. 
     sngStart = Timer 
     
     For intLoop = 1 To 2 
     .MoveFirst 
     Do While Not .EOF 
     ' Execute a simple operation for the 
     ' performance test. 
     strTemp = !title_id 
     .MoveNext 
     Loop 
     Next intLoop 
     
     sngEnd = Timer 
     sngNoCache = sngEnd - sngStart 
     
     ' Cache the first 50 records. 
     .MoveFirst 
     .CacheSize = 50 
     .FillCache 
     sngStart = Timer 
     
     ' Enumerate the Recordset object twice and record 
     ' the elapsed time. 
     For intLoop = 1 To 2 
     intRecords = 0 
     .MoveFirst 
     Do While Not .EOF 
     ' Execute a simple operation for the 
     ' performance test. 
     strTemp = !title_id 
     ' Count the records. If the end of the 
     ' cache is reached, reset the cache to the 
     ' next 50 records. 
     intRecords = intRecords + 1 
     .MoveNext 
     If intRecords Mod 50 = 0 Then 
     .CacheStart = .Bookmark 
     .FillCache 
     End If 
     Loop 
     Next intLoop 
     
     sngEnd = Timer 
     sngCache = sngEnd - sngStart 
     
     ' Display performance results. 
     MsgBox "Caching Performance Results:" & vbCr & _ 
     " No cache: " & Format(sngNoCache, _ 
     "##0.000") & " seconds" & vbCr & _ 
     " 50-record cache: " & Format(sngCache, _ 
     "##0.000") & " seconds" 
     .Close 
     End With 
     
     ' Delete linked table because this is a demonstration. 
     dbsCurrent.TableDefs.Delete tdfRoyalties.Name 
     dbsCurrent.Close 
     
    End Sub
```
