---
title: Recordset.Edit 方法 (DAO)
TOCTitle: Edit Method
ms:assetid: a64d601b-f446-da40-0020-b99110a72872
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821175(v=office.15)
ms:contentKeyID: 48546850
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 82dc6e175c7168d5c1b042e85dce7b77aa96b575
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300537"
---
# <a name="recordsetedit-method-dao"></a><span data-ttu-id="9c69c-102">Recordset.Edit 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9c69c-102">Recordset.Edit method (DAO)</span></span>

<span data-ttu-id="9c69c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="9c69c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9c69c-104">将当前记录从可更新的 **[Recordset](recordset-object-dao.md)** 对象复制到复制缓冲区以进行后续编辑。</span><span class="sxs-lookup"><span data-stu-id="9c69c-104">Copies the current record from an updatable **[Recordset](recordset-object-dao.md)** object to the copy buffer for subsequent editing.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c69c-105">语法</span><span class="sxs-lookup"><span data-stu-id="9c69c-105">Syntax</span></span>

<span data-ttu-id="9c69c-106">*表达式* .Edit</span><span class="sxs-lookup"><span data-stu-id="9c69c-106">*expression* .Edit</span></span>

<span data-ttu-id="9c69c-107">*表达式* 一个表示 **Recordset** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="9c69c-107">*expression*  A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c69c-108">说明</span><span class="sxs-lookup"><span data-stu-id="9c69c-108">Remarks</span></span>

<span data-ttu-id="9c69c-p101">一旦使用 **Edit** 方法，对当前记录的字段所做的更改将被复制到复制缓冲区。对记录执行所需的更改后，使用 **[Update](recordset-update-method-dao.md)** 方法保存更改。</span><span class="sxs-lookup"><span data-stu-id="9c69c-p101">Once you use the **Edit** method, changes made to the current record's fields are copied to the copy buffer. After you make the desired changes to the record, use the **[Update](recordset-update-method-dao.md)** method to save your changes.</span></span>

<span data-ttu-id="9c69c-111">使用 **Edit** 方法后，当前记录仍为当前记录。</span><span class="sxs-lookup"><span data-stu-id="9c69c-111">The current record remains current after you use **Edit**.</span></span>

> [!NOTE]
> <span data-ttu-id="9c69c-112">[!注释] 如果在编辑某条记录后执行了转移到另一条记录的任何操作，但是没有事先使用 **Update**，则更改将会丢失且不发出警告。</span><span class="sxs-lookup"><span data-stu-id="9c69c-112">If you edit a record and then perform any operation that moves to another record, but without first using **Update**, your changes are lost without warning.</span></span> <span data-ttu-id="9c69c-113">此外，如果关闭记录集，或者结束声明 **Recordset**、父 **[Database](database-object-dao.md)** 或 **[Connection](connection-object-dao.md)** 对象的过程，则会放弃编辑的记录且不发出警告。</span><span class="sxs-lookup"><span data-stu-id="9c69c-113">In addition, if you close  recordset or end the procedure which declares the **Recordset** or the parent [**Database**](connection-object-dao.md) or **Connection** object, your edited record is discarded without warning.</span></span>

<span data-ttu-id="9c69c-114">在以下条件下，使用 **Edit** 将产生错误：</span><span class="sxs-lookup"><span data-stu-id="9c69c-114">Using **Edit** produces an error if:</span></span>

- <span data-ttu-id="9c69c-115">没有当前记录。</span><span class="sxs-lookup"><span data-stu-id="9c69c-115">There is no current record.</span></span>

- <span data-ttu-id="9c69c-116">以只读方式打开了 **Connection**、 **Database** 或 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="9c69c-116">The **Connection**, **Database**, or **Recordset** object was opened as read-only.</span></span>

- <span data-ttu-id="9c69c-117">记录中没有可更新的字段。</span><span class="sxs-lookup"><span data-stu-id="9c69c-117">No fields in the record are updatable.</span></span>

- <span data-ttu-id="9c69c-118">打开的 **Database** 或 **Recordset** 被另一个用户独占使用（Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="9c69c-118">The **Database** or **Recordset** was opened for exclusive use by another user (Microsoft Access workspace).</span></span>

- <span data-ttu-id="9c69c-119">另一个用户锁定了包含您的记录的页面（Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="9c69c-119">Another user has locked the page containing your record (Microsoft Access workspace).</span></span>

<span data-ttu-id="9c69c-p103">在 Microsoft Access 工作区中，如果多用户环境中的 **Recordset** 对象的 **[LockEdits](recordset-lockedits-property-dao.md)** 属性设置为 **True**（悲观锁定），那么从开始使用 **Edit** 到完成更新的时间范围内，记录将保持锁定状态。如果 **LockEdits** 属性设置为 **False**（乐观锁定），则会锁定此记录，并且在数据库中对它更新之前，将它与预编辑的记录进行比较。如果自从使用 **Edit** 方法之后记录发生了更改，并且使用了 **OpenRecordset** 且没有指定 **dbSeeChanges**， **Update** 操作将会失败，同时返回运行时错误。默认情况下，Microsoft Access 数据库引擎连接的 ODBC 和可安装的 ISAM 数据库始终使用乐观锁定。</span><span class="sxs-lookup"><span data-stu-id="9c69c-p103">In a Microsoft Access workspace, when the **Recordset** object's **[LockEdits](recordset-lockedits-property-dao.md)** property setting is **True** (pessimistically locked) in a multiuser environment, the record remains locked from the time **Edit** is used until the update is complete. If the **LockEdits** property setting is **False** (optimistically locked), the record is locked and compared with the pre-edited record just before it's updated in the database. If the record has changed since you used the **Edit** method, the **Update** operation fails with a run-time error if you use **OpenRecordset** without specifying **dbSeeChanges**. By default, Microsoft Access database engine-connected ODBC and installable ISAM databases always use optimistic locking.</span></span>

> [!NOTE]
> <span data-ttu-id="9c69c-p104">[!注释] 若要添加、编辑或删除记录，基础数据源中的记录必须存在唯一索引。如果不存在此索引，在 Microsoft Access 工作区中， **[AddNew](recordset-addnew-method-dao.md)** 、 **[Delete](fields-delete-method-dao.md)** 或 **Edit** 方法调用将发生"权限被拒绝"错误。</span><span class="sxs-lookup"><span data-stu-id="9c69c-p104">To add, edit, or delete a record, there must be a unique index on the record in the underlying data source. If not, a "Permission denied" error will occur on the **[AddNew](recordset-addnew-method-dao.md)**, **[Delete](fields-delete-method-dao.md)**, or **Edit** method call in a Microsoft Access workspace.</span></span>

## <a name="example"></a><span data-ttu-id="9c69c-126">示例</span><span class="sxs-lookup"><span data-stu-id="9c69c-126">Example</span></span>

<span data-ttu-id="9c69c-p105">以下示例使用 **Edit** 方法，将当前数据替换为指定的名称。若要使该过程运行，需要使用 EditName 过程。</span><span class="sxs-lookup"><span data-stu-id="9c69c-p105">This example uses the **Edit** method to replace the current data with the specified name. The EditName procedure is required for this procedure to run.</span></span>

```vb
    Sub EditX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
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
     
    Sub EditName(rstTemp As Recordset, _ 
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
