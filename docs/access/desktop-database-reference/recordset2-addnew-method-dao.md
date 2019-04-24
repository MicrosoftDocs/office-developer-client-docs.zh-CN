---
title: Recordset2 方法 (DAO)
TOCTitle: AddNew Method
ms:assetid: 25c7d207-185c-943b-405e-b138ffb8b3e2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191874(v=office.15)
ms:contentKeyID: 48543792
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 49a69b5e8603e72faaba480ea9069d3668bd6de1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307495"
---
# <a name="recordset2addnew-method-dao"></a>Recordset2 方法 (DAO)

**适用于**：Access 2013、Office 2013
 
为可更新的 **Recordset2** 对象创建新记录。

## <a name="syntax"></a>语法

*表达式*。AddNew

*表达式*一个代表**Recordset2**对象的变量。

## <a name="remarks"></a>注解

使用 **AddNew** 方法在记录集命名的 **Recordset2** 对象中创建和添加新记录。此方法将字段设置为默认值，如果未指定默认值，它将字段设置为 Null（为表类型 **Recordset2** 指定的默认值）。

修改新记录后，请使用 **[Update](recordset2-update-method-dao.md)** 方法保存更改，并将记录添加到 **Recordset2**。在使用 **Update** 方法之前，数据库中不发生更改。

> [!NOTE]
> [!注释] 如果发出了 **AddNew**，然后执行了转移到另一条记录的任何操作，但是没有使用 **Update**，则更改将会丢失且不发出警告。此外，如果关闭 **Recordset2**，或者结束声明 **Recordset2** 或其 **[Database](database-object-dao.md)** 对象的过程，则会放弃新记录且不发出警告。

> [!NOTE]
> [!注释] 如果在 Microsoft Access 工作区中使用 **AddNew**，并且数据库引擎必须创建一个新页面以保存当前记录，则页面锁定是悲观的。如果新记录适合现有页面，则页面锁定是乐观的。

如果没有移到 **Recordset2** 的最后一条记录，并且由其他过程添加到基表的记录位于当前记录的上方，则包括这些添加的记录。但是，如果向自己的 **Recordset2** 添加了记录，则该记录将在 **Recordset2** 中可见，并且将包括在基础表中，基础表中的记录对任何新的 **Recordset2** 对象可见。

新记录的位置取决于 **Recordset2** 的类型：

- 在动态集类型 **Recordset2** 对象中，记录将插在 **Recordset** 的末尾，而不管打开 **Recordset** 时的排序或顺序规则如何。

- 在已设置 [**Index**](recordset2-index-property-dao.md) 属性的表类型 **Recordset2** 对象中，记录将按排序次序在正确的位置返回。如果没有设置 **Index** 属性，新记录将在 **Recordset** 的末尾返回。

在使用 **AddNew** 之前处于当前的记录仍然为当前记录。如果想要使新记录成为当前记录，可将 **[Bookmark](recordset2-bookmark-property-dao.md)** 属性设置为 **[LastModified](recordset2-lastmodified-property-dao.md)** 属性设置所标识的书签。

> [!NOTE]
> [!注释] 若要添加、编辑或删除记录，基础数据源中的记录必须存在唯一索引。如果不存在此索引，在 Microsoft Access 工作区中， **AddNew**、 **Delete** 或 **Edit** 方法调用将发生"权限被拒绝"错误。

## <a name="example"></a>示例

以下示例使用 **AddNew** 方法创建一个具有指定名称的新记录。若要使该过程运行，需要使用 AddName 函数。

```vb
    Sub AddNewX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset2 
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
     
    Function AddName(rstTemp As Recordset2, _ 
     strFirst As String, strLast As String) 
     
     ' Adds a new record to a recordset using the data passed 
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
