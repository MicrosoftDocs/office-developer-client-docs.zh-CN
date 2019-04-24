---
title: Recordset2 属性 (DAO)
TOCTitle: Bookmark Property
ms:assetid: 7366d550-2f72-ed10-b230-eb144a6f874b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195857(v=office.15)
ms:contentKeyID: 48545637
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 31791e9fb3c7081989232e36a90b184ed7e31866
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307446"
---
# <a name="recordset2bookmark-property-dao"></a>Recordset2 属性 (DAO)


**适用于**：Access 2013、Office 2013

设置或返回一个书签，该书签唯一地标识 **Recordset** 对象中的当前记录。

## <a name="syntax"></a>语法

*表达式*。书签

*表达式*一个代表**Recordset2**对象的变量。

## <a name="remarks"></a>注解

对于完全基于 Microsoft Access 数据库引擎表的**Recordset**对象, **Bookmarkable**属性的值为 True, 您可以将**Bookmark**属性与该 recordset 一起使用。 但是，其他数据库产品可能不支持书签。 例如，如果有任何 **Recordset2** 对象基于链接的 Paradox 表，而该表没有主键，则您不能在此对象中使用书签。

当创建或打开 **Recordset** 对象时，它的每条记录都已经有一个唯一的书签。可以通过将 **Bookmark** 属性的值赋给一个变量，来保存当前记录的书签。若要在移动到不同的记录后随时快速返回到该记录，请将 **Recordset** 对象的 **Bookmark** 属性设置为该变量的值。

可建立的书签数没有限制。若要为当前记录以外的其他记录创建书签，需移到相应的记录，然后将 **Bookmark** 属性的值分配给标识此记录的 **String** 变量。

若要确保 **Recordset** 对象支持书签，请在使用 **Bookmark** 属性之前，检查该对象的 **[Bookmarkable](recordset2-bookmarkable-property-dao.md)** 属性的值。 如果**Bookmarkable**属性为 False, 则**Recordset**对象不支持书签, 并且使用**Bookmark**属性将导致可捕获的错误。

如果使用 **[Clone](recordset2-clone-method-dao.md)** 方法创建 **Recordset** 对象的副本，原始和重复 **Recordset** 对象的 **Bookmark** 属性设置是完全相同的，二者可以互换。不过，不能将不同 **Recordset** 对象的书签交换使用，即使它们是使用相同的对象或 SQL 语句创建的也不行。

如果将 **Bookmark** 属性设置为表示已删除的记录的值，则会发生可捕获的错误。

**Bookmark** 属性值的不同于记录编号。

## <a name="example"></a>示例

以下示例使用 **Bookmark** 和 **Bookmarkable** 属性，使用户可以对记录集中的记录加标记，稍后再返回到此记录。

```vb
    Sub BookmarkX() 
     
     Dim dbsNorthwind As Database 
     Dim rstCategories As Recordset2 
     Dim strMessage As String 
     Dim intCommand As Integer 
     Dim varBookmark As Variant 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstCategories = _ 
     dbsNorthwind.OpenRecordset("Categories", _ 
     dbOpenSnapshot) 
     
     With rstCategories 
     
     If .Bookmarkable = False Then 
     Debug.Print "Recordset is not Bookmarkable!" 
     Else 
     ' Populate Recordset. 
     .MoveLast 
     .MoveFirst 
     
     Do While True 
     ' Show information about current record and get 
     ' user input. 
     strMessage = "Category: " & !CategoryName & _ 
     " (record " & (.AbsolutePosition + 1) & _ 
     " of " & .RecordCount & ")" & vbCr & _ 
     "Enter command:" & vbCr & _ 
     "[1 - next / 2 - previous /" & vbCr & _ 
     "3 - set bookmark / 4 - go to bookmark]" 
     intCommand = Val(InputBox(strMessage)) 
     
     Select Case intCommand 
     ' Move forward or backward, trapping for BOF 
     ' or EOF. 
     Case 1 
     .MoveNext 
     If .EOF Then .MoveLast 
     Case 2 
     .MovePrevious 
     If .BOF Then .MoveFirst 
     
     ' Store the bookmark of the current record. 
     Case 3 
     varBookmark = .Bookmark 
     
     ' Go to the record indicated by the stored 
     ' bookmark. 
     Case 4 
     If IsEmpty(varBookmark) Then 
     MsgBox "No Bookmark set!" 
     Else 
     .Bookmark = varBookmark 
     End If 
     
     Case Else 
     Exit Do 
     End Select 
     
     Loop 
     
     End If 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

以下示例使用 **LastModified** 属性将当前记录指针移动到已修改的记录和新创建的记录。

```vb
    Sub LastModifiedX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset2 
     Dim strFirst As String 
     Dim strLast As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     With rstEmployees 
     ' Store current data. 
     strFirst = !FirstName 
     strLast = !LastName 
     ' Change data in current record. 
     .Edit 
     !FirstName = "Julie" 
     !LastName = "Warren" 
     .Update 
     ' Move current record pointer to the most recently 
     ' changed or added record. 
     .Bookmark = .LastModified 
     Debug.Print _ 
     "Data in LastModified record after Edit: " & _ 
     !FirstName & " " & !LastName 
     
     ' Restore original data because this is a demonstration. 
     .Edit 
     !FirstName = strFirst 
     !LastName = strLast 
     .Update 
     
     ' Add new record. 
     .AddNew 
     !FirstName = "Roger" 
     !LastName = "Harui" 
     .Update 
     ' Move current record pointer to the most recently 
     ' changed or added record. 
     .Bookmark = .LastModified 
     Debug.Print _ 
     "Data in LastModified record after AddNew: " & _ 
     !FirstName & " " & !LastName 
     
     ' Delete new record because this is a demonstration. 
     .Delete 
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub
```
