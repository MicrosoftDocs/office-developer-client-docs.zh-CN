---
title: Recordset.Update 方法 (DAO)
TOCTitle: Update Method
ms:assetid: aad4171a-da95-ed72-86b3-714615ea0ac8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821467(v=office.15)
ms:contentKeyID: 48546961
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0fa0b6897ea148a57cc17fcc0f908e2fdcae6b26
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465847"
---
# <a name="recordsetupdate-method-dao"></a>Recordset.Update 方法 (DAO)

**适用于**： Access 2013 |Office 2013

## <a name="syntax"></a>语法

*表达式*。更新 （***UpdateType***，***强制***）

*表达式*一个表示**Recordset**对象的变量。

### <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UpdateType</p></td>
<td><p>可选</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>一个 <strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong> 常量，指示"设置"中指定的更新类型（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p>Force</p></td>
<td><p>可选</p></td>
<td><p><strong>Boolean</strong></p></td>
<td><p>一个 <strong>Boolean</strong> 值，指示是否将更改强制到数据库中，而不管自从 <strong><a href="recordset-addnew-method-dao.md">AddNew</a></strong> 、 <strong><a href="fields-delete-method-dao.md">Delete</a></strong> 或 <strong><a href="recordset-edit-method-dao.md">Edit</a></strong> 调用以来，其他用户是否更改了基础数据。如果为 <strong>True</strong> ，则会强制更改，并且只是覆盖由其他用户所做的更改。如果为 <strong>False</strong> （默认值），在更新处于待定状态时由其他用户所做的更改将导致更改对冲突的更改失败。不发生错误，但是 <strong><a href="recordset-batchcollisioncount-property-dao.md">BatchCollisionCount</a></strong> 和 <strong><a href="recordset-batchcollisions-property-dao.md">BatchCollisions</a></strong> 属性将分别指示冲突数和受冲突影响的行数（仅适用于 ODBCDirect 工作区）。  </p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

使用 **Update** 可保存当前记录以及对它所做的任何更改。

> [!IMPORTANT]
> [!重要信息] 在以下情况下，对当前记录所做的更改将会丢失：
> - 使用了 **Edit** 或 **AddNew** 方法，然后在没有事先使用 **Update** 的情况下移到另一条记录。
> - 使用了 **Edit** 或 **AddNew** ，然后在没有事先使用 **Update** 的情况下再次使用 **Edit** 或 **AddNew** 。
> - 将 **[Bookmark](recordset-bookmark-property-dao.md)** 属性设置为另一条记录。
> - 在没有事先使用 **Update** 的情况下关闭了 **Recordset** 。
> - 使用 [**CancelUpdate**](recordset-cancelupdate-method-dao.md) 取消 **Edit** 操作。

要编辑一条记录，请使用 **Edit** 方法将当前记录的内容复制到复制缓冲区。如果不首先使用 **Edit** ，在使用 **Update** 或试图更改字段值时将会发生错误。

在 ODBCDirect 工作区中，如果游标库支持批更新，并且使用开放式批锁定选项打开了 **Recordset** ，则可以执行批更新。

在 Microsoft Access 工作区中，如果多用户环境中的 **Recordset** 对象的 **LockEdits** 属性设置为 **True** （悲观锁定），那么从使用 **Edit** 开始到执行了 **Update** 方法或取消了编辑的时间范围内，记录将保持锁定状态。 如果 **LockEdits** 属性设置为 **False** （乐观锁定），那会锁定此记录，并且在数据库中对它更新之前，将它与预编辑的记录进行比较。 

如果自从使用 **Edit** 方法之后记录发生了更改， **Update** 操作将会失败。 Microsoft Access 数据库引擎连接的 ODBC 和可安装的 ISAM 数据库始终使用乐观锁定。 若要使用更改继续 **Update** 操作，请再次使用 **Update** 方法。 若要恢复到其他用户记录更改它，刷新当前记录，请使用 Move 0。


> [!NOTE]
> [!注释] 若要添加、编辑或删除记录，基础数据源中的记录必须存在唯一索引。如果不存在此索引，在 Microsoft Access 工作区中， **AddNew** 、 **Delete** 或 **Edit** 方法调用将发生"权限被拒绝"错误，在 ODBCDirect 工作区中， **Update** 调用将发生"无效参数"错误。

## <a name="example"></a>示例

以下示例演示如何将 **Update** 方法与 **Edit** 方法一起使用。

