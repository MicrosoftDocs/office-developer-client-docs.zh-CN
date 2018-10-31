---
title: 第 4 章：编辑数据
TOCTitle: 'Chapter 4: Editing Data'
ms:assetid: 822b7365-0926-6411-6fb4-30de032570f8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249563(v=office.15)
ms:contentKeyID: 48545974
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d859f7bc3a74dfde1841be87f4a8237af9b7c48a
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862252"
---
# <a name="chapter-4-editing-data"></a>第 4 章：编辑数据


**适用于**： Access 2013 |Office 2013

前面两章解释了如何使用 ADO 来连接数据源，执行命令，获取 **Recordset** 对象中的结果以及在 **Recordset** 中进行导航。本章重点介绍下一个基本 ADO 操作：编辑数据。

本章继续使用第 3 章中引入的示例 **Recordset** - 但有一项重要更改。使用以下代码打开 **Recordset** ：

```vb 
 
 . . . 
'BeginEditIntro 
 Dim strSQL As String 
 Dim objRs1 As ADODB.Recordset 
 
 strSQL = "SELECT * FROM Shippers" 
 
 Set objRs1 = New ADODB.Recordset 
 
 objRs1.Open strSQL, GetNewConnection, adOpenStatic, _ 
 adLockBatchOptimistic, adCmdText 
 
 ' Disconnect the Recordset from the Connection object. 
 Set objRs1.ActiveConnection = Nothing 
'EndEditIntro 
 
 
 . . . 
```

对代码的重要更改涉及在 GetNewConnection 函数中将 **Connection** 对象的 **CursorLocation** 属性设置为等于 **adUseClient** （如下所示），以指示客户端游标的使用情况。有关客户端和服务器端游标之间的差异的详细信息，请参阅 [第 8 章：了解游标和锁定](chapter-8-understanding-cursors-and-locks.md)。

**CursorLocation** 属性的 **adUseClient** 设置会将游标位置从数据源（在本例中是 SQL Server）移动到客户端代码所指示的位置（桌面工作站）。此设置将强制 ADO 调用客户端上的 OLE DB 客户端游标引擎来创建和管理游标。

您还可能注意到 **Open** 方法的 **LockType** 参数已更改为 **adLockBatchOptimistic** ，这样将在批模式下打开游标。（提供程序会缓存多个更改，只有当您调用 **UpdateBatch** 方法时，才会将它们写入基础数据源。）只有在调用 **UpdateBatch** 方法后，对 **Recordset** 的更改才会更新到数据库中。

最后，本章中的代码将使用第 2 章引入的 GetNewConnection 函数版本，但会稍作修改。该函数的这个版本现在将返回一个客户端游标。该函数类似于：

```vb 
 
'BeginNewConnection 
Public Function GetNewConnection() As ADODB.Connection 
 Dim objConn1 As ADODB.Connection 
 Set objConn1 = New ADODB.Connection 
 
 strConnStr = "Provider=SQLOLEDB;Initial Catalog=Northwind;" & _ 
 "Data Source=MySrvr;Integrated Security=SSPI;" 
 
 objConn1.ConnectionString = strConnStr 
 objConn1.CursorLocation = adUseClient 
 objConn1.Open 
 
 Set GetNewConnection = objConn1 
End Function 
'EndNewConnection 
```

本章包含以下主题：

- [编辑现有记录](editing-existing-records.md)

- [确定受支持的内容](determining-what-is-supported.md)

- [使用 Delete 方法删除记录](deleting-records-using-the-delete-method.md)

- [替代方法：使用 SQL 语句](alternatives-using-sql-statements.md)

- [Adding Records (ADO)](adding-records.md)