---
title: 仅向前游标
TOCTitle: Forward-only cursors
ms:assetid: 27541bac-077b-bfe6-d9d8-713e4a945125
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249035(v=office.15)
ms:contentKeyID: 48543834
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 65eaafe805eabbac1681aa6dcd08b6b99bb056fa
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705643"
---
# <a name="forward-only-cursors"></a><span data-ttu-id="4f19d-102">仅向前游标</span><span class="sxs-lookup"><span data-stu-id="4f19d-102">Forward-only cursors</span></span>

<span data-ttu-id="4f19d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4f19d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4f19d-p101">典型的默认游标类型称为仅向前型（或不可滚动）游标，它只能在结果集中向前移动。仅向前型游标不支持滚动（在结果集中向前和向后移动的能力）；它只支持从结果集的开头到末尾提取行。利用某些仅向前型游标（例如，SQL Server 游标库中的游标），当前用户所发出的（或其他用户提交的）、影响到结果集中的行的所有插入、更新和删除语句在提取这些行时都是可见的。但是，由于游标无法向后滚动，将无法通过游标看见在提取数据库中的行之后对这些行所做的更改。</span><span class="sxs-lookup"><span data-stu-id="4f19d-p101">The typical default cursor type, called a forward-only (or non-scrollable) cursor, can move only forward through the result set. A forward-only cursor does not support scrolling (the ability to move forward and backward in the result set); it only supports fetching rows from the start to the end of the result set. With some forward-only cursors (such as with the SQL Server cursor library), all insert, update, and delete statements made by the current user (or committed by other users) that affect rows in the result set are visible as the rows are fetched. Because the cursor cannot be scrolled backward, however, changes made to rows in the database after the row was fetched are not visible through the cursor.</span></span>

<span data-ttu-id="4f19d-p102">在处理当前行的数据之后，仅向前型游标将释放用来存放该数据的资源。默认情况下，仅向前型游标是动态的，这意味着在处理当前行时将检测所有更改。这样可以更快的速度打开游标，并使结果集能够显示对基础表所做的更新。</span><span class="sxs-lookup"><span data-stu-id="4f19d-p102">After the data for the current row is processed, the forward-only cursor releases the resources that were used to hold that data. Forward-only cursors are dynamic by default, meaning that all changes are detected as the current row is processed. This provides faster cursor opening and enables the result set to display updates made to the underlying tables.</span></span>

<span data-ttu-id="4f19d-p103">虽然仅向前型游标不支持向后滚动，但应用程序可以通过关闭并重新打开游标来返回到结果集的开头。在处理少量数据时，这种方式十分有效。另外，应用程序可以一次性读取结果集，然后在本地缓存数据，再浏览本地数据缓存。</span><span class="sxs-lookup"><span data-stu-id="4f19d-p103">While forward-only cursors do not support backward scrolling, your application can return to the beginning of the result set by closing and reopening the cursor. This is an effective way to work with small amounts of data. As an alternative, your application could read the result set once, cache the data locally, and then browse the local data cache.</span></span>

<span data-ttu-id="4f19d-p104">如果应用程序不需要在结果集中滚动，则仅向前型游标是以最少量开销来快速检索数据的最佳方式。使用 **adOpenForwardOnly** **CursorTypeEnum** 可以指示您要在 ADO 中使用仅向前型游标。</span><span class="sxs-lookup"><span data-stu-id="4f19d-p104">If your application does not require scrolling through the result set, the forward-only cursor is the best way to retrieve data quickly with the least amount of overhead. Use the **adOpenForwardOnly** **CursorTypeEnum** to indicate that you want to use a forward-only cursor in ADO.</span></span>

