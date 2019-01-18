---
title: 使用 Delete 方法删除记录
TOCTitle: Deleting records using the Delete method
ms:assetid: 22917c33-4d14-ebab-d85c-2cbe7f68c560
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249003(v=office.15)
ms:contentKeyID: 48543708
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a476e9bc57224b0e46afb31bf092450c26de0a17
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699063"
---
# <a name="deleting-records-using-the-delete-method"></a><span data-ttu-id="75477-102">使用 Delete 方法删除记录</span><span class="sxs-lookup"><span data-stu-id="75477-102">Deleting records using the Delete method</span></span>


<span data-ttu-id="75477-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="75477-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="75477-p101">使用 **Delete** 方法可以将 **Recordset** 对象中的当前记录或一组记录标记为删除。如果 **Recordset** 对象不允许进行记录删除，则会发生错误。如果处于立即更新模式，则数据库中将立即发生删除。如果无法成功删除记录（例如，由于数据库完整性受到破坏），则在调用 **Update** 之后记录将继续处于编辑模式。这意味着，在离开当前记录（例如，使用 [Close](cancelupdate-method-ado.md)、[Move](close-method-ado.md) 或 [NextRecordset](move-method-ado.md)）之前，必须使用 [CancelUpdate](nextrecordset-method-ado.md) 取消更新。</span><span class="sxs-lookup"><span data-stu-id="75477-p101">Using the **Delete** method marks the current record or a group of records in a **Recordset** object for deletion. If the **Recordset** object does not allow record deletion, an error occurs. If you are in immediate update mode, deletions occur in the database immediately. If a record cannot be successfully deleted (due to database integrity violations, for example), the record will remain in edit mode after the call to **Update**. This means that you must cancel the update using [CancelUpdate](cancelupdate-method-ado.md) before moving off the current record (for example, using [Close](close-method-ado.md), [Move](move-method-ado.md), or [NextRecordset](nextrecordset-method-ado.md)).</span></span>

<span data-ttu-id="75477-p102">如果处于批更新模式，则记录将在缓存中被标记为删除，并在调用 **UpdateBatch** 方法时发生实际的删除。（若要查看删除的记录，请在调用 **Delete** 之后将 **Filter** 属性设置为 **adFilterAffectedRecords** 。）</span><span class="sxs-lookup"><span data-stu-id="75477-p102">If you are in batch update mode, the records are marked for deletion from the cache and the actual deletion happens when you call the **UpdateBatch** method. (To view the deleted records, set the **Filter** property to **adFilterAffectedRecords** after **Delete** is called.)</span></span>

<span data-ttu-id="75477-p103">试图从删除的记录中检索字段值将生成错误。删除当前记录之后，删除的记录仍然是当前记录，直到移动到其他记录。一旦离开删除的记录，它将不再可访问。</span><span class="sxs-lookup"><span data-stu-id="75477-p103">Attempting to retrieve field values from the deleted record generates an error. After deleting the current record, the deleted record remains current until you move to a different record. Once you move away from the deleted record, it is no longer accessible.</span></span>

<span data-ttu-id="75477-p104">如果在事务中嵌套删除，则可以使用 **RollbackTrans** 方法恢复删除的记录。如果处于批更新模式，则可以使用 **CancelBatch** 方法来取消挂起的删除或一组挂起的删除。</span><span class="sxs-lookup"><span data-stu-id="75477-p104">If you nest deletions in a transaction, you can recover deleted records by using the **RollbackTrans** method. If you are in batch update mode, you can cancel a pending deletion or group of pending deletions by using the **CancelBatch** method.</span></span>

<span data-ttu-id="75477-p105">如果由于与基础数据冲突而导致删除记录的尝试失败（例如，记录已被另一个用户删除），则提供程序会将警告返回到 **Errors** 集合，但是不会停止程序执行。只有当所有被请求的记录都有冲突时，才会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="75477-p105">If the attempt to delete records fails because of a conflict with the underlying data (for example, a record has already been deleted by another user), the provider returns warnings to the **Errors** collection but does not halt program execution. A run-time error occurs only if there are conflicts on all the requested records.</span></span>

