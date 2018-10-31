---
title: CopyRecord、CopyTo 和 SaveToFile 方法示例 (VB)
TOCTitle: CopyRecord, CopyTo, and SaveToFile methods example (VB)
ms:assetid: 97f9bdc5-acde-ef74-f96a-d2daeb252911
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249679(v=office.15)
ms:contentKeyID: 48546479
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3f17c0315016b6cd38ef0eda5c975b79047967ff
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861237"
---
# <a name="copyrecord-copyto-and-savetofile-methods-example-vb"></a>CopyRecord、CopyTo 和 SaveToFile 方法示例 (VB)


**适用于**： Access 2013 |Office 2013

<<<<<<< 头本示例演示如何创建使用[流](stream-object-ado.md)或[Record](record-object-ado.md)对象的文件的副本。 在 Web 文件夹中创建了一个副本，用于进行 Internet 发布。 还显示了其他属性和方法，包括 [Stream Type](type-property-ado-stream.md)、 **Open** 、 [LoadFromFile](loadfromfile-method-ado.md) 和 [Record Open](open-method-ado-record.md)。
=== 本示例演示如何创建使用[流](stream-object-ado.md)或[Record](record-object-ado.md)对象的文件的副本。 一个副本到 Internet 发布的 web 文件夹。 还显示了其他属性和方法，包括 [Stream Type](type-property-ado-stream.md)、 **Open** 、 [LoadFromFile](loadfromfile-method-ado.md) 和 [Record Open](open-method-ado-record.md)。
>>>>>>> 母版

```vb 
 
'BeginCopyRecordVB 
 
'Note: 
' This sample requires that "C:\checkmrk.wmf" and 
' "https://MyServer/mywmf.wmf" exist. 
 
Option Explicit 
 
Private Sub Form_Load() 
 On Error GoTo ErrorHandler 
 
 ' Declare variables 
 Dim strPicturePath, strStreamPath, strStream2Path, _ 
 strRecordPath, strStreamURL, strRecordURL As String 
 Dim objStream, objStream2 As Stream 
 Dim objRecord As Record 
 Dim objField As Field 
 
 ' Instantiate objects 
 Set objStream = New Stream 
 Set objStream2 = New Stream 
 Set objRecord = New Record 
 
 ' Initialize path and URL strings 
 strPicturePath = "C:\checkmrk.wmf" 
 strStreamPath = "C:\mywmf.wmf" 
 strStreamURL = "URL=https://MyServer/mywmf.wmf" 
 strStream2Path = "C:\checkmrk2.wmf" 
 strRecordPath = "C:\mywmf.wmf" 
 strRecordURL = "https://MyServer/mywmf2.wmf" 
 
 ' Load the file into the stream 
 objStream.Open 
 objStream.Type = adTypeBinary 
 objStream.LoadFromFile (strPicturePath) 
 
 ' Save the stream to a new path and filename 
 objStream.SaveToFile strStreamPath, adSaveCreateOverWrite 
 
 ' Copy the contents of the first stream to a second stream 
 objStream2.Open 
 objStream2.Type = adTypeBinary 
 objStream.CopyTo objStream2 
 
 ' Save the second stream to a different path 
 objStream2.SaveToFile strStream2Path, adSaveCreateOverWrite 
 
<<<<<<< HEAD
 ' Because strStreamPath is a Web Folder, open a Record on the URL 
=======
 ' Because strStreamPath is a web folder, open a Record on the URL 
>>>>>>> master
 objRecord.Open "", strStreamURL 
 
 ' Display the Fields of the record 
 For Each objField In objRecord.Fields 
 Debug.Print objField.Name & ": " & objField.Value 
 Next 
 
 ' Copy the record to a new URL 
 objRecord.CopyRecord "", strRecordURL, , , adCopyOverWrite 
 
 ' Load each copy of the graphic into Image controls for viewing 
 Image1.Picture = LoadPicture(strPicturePath) 
 Image2.Picture = LoadPicture(strStreamPath) 
 Image3.Picture = LoadPicture(strStream2Path) 
 Image4.Picture = LoadPicture(strRecordPath) 
 
 ' clean up 
 objStream.Close 
 objStream2.Close 
 objRecord.Close 
 Set objStream = Nothing 
 Set objStream2 = Nothing 
 Set objRecord = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not objStream Is Nothing Then 
 If objStream.State = adStateOpen Then objStream.Close 
 End If 
 Set objStream = Nothing 
 
 If Not objStream2 Is Nothing Then 
 If objStream2.State = adStateOpen Then objStream2.Close 
 End If 
 Set objStream2 = Nothing 
 
 If Not objRecord Is Nothing Then 
 If objRecord.State = adStateOpen Then objRecord.Close 
 End If 
 Set objRecord = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndCopyRecordVB 
```

