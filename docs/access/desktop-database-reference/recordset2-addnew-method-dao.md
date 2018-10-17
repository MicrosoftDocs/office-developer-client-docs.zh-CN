---
title: Recordset2.AddNew Method (DAO)
TOCTitle: AddNew Method
ms:assetid: 25c7d207-185c-943b-405e-b138ffb8b3e2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191874(v=office.15)
ms:contentKeyID: 48543792
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7e8123fc67d8b41b892f92b19605a26384af68b5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467063"
---
# <a name="recordset2addnew-method-dao"></a><span data-ttu-id="58089-102">Recordset2.AddNew Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="58089-102">Recordset2.AddNew Method (DAO)</span></span>


<span data-ttu-id="58089-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="58089-103">**Applies to**: Access 2013 | Office 2013</span></span>
 

<span data-ttu-id="58089-104">为可更新的 **Recordset2** 对象创建新记录。</span><span class="sxs-lookup"><span data-stu-id="58089-104">Creates a new record for an updatable **Recordset2** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="58089-105">语法</span><span class="sxs-lookup"><span data-stu-id="58089-105">Syntax</span></span>

<span data-ttu-id="58089-106">*表达式*。AddNew</span><span class="sxs-lookup"><span data-stu-id="58089-106">*expression* .AddNew</span></span>

<span data-ttu-id="58089-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="58089-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="58089-108">注解</span><span class="sxs-lookup"><span data-stu-id="58089-108">Remarks</span></span>

<span data-ttu-id="58089-p101">使用 **AddNew** 方法在记录集命名的 **Recordset2** 对象中创建和添加新记录。此方法将字段设置为默认值，如果未指定默认值，它将字段设置为 Null（为表类型 **Recordset2** 指定的默认值）。</span><span class="sxs-lookup"><span data-stu-id="58089-p101">Use the **AddNew** method to create and add a new record in the **Recordset2** object named by recordset. This method sets the fields to default values, and if no default values are specified, it sets the fields to Null (the default values specified for a table-type **Recordset2**).</span></span>

<span data-ttu-id="58089-p102">修改新记录后，请使用 **[Update](recordset2-update-method-dao.md)** 方法保存更改，并将记录添加到 **Recordset2**。在使用 **Update** 方法之前，数据库中不发生更改。</span><span class="sxs-lookup"><span data-stu-id="58089-p102">After you modify the new record, use the **[Update](recordset2-update-method-dao.md)** method to save the changes and add the record to the **Recordset2**. No changes occur in the database until you use the **Update** method.</span></span>


> [!NOTE]
> <P><span data-ttu-id="58089-p103">[!注释] 如果发出了 <STRONG>AddNew</STRONG>，然后执行了转移到另一条记录的任何操作，但是没有使用 <STRONG>Update</STRONG>，则更改将会丢失且不发出警告。此外，如果关闭 <STRONG>Recordset2</STRONG>，或者结束声明 <STRONG>Recordset2</STRONG> 或其 <STRONG><A href="database-object-dao.md">Database</A></STRONG> 对象的过程，则会放弃新记录且不发出警告。</span><span class="sxs-lookup"><span data-stu-id="58089-p103">If you issue an <STRONG>AddNew</STRONG> and then perform any operation that moves to another record, but without using <STRONG>Update</STRONG>, your changes are lost without warning. In addition, if you close the <STRONG>Recordset2</STRONG> or end the procedure that declares the <STRONG>Recordset2</STRONG> or its <STRONG><A href="database-object-dao.md">Database</A></STRONG> object, the new record is discarded without warning.</span></span></P>




> [!NOTE]
> <P><span data-ttu-id="58089-p104">[!注释] 如果在 Microsoft Access 工作区中使用 <STRONG>AddNew</STRONG>，并且数据库引擎必须创建一个新页面以保存当前记录，则页面锁定是悲观的。如果新记录适合现有页面，则页面锁定是乐观的。</span><span class="sxs-lookup"><span data-stu-id="58089-p104">When you use <STRONG>AddNew</STRONG> in a Microsoft Access workspace and the database engine has to create a new page to hold the current record, page locking is pessimistic. If the new record fits in an existing page, page locking is optimistic.</span></span></P>



