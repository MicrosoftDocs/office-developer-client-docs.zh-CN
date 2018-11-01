---
title: Recordset2.BatchCollisionCount Property (DAO)
TOCTitle: BatchCollisionCount Property
ms:assetid: 997dfbb3-673c-8813-f51b-ab8d95093c4f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197961(v=office.15)
ms:contentKeyID: 48546514
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 56f2b2debdcd974df3232ee42f07ca1235ff73c5
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25871337"
---
# <a name="recordset2batchcollisioncount-property-dao"></a>Recordset2.BatchCollisionCount Property (DAO)


**适用于**： Access 2013、 Office 2013

## <a name="syntax"></a>语法

*表达式*。BatchCollisionCount

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

该属性指示在上次批更新尝试过程中发生冲突或未能更新的记录数。该属性的值对应于 **[BatchCollisions](recordset2-batchcollisions-property-dao.md)** 属性中的书签数。

如果将正在工作的 **Recordset** 对象的 **[Bookmark](recordset2-bookmark-property-dao.md)** 属性设置为 **BatchCollisions** 数组中的书签值，则可以移到无法完成最近一次批 **[Update](recordset2-update-method-dao.md)** 操作的每条记录。

更正冲突记录后，可再次调用批模式 **Update** 方法。此时，DAO 将尝试进行另一次批更新，同时 **BatchCollisions** 属性将再次反映第二次尝试失败的记录集。不会在当前尝试中发送上一次尝试成功的任何记录，因为这些记录的 **[RecordStatus](recordset2-recordstatus-property-dao.md)** 属性现在已经为 **dbRecordUnmodified**。只要发生冲突，此过程就会继续下去，直到您放弃更新并关闭结果集为止。

## <a name="example"></a>示例

以下示例使用 **BatchCollisionCount** 属性和 **Update** 方法演示批更新，在其中通过强制批更新来解决任何冲突。

```vb 
Sub BatchX() 
 
 Dim wrkMain As Workspace 
 Dim conMain As Connection 
 Dim rstTemp As Recordset2 
 Dim intLoop As Integer 
 Dim strPrompt As String 
 
 Set wrkMain = CreateWorkspace("ODBCWorkspace", _ 
 "admin", "", dbUseODBC) 
 ' This DefaultCursorDriver setting is required for 
 ' batch updating. 
 wrkMain.DefaultCursorDriver = dbUseClientBatchCursor 
 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set conMain = wrkMain.OpenConnection("Publishers", _ 
 dbDriverNoPrompt, False, _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 ' The following locking argument is required for 
 ' batch updating. It is also required that a table 
 ' with a primary key is used. 
 Set rstTemp = conMain.OpenRecordset( _ 
 "SELECT * FROM roysched", dbOpenDynaset, 0, _ 
 dbOptimisticBatch) 
 
 With rstTemp 
 ' Modify data in local recordset. 
 Do While Not .EOF 
 .Edit 
 If !royalty <= 20 Then 
 !royalty = !royalty - 4 
 Else 
 !royalty = !royalty + 2 
 End If 
 .Update 
 .MoveNext 
 Loop 
 
 ' Attempt a batch update. 
 .Update dbUpdateBatch 
 
 ' If there are collisions, give the user the option 
 ' of forcing the changes or resolving them 
 ' individually. 
 If .BatchCollisionCount > 0 Then 
 strPrompt = "There are collisions. " & vbCr & _ 
 "Do you want the program to force " & _ 
 vbCr & "an update using the local data?" 
 If MsgBox(strPrompt, vbYesNo) = vbYes Then _ 
 .Update dbUpdateBatch, True 
 End If 
 
 .Close 
 End With 
 
 conMain.Close 
 wrkMain.Close 
 
End Sub 
 
```

