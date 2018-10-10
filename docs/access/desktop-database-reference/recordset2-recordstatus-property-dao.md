---
title: Recordset2.RecordStatus Property (DAO)
TOCTitle: RecordStatus Property
ms:assetid: 178872a9-e361-f277-627d-f91b01ceb6d1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845575(v=office.15)
ms:contentKeyID: 48543451
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a13f9f64ab6f699979633c70fb2e8a9386ce2134
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465519"
---
# <a name="recordset2recordstatus-property-dao"></a><span data-ttu-id="5a5e1-102">Recordset2.RecordStatus Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="5a5e1-102">Recordset2.RecordStatus Property (DAO)</span></span>


<span data-ttu-id="5a5e1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5a5e1-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="5a5e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a5e1-104">Syntax</span></span>

<span data-ttu-id="5a5e1-105">*表达式*。RecordStatus</span><span class="sxs-lookup"><span data-stu-id="5a5e1-105">*expression* .RecordStatus</span></span>

<span data-ttu-id="5a5e1-106">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="5a5e1-106">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a5e1-107">注解</span><span class="sxs-lookup"><span data-stu-id="5a5e1-107">Remarks</span></span>

<span data-ttu-id="5a5e1-108">**RecordStatus** 属性的值指示在下一次乐观批更新中是否包含当前记录以及如何包含当前记录。</span><span class="sxs-lookup"><span data-stu-id="5a5e1-108">The value of the **RecordStatus** property indicates whether and how the current record will be involved in the next optimistic batch update.</span></span>

<span data-ttu-id="5a5e1-p101">当用户更改记录时，该记录的 **RecordStatus** 自动更改为 **dbRecordModified**。同样，如果添加或删除记录， **RecordStatus** 会反映相应的常量。如果您之后使用批处理模式的 **[Update](recordset2-update-method-dao.md)** 方法，DAO 将根据每条记录的 **RecordStatus** 属性，向远程服务器提交针对每条记录的相应操作。</span><span class="sxs-lookup"><span data-stu-id="5a5e1-p101">When a user changes a record, the **RecordStatus** for that record automatically changes to **dbRecordModified**. Similarly, if a record is added or deleted, **RecordStatus** reflects the appropriate constant. When you then use a batch-mode **[Update](recordset2-update-method-dao.md)** method, DAO will submit an appropriate operation to the remote server for each record, based on the record's **RecordStatus** property.</span></span>

## <a name="example"></a><span data-ttu-id="5a5e1-112">示例</span><span class="sxs-lookup"><span data-stu-id="5a5e1-112">Example</span></span>

<span data-ttu-id="5a5e1-p102">以下示例使用 **RecordStatus** 和 **DefaultCursorDriver** 属性演示如何在批更新中跟踪对本地 **Recordset** 的更改。若要使该过程运行，需要使用 RecordStatusOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="5a5e1-p102">This example uses the **RecordStatus** and **DefaultCursorDriver** properties to show how changes to a local **Recordset** are tracked during batch updating. The RecordStatusOutput function is required for this procedure to run.</span></span>

```vb 
Sub RecordStatusX() 
 
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
 "SELECT * FROM authors", dbOpenDynaset, 0, _ 
 dbOptimisticBatch) 
 
 With rstTemp 
 .MoveFirst 
 Debug.Print "Original record: " & !au_lname 
 Debug.Print , RecordStatusOutput2(.RecordStatus) 
 
 .Edit 
 !au_lname = "Bowen" 
 .Update 
 Debug.Print "Edited record: " & !au_lname 
 Debug.Print , RecordStatusOutput2(.RecordStatus) 
 
 .AddNew 
 !au_lname = "NewName" 
 .Update 
 Debug.Print "New record: " & !au_lname 
 Debug.Print , RecordStatusOutput2(.RecordStatus) 
 
 .Delete 
 Debug.Print "Deleted record: " & !au_lname 
 Debug.Print , RecordStatusOutput2(.RecordStatus) 
 
 ' Close the local recordset without updating the 
 ' data on the server. 
 .Close 
 End With 
 
 conMain.Close 
 wrkMain.Close 
 
End Sub 
 
Function RecordStatusOutput(lngTemp As Long) As String 
 
 Dim strTemp As String 
 
 strTemp = "" 
 
 ' Construct an output string based on the RecordStatus 
 ' value. 
If lngTemp = dbRecordUnmodified Then _ 
 strTemp = "[dbRecordUnmodified]" 
 If lngTemp = dbRecordModified Then _ 
 strTemp = "[dbRecordModified]" 
 If lngTemp = dbRecordNew Then _ 
 strTemp = "[dbRecordNew]" 
 If lngTemp = dbRecordDeleted Then _ 
 strTemp = "[dbRecordDeleted]" 
 If lngTemp = dbRecordDBDeleted Then _ 
 strTemp = "[dbRecordDBDeleted]" 
 
 RecordStatusOutput = strTemp 
 
End Function 
 
```

