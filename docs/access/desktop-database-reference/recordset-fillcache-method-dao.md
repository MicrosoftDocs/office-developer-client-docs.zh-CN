---
title: Recordset.FillCache 方法 (DAO)
TOCTitle: FillCache Method
ms:assetid: d171b939-b904-c6bd-6217-68bc2814e282
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834751(v=office.15)
ms:contentKeyID: 48547861
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7fc8843e2d36179ec8a0168b0c44c6cdf3e866c4
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998495"
---
# <a name="recordsetfillcache-method-dao"></a><span data-ttu-id="e3618-102">Recordset.FillCache 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e3618-102">Recordset.FillCache method (DAO)</span></span>

<span data-ttu-id="e3618-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e3618-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e3618-104">为某个 **Recordset** 对象填充所有或一部分本地缓存，该对象包含来自 Microsoft Access 数据库引擎连接的 ODBC 数据源中的数据（仅适用于 Microsoft Access 数据库引擎连接的 ODBC 数据库）。</span><span class="sxs-lookup"><span data-stu-id="e3618-104">Fills all or a part of a local cache for a **Recordset** object that contains data from a Microsoft Access database engine-connected ODBC data source (Microsoft Access database engine-connected ODBC databases only).</span></span>

## <a name="syntax"></a><span data-ttu-id="e3618-105">语法</span><span class="sxs-lookup"><span data-stu-id="e3618-105">Syntax</span></span>

<span data-ttu-id="e3618-106">*表达式*。FillCache （***行***、 ***StartBookmark***）</span><span class="sxs-lookup"><span data-stu-id="e3618-106">*expression* .FillCache(***Rows***, ***StartBookmark***)</span></span>

<span data-ttu-id="e3618-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e3618-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="e3618-108">参数</span><span class="sxs-lookup"><span data-stu-id="e3618-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e3618-109">名称</span><span class="sxs-lookup"><span data-stu-id="e3618-109">Name</span></span></p></th>
<th><p><span data-ttu-id="e3618-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="e3618-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="e3618-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="e3618-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="e3618-112">说明</span><span class="sxs-lookup"><span data-stu-id="e3618-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3618-113"><em>Rows</em></span><span class="sxs-lookup"><span data-stu-id="e3618-113"><em>Rows</em></span></span></p></td>
<td><p><span data-ttu-id="e3618-114">可选</span><span class="sxs-lookup"><span data-stu-id="e3618-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="e3618-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="e3618-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="e3618-p101">一个 <strong>Variant</strong>（<strong>Integer</strong> 子类型），用于指定要存储在缓存中的行数。如果省略此参数，值将由 <strong><a href="recordset-cachesize-property-dao.md">CacheSize</a></strong> 属性设置确定。</span><span class="sxs-lookup"><span data-stu-id="e3618-p101">A <strong>Variant</strong> (<strong>Integer</strong> subtype) that specifies the number of rows to store in the cache. If you omit this argument, the value is determined by the <strong><a href="recordset-cachesize-property-dao.md">CacheSize</a></strong> property setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3618-118"><em>StartBookmark</em></span><span class="sxs-lookup"><span data-stu-id="e3618-118"><em>StartBookmark</em></span></span></p></td>
<td><p><span data-ttu-id="e3618-119">可选</span><span class="sxs-lookup"><span data-stu-id="e3618-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="e3618-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="e3618-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="e3618-p102">一个 <strong>Variant</strong>（<strong>String</strong> 子类型），用于指定书签。将从此书签指示的记录开始填充缓存。如果省略此参数，将从 <strong><a href="recordset-cachestart-property-dao.md">CacheStart</a></strong> 属性指示的记录开始填充缓存。</span><span class="sxs-lookup"><span data-stu-id="e3618-p102">A <strong>Variant</strong> (<strong>String</strong> subtype) that specifies a bookmark. The cache is filled starting from the record indicated by this bookmark. If you omit this argument, the cache is filled starting from the record indicated by the <strong><a href="recordset-cachestart-property-dao.md">CacheStart</a></strong> property.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="e3618-124">注解</span><span class="sxs-lookup"><span data-stu-id="e3618-124">Remarks</span></span>

<span data-ttu-id="e3618-p103">缓存可以改善从远程服务器检索数据的应用程序的性能。缓存是指本地内存中用于保存最近从服务器检索的数据的空间；这假定在应用程序运行时，可能需要再次请求此数据。用户请求数据时，Microsoft Access 数据库引擎将首先检查数据的缓存，而不是从服务器检索此数据（从服务器检索会花费较长时间）。缓存不保存来自 ODBC 数据源以外的数据。</span><span class="sxs-lookup"><span data-stu-id="e3618-p103">Caching improves the performance of an application that retrieves data from a remote server. A cache is space in local memory that holds the data most recently retrieved from the server; this assumes that the data will probably be requested again while the application is running. When a user requests data, the Microsoft Access database engine checks the cache for the data first rather than retrieving it from the server, which takes more time. The cache doesn't save data that doesn't come from an ODBC data source.</span></span>

