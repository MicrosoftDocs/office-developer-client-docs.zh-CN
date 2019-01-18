---
title: QueryDef.MaxRecords 属性 (DAO)
TOCTitle: MaxRecords Property
ms:assetid: 7492cde9-be30-3473-dabc-9602465910d1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195877(v=office.15)
ms:contentKeyID: 48545664
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053583
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 6738762ba18289293c67392d47e278066ead071d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699308"
---
# <a name="querydefmaxrecords-property-dao"></a>QueryDef.MaxRecords 属性 (DAO)

**适用于**： Access 2013、 Office 2013

设置或返回针对 ODBC 数据源的查询所返回的最大记录数。

## <a name="syntax"></a>语法

*表达式*。MaxRecords

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

默认值为 0，表示不限制返回记录的数目。

将 **MaxRecords** 指定的行数返回到 **[Recordset](recordset-object-dao.md)** 中的应用程序后，查询处理器将停止返回其他记录，即使有更多的记录符合列入 **Recordset** 的条件，也是如此。如果有限的客户端资源阻止了对大量记录的管理，该属性将十分有用。

> [!NOTE]
> [!注释] **MaxRecords** 属性只能用于 ODBC 数据源。

## <a name="example"></a>示例

以下示例使用 **MaxRecords** 属性设置对 ODBC 数据源上的查询返回的记录数的限制。

```vb 
Sub MaxRecordsX() 
 
 Dim dbsCurrent As Database 
 Dim qdfPassThrough As QueryDef 
 Dim qdfLocal As QueryDef 
 Dim rstTemp As Recordset 
 
 ' Open a database from which QueryDef objects can be 
 ' created. 
 Set dbsCurrent = OpenDatabase("DB1.mdb") 
 
 ' Create a pass-through query to retrieve data from 
 ' a Microsoft SQL Server database. 
 Set qdfPassThrough = _ 
 dbsCurrent.CreateQueryDef("") 
 
 ' Set the properties of the new query, limiting the 
 ' number of returnable records to 20. 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 qdfPassThrough.Connect = _ 
 "ODBC;DATABASE=pubs;DSN=Publishers" 
 qdfPassThrough.SQL = "SELECT * FROM titles" 
 qdfPassThrough.ReturnsRecords = True 
 qdfPassThrough.MaxRecords = 20 
 
 Set rstTemp = qdfPassThrough.OpenRecordset() 
 
 ' Display results of query. 
 Debug.Print "Query results:" 
 With rstTemp 
 Do While Not .EOF 
 Debug.Print , .Fields(0), .Fields(1) 
 .MoveNext 
 Loop 
 .Close 
 End With 
 
 dbsCurrent.Close 
 
End Sub 
 
```

