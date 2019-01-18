---
title: 检测和解决冲突
TOCTitle: Detecting and resolving conflicts
ms:assetid: 8299745b-e595-21d5-26c1-a078d00a1c0c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249566(v=office.15)
ms:contentKeyID: 48545983
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ddd7566be2581fe449872eb576bf7f11e5a806fb
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716625"
---
# <a name="detecting-and-resolving-conflicts"></a><span data-ttu-id="60c47-102">检测和解决冲突</span><span class="sxs-lookup"><span data-stu-id="60c47-102">Detecting and resolving conflicts</span></span>

<span data-ttu-id="60c47-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="60c47-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="detecting-and-resolving-conflicts"></a><span data-ttu-id="60c47-104">检测和解决冲突</span><span class="sxs-lookup"><span data-stu-id="60c47-104">Detecting and Resolving Conflicts</span></span>

<span data-ttu-id="60c47-p101">如果在立即模式下处理 **Recordset** ，则很少会发生并发性问题。另一方面，如果应用程序使用批模式更新，则很容易遇到一个用户对记录进行的编辑尚未保存时另一个用户却更改同一记录的情况。这种情况下，您需要应用程序合理地处理冲突。您可能希望最后一个向服务器发送更新的人"获胜"，也可能希望让最后编辑数据的用户在两个冲突值之间做出选择，以便由该用户决定哪个更新应当优先。</span><span class="sxs-lookup"><span data-stu-id="60c47-p101">If you are dealing with your **Recordset** in immediate mode, there is much less chance for concurrency problems to arise. On the other hand, if your application uses batch mode updating, there may be a good chance that one user will change a record before changes made by another user editing the same record are saved. In such a case, you will want your application to gracefully handle the conflict. It may be your wish that the last person to send an update to the server "wins." Or you may want to let the most recent user to decide which update should take precedence by providing him with a choice between the two conflicting values.</span></span>

<span data-ttu-id="60c47-p102">无论是哪种情况，都可以使用 ADO 提供的 **Field** 对象的 **UnderlyingValue** 和 **OriginalValue** 属性来处理这些类型的冲突。这些属性需要与 **Recordset** 的 **Resync** 方法和 **Filter** 属性组合使用。</span><span class="sxs-lookup"><span data-stu-id="60c47-p102">Whatever the case, ADO provides the **UnderlyingValue** and **OriginalValue** properties of the **Field** object in order to handle these types of conflicts. Use these properties in combination with the **Resync** method and **Filter** property of the **Recordset**.</span></span>

## <a name="detecting-errors"></a><span data-ttu-id="60c47-112">检测错误</span><span class="sxs-lookup"><span data-stu-id="60c47-112">Detecting Errors</span></span>

<span data-ttu-id="60c47-p103">在批更新期间，当 ADO 遇到冲突时，会将警告放在 **Errors** 集合中。因此，在调用 **BatchUpdate** 之后，应当始终立即检查是否有错误，如果发现错误，则开始对已遇到冲突的假设进行测试。第一步是将 **Recordset** 的 **Filter** 属性设置为等于 **adFilterConflictingRecords** （前一章讨论了 **Filter** 属性）。这将使 **Recordset** 中只有那些发生冲突的记录可见。如果此步骤之后 **RecordCount** 属性等于零，则可以知道错误是由冲突以外的其他原因引起的。</span><span class="sxs-lookup"><span data-stu-id="60c47-p103">When ADO encounters a conflict during a batch update, a warning will be placed in the **Errors** collection. Therefore, you should always check for errors immediately after calling **BatchUpdate**, and if you find them, begin testing the assumption that you have encountered a conflict. The first step is to set the **Filter** property on the **Recordset** equal to **adFilterConflictingRecords** (the **Filter** property is discussed in the preceding chapter). This limits the view on your **Recordset** to only those records that are in conflict. If the **RecordCount** property is equal to zero after this step, you know the error was raised by something other than a conflict.</span></span>

