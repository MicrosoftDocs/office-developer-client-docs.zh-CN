---
title: 使用书签 (Access 桌面数据库参考)
TOCTitle: Using Bookmarks
ms:assetid: fe6333ef-c9d9-1e84-2252-d27edc676e97
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250306(v=office.15)
ms:contentKeyID: 48548935
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 469d8a0cc9b644fe434770d51c21d8210c8038d0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306305"
---
# <a name="using-bookmarks"></a>使用书签


**适用于**：Access 2013、Office 2013

通常需要在 **Recordset** 中移动到其他位置之后直接返回到特定记录，而不用滚动经过每个记录并比较值。例如，如果试图使用 **Find** 方法搜索记录但搜索没有返回记录，您将自动位于 **Recordset** 的末尾。如果提供程序支持，则在使用 **Find** 方法之前，可以用书签来标记您的位置，以便可以返回该位置。书签是 **变量型** 类型值，它可以唯一标识 **Recordset** 对象中的记录。

还可以通过 **Recordset** **Filter** 方法使用变量型书签数组来筛选一组选定的记录。有关此技术的详细信息，请参阅本章随后的主题 [使用 Recordset](working-with-recordsets.md) 中的"筛选结果"。

可以使用 **Bookmark** 属性获得记录的书签，或将 **Recordset** 对象中的当前记录设置为有效书签所标识的记录。以下代码使用 **Bookmark** 属性来设置书签，然后在继续移动到其他记录之后，返回到已设置书签的记录。若要确定 **Recordset** 是否支持书签，请使用 **Supports** 方法。

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

随后将更详细介绍 [Supports](supports-method-ado.md) 方法。

除了克隆的 **Recordset** 情况以外，对于在其中创建书签的 **Recordset** 来说，即使使用相同命令，这些书签仍然是唯一的。这意味着，不能使用从一个 **Recordset** 获得的 **Bookmark** 来移动到以相同命令打开的第二个 **Recordset** 中的同一个记录。

