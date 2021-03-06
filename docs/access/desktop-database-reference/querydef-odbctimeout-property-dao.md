---
title: ODBCTimeout 属性 (DAO)
TOCTitle: ODBCTimeout Property
ms:assetid: b251c4fb-64a8-aa95-deed-64425df3e00c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822019(v=office.15)
ms:contentKeyID: 48547166
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053052
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 2d34aee30e649b1c25ddc6af8078da2af9dd3b84
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300999"
---
# <a name="querydefodbctimeout-property-dao"></a>ODBCTimeout 属性 (DAO)


**适用于**：Access 2013、Office 2013

指示在开放式数据库连接 (ODBC) 数据库上执行 **[QueryDef](querydef-object-dao.md)** 时，发生超时错误之前等待的秒数。

## <a name="syntax"></a>语法

*表达式*。ODBCTimeout

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

如果 **ODBCTimeout** 属性设置为 -1，则超时默认为包含 **QueryDef** 的 **[Connection](database-querytimeout-property-dao.md)** 或 **[Database](connection-object-dao.md)** 对象的 **[QueryTimeout](database-object-dao.md)** 属性的当前设置。 如果 **ODBCTimeout** 属性设置为 0，则不发生超时错误。

如果使用的是 ODBC 数据库（如 Microsoft SQL Server），可能会由于网络阻塞或大量使用 ODBC 服务器而导致延迟。不需要无限期地等待，您可以指定返回错误前的等待时间。

设置 **QueryDef** 对象的 **ODBCTimeout** 属性将重写由包含 **QueryDef** 的 **Connection** 或 **Database** 对象的 **QueryTimeout** 属性指定的值，但这一点只适用于该 **QueryDef** 对象。

## <a name="example"></a>示例

以下示例使用 **ODBCTimeout** 和 **QueryTimeout** 属性，演示 **Database** 对象的 **QueryTimeout** 设置如何设置从 **Database** 对象创建的任何 **QueryDef** 对象的默认 **ODBCTimeout** 设置。

```vb 
Sub ODBCTimeoutX() 
 
 Dim dbsCurrent As Database 
 Dim qdfStores As QueryDef 
 Dim rstStores As Recordset 
 
 Set dbsCurrent = OpenDatabase("Northwind.mdb") 
 
 ' Change the default QueryTimeout of the Northwind 
 ' database. 
 Debug.Print "Default QueryTimeout of Database: " & _ 
 dbsCurrent.QueryTimeout 
 dbsCurrent.QueryTimeout = 30 
 Debug.Print "New QueryTimeout of Database: " & _ 
 dbsCurrent.QueryTimeout 
 
 ' Create a new QueryDef object. 
 Set qdfStores = dbsCurrent.CreateQueryDef("Stores", _ 
 "SELECT * FROM stores") 
 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the SQL Server. 
 qdfStores.Connect = _ 
 "ODBC;DATABASE=pubs;DSN=Publishers" 
 
 ' Change the ODBCTimeout setting of the new QueryDef 
 ' object from its default setting. 
 Debug.Print "Default ODBCTimeout of QueryDef: " & _ 
 qdfStores.ODBCTimeout 
 qdfStores.ODBCTimeout = 0 
 Debug.Print "New ODBCTimeout of QueryDef: " & _ 
 qdfStores.ODBCTimeout 
 
 ' Execute the query and display the results. 
 Set rstStores = qdfStores.OpenRecordset() 
 
 Debug.Print "Contents of recordset:" 
 With rstStores 
 Do While Not .EOF 
 Debug.Print , .Fields(0), .Fields(1) 
 .MoveNext 
 Loop 
 .Close 
 End With 
 
 ' Delete new QueryDef because this is a demonstration. 
 dbsCurrent.QueryDefs.Delete qdfStores.Name 
 dbsCurrent.Close 
 
End Sub 
 
```

