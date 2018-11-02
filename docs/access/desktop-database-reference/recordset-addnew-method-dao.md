---
title: Recordset.AddNew 方法 (DAO)
TOCTitle: AddNew Method
ms:assetid: 18cb35f6-8652-fb20-2460-3d13fae39d23
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845624(v=office.15)
ms:contentKeyID: 48543483
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052883
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b07717a209fdb0152964bcd33d228d17cecd4eec
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922347"
---
# <a name="recordsetaddnew-method-dao"></a>Recordset.AddNew 方法 (DAO)


**适用于**： Access 2013、 Office 2013

为可更新的 **[Recordset](recordset-object-dao.md)** 对象创建新记录。

## <a name="syntax"></a>语法

*表达式*。AddNew

*表达式*一个表示**Recordset**对象的变量。

## <a name="remarks"></a>注解

使用 **AddNew** 方法在记录集命名的 **Recordset** 对象中创建和添加新记录。此方法将字段设置为默认值，如果未指定默认值，它将字段设置为 Null（为表类型 **Recordset** 指定的默认值）。

修改新记录后，请使用 **[Update](recordset-update-method-dao.md)** 方法保存更改，并将记录添加到 **Recordset**。在使用 **Update** 方法之前，数据库中不发生更改。


> [!NOTE]
> <P>[!注释] 如果发出了 <STRONG>AddNew</STRONG>，然后执行了转移到另一条记录的任何操作，但是没有使用 <STRONG>Update</STRONG>，则更改将会丢失且不发出警告。此外，如果关闭 <STRONG>Recordset</STRONG>，或者结束声明 <STRONG>Recordset</STRONG> 或其 <STRONG><A href="database-object-dao.md">Database</A></STRONG> 对象的过程，则会放弃新记录且不发出警告。</P>




> [!NOTE]
> <P>[!注释] 如果在 Microsoft Access 工作区中使用 <STRONG>AddNew</STRONG>，并且数据库引擎必须创建一个新页面以保存当前记录，则页面锁定是悲观的。如果新记录适合现有页面，则页面锁定是乐观的。</P>



如果没有移到 **Recordset** 的最后一条记录，并且由其他过程添加到基表的记录位于当前记录的上方，则包括这些添加的记录。但是，如果向自己的 **Recordset** 添加了记录，则该记录将在 **Recordset** 中可见，并且将包括在基础表中，基础表中的记录对任何新的 **Recordset** 对象可见。

新记录的位置取决于 **Recordset** 的类型：

  - 在动态集类型 **Recordset** 对象中，记录将插在 **Recordset** 的末尾，而不管打开 **Recordset** 时应用的排序或顺序规则如何。

  - 在已设置 [**Index**](recordset-index-property-dao.md) 属性的表类型 **Recordset** 对象中，记录将按排序次序在正确的位置返回。如果没有设置 **Index** 属性，新记录将在 **Recordset** 的末尾返回。

在使用 **AddNew** 之前处于当前的记录仍然为当前记录。如果想要使新记录成为当前记录，可将 **[Bookmark](recordset-bookmark-property-dao.md)** 属性设置为 **[LastModified](recordset-lastmodified-property-dao.md)** 属性设置所标识的书签。


> [!NOTE]
> <P>[!注释] 若要添加、编辑或删除记录，基础数据源中的记录必须存在唯一索引。如果不存在此索引，在 Microsoft Access 工作区中， <STRONG>AddNew</STRONG>、 <STRONG>Delete</STRONG> 或 <STRONG>Edit</STRONG> 方法调用将发生"权限被拒绝"错误。</P>



## <a name="example"></a>示例

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
