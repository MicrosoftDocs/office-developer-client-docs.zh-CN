---
title: Recordset2.Edit 方法 (DAO)
TOCTitle: Edit Method
ms:assetid: 34c51eee-274d-3511-b5e2-cb74e4925ec8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192452(v=office.15)
ms:contentKeyID: 48544137
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052869
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 8fbbbe147c4c943044123b711ffb3361af5284cf
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928234"
---
# <a name="recordset2edit-method-dao"></a>Recordset2.Edit 方法 (DAO)


**适用于**： Access 2013、 Office 2013

将当前记录从可更新的 **[Recordset](recordset-object-dao.md)** 对象复制到复制缓冲区，以进行后续编辑。

## <a name="syntax"></a>语法

*表达式*。编辑

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

一旦使用 **Edit** 方法，对当前记录的字段所做的更改将被复制到复制缓冲区。对记录执行所需的更改后，使用 **[Update](recordset2-update-method-dao.md)** 方法保存更改。

使用 **Edit** 方法后，当前记录仍为当前记录。


> [!NOTE]
> <P>[!注释] 如果在编辑某条记录后执行了转移到另一条记录的任何操作，但是没有事先使用 <STRONG>Update</STRONG>，则更改将会丢失且不发出警告。 此外，如果您关闭 recordset 或结束声明<STRONG>记录集</STRONG>或父<STRONG><A href="database-object-dao.md">数据库</A></STRONG>或<STRONG><A href="connection-object-dao.md">连接</A></STRONG>对象的过程，您已编辑的记录将不警告的情况下被丢弃。</P>



在以下条件下，使用 **Edit** 将产生错误：

  - 没有当前记录。

  - 以只读方式打开了 **Connection**、 **Database** 或 **Recordset** 对象。

  - 记录中没有可更新的字段。

  - 打开的 **Database** 或 **Recordset** 被另一个用户独占使用（Microsoft Access 工作区）。

  - 另一个用户锁定了包含您的记录的页面（Microsoft Access 工作区）。

在 Microsoft Access 工作区中，如果多用户环境中的 **Recordset** 对象的 **[LockEdits](recordset2-lockedits-property-dao.md)** 属性设置为 **True**（悲观锁定），那么从开始使用 **Edit** 到完成更新的时间范围内，记录将保持锁定状态。如果 **LockEdits** 属性设置为 **False**（乐观锁定），则会锁定此记录，并且在数据库中对它更新之前，将它与预编辑的记录进行比较。如果自从使用 **Edit** 方法之后记录发生了更改，并且使用了 **OpenRecordset** 且没有指定 **dbSeeChanges**， **Update** 操作将会失败，同时返回运行时错误。默认情况下，Microsoft Access 数据库引擎连接的 ODBC 和可安装的 ISAM 数据库始终使用乐观锁定。


> [!NOTE]
> <P>[!注释] 若要添加、编辑或删除记录，基础数据源中的记录必须存在唯一索引。如果不存在此索引，在 Microsoft Access 工作区中， <STRONG><A href="recordset2-addnew-method-dao.md">AddNew</A></STRONG> 、 <STRONG><A href="fields-delete-method-dao.md">Delete</A></STRONG> 或 <STRONG>Edit</STRONG> 方法调用将发生"权限被拒绝"错误。</P>



## <a name="example"></a>示例

以下示例使用 **Edit** 方法，将当前数据替换为指定的名称。若要使该过程运行，需要使用 EditName 过程。

```vb
    Sub EditX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset2 
     Dim strOldFirst As String 
     Dim strOldLast As String 
     Dim strFirstName As String 
     Dim strLastName As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     ' Store original data. 
     strOldFirst = rstEmployees!FirstName 
     strOldLast = rstEmployees!LastName 
     
     ' Get new data for record. 
     strFirstName = Trim(InputBox( _ 
     "Enter first name:")) 
     strLastName = Trim(InputBox( _ 
     "Enter last name:")) 
     
     ' Proceed if the user entered something for both fields. 
     If strFirstName <> "" and strLastName <> "" Then 
     ' Update record with new data. 
     EditName rstEmployees, strFirstName, strLastName 
     
     With rstEmployees 
     ' Show old and new data. 
     Debug.Print "Old data: " & strOldFirst & _ 
     " " & strOldLast 
     Debug.Print "New data: " & !FirstName & _ 
     " " & !LastName 
     ' Restore original data because this is a 
     ' demonstration. 
     .Edit 
     !FirstName = strOldFirst 
     !LastName = strOldLast 
     .Update 
     End With 
     
     Else 
     Debug.Print _ 
     "You must input a string for first and last name!" 
     End If 
     
     rstEmployees.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Sub EditName(rstTemp As Recordset2, _ 
     strFirst As String, strLast As String) 
     
     ' Make changes to record and set the bookmark to keep 
     ' the same record current. 
     With rstTemp 
     .Edit 
     !FirstName = strFirst 
     !LastName = strLast 
     .Update 
     .Bookmark = .LastModified 
     End With 
     
    End Sub
```