<span data-ttu-id="60c47-p104">调用 **BatchUpdate** 时，ADO 和提供程序将生成 SQL 语句以便对数据源执行更新。请记住，对于在 WHERE 子句中可以使用的列类型，某些数据源会有限制。</span><span class="sxs-lookup"><span data-stu-id="60c47-p104">When you call **BatchUpdate**, ADO and the provider are generating SQL statements to perform updates on the data source. Remember that certain data sources have limitations on which types of columns can be used in a WHERE clause.</span></span>

<span data-ttu-id="60c47-120">接下来，调用**Resync**方法在**Recordset**上设置为等于**adAffectGroup** *AffectRecords*参数而*ResyncValues*参数设置为等于**adResyncUnderlyingValues**。</span><span class="sxs-lookup"><span data-stu-id="60c47-120">Next, call the **Resync** method on the **Recordset** with the *AffectRecords* argument set equal to **adAffectGroup** and the *ResyncValues* argument set equal to **adResyncUnderlyingValues**.</span></span> <span data-ttu-id="60c47-121">**Resync** 方法将从基础数据库刷新当前 **Recordset** 对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="60c47-121">The **Resync** method refreshes the data in the current **Recordset** object from the underlying database.</span></span> <span data-ttu-id="60c47-122">通过使用 **adAffectGroup** ，可以确保只有那些使用当前筛选器设置时可见的记录（即只有冲突记录）才会与数据库重新同步。</span><span class="sxs-lookup"><span data-stu-id="60c47-122">By using **adAffectGroup**, you are ensuring that only the records visible with the current filter setting, that is, only the conflicting records, are resynchronized with the database.</span></span> <span data-ttu-id="60c47-123">如果处理大型 **Recordset** ，这将导致巨大的性能差异。</span><span class="sxs-lookup"><span data-stu-id="60c47-123">This could make a significant performance difference if you are dealing with a large **Recordset**.</span></span> <span data-ttu-id="60c47-124">通过调用**Resync**时， *ResyncValues*参数设置为**adResyncUnderlyingValues** ，确保**UnderlyingValue**属性将包含从数据库 （冲突） 值的**值**按用户输入的值和**OriginalValue**属性将保留为字段 （发起的最后一个成功**UpdateBatch**呼叫之前的值） 的原始值，将保持属性。</span><span class="sxs-lookup"><span data-stu-id="60c47-124">By setting the *ResyncValues* argument to **adResyncUnderlyingValues** when calling **Resync**, you ensure that the **UnderlyingValue** property will contain the (conflicting) value from the database, that the **Value** property will maintain the value entered by the user, and that the **OriginalValue** property will hold the original value for the field (the value it had before the last successful **UpdateBatch** call was made).</span></span> <span data-ttu-id="60c47-125">然后，可以使用这些值通过编程来解决冲突，或要求用户选择将使用的值。</span><span class="sxs-lookup"><span data-stu-id="60c47-125">You can then use these values to resolve the conflict programmatically or require the user to choose the value that will be used.</span></span>

<span data-ttu-id="60c47-p106">以下代码示例显示了此技术。该示例将在调用 **UpdateBatch** 之前使用独立的 **Recordset** 来更改基础表中的值，从而人为制造冲突。</span><span class="sxs-lookup"><span data-stu-id="60c47-p106">This technique is shown in the code example below. The example artificially creates a conflict by using a separate **Recordset** to change a value in the underlying table before **UpdateBatch** is called.</span></span>

