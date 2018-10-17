---
title: Recordset.Bookmark Property (DAO)
TOCTitle: Bookmark Property
ms:assetid: c4b1c2d9-668e-e365-544c-efb4ae4efcc9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823084(v=office.15)
ms:contentKeyID: 48547597
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052887
f1_categories:
- Office.Version=v15
ms.openlocfilehash: c61cc86fbca68e8c3aca38fd86ed36b8c8f403dd
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466997"
---
# <a name="recordsetbookmark-property-dao"></a><span data-ttu-id="8c88b-102">Recordset.Bookmark Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="8c88b-102">Recordset.Bookmark Property (DAO)</span></span>


<span data-ttu-id="8c88b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8c88b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8c88b-104">设置或返回一个书签，该书签唯一地标识 **[Recordset](recordset-object-dao.md)** 对象中的当前记录。</span><span class="sxs-lookup"><span data-stu-id="8c88b-104">Sets or returns a bookmark that uniquely identifies the current record in a **[Recordset](recordset-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="8c88b-105">语法</span><span class="sxs-lookup"><span data-stu-id="8c88b-105">Syntax</span></span>

<span data-ttu-id="8c88b-106">*表达式*。书签</span><span class="sxs-lookup"><span data-stu-id="8c88b-106">*expression* .Bookmark</span></span>

<span data-ttu-id="8c88b-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="8c88b-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c88b-108">说明</span><span class="sxs-lookup"><span data-stu-id="8c88b-108">Remarks</span></span>

<span data-ttu-id="8c88b-109">对于**Recordset**对象完全基于 Microsoft Access 数据库引擎表， **Bookmarkable**属性的值为 True，并使用该**记录集**，可以使用**Bookmark**属性。</span><span class="sxs-lookup"><span data-stu-id="8c88b-109">For a **Recordset** object based entirely on Microsoft Access database engine tables, the value of the **Bookmarkable** property is True, and you can use the **Bookmark** property with that **Recordset**.</span></span> <span data-ttu-id="8c88b-110">但是，其他数据库产品可能不支持书签。</span><span class="sxs-lookup"><span data-stu-id="8c88b-110">Other database products may not support bookmarks, however.</span></span> <span data-ttu-id="8c88b-111">例如，不能在基于 Paradox 链接表（没有主键）的任何 **Recordset** 对象中使用书签。</span><span class="sxs-lookup"><span data-stu-id="8c88b-111">For example, you can't use bookmarks in any **Recordset** object based on a linked Paradox table that has no primary key.</span></span>

<span data-ttu-id="8c88b-p102">在创建或打开 **Recordset** 对象时，它的每条记录都有一个唯一的书签。可以通过将 **Bookmark** 属性的值赋给一个变量，来保存当前记录的书签。要在移到另一个记录后随时快速地返回到该记录，请将 **Recordset** 对象的 **Bookmark** 属性设置为该变量的值。</span><span class="sxs-lookup"><span data-stu-id="8c88b-p102">When you create or open a **Recordset** object, each of its records already has a unique bookmark. You can save the bookmark for the current record by assigning the value of the **Bookmark** property to a variable. To quickly return to that record at any time after moving to a different record, set the **Recordset** object's **Bookmark** property to the value of that variable.</span></span>

<span data-ttu-id="8c88b-p103">可建立的书签数没有限制。若要为当前记录以外的其他记录创建书签，需移到相应的记录，然后将 **Bookmark** 属性的值分配给标识此记录的 **String** 变量。</span><span class="sxs-lookup"><span data-stu-id="8c88b-p103">There is no limit to the number of bookmarks you can establish. To create a bookmark for a record other than the current record, move to the desired record and assign the value of the **Bookmark** property to a **String** variable that identifies the record.</span></span>

<span data-ttu-id="8c88b-117">若要确保 **Recordset** 对象支持书签，请在使用 [Bookmark](recordset-bookmarkable-property-dao.md) 属性之前，检查该对象的 \*\*\*\*Bookmarkable\*\*\*\* 属性的值。</span><span class="sxs-lookup"><span data-stu-id="8c88b-117">To make sure the **Recordset** object supports bookmarks, check the value of its **[Bookmarkable](recordset-bookmarkable-property-dao.md)** property before you use the **Bookmark** property.</span></span> <span data-ttu-id="8c88b-118">如果**Bookmarkable**属性为 False， **Recordset**对象不支持书签，并使用**Bookmark**属性会导致可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="8c88b-118">If the **Bookmarkable** property is False, the **Recordset** object doesn't support bookmarks, and using the **Bookmark** property results in a trappable error.</span></span>

<span data-ttu-id="8c88b-p105">如果使用 **[Clone](recordset-clone-method-dao.md)** 方法创建 **Recordset** 对象的副本，则原始和复制的 **Recordset** 对象的 **Bookmark** 属性设置将会相同，并且可交换使用。不过，不能将不同 **Recordset** 对象的书签交换使用，即使它们是使用相同的对象或 SQL 语句创建的也不行。</span><span class="sxs-lookup"><span data-stu-id="8c88b-p105">If you use the **[Clone](recordset-clone-method-dao.md)** method to create a copy of a **Recordset** object, the **Bookmark** property settings for the original and the duplicate **Recordset** objects are identical and can be used interchangeably. However, you can't use bookmarks from different **Recordset** objects interchangeably, even if they were created by using the same object or the same SQL statement.</span></span>

<span data-ttu-id="8c88b-121">如果将 **Bookmark** 属性设置为表示已删除记录的值，将发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="8c88b-121">If you set the **Bookmark** property to a value that represents a deleted record, a trappable error occurs.</span></span>

<span data-ttu-id="8c88b-122">**Bookmark** 属性值不同于记录编号。</span><span class="sxs-lookup"><span data-stu-id="8c88b-122">The value of the **Bookmark** property isn't the same as a record number.</span></span>

## <a name="example"></a><span data-ttu-id="8c88b-123">示例</span><span class="sxs-lookup"><span data-stu-id="8c88b-123">Example</span></span>

<span data-ttu-id="8c88b-124">以下示例使用 **Bookmark** 和 **Bookmarkable** 属性，让用户对 **Recordset** 中的记录做上标记，稍后再返回到此记录。</span><span class="sxs-lookup"><span data-stu-id="8c88b-124">This example uses the **Bookmark** and **Bookmarkable** properties to let the user flag a record in a **Recordset** and return to it later.</span></span>

```vb
    Sub BookmarkX() 
     
     Dim dbsNorthwind As Database 
     Dim rstCategories As Recordset 
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

<span data-ttu-id="8c88b-125">以下示例使用 **LastModified** 属性将当前记录指针移动到已修改的记录和新创建的记录。</span><span class="sxs-lookup"><span data-stu-id="8c88b-125">This example uses the **LastModified** property to move the current record pointer to both a record that has been modified and a newly created record.</span></span>

```vb
    Sub LastModifiedX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
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