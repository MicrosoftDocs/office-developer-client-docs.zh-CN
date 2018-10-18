---
<<<<<<< 标头标题： 说明，HelpContext HelpFile 属性示例 (VB) TOCTitle: Description、 HelpContext、 HelpFile、 NativeError、 号码、 源和 SQLState 属性示例 (VB) === 标题: 说明，HelpFile 属性示例 (VB) HelpContext TOCTitle: Description、 HelpContext、 HelpFile、 NativeError、 号码、 源和 SQLState 属性示例 (VB)
>>>>>>> 母版页 ms:assetid: 3c129aec-cd69-5822-4dad-ebef226538e1 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249156(v=office.15) ms:contentKeyID: 48544304 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="description-helpcontext-helpfile-nativeerror-number-source-and-sqlstate-properties-example-vb"></a>Description、HelpContext、HelpFile、NativeError、Number、Source 和 SQLState 属性示例 (VB)
=======
# <a name="description-helpcontext-helpfile-nativeerror-number-source-and-sqlstate-properties-example-vb"></a>Description、 HelpContext、 HelpFile、 NativeError、 号码、 源和 SQLState 属性示例 (VB)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

此示例触发一个错误，将其捕获，并显示产生的 [Error](description-property-ado.md) 对象的 [Description](helpcontext-helpfile-properties-ado.md)、[HelpContext](helpcontext-helpfile-properties-ado.md)、[HelpFile](nativeerror-property-ado.md)、[NativeError](number-property-ado.md)、[Number](source-property-ado-error.md)、[Source](sqlstate-property-ado.md) 和 [SQLState](error-object-ado.md) 属性。

```vb
    'BeginDescriptionVB
    Public Sub Main()
    
        Dim Cnxn As ADODB.Connection
        Dim Err As ADODB.Error
        Dim strError As String
        
        On Error GoTo ErrorHandler
        
        ' Intentionally trigger an error
        Set Cnxn = New ADODB.Connection
        Cnxn.Open "nothing"
        
        Set Cnxn = Nothing
        Exit Sub
    
    ErrorHandler:
    
        ' Enumerate Errors collection and display
        ' properties of each Error object
        For Each Err In Cnxn.Errors
            strError = "Error #" & Err.Number & vbCr & _
                "   " & Err.Description & vbCr & _
                "   (Source: " & Err.Source & ")" & vbCr & _
                "   (SQL State: " & Err.SQLState & ")" & vbCr & _
                "   (NativeError: " & Err.NativeError & ")" & vbCr
            If Err.HelpFile = "" Then
                strError = strError & "   No Help file available"
            Else
                strError = strError & _
                   "   (HelpFile: " & Err.HelpFile & ")" & vbCr & _
                   "   (HelpContext: " & Err.HelpContext & ")" & _
                   vbCr & vbCr
            End If
             
            Debug.Print strError
        Next
    
        Resume Next
    End Sub
    'EndDescriptionVB
```
