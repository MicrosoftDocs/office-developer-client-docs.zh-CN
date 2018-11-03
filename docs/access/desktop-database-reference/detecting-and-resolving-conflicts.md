---
title: 检测和解决冲突
TOCTitle: Detecting and resolving conflicts
ms:assetid: 8299745b-e595-21d5-26c1-a078d00a1c0c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249566(v=office.15)
ms:contentKeyID: 48545983
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c267f33577f3fb2a8d586d33949325517bcc16ba
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944415"
---
# <a name="detecting-and-resolving-conflicts"></a>检测和解决冲突

**适用于**： Access 2013、 Office 2013

## <a name="detecting-and-resolving-conflicts"></a>检测和解决冲突

如果在立即模式下处理 **Recordset** ，则很少会发生并发性问题。另一方面，如果应用程序使用批模式更新，则很容易遇到一个用户对记录进行的编辑尚未保存时另一个用户却更改同一记录的情况。这种情况下，您需要应用程序合理地处理冲突。您可能希望最后一个向服务器发送更新的人"获胜"，也可能希望让最后编辑数据的用户在两个冲突值之间做出选择，以便由该用户决定哪个更新应当优先。

无论是哪种情况，都可以使用 ADO 提供的 **Field** 对象的 **UnderlyingValue** 和 **OriginalValue** 属性来处理这些类型的冲突。这些属性需要与 **Recordset** 的 **Resync** 方法和 **Filter** 属性组合使用。

## <a name="detecting-errors"></a>检测错误

在批更新期间，当 ADO 遇到冲突时，会将警告放在 **Errors** 集合中。因此，在调用 **BatchUpdate** 之后，应当始终立即检查是否有错误，如果发现错误，则开始对已遇到冲突的假设进行测试。第一步是将 **Recordset** 的 **Filter** 属性设置为等于 **adFilterConflictingRecords** （前一章讨论了 **Filter** 属性）。这将使 **Recordset** 中只有那些发生冲突的记录可见。如果此步骤之后 **RecordCount** 属性等于零，则可以知道错误是由冲突以外的其他原因引起的。

调用 **BatchUpdate** 时，ADO 和提供程序将生成 SQL 语句以便对数据源执行更新。请记住，对于在 WHERE 子句中可以使用的列类型，某些数据源会有限制。

接下来，调用**Resync**方法在**Recordset**上设置为等于**adAffectGroup** *AffectRecords*参数而*ResyncValues*参数设置为等于**adResyncUnderlyingValues**。 **Resync** 方法将从基础数据库刷新当前 **Recordset** 对象中的数据。 通过使用 **adAffectGroup** ，可以确保只有那些使用当前筛选器设置时可见的记录（即只有冲突记录）才会与数据库重新同步。 如果处理大型 **Recordset** ，这将导致巨大的性能差异。 通过调用**Resync**时， *ResyncValues*参数设置为**adResyncUnderlyingValues** ，确保**UnderlyingValue**属性将包含从数据库 （冲突） 值的**值**按用户输入的值和**OriginalValue**属性将保留为字段 （发起的最后一个成功**UpdateBatch**呼叫之前的值） 的原始值，将保持属性。 然后，可以使用这些值通过编程来解决冲突，或要求用户选择将使用的值。

以下代码示例显示了此技术。该示例将在调用 **UpdateBatch** 之前使用独立的 **Recordset** 来更改基础表中的值，从而人为制造冲突。

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

可以使用当前 **Record** 或特定 **Field** 的 **Status** 属性来确定已发生何种冲突。

有关错误处理的更详细信息，请参阅[第 6 章：错误处理](chapter-6-error-handling.md)。

