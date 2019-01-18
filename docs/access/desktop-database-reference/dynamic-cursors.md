---
title: 动态游标 （访问桌面数据库参考 （英文）
TOCTitle: Dynamic cursors
ms:assetid: ae599d86-6b89-6103-fda1-c899a6138e1d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249823(v=office.15)
ms:contentKeyID: 48547068
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2ee81b2bd0e7d40b3a426c6416111d21e2ec760c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726027"
---
# <a name="dynamic-cursors"></a><span data-ttu-id="99428-102">动态游标</span><span class="sxs-lookup"><span data-stu-id="99428-102">Dynamic cursors</span></span>


<span data-ttu-id="99428-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="99428-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="99428-p101">动态游标可以检测对结果集中的行的所有更改，无论这些更改是从游标内部发生的，还是由游标外部的其他用户引起的。通过游标，所有用户发出的所有插入、更新和删除语句都是可见的。动态游标可以检测在游标打开之后对结果集中的行、顺序和值进行的任何更改。在游标外部所做的更新要等到这些更新被提交以后才是可见的（除非将游标事务隔离级别设置为"不提交"）。</span><span class="sxs-lookup"><span data-stu-id="99428-p101">Dynamic cursors detect all changes made to the rows in the result set, regardless of whether the changes occur from inside the cursor or by other users outside the cursor. All insert, update, and delete statements made by all users are visible through the cursor. The dynamic cursor can detect any changes made to the rows, order, and values in the result set after the cursor is opened. Updates made outside the cursor are not visible until they are committed (unless the cursor transaction isolation level is set to "uncommitted").</span></span>

<span data-ttu-id="99428-p102">例如，假设动态游标提取了两个行和另一个应用程序，然后更新这些行中的某一行并删除其他行。如果动态游标随后再提取这些行，它将找不到已删除的行，但对于已更新的行它将显示新的值。</span><span class="sxs-lookup"><span data-stu-id="99428-p102">For example, suppose a dynamic cursor fetches two rows and another application, and then updates one of those rows and deletes the other. If the dynamic cursor then fetches those rows, it will not find the deleted row, but it will display the new values for the updated row.</span></span>

<span data-ttu-id="99428-p103">如果应用程序必须检测到由其他用户进行的所有并发更新，则动态游标是个好的选择。使用 **adOpenDynamic** **CursorTypeEnum** 可以指示您希望在 ADO 中使用动态游标。</span><span class="sxs-lookup"><span data-stu-id="99428-p103">The dynamic cursor is a good choice if your application must detect all concurrent updates made by other users. Use the **adOpenDynamic** **CursorTypeEnum** to indicate that you want to use a dynamic cursor in ADO.</span></span>

<span data-ttu-id="99428-112">[仅向前型游标](forward-only-cursors.md) | [静态游标](static-cursors.md) | [键集游标](keyset-cursors.md)</span><span class="sxs-lookup"><span data-stu-id="99428-112">[Forward-Only Cursors](forward-only-cursors.md) | [Static Cursors](static-cursors.md) | [Keyset Cursors](keyset-cursors.md)</span></span>

