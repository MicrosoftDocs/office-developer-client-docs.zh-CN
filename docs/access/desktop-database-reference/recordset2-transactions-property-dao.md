---
title: Recordset2.Transactions 属性 (DAO)
TOCTitle: Transactions Property
ms:assetid: f2169565-f782-4089-0e4b-bc5d58d37db5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836614(v=office.15)
ms:contentKeyID: 48548642
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 58610ee87e61a8b342955107c2ba2b690e610c8b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713868"
---
# <a name="recordset2transactions-property-dao"></a>Recordset2.Transactions 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回一个值，该值指示对象是否支持事务。只读 **Boolean** 类型。

## <a name="syntax"></a>语法

*表达式*。事务

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

在 Microsoft Access 工作区中，也可以将 **Transactions** 属性用于动态集类型或表类型的 **Recordset** 对象。 快照-和向前仅类型**[Recordset](recordset-object-dao.md)** 对象始终返回**False**。

如果动态集类型或表类型的 **Recordset** 基于 Microsoft Access 数据库引擎表，则 **Transactions** 属性为 **True** 且您可以使用事务。其他数据库引擎可能不支持事务。例如，不能在基于 Paradox 表的动态集类型 **Recordset** 对象中使用事务。

在对 **Recordset** 对象的 **[Workspace](dbengine-begintrans-method-dao.md)** 对象使用 [**BeginTrans**](workspace-object-dao.md) 方法之前，检查 **Transactions** 属性，以确保支持事务。对不受支持的对象使用 **BeginTrans**、 **CommitTrans** 或 **Rollback** 方法没有效果。

## <a name="example"></a>示例

以下示例在 Microsoft Access 工作区中演示 **Transactions** 属性。

```vb 
Sub TransactionsX() 
 
 Dim wrkAcc As Workspace 
 Dim dbsNorthwind As Database 
 Dim conPubs As Connection 
 Dim rstTemp As Recordset 
 
 Set wrkAcc = CreateWorkspace("", "admin", "", dbUseJet) 
 Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
 
 ' Open two different Recordset objects and display the 
 ' Transactions property of each. 
 
 Debug.Print "Opening Microsoft Access table-type " & _ 
 "recordset..." 
 Set rstTemp = dbsNorthwind.OpenRecordset( _ 
 "Employees", dbOpenTable) 
 Debug.Print " Transactions = " & rstTemp.Transactions 
 
 Debug.Print "Opening forward-only-type " & _ 
 "recordset where the source is an SQL statement..." 
 Set rstTemp = dbsNorthwind.OpenRecordset( _ 
 "SELECT * FROM Employees", dbOpenForwardOnly) 
 Debug.Print " Transactions = " & rstTemp.Transactions 
 
 rstTemp.Close 
 dbsNorthwind.Close 
 conPubs.Close 
 wrkAcc.Close 
End Sub 
 
```

