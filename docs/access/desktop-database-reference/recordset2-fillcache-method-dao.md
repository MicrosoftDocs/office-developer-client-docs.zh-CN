---
title: FillCache 方法 (DAO) Recordset2
TOCTitle: FillCache Method
ms:assetid: 28a70997-a8d4-73e6-171a-61286e3d3485
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192007(v=office.15)
ms:contentKeyID: 48543864
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052942
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 2098df82375ac47b7d5abe0bd63b0af2bb29ba40
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309700"
---
# <a name="recordset2fillcache-method-dao"></a>FillCache 方法 (DAO) Recordset2

**适用于**：Access 2013、Office 2013

为某个 **Recordset** 对象填充所有或一部分本地缓存，该对象包含来自 Microsoft Access 数据库引擎连接的 ODBC 数据源中的数据（仅适用于 Microsoft Access 数据库引擎连接的 ODBC 数据库）。

## <a name="syntax"></a>语法

*表达式*。FillCache (***Rows***, ***StartBookmark***)

*表达式*一个代表**Recordset2**对象的变量。

## <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Rows</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 <strong>Variant</strong>（<strong>Integer</strong> 子类型），用于指定要存储在缓存中的行数。 如果省略此参数, 则值由<strong><a href="recordset2-cachesize-property-dao.md">CacheSize</a></strong>属性设置决定。</p></td>
</tr>
<tr class="even">
<td><p><em>StartBookmark</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 <strong>Variant</strong>（<strong>String</strong> 子类型），用于指定书签。 将从此书签指示的记录开始填充缓存。 如果省略此参数, 则将从<strong><a href="recordset2-cachestart-property-dao.md">CacheStart</a></strong>属性指示的记录开始填充缓存。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

缓存可以改善从远程服务器检索数据的应用程序的性能。缓存是指本地内存中用于保存最近从服务器检索的数据的空间；这假定在应用程序运行时，可能需要再次请求此数据。用户请求数据时，Microsoft Access 数据库引擎将首先检查数据的缓存，而不是从服务器检索此数据（从服务器检索会花费较长时间）。缓存不保存来自 ODBC 数据源以外的数据。

可以在任何时候使用 **FillCache** 方法显式填充缓存，而不必等待检索记录后使用记录填充缓存。这是填充缓存的较快方式，因为 **FillCache** 一次可检索多条记录，而不是一次检索一条。例如，在查看每一满屏记录时，应用程序将使用 **FillCache** 检索要查看的下一满屏记录。

使用 **Recordset** 对象访问的、Microsoft Access 数据库引擎连接的任何 ODBC 数据源都可能具有本地缓存。若要创建此缓存，请打开远程数据源中的某个 **Recordset** 对象，然后设置 **Recordset** 的 **CacheSize** 和 **CacheStart** 属性。

如果 rows 和 startbookmark 创建的记录范围部分或全部超出**CacheSize**和**CacheStart**属性指定的记录范围, 则忽略此范围之外的 recordset 部分, 且不会加载该部分。到缓存中。

如果 **FillCache** 请求的记录数多于远程数据源中剩余记录的数目，Microsoft Access 数据库引擎只检索剩余的记录，并且不发生错误。

> [!NOTE]
> - 从缓存中检索的记录并不能反映其他用户对源数据所做的并发更改。
> - **FillCache** 只检索尚未缓存的记录。若要强制更新所有缓存的数据，请将 **Recordset** 的 **CacheSize** 属性设置为 0，再将它重置为最初请求的缓存的大小，然后使用 **FillCache**。

## <a name="example"></a>示例

以下示例使用 **CreateTableDef** 和 **FillCache** 方法以及 **CacheSize**、 **CacheStart** 和 **SourceTableName** 属性两次枚举链接表中的记录，再使用存有 50 条记录的缓存两次枚举这些记录，然后通过链接表显示未缓存运行和缓存运行的性能统计。

```vb
    Sub ClientServerX3() 
     
       Dim dbsCurrent As Database 
       Dim tdfRoyalties As TableDef 
       Dim rstRemote As Recordset2 
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
