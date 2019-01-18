---
title: Recordset2.Bookmarkable 属性 (DAO)
TOCTitle: Bookmarkable Property
ms:assetid: 9c93d04d-ca10-acf5-122a-58625ed93424
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198125(v=office.15)
ms:contentKeyID: 48546601
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052888
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 26b8b60255b4e50a2288dedb8e27906476926e8c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28714680"
---
# <a name="recordset2bookmarkable-property-dao"></a><span data-ttu-id="fb5a6-102">Recordset2.Bookmarkable 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="fb5a6-102">Recordset2.Bookmarkable property (DAO)</span></span>


<span data-ttu-id="fb5a6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fb5a6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fb5a6-104">返回一个值，该值表示 **Recordset** 对象是否支持书签（可以使用 **[Bookmark](recordset2-bookmark-property-dao.md)** 属性来设置书签）。</span><span class="sxs-lookup"><span data-stu-id="fb5a6-104">Returns a value that indicates whether a **Recordset** object supports bookmarks, which you can set by using the **[Bookmark](recordset2-bookmark-property-dao.md)** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb5a6-105">语法</span><span class="sxs-lookup"><span data-stu-id="fb5a6-105">Syntax</span></span>

<span data-ttu-id="fb5a6-106">*表达式*。Bookmarkable</span><span class="sxs-lookup"><span data-stu-id="fb5a6-106">*expression* .Bookmarkable</span></span>

<span data-ttu-id="fb5a6-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="fb5a6-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb5a6-108">注解</span><span class="sxs-lookup"><span data-stu-id="fb5a6-108">Remarks</span></span>

<span data-ttu-id="fb5a6-109">在尝试设置或检查 **Bookmark** 属性之前，请检查 **Recordset** 对象的 **Bookmarkable** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="fb5a6-109">Check the **Bookmarkable** property setting of a **Recordset** object before you attempt to set or check the **Bookmark** property.</span></span>

<span data-ttu-id="fb5a6-110">对于**Recordset**对象完全基于 Microsoft Access 数据库引擎表， **Bookmarkable**属性的值为 True，并可以使用书签。</span><span class="sxs-lookup"><span data-stu-id="fb5a6-110">For **Recordset** objects based entirely on Microsoft Access database engine tables, the value of the **Bookmarkable** property is True, and you can use bookmarks.</span></span> <span data-ttu-id="fb5a6-111">但是，其他数据库产品可能不支持书签。</span><span class="sxs-lookup"><span data-stu-id="fb5a6-111">Other database products may not support bookmarks, however.</span></span> <span data-ttu-id="fb5a6-112">例如，在基于 Paradox 链接表（没有主键）的任何 **Recordset** 对象中，都不能使用书签。</span><span class="sxs-lookup"><span data-stu-id="fb5a6-112">For example, you can't use bookmarks in any **Recordset** object based on a linked Paradox table that has no primary key.</span></span>

## <a name="example"></a><span data-ttu-id="fb5a6-113">示例</span><span class="sxs-lookup"><span data-stu-id="fb5a6-113">Example</span></span>

<span data-ttu-id="fb5a6-114">以下示例使用 **Bookmark** 和 **Bookmarkable** 属性，使用户可以对记录集中的记录加标记，稍后再返回到此记录。</span><span class="sxs-lookup"><span data-stu-id="fb5a6-114">This example uses the **Bookmark** and **Bookmarkable** properties to let the user flag a record in a recordset and return to it later.</span></span>

```vb
    Sub BookmarkX() 
     
     Dim dbsNorthwind As Database 
     Dim rstCategories As Recordset2 
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
