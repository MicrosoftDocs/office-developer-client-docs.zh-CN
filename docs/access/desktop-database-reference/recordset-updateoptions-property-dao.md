---
title: Recordset.UpdateOptions Property (DAO)
TOCTitle: UpdateOptions Property
ms:assetid: 14ab955d-1c5a-dc76-8dbf-dbca49816bc8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845468(v=office.15)
ms:contentKeyID: 48543391
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101185
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b39b9920625d970a51feadc706a3c5ff62359e53
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884350"
---
# <a name="recordsetupdateoptions-property-dao"></a>Recordset.UpdateOptions Property (DAO)


**适用于**： Access 2013、 Office 2013

## <a name="syntax"></a>语法

*表达式*。UpdateOptions

*表达式*一个表示**Recordset**对象的变量。

## <a name="remarks"></a>注解

当执行批处理模式的 **[Update](recordset-update-method-dao.md)** 时，DAO 和客户端批处理光标库创建一系列 SQL UPDATE 语句，以进行所需的更改。 为每次更新创建了 SQL WHERE 子句，以便隔离被 **[RecordStatus](recordset-recordstatus-property-dao.md)** 属性标记为已更改的记录。 由于某些远程服务器使用触发器或其他方法实施参照完整性，所以将更新的字段限制为受更改影响的那些记录通常是很有必要的。 

为此，需要将 **UpdateOptions** 属性设置为常量 **dbCriteriaKey**、 **dbCriteriaModValues**、 **dbCriteriaAllCols** 或 **dbCriteriaTimeStamp** 之一。 这样，将只执行触发器代码的最小绝对量。 因此，可以更快速地执行更新操作，潜在错误也会较少。

还可以连接 **dbCriteriaDeleteInsert** 或 **dbCriteriaUpdate**，以确定在将批修改发送回服务器时，对于每次更新是使用 SQL DELETE 和 INSERT 语句集合，还是使用 SQL UPDATE 语句。在前一种情况下，需要两个单独操作才能更新记录。在某些情况下，尤其是远程系统实施 DELETE、INSERT 和 UPDATE 触发器时，选择正确的 **UpdateOptions** 属性设置会显著影响性能。

如果您不指定任何常量，将使用 **dbCriteriaUpdate** 和 **dbCriteriaKey**。

新添加的记录始终生成 INSERT 语句，删除的记录始终生成 DELETE 语句，所以该属性只对光标库如何更新修改的记录适用。

## <a name="example"></a>示例

以下示例使用 **BatchSize** 和 **UpdateOptions** 属性控制指定的 **Recordset** 对象的任何批更新的各个方面。

```vb 
Sub BatchSizeX() 
 
 Dim wrkMain As Workspace 
 Dim conMain As Connection 
 Dim rstTemp As Recordset 
 
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
 ' batch updating. 
 Set rstTemp = conMain.OpenRecordset( _ 
 "SELECT * FROM roysched", dbOpenDynaset, 0, _ 
 dbOptimisticBatch) 
 
 With rstTemp 
 ' Increase the number of statements sent to the server 
 ' during a single batch update, thereby reducing the 
 ' number of times an update would have to access the 
 ' server. 
 .BatchSize = 25 
 
 ' Change the UpdateOptions property so that the WHERE 
 ' clause of any batched statements going to the server 
 ' will include any updated columns in addition to the 
 ' key column(s). Also, any modifications to records 
 ' will be made by deleting the original record 
 ' and adding a modified version rather than just 
 ' modifying the original record. 
 .UpdateOptions = dbCriteriaModValues + _ 
 dbCriteriaDeleteInsert 
 
 ' Engage in batch updating using the new settings 
 ' above. 
 ' ... 
 
 .Close 
 End With 
 
 conMain.Close 
 wrkMain.Close 
 
End Sub 
 
```

