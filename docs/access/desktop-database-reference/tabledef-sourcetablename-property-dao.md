---
title: TableDef.SourceTableName 属性 (DAO)
TOCTitle: SourceTableName Property
ms:assetid: 3c02f5f6-70ae-39ec-0984-8d6b81992418
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192675(v=office.15)
ms:contentKeyID: 48544300
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052901
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: bd2610e728d97d3a9fc2f6359a42fd3cdccb11e5
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722548"
---
# <a name="tabledefsourcetablename-property-dao"></a>TableDef.SourceTableName 属性 (DAO)


**适用于**： Access 2013、 Office 2013 

设置或返回一个值，该值指定链接表或基表的名称（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。SourceTableName

*表达式*一个代表**TableDef**对象的变量。

## <a name="remarks"></a>注解

对于基表，该属性设置是只读的；对于链接表或未追加到集合中的对象，该属性设置是可读写的。对于基表，此设置为零长度字符串 ("")。

## <a name="example"></a>示例

以下示例使用 **Connect** 和 **SourceTableName** 属性将各种外部表链接到 Microsoft Access 数据库。若要使该过程运行，需要使用 ConnectOutput 过程。

```vb 
Sub ConnectX() 
 
 Dim dbsTemp As Database 
 Dim strMenu As String 
 Dim strInput As String 
 
 ' Open a Microsoft Access database to which you will link 
 ' a table. 
 Set dbsTemp = OpenDatabase("DB1.mdb") 
 
 ' Build menu text. 
 strMenu = "Enter number for data source:" & vbCr 
 strMenu = strMenu & _ 
 " 1. Microsoft Access database" & vbCr 
 strMenu = strMenu & _ 
 " 2. Microsoft FoxPro 3.0 table" & vbCr 
 strMenu = strMenu & _ 
 " 3. dBASE table" & vbCr 
 strMenu = strMenu & _ 
 " 4. Paradox table" & vbCr 
 strMenu = strMenu & _ 
 " M. (see choices 5-9)" 
 
 ' Get user's choice. 
 strInput = InputBox(strMenu) 
 
 If UCase(strInput) = "M" Then 
 
 ' Build menu text. 
 strMenu = "Enter number for data source:" & vbCr 
 strMenu = strMenu & _ 
 " 5. Microsoft Excel spreadsheet" & vbCr 
 strMenu = strMenu & _ 
 " 6. Lotus spreadsheet" & vbCr 
 strMenu = strMenu & _ 
 " 7. Comma-delimited text (CSV)" & vbCr 
 strMenu = strMenu & _ 
 " 8. HTML table" & vbCr 
 strMenu = strMenu & _ 
 " 9. Microsoft Exchange folder" 
 
 ' Get user's choice. 
 strInput = InputBox(strMenu) 
 
 End If 
 
 ' Call the ConnectOutput procedure. The third argument 
 ' will be used as the Connect string, and the fourth 
 ' argument will be used as the SourceTableName. 
 Select Case Val(strInput) 
 Case 1 
 ConnectOutput dbsTemp, _ 
 "AccessTable", _ 
 ";DATABASE=C:\My Documents\Northwind.mdb", _ 
 "Employees" 
 Case 2 
 ConnectOutput dbsTemp, _ 
 "FoxProTable", _ 
 "FoxPro 3.0;DATABASE=C:\FoxPro30\Samples", _ 
 "Q1Sales" 
 Case 3 
 ConnectOutput dbsTemp, _ 
 "dBASETable", _ 
 "dBase IV;DATABASE=C:\dBASE\Samples", _ 
 "Accounts" 
 Case 4 
 ConnectOutput dbsTemp, _ 
 "ParadoxTable", _ 
 "Paradox 3.X;DATABASE=C:\Paradox\Samples", _ 
 "Accounts" 
 Case 5 
 ConnectOutput dbsTemp, _ 
 "ExcelTable", _ 
 "Excel 5.0;" & _ 
 "DATABASE=C:\Excel\Samples\Q1Sales.xls", _ 
 "January Sales" 
 Case 6 
 ConnectOutput dbsTemp, _ 
 "LotusTable", _ 
 "Lotus WK3;" & _ 
 "DATABASE=C:\Lotus\Samples\Sales.xls", _ 
 "THIRDQTR" 
 Case 7 
 ConnectOutput dbsTemp, _ 
 "CSVTable", _ 
 "Text;DATABASE=C:\Samples", _ 
 "Sample.txt" 
 Case 8 
 ConnectOutput dbsTemp, _ 
 "HTMLTable", _ 
 "HTML Import;DATABASE=https://" & _ 
 "www.server1.com/samples/page1.html", _ 
 "Q1SalesData" 
 Case 9 
 ConnectOutput dbsTemp, _ 
 "ExchangeTable", _ 
 "Exchange 4.0;MAPILEVEL=" & _ 
 "Mailbox - Michelle Wortman (Exchange)" & _ 
 "|People\Important;", _ 
 "Jerry Wheeler" 
 End Select 
 
 dbsTemp.Close 
 
End Sub 
 
Sub ConnectOutput(dbsTemp As Database, _ 
 strTable As String, strConnect As String, _ 
 strSourceTable As String) 
 
 Dim tdfLinked As TableDef 
 Dim rstLinked As Recordset 
 Dim intTemp As Integer 
 
 ' Create a new TableDef, set its Connect and 
 ' SourceTableName properties based on the passed 
 ' arguments, and append it to the TableDefs collection. 
 Set tdfLinked = dbsTemp.CreateTableDef(strTable) 
 
 tdfLinked.Connect = strConnect 
 tdfLinked.SourceTableName = strSourceTable 
 dbsTemp.TableDefs.Append tdfLinked 
 
 Set rstLinked = dbsTemp.OpenRecordset(strTable) 
 
 Debug.Print "Data from linked table:" 
 
 ' Display the first three records of the linked table. 
 intTemp = 1 
 With rstLinked 
 Do While Not .EOF And intTemp <= 3 
 Debug.Print , .Fields(0), .Fields(1) 
 intTemp = intTemp + 1 
 .MoveNext 
 Loop 
 If Not .EOF Then Debug.Print , "[additional records]" 
 .Close 
 End With 
 
 ' Delete the linked table because this is a demonstration. 
 dbsTemp.TableDefs.Delete strTable 
 
End Sub 
 
```

