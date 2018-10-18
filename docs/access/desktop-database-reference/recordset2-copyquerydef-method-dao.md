---
title: Recordset2.CopyQueryDef Method (DAO)
TOCTitle: CopyQueryDef Method
ms:assetid: 36689ac0-f8a6-1f3e-4170-799141373777
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192474(v=office.15)
ms:contentKeyID: 48544170
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053073
f1_categories:
- Office.Version=v15
ms.openlocfilehash: e70093a6678a61874462ec3517f6424e5da79f71
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605581"
---
# <a name="recordset2copyquerydef-method-dao"></a>Recordset2.CopyQueryDef Method (DAO)


**适用于**： Access 2013 |Office 2013 

返回一个**QueryDef**的副本的**[QueryDef](querydef-object-dao.md)** 对象用于创建**[Recordset](recordset-object-dao.md)** 对象表示由 recordset 占位符 （仅限 Microsoft Access 工作区）。 .

## <a name="syntax"></a>语法

*表达式*。CopyQueryDef

*表达式*一个表示**Recordset2**对象的变量。

<<<<<<< 标头
### <a name="return-value"></a>返回值
=======
### <a name="return-value"></a>返回值
>>>>>>> master

QueryDef

## <a name="remarks"></a>注解

可以使用 **CopyQueryDef** 方法创建一个新的 **QueryDef**，该对象是用于创建 **Recordset** 的 **QueryDef** 的副本。

如果没有使用 **QueryDef** 创建此 **Recordset**，将会发生错误。使用 **CopyQueryDef** 方法之前，必须首先使用 **OpenRecordset** 方法打开 **Recordset**。

如果从 **QueryDef** 创建了一个 **Recordset** 对象，然后将 **Recordset** 传递给了一个函数，则使用此方法十分有用，函数必须重新创建查询的 SQL 等效项，例如，以某种方式对它进行修改。

## <a name="example"></a>示例

以下示例使用 **CopyQueryDef** 方法从现有的 **Recordset** 创建 **QueryDef** 的副本，然后通过向 SQL 属性添加子句，对副本进行修改。创建了永久的 **QueryDef** 后，可以向 SQL 属性添加空格、分号或换行符。只有在删除这些额外的字符之后，才可以将任何新子句附加到 SQL 语句。

```vb
    Function CopyQueryNew(rstTemp As Recordset, _ 
     strAdd As String) As QueryDef 
     
     Dim strSQL As String 
     Dim strRightSQL As String 
     
     Set CopyQueryNew = rstTemp.CopyQueryDef 
     With CopyQueryNew 
     ' Strip extra characters. 
     strSQL = .SQL 
     strRightSQL = Right(strSQL, 1) 
     Do While strRightSQL = " " Or strRightSQL = ";" Or _ 
     strRightSQL = Chr(10) Or strRightSQL = vbCr 
     strSQL = Left(strSQL, Len(strSQL) - 1) 
     strRightSQL = Right(strSQL, 1) 
     Loop 
     .SQL = strSQL & strAdd 
     End With 
     
    End Function 
```     

<br/>

以下示例演示 CopyQueryNew() 可能的用法。

```vb
Sub CopyQueryDefX() 
 
 Dim dbsNorthwind As Database 
 Dim qdfEmployees As QueryDef 
 Dim rstEmployees As Recordset2 
 Dim intCommand As Integer 
 Dim strOrderBy As String 
 Dim qdfCopy As QueryDef 
 Dim rstCopy As Recordset 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 Set qdfEmployees = dbsNorthwind.CreateQueryDef( _ 
 "NewQueryDef", "SELECT FirstName, LastName, " & _ 
 "BirthDate FROM Employees") 
 Set rstEmployees = qdfEmployees.OpenRecordset( _ 
 dbOpenForwardOnly) 
 
 Do While True 
 intCommand = Val(InputBox( _ 
 "Choose field on which to order a new " & _ 
 "Recordset:" & vbCr & "1 - FirstName" & vbCr & _ 
 "2 - LastName" & vbCr & "3 - BirthDate" & vbCr & _ 
 "[Cancel - exit]")) 
 Select Case intCommand 
 Case 1 
 strOrderBy = " ORDER BY FirstName" 
 Case 2 
 strOrderBy = " ORDER BY LastName" 
 Case 3 
 strOrderBy = " ORDER BY BirthDate" 
 Case Else 
 Exit Do 
 End Select 
 Set qdfCopy = CopyQueryNew(rstEmployees, strOrderBy) 
 Set rstCopy = qdfCopy.OpenRecordset(dbOpenSnapshot, _ 
 dbForwardOnly) 
 With rstCopy 
 Do While Not .EOF 
 Debug.Print !LastName & ", " & !FirstName & _ 
 " - " & !BirthDate 
 .MoveNext 
 Loop 
 .Close 
 End With 
 Exit Do 
 Loop 
 
 rstEmployees.Close 
 ' Delete new QueryDef because this is a demonstration. 
 dbsNorthwind.QueryDefs.Delete qdfEmployees.Name 
 dbsNorthwind.Close 
 
End Sub 
 
```