```vb
    Sub UpdateX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim strOldFirst As String 
     Dim strOldLast As String 
     Dim strMessage As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     With rstEmployees 
     .Edit 
     ' Store original data. 
     strOldFirst = !FirstName 
     strOldLast = !LastName 
     ' Change data in edit buffer. 
     !FirstName = "Linda" 
     !LastName = "Kobara" 
     
     ' Show contents of buffer and get user input. 
     strMessage = "Edit in progress:" & vbCr & _ 
     " Original data = " & strOldFirst & " " & _ 
     strOldLast & vbCr & " Data in buffer = " & _ 
     !FirstName & " " & !LastName & vbCr & vbCr & _ 
     "Use Update to replace the original data with " & _ 
     "the buffered data in the Recordset?" 
     
     If MsgBox(strMessage, vbYesNo) = vbYes Then 
     .Update 
     Else 
     .CancelUpdate 
     End If 
     
     ' Show the resulting data. 
     MsgBox "Data in recordset = " & !FirstName & " " & _ 
     !LastName 
     
     ' Restore original data because this is a demonstration. 
     If Not (strOldFirst = !FirstName And _ 
     strOldLast = !LastName) Then 
     .Edit 
     !FirstName = strOldFirst 
     !LastName = strOldLast 
     .Update 
     End If 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

以下示例演示如何将 **Update** 方法与 **AddNew** 方法一起使用。

```vb
    Sub UpdateX2() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim strOldFirst As String 
     Dim strOldLast As String 
     Dim strMessage As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     With rstEmployees 
     .AddNew 
     !FirstName = "Bill" 
     !LastName = "Sornsin" 
     
     ' Show contents of buffer and get user input. 
     strMessage = "AddNew in progress:" & vbCr & _ 
     " Data in buffer = " & !FirstName & " " & _ 
     !LastName & vbCr & vbCr & _ 
     "Use Update to save buffer to recordset?" 
     
     If MsgBox(strMessage, vbYesNoCancel) = vbYes Then 
     .Update 
     ' Go to the new record and show the resulting data. 
     .Bookmark = .LastModified 
     MsgBox "Data in recordset = " & !FirstName & _ 
     " " & !LastName 
     ' Delete new data because this is a demonstration. 
     .Delete 
     Else 
     .CancelUpdate 
     MsgBox "No new record added." 
     End If 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

以下示例使用 **BatchCollisionCount** 属性和 **Update** 方法演示批更新，在其中通过强制批更新来解决任何冲突。

```vb 
Sub BatchX() 
 
 Dim wrkMain As Workspace 
 Dim conMain As Connection 
 Dim rstTemp As Recordset 
 Dim intLoop As Integer 
 Dim strPrompt As String 
 
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
 ' batch updating. It is also required that a table 
 ' with a primary key is used. 
 Set rstTemp = conMain.OpenRecordset( _ 
 "SELECT * FROM roysched", dbOpenDynaset, 0, _ 
 dbOptimisticBatch) 
 
 With rstTemp 
 ' Modify data in local recordset. 
 Do While Not .EOF 
 .Edit 
 If !royalty <= 20 Then 
 !royalty = !royalty - 4 
 Else 
 !royalty = !royalty + 2 
 End If 
 .Update 
 .MoveNext 
 Loop 
 
 ' Attempt a batch update. 
 .Update dbUpdateBatch 
 
 ' If there are collisions, give the user the option 
 ' of forcing the changes or resolving them 
 ' individually. 
 If .BatchCollisionCount > 0 Then 
 strPrompt = "There are collisions. " & vbCr & _ 
 "Do you want the program to force " & _ 
 vbCr & "an update using the local data?" 
 If MsgBox(strPrompt, vbYesNo) = vbYes Then _ 
 .Update dbUpdateBatch, True 
 End If 
 
 .Close 
 End With 
 
 conMain.Close 
 wrkMain.Close 
 
End Sub 
 
```

<br/>

以下示例使用 **AddNew** 方法创建一个具有指定名称的新记录。若要使该过程运行，需要使用 AddName 函数。

```vb
    Sub AddNewX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim strFirstName As String 
     Dim strLastName As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", dbOpenDynaset) 
     
     ' Get data from the user. 
     strFirstName = Trim(InputBox( _ 
     "Enter first name:")) 
     strLastName = Trim(InputBox( _ 
     "Enter last name:")) 
     
     ' Proceed only if the user actually entered something 
     ' for both the first and last names. 
     If strFirstName <> "" and strLastName <> "" Then 
     
     ' Call the function that adds the record. 
     AddName rstEmployees, strFirstName, strLastName 
     
     ' Show the newly added data. 
     With rstEmployees 
     Debug.Print "New record: " & !FirstName & _ 
     " " & !LastName 
     ' Delete new record because this is a demonstration. 
     .Delete 
     End With 
     
     Else 
     Debug.Print _ 
     "You must input a string for first and last name!" 
     End If 
     
     rstEmployees.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Function AddName(rstTemp As Recordset, _ 
     strFirst As String, strLast As String) 
     
     ' Adds a new record to a Recordset using the data passed 
     ' by the calling procedure. The new record is then made 
     ' the current record. 
     With rstTemp 
     .AddNew 
     !FirstName = strFirst 
     !LastName = strLast 
     .Update 
     .Bookmark = .LastModified 
     End With 
     
    End Function
```
