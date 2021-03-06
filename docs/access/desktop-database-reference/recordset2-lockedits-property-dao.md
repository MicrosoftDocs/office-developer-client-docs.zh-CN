---
title: LockEdits 属性 (DAO) Recordset2
TOCTitle: LockEdits Property
ms:assetid: 77055f44-f8e9-ac64-ecc3-144ddb4a4558
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196045(v=office.15)
ms:contentKeyID: 48545716
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ff2db22dcb0119792eb57a971d3cf36e763d3049
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309644"
---
# <a name="recordset2lockedits-property-dao"></a>LockEdits 属性 (DAO) Recordset2

**适用于**：Access 2013、Office 2013

设置或返回一个值，该值指示编辑时生效的锁定的类型。

## <a name="syntax"></a>语法

*表达式*。LockEdits

*表达式*一个代表**Recordset2**对象的变量。

## <a name="remarks"></a>注解

设置或返回值指示了锁定类型，如下表所示。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>True</p></td>
<td><p>默认值。悲观锁定生效。只要您调用了 Edit 方法，就会锁定包含正在编辑的记录的页。</p></td>
</tr>
<tr class="even">
<td><p>False</p></td>
<td><p>乐观锁定生效以便进行编辑。 在执行 Update 方法之前, 不会锁定包含该记录的页面。</p></td>
</tr>
</tbody>
</table>


可以将 **LockEdits** 属性用于可更新的 **[Recordset](recordset-object-dao.md)** 对象。

如果锁定了某页，其他用户不能编辑同一页上的记录。如果您将 **LockEdits** 设置为 **True**，而另一个用户已经锁定了该页，则当您使用 **Edit** 方法时会发生错误。其他用户可以从锁定的页中读取数据。

如果将 **LockEdits** 属性设置为 **False**，此后又使用 **Update** 方法，而此时另一个用户已经锁定了该页，则会发生错误。若要查看另一个用户对您的记录的更改，请使用包含 0 的 **[Move](recordset2-move-method-dao.md)** 方法作为参数；但是如果这样做，您将丢失所做的更改。

当使用 Microsoft Access 数据库引擎连接的 ODBC 数据源时， **LockEdits** 属性始终设置为 **False** 或乐观锁定。Microsoft Access 数据库引擎不对外部数据库服务器中使用的锁定机制进行控制。

> [!NOTE]
> 可以通过设置 **[OpenRecordset](connection-openrecordset-method-dao.md)** 方法的 lockedits 参数，在第一次打开 **Recordset** 时重置 **LockEdits** 的值。 将 lockedits 参数设置为 **dbPessimistic** 会将 **LockEdits** 属性设置为 **True**，将 lockedits 设置为任何其他值会将 **LockEdits** 属性设置为 **False**。

## <a name="example"></a>示例

以下示例通过将 **LockEdits** 属性设置为 **True** 来演示悲观锁定，然后通过将 **LockEdits** 属性设置为 False 来演示乐观锁定。它还演示为了修改字段，在多用户数据库环境下需要进行何种类型的错误处理。若要使该过程运行，需要使用 PessimisticLock 和 OptimisticLock 函数。

```vb
    Sub LockEditsX() 
     
     Dim dbsNorthwind As Database 
     Dim rstCustomers As Recordset2 
     Dim strOldName As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstCustomers = _ 
     dbsNorthwind.OpenRecordset("Customers", _ 
     dbOpenDynaset) 
     
     With rstCustomers 
     ' Store original data. 
     strOldName = !CompanyName 
     
     If MsgBox("Pessimistic locking demonstration...", _ 
     vbOKCancel) = vbOK Then 
     
     ' Attempt to modify data with pessimistic locking 
     ' in effect. 
     If PessimisticLock(rstCustomers, !CompanyName, _ 
     "Acme Foods") Then 
     MsgBox "Record successfully edited." 
     
     ' Restore original data... 
     .Edit 
     !CompanyName = strOldName 
     .Update 
     End If 
     
     End If 
     
     If MsgBox("Optimistic locking demonstration...", _ 
     vbOKCancel) = vbOK Then 
     
     ' Attempt to modify data with optimistic locking 
     ' in effect. 
     If OptimisticLock(rstCustomers, !CompanyName, _ 
     "Acme Foods") Then 
     MsgBox "Record successfully edited." 
     
     ' Restore original data... 
     .Edit 
     !CompanyName = strOldName 
     .Update 
     End If 
     
     End If 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function PessimisticLock(rstTemp As Recordset2, _ 
     fldTemp As Field, strNew As String) As Boolean 
     
     dim ErrLoop as Error 
     
     PessimisticLock = True 
     
     With rstTemp 
     .LockEdits = True 
     
     ' When you set LockEdits to True, you trap for errors 
     ' when you call the Edit method. 
     On Error GoTo Err_Lock 
     .Edit 
     On Error GoTo 0 
     
     ' If the Edit is still in progress, then no errors 
     ' were triggered; you may modify the data. 
     If .EditMode = dbEditInProgress Then 
     fldTemp = strNew 
     .Update 
     .Bookmark = .LastModified 
     Else 
     ' Retrieve current record to see changes made by 
     ' other user. 
     .Move 0 
     End If 
     
     End With 
     
     Exit Function 
     
    Err_Lock: 
     
     If DBEngine.Errors.Count > 0 Then 
     ' Enumerate the Errors collection. 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & _ 
     vbCr & errLoop.Description 
     Next errLoop 
     PessimisticLock = False 
     End If 
     
     Resume Next 
     
    End Function 
     
    Function OptimisticLock(rstTemp As Recordset, _ 
     fldTemp As Field, strNew As String) As Boolean 
     
     dim ErrLoop as Error 
     
     OptimisticLock = True 
     
     With rstTemp 
     .LockEdits = False 
     .Edit 
     fldTemp = strNew 
     
     ' When you set LockEdits to False, you trap for errors 
     ' when you call the Update method. 
     On Error GoTo Err_Lock 
     .Update 
     On Error GoTo 0 
     
     ' If there is no Edit in progress, then no errors were 
     ' triggered; you may modify the data. 
     If .EditMode = dbEditNone Then 
     ' Move current record pointer to the most recently 
     ' modified record. 
     .Bookmark = .LastModified 
     Else 
     .CancelUpdate 
     ' Retrieve current record to see changes made by 
     ' other user. 
     .Move 0 
     End If 
     
     End With 
     
     Exit Function 
     
    Err_Lock: 
     
     If DBEngine.Errors.Count > 0 Then 
     ' Enumerate the Errors collection. 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & _ 
     vbCr & errLoop.Description 
     Next errLoop 
     OptimisticLock = False 
     End If 
     
     Resume Next 
     
    End Function
```
