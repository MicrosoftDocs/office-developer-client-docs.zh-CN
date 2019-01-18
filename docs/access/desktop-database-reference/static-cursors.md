---
title: 静态游标 （访问桌面数据库参考 （英文）
TOCTitle: Static cursors
ms:assetid: 1acf7fc5-fb12-e59e-f480-dde378a29c53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248950(v=office.15)
ms:contentKeyID: 48543524
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2eb019a6fc960d58771ff5ab0de7dca547c55f1c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699518"
---
# <a name="static-cursors"></a><span data-ttu-id="317c1-102">静态游标</span><span class="sxs-lookup"><span data-stu-id="317c1-102">Static cursors</span></span>


<span data-ttu-id="317c1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="317c1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="317c1-p101">静态游标总是显示结果集在首次打开游标时的样子。静态游标是只读或可读/写的（因具体实现而异），并提供向前和向后滚动。静态游标通常不检测在打开游标之后对结果集的成员、顺序或值进行的更改。静态游标可以检测它们自己的更新、删除和插入，尽管它们不需要这样做。</span><span class="sxs-lookup"><span data-stu-id="317c1-p101">The static cursor always displays the result set as it was when the cursor was first opened. Depending on implementation, static cursors are either read-only or read/write and provide forward and backward scrolling. The static cursor does not usually detect changes made to the membership, order, or values of the result set after the cursor is opened. Static cursors may detect their own updates, deletes, and inserts, although they are not required to do so.</span></span>

<span data-ttu-id="317c1-p102">静态游标从不检测其他更新、删除和插入。例如，假设静态游标提取某行，另一个应用程序随后对该行进行更新。如果该应用程序从静态游标重新提取此行，尽管另一个应用程序已进行了更改，但该应用程序看到仍是未更改的值。所有类型的滚动均受支持，但提供程序可能支持书签，也可能不支持书签。</span><span class="sxs-lookup"><span data-stu-id="317c1-p102">Static cursors never detect other updates, deletes, and inserts. For example, suppose a static cursor fetches a row, and another application then updates that row. If the application refetches the row from the static cursor, the values it sees are unchanged, despite the changes made by the other application. All types of scrolling are supported, but providers may or may not support bookmarks.</span></span>

<span data-ttu-id="317c1-p103">如果您的应用程序不需要检测对数据进行的更改，只是需要滚动，则静态游标是最佳选择。使用 **adOpenStatic** **CursorTypeEnum** 指示要在 ADO 中使用静态游标。</span><span class="sxs-lookup"><span data-stu-id="317c1-p103">If your application does not need to detect data changes and requires scrolling, the static cursor is the best choice. Use the **adOpenStatic** **CursorTypeEnum** to indicate that you want to use a static cursor in ADO.</span></span>