<span data-ttu-id="e3618-p104">可以在任何时候使用 **FillCache** 方法显式填充缓存，而不必等待检索记录后使用记录填充缓存。这是填充缓存的较快方式，因为 **FillCache** 一次可检索多条记录，而不是一次检索一条。例如，在查看每一满屏记录时，应用程序将使用 **FillCache** 检索要查看的下一满屏记录。</span><span class="sxs-lookup"><span data-stu-id="e3618-p104">Rather than waiting for the cache to be filled with records as they are retrieved, you can use the **FillCache** method to explicitly fill the cache at any time. This is a faster way to fill the cache because **FillCache** retrieves several records at once instead of one at a time. For example, while you view each screenful of records, your application uses **FillCache** to retrieve the next screenful of records for viewing.</span></span>

<span data-ttu-id="e3618-p105">使用 **Recordset** 对象访问的、Microsoft Access 数据库引擎连接的任何 ODBC 数据源都可能具有本地缓存。若要创建此缓存，请打开远程数据源中的某个 **Recordset** 对象，然后设置 **Recordset** 的 **CacheSize** 和 **CacheStart** 属性。</span><span class="sxs-lookup"><span data-stu-id="e3618-p105">Any Microsoft Access database engine-connected ODBC data source that you access with **Recordset** objects can have a local cache. To create the cache, open a **Recordset** object from the remote data source, and then set the **CacheSize** and **CacheStart** properties of the **Recordset**.</span></span>

<span data-ttu-id="e3618-134">如果行和 startbookmark 创建范围的记录的部分或完全由**CacheSize**和**CacheStart**属性所指定记录的范围之外，则会忽略此范围之外的记录集的部分，并将不会加载到缓存中。</span><span class="sxs-lookup"><span data-stu-id="e3618-134">If rows and startbookmark create a range of records that is partially or entirely outside the range of records specified by the **CacheSize** and **CacheStart** properties, the portion of the recordset outside this range is ignored and will not be loaded into the cache.</span></span>

<span data-ttu-id="e3618-135">如果 **FillCache** 请求的记录数多于远程数据源中剩余记录的数目，Microsoft Access 数据库引擎只检索剩余的记录，并且不发生错误。</span><span class="sxs-lookup"><span data-stu-id="e3618-135">If **FillCache** requests more records than the number remaining in the remote data source, the Microsoft Access database engine retrieves only the remaining records, and no error occurs.</span></span>

> [!NOTE]
> - <span data-ttu-id="e3618-136">从缓存中检索的记录并不能反映其他用户对源数据所做的并发更改。</span><span class="sxs-lookup"><span data-stu-id="e3618-136">Records retrieved from the cache don't reflect concurrent changes that other users made to the source data.</span></span>
> - <span data-ttu-id="e3618-p106">**FillCache** 只检索尚未缓存的记录。若要强制更新所有缓存的数据，请将 **Recordset** 的 **CacheSize** 属性设置为 0，再将它重置为最初请求的缓存的大小，然后使用 **FillCache**。</span><span class="sxs-lookup"><span data-stu-id="e3618-p106">**FillCache** only retrieves records not already cached. To force an update of all the cached data, set the **CacheSize** property of the **Recordset** to 0, reset it to the size of the cache you originally requested, and then use **FillCache**.</span></span>

## <a name="example"></a><span data-ttu-id="e3618-139">示例</span><span class="sxs-lookup"><span data-stu-id="e3618-139">Example</span></span>

<span data-ttu-id="e3618-p107">以下示例使用 **CreateTableDef** 和 **FillCache** 方法以及 **CacheSize**、 **CacheStart** 和 **SourceTableName** 属性两次枚举链接表中的记录，再使用存有 50 条记录的缓存两次枚举这些记录，然后通过链接表显示未缓存运行和缓存运行的性能统计。</span><span class="sxs-lookup"><span data-stu-id="e3618-p107">This example uses the **CreateTableDef** and **FillCache** methods and the **CacheSize**, **CacheStart** and **SourceTableName** properties to enumerate the records in a linked table twice. Then it enumerates the records twice with a 50-record cache. The example then displays the performance statistics for the uncached and cached runs through the linked table.</span></span>

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
       '       use Microsoft Windows NT Authentication Mode to  
       '       authorize user access to the Microsoft SQL Server. 
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
             "  No cache: " & Format(sngNoCache, _ 
             "##0.000") & " seconds" & vbCr & _ 
             "  50-record cache: " & Format(sngCache, _ 
             "##0.000") & " seconds" 
          .Close 
       End With 
     
       ' Delete linked table because this is a demonstration. 
       dbsCurrent.TableDefs.Delete tdfRoyalties.Name 
       dbsCurrent.Close 
     
    End Sub
```
