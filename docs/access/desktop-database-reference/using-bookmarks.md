---
title: 使用书签 （访问桌面数据库参考 （英文）
TOCTitle: Using Bookmarks
ms:assetid: fe6333ef-c9d9-1e84-2252-d27edc676e97
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250306(v=office.15)
ms:contentKeyID: 48548935
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 469d8a0cc9b644fe434770d51c21d8210c8038d0
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706316"
---
# <a name="using-bookmarks"></a><span data-ttu-id="005d2-102">使用书签</span><span class="sxs-lookup"><span data-stu-id="005d2-102">Using bookmarks</span></span>


<span data-ttu-id="005d2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="005d2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="005d2-p101">通常需要在 **Recordset** 中移动到其他位置之后直接返回到特定记录，而不用滚动经过每个记录并比较值。例如，如果试图使用 **Find** 方法搜索记录但搜索没有返回记录，您将自动位于 **Recordset** 的末尾。如果提供程序支持，则在使用 **Find** 方法之前，可以用书签来标记您的位置，以便可以返回该位置。书签是 **变量型** 类型值，它可以唯一标识 **Recordset** 对象中的记录。</span><span class="sxs-lookup"><span data-stu-id="005d2-p101">It is often useful to return directly to a specific record after having moved around in the **Recordset** without having to scroll through every record and compare values. For example, if you attempt to search for a record using the **Find** method but the search returns no records, you are automatically placed at either end of the **Recordset**. If your provider supports them, bookmarks can be used to mark your place before using the **Find** method so you can return to your location. A bookmark is a **Variant** type value that uniquely identifies a record in a **Recordset** object.</span></span>

<span data-ttu-id="005d2-p102">还可以通过 **Recordset** **Filter** 方法使用变量型书签数组来筛选一组选定的记录。有关此技术的详细信息，请参阅本章随后的主题 [使用 Recordset](working-with-recordsets.md) 中的"筛选结果"。</span><span class="sxs-lookup"><span data-stu-id="005d2-p102">You can also use a variant array of bookmarks with the **Recordset** **Filter** method to filter on a selected set of records. For details about this technique, see Filtering the Results in the topic, [Working with Recordsets](working-with-recordsets.md), later in this chapter.</span></span>

<span data-ttu-id="005d2-p103">可以使用 **Bookmark** 属性获得记录的书签，或将 **Recordset** 对象中的当前记录设置为有效书签所标识的记录。以下代码使用 **Bookmark** 属性来设置书签，然后在继续移动到其他记录之后，返回到已设置书签的记录。若要确定 **Recordset** 是否支持书签，请使用 **Supports** 方法。</span><span class="sxs-lookup"><span data-stu-id="005d2-p103">You can use the **Bookmark** property to get a bookmark for a record, or set the current record in a **Recordset** object to the record identified by a valid bookmark. The following code uses the **Bookmark** property to set a bookmark and then return to the bookmarked record after moving on to other records. To determine if your **Recordset** supports bookmarks, use the **Supports** method.</span></span>

```vb 
 
'BeginBookmarkEg 
 Dim varBookmark As Variant 
 Dim blnCanBkmrk As Boolean 
 
 objRs.Open strSQL, strConnStr, adOpenStatic, adLockOptimistic, adCmdText 
 
 If objRs.RecordCount > 4 Then 
 objRs.Move 4 ' move to the fifth record 
 blnCanBkmrk = objRs.Supports(adBookmark) 
 If blnCanBkmrk = True Then 
 varBookmark = objRs.Bookmark ' record the bookmark 
 objRs.MoveLast ' move to a different record 
 objRs.Bookmark = varBookmark ' return to the bookmarked (sixth) record 
 End If 
 End If 
'EndBookmarkEg 
```

<span data-ttu-id="005d2-113">随后将更详细介绍 [Supports](supports-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="005d2-113">The [Supports](supports-method-ado.md) method is covered in more detail later.</span></span>

<span data-ttu-id="005d2-p104">除了克隆的 **Recordset** 情况以外，对于在其中创建书签的 **Recordset** 来说，即使使用相同命令，这些书签仍然是唯一的。这意味着，不能使用从一个 **Recordset** 获得的 **Bookmark** 来移动到以相同命令打开的第二个 **Recordset** 中的同一个记录。</span><span class="sxs-lookup"><span data-stu-id="005d2-p104">Except for the case of cloned **Recordsets**, bookmarks are unique to the **Recordset** in which they were created, even if the same command is used. This means that you cannot use a **Bookmark** obtained from one **Recordset** to move to the same record in a second **Recordset** opened with the same command.</span></span>

