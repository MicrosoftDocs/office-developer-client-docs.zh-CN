---
title: Recordset.UpdateOptions 属性 (DAO)
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
ms.openlocfilehash: 2e267e913ed89707ca79642b96dafa2cae85a574
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927529"
---
# <a name="recordsetupdateoptions-property-dao"></a><span data-ttu-id="8ca3d-102">Recordset.UpdateOptions 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="8ca3d-102">Recordset.UpdateOptions property (DAO)</span></span>


<span data-ttu-id="8ca3d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8ca3d-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="8ca3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ca3d-104">Syntax</span></span>

<span data-ttu-id="8ca3d-105">*表达式*。UpdateOptions</span><span class="sxs-lookup"><span data-stu-id="8ca3d-105">*expression* .UpdateOptions</span></span>

<span data-ttu-id="8ca3d-106">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-106">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ca3d-107">注解</span><span class="sxs-lookup"><span data-stu-id="8ca3d-107">Remarks</span></span>

<span data-ttu-id="8ca3d-108">当执行批处理模式的 **[Update](recordset-update-method-dao.md)** 时，DAO 和客户端批处理光标库创建一系列 SQL UPDATE 语句，以进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-108">When a batch-mode **[Update](recordset-update-method-dao.md)** is executed, DAO and the client batch cursor library create a series of SQL UPDATE statements to make the needed changes.</span></span> <span data-ttu-id="8ca3d-109">为每次更新创建了 SQL WHERE 子句，以便隔离被 **[RecordStatus](recordset-recordstatus-property-dao.md)** 属性标记为已更改的记录。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-109">An SQL WHERE clause is created for each update to isolate the records that are marked as changed by the **[RecordStatus](recordset-recordstatus-property-dao.md)** property.</span></span> <span data-ttu-id="8ca3d-110">由于某些远程服务器使用触发器或其他方法实施参照完整性，所以将更新的字段限制为受更改影响的那些记录通常是很有必要的。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-110">Because some remote servers use triggers or other ways to enforce referential integrity, is it often important to limit the fields being updated to just those affected by the change.</span></span> 

<span data-ttu-id="8ca3d-111">为此，需要将 **UpdateOptions** 属性设置为常量 **dbCriteriaKey**、 **dbCriteriaModValues**、 **dbCriteriaAllCols** 或 **dbCriteriaTimeStamp** 之一。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-111">To do this, set the **UpdateOptions** property to one of the constants **dbCriteriaKey**, **dbCriteriaModValues**, **dbCriteriaAllCols**, or **dbCriteriaTimeStamp**.</span></span> <span data-ttu-id="8ca3d-112">这样，将只执行触发器代码的最小绝对量。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-112">This way, only the absolute minimum amount of trigger code is executed.</span></span> <span data-ttu-id="8ca3d-113">因此，可以更快速地执行更新操作，潜在错误也会较少。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-113">As a result, the update operation is executed more quickly, and with fewer potential errors.</span></span>

<span data-ttu-id="8ca3d-p103">还可以连接 **dbCriteriaDeleteInsert** 或 **dbCriteriaUpdate**，以确定在将批修改发送回服务器时，对于每次更新是使用 SQL DELETE 和 INSERT 语句集合，还是使用 SQL UPDATE 语句。在前一种情况下，需要两个单独操作才能更新记录。在某些情况下，尤其是远程系统实施 DELETE、INSERT 和 UPDATE 触发器时，选择正确的 **UpdateOptions** 属性设置会显著影响性能。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-p103">You can also concatenate either of the constants **dbCriteriaDeleteInsert** or **dbCriteriaUpdate** to determine whether to use a set of SQL DELETE and INSERT statements or an SQL UPDATE statement for each update when sending batched modifications back to the server. In the former case, two separate operations are required to update the record. In some cases, especially where the remote system implements DELETE, INSERT, and UPDATE triggers, choosing the correct **UpdateOptions** property setting can significantly impact performance.</span></span>

<span data-ttu-id="8ca3d-117">如果您不指定任何常量，将使用 **dbCriteriaUpdate** 和 **dbCriteriaKey**。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-117">If you don't specify any constants, **dbCriteriaUpdate** and **dbCriteriaKey** will be used.</span></span>

<span data-ttu-id="8ca3d-118">新添加的记录始终生成 INSERT 语句，删除的记录始终生成 DELETE 语句，所以该属性只对光标库如何更新修改的记录适用。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-118">Newly added records will always generate INSERT statements and deleted records will always generate DELETE statements, so this property only applies to how the cursor library updates modified records.</span></span>

## <a name="example"></a><span data-ttu-id="8ca3d-119">示例</span><span class="sxs-lookup"><span data-stu-id="8ca3d-119">Example</span></span>

<span data-ttu-id="8ca3d-120">以下示例使用 **BatchSize** 和 **UpdateOptions** 属性控制指定的 **Recordset** 对象的任何批更新的各个方面。</span><span class="sxs-lookup"><span data-stu-id="8ca3d-120">This example uses the **BatchSize** and **UpdateOptions** properties to control aspects of any batch updating for the specified **Recordset** object.</span></span>

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

