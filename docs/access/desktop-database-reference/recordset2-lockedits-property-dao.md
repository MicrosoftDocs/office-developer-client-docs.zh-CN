---
title: Recordset2.LockEdits Property (DAO)
TOCTitle: LockEdits Property
ms:assetid: 77055f44-f8e9-ac64-ecc3-144ddb4a4558
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196045(v=office.15)
ms:contentKeyID: 48545716
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c963e4dfe2c1d507845333b7c20efe23aaf050f6
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872527"
---
# <a name="recordset2lockedits-property-dao"></a><span data-ttu-id="28907-102">Recordset2.LockEdits Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="28907-102">Recordset2.LockEdits Property (DAO)</span></span>


<span data-ttu-id="28907-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="28907-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="28907-104">设置或返回一个值，该值指示编辑时生效的锁定的类型。</span><span class="sxs-lookup"><span data-stu-id="28907-104">Sets or returns a value indicating the type of locking that is in effect while editing.</span></span>

## <a name="syntax"></a><span data-ttu-id="28907-105">语法</span><span class="sxs-lookup"><span data-stu-id="28907-105">Syntax</span></span>

<span data-ttu-id="28907-106">*表达式*。LockEdits</span><span class="sxs-lookup"><span data-stu-id="28907-106">*expression* .LockEdits</span></span>

<span data-ttu-id="28907-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="28907-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="28907-108">注解</span><span class="sxs-lookup"><span data-stu-id="28907-108">Remarks</span></span>

<span data-ttu-id="28907-109">设置或返回值指示了锁定类型，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="28907-109">The setting or return value indicates the type of locking, as specified in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="28907-110">值</span><span class="sxs-lookup"><span data-stu-id="28907-110">Value</span></span></p></th>
<th><p><span data-ttu-id="28907-111">说明</span><span class="sxs-lookup"><span data-stu-id="28907-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28907-112">True</span><span class="sxs-lookup"><span data-stu-id="28907-112">True</span></span></p></td>
<td><p><span data-ttu-id="28907-p101">默认值。悲观锁定生效。只要您调用了 Edit 方法，就会锁定包含正在编辑的记录的页。</span><span class="sxs-lookup"><span data-stu-id="28907-p101">Default. Pessimistic locking is in effect. The page containing the record you're editing is locked as soon as you call the Edit method.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28907-116">False</span><span class="sxs-lookup"><span data-stu-id="28907-116">False</span></span></p></td>
<td><p><span data-ttu-id="28907-117">对编辑有效时开放式锁定。</span><span class="sxs-lookup"><span data-stu-id="28907-117">Optimistic locking is in effect for editing.</span></span> <span data-ttu-id="28907-118">包含记录的页面未锁定之前执行 Update 方法。</span><span class="sxs-lookup"><span data-stu-id="28907-118">The page containing the record is not locked until the Update method is executed.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="28907-119">可以将 **LockEdits** 属性用于可更新的 **[Recordset](recordset-object-dao.md)** 对象。</span><span class="sxs-lookup"><span data-stu-id="28907-119">You can use the **LockEdits** property with updatable **[Recordset](recordset-object-dao.md)** objects.</span></span>

<span data-ttu-id="28907-p103">如果锁定了某页，其他用户不能编辑同一页上的记录。如果您将 **LockEdits** 设置为 **True**，而另一个用户已经锁定了该页，则当您使用 **Edit** 方法时会发生错误。其他用户可以从锁定的页中读取数据。</span><span class="sxs-lookup"><span data-stu-id="28907-p103">If a page is locked, no other user can edit records on the same page. If you set **LockEdits** to **True** and another user already has the page locked, an error occurs when you use the **Edit** method. Other users can read data from locked pages.</span></span>

<span data-ttu-id="28907-p104">如果将 **LockEdits** 属性设置为 **False**，此后又使用 **Update** 方法，而此时另一个用户已经锁定了该页，则会发生错误。若要查看另一个用户对您的记录的更改，请使用将 0 作为参数的 **[Move](recordset2-move-method-dao.md)** 方法；但是如果这样做，您将丢失所做的更改。</span><span class="sxs-lookup"><span data-stu-id="28907-p104">If you set the **LockEdits** property to **False** and later use the **Update** method while another user has the page locked, an error occurs. To see the changes made to your record by another user, use the **[Move](recordset2-move-method-dao.md)** method with 0 as the argument; however, if you do this, you will lose your changes.</span></span>

<span data-ttu-id="28907-p105">当使用 Microsoft Access 数据库引擎连接的 ODBC 数据源时， **LockEdits** 属性始终设置为 **False** 或乐观锁定。Microsoft Access 数据库引擎对外部数据库服务器中使用的锁定机制没有控制权限。</span><span class="sxs-lookup"><span data-stu-id="28907-p105">When working with Microsoft Access database engine-connected ODBC data sources, the **LockEdits** property is always set to **False**, or optimistic locking. The Microsoft Access database engine has no control over the locking mechanisms used in external database servers.</span></span>


> [!NOTE]
> <P><span data-ttu-id="28907-127">首先通过设置<STRONG><A href="connection-openrecordset-method-dao.md">OpenRecordset</A></STRONG>方法的 lockedits 参数打开<STRONG>Recordset</STRONG>时，您可以预设<STRONG>LockEdits</STRONG>的值。</span><span class="sxs-lookup"><span data-stu-id="28907-127">You can preset the value of <STRONG>LockEdits</STRONG> when you first open the <STRONG>Recordset</STRONG> by setting the lockedits argument of the <STRONG><A href="connection-openrecordset-method-dao.md">OpenRecordset</A></STRONG> method.</span></span> <span data-ttu-id="28907-128">将 lockedits 参数设置为<STRONG>dbPessimistic</STRONG>会将<STRONG>LockEdits</STRONG>属性设置为<STRONG>True</STRONG>，并设置为任何其他值的 lockedits 会将<STRONG>LockEdits</STRONG>属性设置为<STRONG>False</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="28907-128">Setting the lockedits argument to <STRONG>dbPessimistic</STRONG> will set the <STRONG>LockEdits</STRONG> property to <STRONG>True</STRONG>, and setting lockedits to any other value will set the <STRONG>LockEdits</STRONG> property to <STRONG>False</STRONG>.</span></span></P>



## <a name="example"></a><span data-ttu-id="28907-129">示例</span><span class="sxs-lookup"><span data-stu-id="28907-129">Example</span></span>

<span data-ttu-id="28907-p107">以下示例通过将 **LockEdits** 属性设置为 **True** 来演示悲观锁定，然后通过将 **LockEdits** 属性设置为 False 来演示乐观锁定。它还演示为了修改字段，在多用户数据库环境下需要进行何种类型的错误处理。若要使该过程运行，需要使用 PessimisticLock 和 OptimisticLock 函数。</span><span class="sxs-lookup"><span data-stu-id="28907-p107">This example demonstrates pessimistic locking by setting the **LockEdits** property to **True**, and then demonstrates optimistic locking by setting the **LockEdits** property to False. It also demonstrates what kind of error handling is required in a multiuser database environment in order to modify a field. The PessimisticLock and OptimisticLock functions are required for this procedure to run.</span></span>

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
