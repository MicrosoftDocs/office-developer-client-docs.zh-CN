---
title: CreateRecordset 方法示例 (VB)
TOCTitle: CreateRecordset method example (VB)
ms:assetid: c1c05c91-0c74-1f30-7ead-6b52f0b4906c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249943(v=office.15)
ms:contentKeyID: 48547536
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 79d4bcb9547cdfd9b72dda71c8591a1ad009890b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295343"
---
# <a name="createrecordset-method-example-vb"></a>CreateRecordset 方法示例 (VB)


**适用于**：Access 2013、Office 2013

您可以创建一个 [Recordset](recordset-object-ado.md) 对象并指定列信息。然后，可以将数据插入到该 **Recordset** 对象中；基础行集将缓冲插入的内容。

下面的代码示例演示如何使用 **RDSServer.DataFactory** 对象来定义 [Recordset](datafactory-object-rdsserver.md) 。您也可以使用 [RDS.DataControl](datacontrol-object-rds.md) 对象来实现此目的。

```vb 
 
'BeginRsDefineShapeVB 
Sub Main() 
 On Error GoTo ErrorHandler 
 
 Dim ADF As RDSServer.DataFactory 
 Dim vntRecordShape(3) 
 Dim vntField1Shape(3) 
 Dim vntField2Shape(3) 
 Dim vntField3Shape(3) 
 Dim vntField4Shape(3) 
 
 Set ADF = New RDSServer.DataFactory 
 
 ' For each field, specify the name, 
 ' type, size, and nullability. 
 
 vntField1Shape(0) = "Name" ' Column name. 
 vntField1Shape(1) = CInt(129) ' Column type. 
 vntField1Shape(2) = CInt(40) ' Column size. 
 vntField1Shape(3) = False ' Nullable? 
 
 vntField2Shape(0) = "Age" 
 vntField2Shape(1) = CInt(3) 
 vntField2Shape(2) = CInt(-1) 
 vntField2Shape(3) = True 
 
 vntField3Shape(0) = "DateOfBirth" 
 vntField3Shape(1) = CInt(7) 
 vntField3Shape(2) = CInt(-1) 
 vntField3Shape(3) = True 
 
 vntField4Shape(0) = "Balance" 
 vntField4Shape(1) = CInt(6) 
 vntField4Shape(2) = CInt(-1) 
 vntField4Shape(3) = True 
 
 ' Put all fields into an array of arrays. 
 vntRecordShape(0) = vntField1Shape 
 vntRecordShape(1) = vntField2Shape 
 vntRecordShape(2) = vntField3Shape 
 vntRecordShape(3) = vntField4Shape 
 
 ' Use the RDSServer.DataFactory to create an empty 
 ' recordset. It takes an array of variants where 
 ' every element is itself another array of 
 ' variants, one for every column required in the 
 ' recordset. 
 ' The elements of the inner array are the column's 
 ' name, type, size, and nullability. 
 ' 
 ' NOTE: You could just use the RDS.DataControl object 
 ' instead of the RDSServer.DataFactory object. In 
 ' that case, the following code would be Set NewRS 
 ' = ADC1.CreateRecordset(vntRecordShape) 
 Dim NewRs As ADODB.Recordset 
 Set NewRs = ADF.CreateRecordSet(vntRecordShape) 
 
 Dim fields(3) 
 fields(0) = vntField1Shape(0) 
 fields(1) = vntField2Shape(0) 
 fields(2) = vntField3Shape(0) 
 fields(3) = vntField4Shape(0) 
 
 ' Populate the new recordset with data values. 
 Dim fieldVals(3) 
 
 ' Use AddNew to add the records. 
 fieldVals(0) = "Joe" 
 fieldVals(1) = 5 
 fieldVals(2) = CDate(#1/5/1996#) 
 fieldVals(3) = 123.456 
 NewRs.AddNew fields, fieldVals 
 
 fieldVals(0) = "Mary" 
 fieldVals(1) = 6 
 fieldVals(2) = CDate(#6/5/1996#) 
 fieldVals(3) = 31 
 NewRs.AddNew fields, fieldVals 
 
 fieldVals(0) = "Alex" 
 fieldVals(1) = 13 
 fieldVals(2) = CDate(#1/6/1996#) 
 fieldVals(3) = 34.0001 
 NewRs.AddNew fields, fieldVals 
 
 fieldVals(0) = "Susan" 
 fieldVals(1) = 13 
 fieldVals(2) = CDate(#8/6/1996#) 
 fieldVals(3) = 0# 
 NewRs.AddNew fields, fieldVals 
 
 NewRs.MoveFirst 
 
 ' Set the newly created and populated Recordset to 
 ' the SourceRecordset property of the 
 ' RDS.DataControl to bind to visual controls 
 Dim ADC1 As RDS.DataControl 
 Set ADC1 = New RDS.DataControl 
 Set ADC1.SourceRecordset = NewRs 
 
 'Clean up 
 If NewRs.State = adStateOpen Then NewRs.Close 
 Set NewRs = Nothing 
 Set ADC1 = Nothing 
 Set ADF = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not NewRs Is Nothing Then 
 If NewRs.State = adStateOpen Then NewRs.Close 
 End If 
 Set NewRs = Nothing 
 Set ADC1 = Nothing 
 Set ADF = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndRsDefineShapeVB 
```

