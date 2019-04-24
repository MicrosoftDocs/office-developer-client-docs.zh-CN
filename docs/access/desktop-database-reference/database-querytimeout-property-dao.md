---
title: QueryTimeout 属性 (DAO)
TOCTitle: QueryTimeout Property
ms:assetid: c83ca852-715a-c853-429b-80a15c3fc39b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823170(v=office.15)
ms:contentKeyID: 48547648
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f47d6c51079bf36cb7e1ca596a3476f1a7219c5d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294736"
---
# <a name="databasequerytimeout-property-dao"></a>QueryTimeout 属性 (DAO)


**适用于**：Access 2013、Office 2013


设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。

## <a name="syntax"></a>语法

*表达式*。QueryTimeout

*表达式*一个代表**Database**对象的变量。

## <a name="remarks"></a>注解

默认值为 60。

在使用 ODBC 数据库（如 Microsoft SQL Server）时，由于网络阻塞或大量使用 ODBC 服务器的原因，可能会有延迟。不需要无限期地等待，您可以指定等待时间。

将 **QueryTimeout** 用于 **[Connection](connection-object-dao.md)** 或 **[Database](database-object-dao.md)** 对象时，它为所有与数据库关联的查询指定了全局值。可以通过设置特定 [**QueryDef**](querydef-object-dao.md) 对象的 **ODBCTimeout** 属性来重写特定查询的这个值。

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