<span data-ttu-id="75477-118">如果设置了 **Unique Table** 动态属性并且 **Recordset** 是对多个表执行 JOIN 操作后的结果，则 **Delete** 方法将只删除 **Unique Table** 属性所命名的表内的行。</span><span class="sxs-lookup"><span data-stu-id="75477-118">If the **Unique Table** dynamic property is set and the **Recordset** is the result of executing a JOIN operation on multiple tables, the **Delete** method will delete rows only from the table named in the **Unique Table** property.</span></span>

<span data-ttu-id="75477-p106">**Delete** 方法的一个可选参数用于指定哪些记录会受 **Delete** 操作的影响。此参数的唯一有效值是以下 ADO **AffectEnum** 枚举常量之一：</span><span class="sxs-lookup"><span data-stu-id="75477-p106">The **Delete** method takes an optional argument that allows you to specify which records are affected by the **Delete** operation. The only valid values for this argument are either of the following ADO **AffectEnum** enumerated constants:</span></span>

  - <span data-ttu-id="75477-121">**adaffectcurrent:** 只影响当前记录。</span><span class="sxs-lookup"><span data-stu-id="75477-121">**adAffectCurrent**Affects only the current record.</span></span>

  - <span data-ttu-id="75477-122">**adAffectGroup**影响满足当前**筛选器**属性设置的记录。</span><span class="sxs-lookup"><span data-stu-id="75477-122">**adAffectGroup**Affects only records that satisfy the current **Filter** property setting.</span></span> <span data-ttu-id="75477-123">若要使用此选项，必须将 **Filter** 属性设置为 **FilterGroupEnum** 值或 **Bookmarks** 数组。</span><span class="sxs-lookup"><span data-stu-id="75477-123">The **Filter** property must be set to a **FilterGroupEnum** value or an array of **Bookmarks** to use this option.</span></span>

<span data-ttu-id="75477-p108">以下代码显示在调用 **Delete** 方法时指定 **adAffectGroup** 的示例。此示例将某些记录添加到示例 **Recordset** 中并更新数据库。然后，它使用 **adFilterAffectedRecords** 筛选枚举常量来筛选 **Recordset** ，从而使得只有那些新添加的记录在 **Recordset** 中可见。最后，它调用 **Delete** 方法，并指定应当删除满足当前 **Filter** 属性设置的所有记录（新记录）。</span><span class="sxs-lookup"><span data-stu-id="75477-p108">The following code shows an example of specifying **adAffectGroup** when calling the **Delete** method. This example adds some records to the sample **Recordset** and updates the database. Then it filters the **Recordset** using the **adFilterAffectedRecords** filter enumerated constant, which leaves only the newly added records visible in the **Recordset**. Finally, it calls the **Delete** method and specifies that all of the records that satisfy the current **Filter** property setting (the new records) should be deleted.</span></span>

```vb 
 
'BeginDeleteGroup 
 'add some bogus records 
 With objRs1 
 For i = 0 To 8 
 .AddNew 
 .Fields("CompanyName") = "Shipper Number " & i + 1 
 .Fields("Phone") = "(425) 555-000" & (i + 1) 
 .Update 
 Next i 
 
 're-connect & update 
 .ActiveConnection = GetNewConnection 
 .UpdateBatch 
 
 'filter on newly added records 
 .Filter = adFilterAffectedRecords 
 Debug.Print "Deleting the " & .RecordCount & _ 
 " records you just added." 
 
 'delete the newly added bogus records 
 .Delete adAffectGroup 
 .Filter = adFilterNone 
 Debug.Print .RecordCount & " records remain." 
 
 .Close 
 End With 
'EndDeleteGroup 
```

