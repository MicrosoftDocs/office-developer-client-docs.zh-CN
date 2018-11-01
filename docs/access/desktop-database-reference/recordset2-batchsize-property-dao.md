---
title: Recordset2.BatchSize Property (DAO)
TOCTitle: BatchSize Property
ms:assetid: fa7f12f6-36c8-5aad-31d2-668cfe46f9f7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837054(v=office.15)
ms:contentKeyID: 48548846
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: edb0f18e68021bf6e23e006d5d8e37e6eb6d816c
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867949"
---
# <a name="recordset2batchsize-property-dao"></a><span data-ttu-id="ea34b-102">Recordset2.BatchSize Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="ea34b-102">Recordset2.BatchSize Property (DAO)</span></span>


<span data-ttu-id="ea34b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ea34b-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="ea34b-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea34b-104">Syntax</span></span>

<span data-ttu-id="ea34b-105">*表达式*。BatchSize</span><span class="sxs-lookup"><span data-stu-id="ea34b-105">*expression* .BatchSize</span></span>

<span data-ttu-id="ea34b-106">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="ea34b-106">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea34b-107">注解</span><span class="sxs-lookup"><span data-stu-id="ea34b-107">Remarks</span></span>

<span data-ttu-id="ea34b-p101">**BatchSize** 属性确定在批更新中将语句发送到服务器时使用的批大小。该属性的值决定了在一个命令缓冲中发送到服务器的语句数。默认情况下，在每次批处理中将 15 个语句发送到服务器。可以随时更改该属性。如果数据库服务器不支持语句批处理，可以将该属性设置为 1，这样就会导致单独发送每个语句。</span><span class="sxs-lookup"><span data-stu-id="ea34b-p101">The **BatchSize** property determines the batch size used when sending statements to the server in a batch update. The value of the property determines the number of statements sent to the server in one command buffer. By default, 15 statements are sent to the server in each batch. This property can be changed at any time. If a database server doesn't support statement batching, you can set this property to 1, causing each statement to be sent separately.</span></span>

## <a name="example"></a><span data-ttu-id="ea34b-113">示例</span><span class="sxs-lookup"><span data-stu-id="ea34b-113">Example</span></span>

<span data-ttu-id="ea34b-114">以下示例使用 **BatchSize** 和 **UpdateOptions** 属性控制指定的 Recordset 对象的任何批更新的各个方面。</span><span class="sxs-lookup"><span data-stu-id="ea34b-114">This example uses the **BatchSize** and **UpdateOptions** properties to control aspects of any batch updating for the specified Recordset object.</span></span>

```vb
Sub BatchSizeX() 
 
 Dim wrkMain As Workspace 
 Dim conMain As Connection 
 Dim rstTemp As Recordset2 
 
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