```vb 
 
'BeginConflicts 
    On Error GoTo ErrHandler: 
     
    Dim objRs1 As New ADODB.Recordset 
    Dim objRs2 As New ADODB.Recordset 
    Dim strSQL As String 
    Dim strMsg As String 
     
    strSQL = "SELECT * FROM Shippers WHERE ShipperID = 2" 
                  
    'Open Rs and change a value 
    objRs1.CursorLocation = adUseClient 
    objRs1.Open strSQL, strConn, adOpenStatic, adLockBatchOptimistic, adCmdText 
    objRs1("Phone") = "(111) 555-1111" 
     
    'Introduce a conflict at the db... 
    objRs2.Open strSQL, strConn, adOpenKeyset, adLockOptimistic, adCmdText 
    objRs2("Phone") = "(999) 555-9999" 
    objRs2.Update 
    objRs2.Close 
    Set objRs2 = Nothing 
     
    On Error Resume Next 
    objRs1.UpdateBatch 
     
    If objRs1.ActiveConnection.Errors.Count <> 0 Then 
        Dim intConflicts As Integer 
         
        intConflicts = 0 
         
        objRs1.Filter = adFilterConflictingRecords 
         
        intConflicts = objRs1.RecordCount 
         
        'Resync so we can see the UnderlyingValue and offer user a choice. 
        'This sample only displays all three values and resets to original. 
        objRs1.Resync adAffectGroup, adResyncUnderlyingValues 
         
        If intConflicts > 0 Then 
            strMsg = "A conflict occurred with updates for " & intConflicts & _ 
                     " record(s)." & vbCrLf & "The values will be restored" & _ 
                     " to their original values." & vbCrLf & vbCrLf 
                      
            objRs1.MoveFirst 
            While Not objRs1.EOF 
                strMsg = strMsg & "SHIPPER = " & objRs1("CompanyName") & vbCrLf 
                strMsg = strMsg & "Value = " & objRs1("Phone").Value & vbCrLf 
                strMsg = strMsg & "UnderlyingValue = " & _ 
                                   objRs1("Phone").UnderlyingValue & vbCrLf 
                strMsg = strMsg & "OriginalValue = " & _ 
                                   objRs1("Phone").OriginalValue & vbCrLf 
                strMsg = strMsg & vbCrLf & "Original value has been restored." 
                   
                MsgBox strMsg, vbOKOnly, _ 
                      "Conflict " & objRs1.AbsolutePosition & _ 
                      " of " & intConflicts 
                   
                objRs1("Phone").Value = objRs1("Phone").OriginalValue 
                objRs1.MoveNext 
            Wend 
             
            objRs1.UpdateBatch adAffectGroup 
        Else 
            'Other error occurred. Minimal handling in this example. 
             strMsg = "Errors occurred during the update. " & _ 
                        objRs1.ActiveConnection.Errors(0).Number & " " & _ 
                        objRs1.ActiveConnection.Errors(0).Description 
        End If 
         
        On Error GoTo 0 
    End If 
     
    objRs1.MoveFirst 
     
    'Clean up 
    objRs1.Close 
    Set objRs1 = Nothing 
    Exit Sub 
     
ErrHandler: 
    
    If Not objRs1 Is Nothing Then 
        If objRs1.State = adStateOpen Then objRs1.Close 
        Set objRs1 = Nothing 
    End If 
     
    If Not objRs2 Is Nothing Then 
        If objRs2.State = adStateOpen Then objRs2.Close 
        Set objRs2 = Nothing 
    End If 
     
    If Err <> 0 Then 
        MsgBox Err.Source & "-->" & Err.Description, , "Error" 
    End If 
     
'EndConflicts 
```

<span data-ttu-id="60c47-128">可以使用当前 **Record** 或特定 **Field** 的 **Status** 属性来确定已发生何种冲突。</span><span class="sxs-lookup"><span data-stu-id="60c47-128">You can use the **Status** property of the current **Record** or of a specific **Field** to determine what kind of a conflict has occurred.</span></span>

<span data-ttu-id="60c47-129">有关错误处理的更详细信息，请参阅[第 6 章：错误处理](chapter-6-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="60c47-129">For more detailed information on error handling, see [Chapter 6: Error Handling](chapter-6-error-handling.md).</span></span>

