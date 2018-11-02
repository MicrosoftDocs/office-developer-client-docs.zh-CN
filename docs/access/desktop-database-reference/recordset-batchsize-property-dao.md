---
title: Recordset.BatchSize 属性 (DAO)
TOCTitle: BatchSize Property
ms:assetid: f03dc505-682f-4b60-62f2-1bd088d873c4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836544(v=office.15)
ms:contentKeyID: 48548599
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101179
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1801d03eb874f5d3dec16e2adcc8595c0a88eb84
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928934"
---
# <a name="recordsetbatchsize-property-dao"></a><span data-ttu-id="a8097-102">Recordset.BatchSize 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="a8097-102">Recordset.BatchSize property (DAO)</span></span>


<span data-ttu-id="a8097-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a8097-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="a8097-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8097-104">Syntax</span></span>

<span data-ttu-id="a8097-105">*表达式*。BatchSize</span><span class="sxs-lookup"><span data-stu-id="a8097-105">*expression* .BatchSize</span></span>

<span data-ttu-id="a8097-106">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="a8097-106">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8097-107">注解</span><span class="sxs-lookup"><span data-stu-id="a8097-107">Remarks</span></span>

<span data-ttu-id="a8097-p101">**BatchSize** 属性确定在批更新中将语句发送到服务器时使用的批大小。该属性的值决定了在一个命令缓冲中发送到服务器的语句数。默认情况下，在每次批处理中将 15 个语句发送到服务器。可以随时更改该属性。如果数据库服务器不支持语句批处理，可以将该属性设置为 1，这样就会导致单独发送每个语句。</span><span class="sxs-lookup"><span data-stu-id="a8097-p101">The **BatchSize** property determines the batch size used when sending statements to the server in a batch update. The value of the property determines the number of statements sent to the server in one command buffer. By default, 15 statements are sent to the server in each batch. This property can be changed at any time. If a database server doesn't support statement batching, you can set this property to 1, causing each statement to be sent separately.</span></span>

## <a name="example"></a><span data-ttu-id="a8097-113">示例</span><span class="sxs-lookup"><span data-stu-id="a8097-113">Example</span></span>

<span data-ttu-id="a8097-114">以下示例使用 **BatchSize** 和 **UpdateOptions** 属性控制指定的 Recordset 对象的任何批更新的各个方面。</span><span class="sxs-lookup"><span data-stu-id="a8097-114">This example uses the **BatchSize** and **UpdateOptions** properties to control aspects of any batch updating for the specified Recordset object.</span></span>

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