<span data-ttu-id="58089-p105">如果没有移到 **Recordset2** 的最后一条记录，并且由其他过程添加到基表的记录位于当前记录的上方，则包括这些添加的记录。但是，如果向自己的 **Recordset2** 添加了记录，则该记录将在 **Recordset2** 中可见，并且将包括在基础表中，基础表中的记录对任何新的 **Recordset2** 对象可见。</span><span class="sxs-lookup"><span data-stu-id="58089-p105">If you haven't moved to the last record of your **Recordset2**, records added to base tables by other processes may be included if they are positioned beyond the current record. If you add a record to your own **Recordset2**, however, the record is visible in the **Recordset2** and included in the underlying table where it becomes visible to any new **Recordset2** objects.</span></span>

<span data-ttu-id="58089-119">新记录的位置取决于 **Recordset2** 的类型：</span><span class="sxs-lookup"><span data-stu-id="58089-119">The position of the new record depends on the type of **Recordset2**:</span></span>

  - <span data-ttu-id="58089-120">在动态集类型 **Recordset2** 对象中，记录将插在 **Recordset** 的末尾，而不管打开 **Recordset** 时的排序或顺序规则如何。</span><span class="sxs-lookup"><span data-stu-id="58089-120">In a dynaset-type **Recordset2** object, records are inserted at the end of the **Recordset**, regardless of any sorting or ordering rules that were in effect when the **Recordset** was opened.</span></span>

  - <span data-ttu-id="58089-p106">在已设置 [**Index**](recordset2-index-property-dao.md) 属性的表类型 **Recordset2** 对象中，记录将按排序次序在正确的位置返回。如果没有设置 **Index** 属性，新记录将在 **Recordset** 的末尾返回。</span><span class="sxs-lookup"><span data-stu-id="58089-p106">In a table-type **Recordset2** object whose **[Index](recordset2-index-property-dao.md)** property has been set, records are returned in their proper place in the sort order. If you haven't set the **Index** property, new records are returned at the end of the **Recordset**.</span></span>

<span data-ttu-id="58089-p107">在使用 **AddNew** 之前处于当前的记录仍然为当前记录。如果想要使新记录成为当前记录，可将 **[Bookmark](recordset2-bookmark-property-dao.md)** 属性设置为 **[LastModified](recordset2-lastmodified-property-dao.md)** 属性设置所标识的书签。</span><span class="sxs-lookup"><span data-stu-id="58089-p107">The record that was current before you used **AddNew** remains current. If you want to make the new record current, you can set the **[Bookmark](recordset2-bookmark-property-dao.md)** property to the bookmark identified by the **[LastModified](recordset2-lastmodified-property-dao.md)** property setting.</span></span>


> [!NOTE]
> <P><span data-ttu-id="58089-p108">[!注释] 若要添加、编辑或删除记录，基础数据源中的记录必须存在唯一索引。如果不存在此索引，在 Microsoft Access 工作区中， <STRONG>AddNew</STRONG>、 <STRONG>Delete</STRONG> 或 <STRONG>Edit</STRONG> 方法调用将发生"权限被拒绝"错误。</span><span class="sxs-lookup"><span data-stu-id="58089-p108">To add, edit, or delete a record, there must be a unique index on the record in the underlying data source. If not, a "Permission denied" error will occur on the <STRONG>AddNew</STRONG>, <STRONG>Delete</STRONG>, or <STRONG>Edit</STRONG> method call in a Microsoft Access workspace.</span></span></P>



## <a name="example"></a><span data-ttu-id="58089-127">示例</span><span class="sxs-lookup"><span data-stu-id="58089-127">Example</span></span>

<span data-ttu-id="58089-p109">以下示例使用 **AddNew** 方法创建一个具有指定名称的新记录。若要使该过程运行，需要使用 AddName 函数。</span><span class="sxs-lookup"><span data-stu-id="58089-p109">This example uses the **AddNew** method to create a new record with the specified name. The AddName function is required for this procedure to run.</span></span>

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