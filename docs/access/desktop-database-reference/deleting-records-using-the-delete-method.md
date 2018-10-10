---
title: 使用 Delete 方法删除记录
TOCTitle: Deleting Records Using the Delete Method
ms:assetid: 22917c33-4d14-ebab-d85c-2cbe7f68c560
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249003(v=office.15)
ms:contentKeyID: 48543708
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 22ed36c0015df458b9f0577350f5f05a03561515
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468373"
---
# <a name="deleting-records-using-the-delete-method"></a>使用 Delete 方法删除记录


**适用于**： Access 2013 |Office 2013

使用 **Delete** 方法可以将 **Recordset** 对象中的当前记录或一组记录标记为删除。如果 **Recordset** 对象不允许进行记录删除，则会发生错误。如果处于立即更新模式，则数据库中将立即发生删除。如果无法成功删除记录（例如，由于数据库完整性受到破坏），则在调用 **Update** 之后记录将继续处于编辑模式。这意味着，在离开当前记录（例如，使用 [Close](cancelupdate-method-ado.md)、[Move](close-method-ado.md) 或 [NextRecordset](move-method-ado.md)）之前，必须使用 [CancelUpdate](nextrecordset-method-ado.md) 取消更新。

如果处于批更新模式，则记录将在缓存中被标记为删除，并在调用 **UpdateBatch** 方法时发生实际的删除。（若要查看删除的记录，请在调用 **Delete** 之后将 **Filter** 属性设置为 **adFilterAffectedRecords** 。）

试图从删除的记录中检索字段值将生成错误。删除当前记录之后，删除的记录仍然是当前记录，直到移动到其他记录。一旦离开删除的记录，它将不再可访问。

如果在事务中嵌套删除，则可以使用 **RollbackTrans** 方法恢复删除的记录。如果处于批更新模式，则可以使用 **CancelBatch** 方法来取消挂起的删除或一组挂起的删除。

如果由于与基础数据冲突而导致删除记录的尝试失败（例如，记录已被另一个用户删除），则提供程序会将警告返回到 **Errors** 集合，但是不会停止程序执行。只有当所有被请求的记录都有冲突时，才会发生运行时错误。

如果设置了 **Unique Table** 动态属性并且 **Recordset** 是对多个表执行 JOIN 操作后的结果，则 **Delete** 方法将只删除 **Unique Table** 属性所命名的表内的行。

**Delete** 方法的一个可选参数用于指定哪些记录会受 **Delete** 操作的影响。此参数的唯一有效值是以下 ADO **AffectEnum** 枚举常量之一：

  - **adaffectcurrent:** 只影响当前记录。

  - **adAffectGroup**影响满足当前**筛选器**属性设置的记录。 若要使用此选项，必须将 **Filter** 属性设置为 **FilterGroupEnum** 值或 **Bookmarks** 数组。

以下代码显示在调用 **Delete** 方法时指定 **adAffectGroup** 的示例。此示例将某些记录添加到示例 **Recordset** 中并更新数据库。然后，它使用 **adFilterAffectedRecords** 筛选枚举常量来筛选 **Recordset** ，从而使得只有那些新添加的记录在 **Recordset** 中可见。最后，它调用 **Delete** 方法，并指定应当删除满足当前 **Filter** 属性设置的所有记录（新记录）。

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

