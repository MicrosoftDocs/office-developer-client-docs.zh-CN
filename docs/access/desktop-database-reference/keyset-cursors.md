---
title: 键集游标 （访问桌面数据库参考 （英文）
TOCTitle: Keyset Cursors
ms:assetid: 4b6e5f90-4413-4fb3-0a08-2cb89d3c61f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249236(v=office.15)
ms:contentKeyID: 48544690
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 66e6b5ff69d22fa50d9765eb2087c373613bdb7d
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886940"
---
# <a name="keyset-cursors"></a><span data-ttu-id="c91c5-102">键集游标</span><span class="sxs-lookup"><span data-stu-id="c91c5-102">Keyset Cursors</span></span>


<span data-ttu-id="c91c5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c91c5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c91c5-p101">在检测更改的能力方面，键集游标提供的功能介于静态游标和动态游标之间。像静态游标一样，它并不总是会检测对结果集的成员及顺序的更改。像动态游标一样，它确实会检测对结果集中行的值的更改。</span><span class="sxs-lookup"><span data-stu-id="c91c5-p101">The keyset cursor provides functionality between a static and a dynamic cursor in its ability to detect changes. Like a static cursor, it does not always detect changes to the membership and order of the result set. Like a dynamic cursor, it does detect changes to the values of rows in the result set.</span></span>

<span data-ttu-id="c91c5-p102">键集驱动型游标由一组唯一标识符（键）来控制，该标识符集合称为键集。键是从一组列（这些列可唯一标识结果集中的行）中生成的。键集是查询语句返回的所有行中的键值的集合。</span><span class="sxs-lookup"><span data-stu-id="c91c5-p102">Keyset-driven cursors are controlled by a set of unique identifiers (keys) known as the keyset. The keys are built from a set of columns that uniquely identify the rows in the result set. The keyset is the set of key values from all the rows returned by the query statement.</span></span>

<span data-ttu-id="c91c5-p103">使用键集驱动型游标时，将为游标中的每一行生成和保存相应的键，并将键存储在客户端工作站或服务器上。在访问每一行时，将用存储的键来从数据源提取当前数据值。在键集驱动型游标中，当键集被完全充满时，会将结果集成员冻结起来。此后，影响成员的添加或更新将不包含在结果集之内，直到重新打开该结果集。</span><span class="sxs-lookup"><span data-stu-id="c91c5-p103">With keyset-driven cursors, a key is built and saved for each row in the cursor and stored either on the client workstation or on the server. When you access each row, the stored key is used to fetch the current data values from the data source. In a keyset-driven cursor, result set membership is frozen when the keyset is fully populated. Thereafter, additions or updates that affect membership are not a part of the result set until it is reopened.</span></span>

<span data-ttu-id="c91c5-p104">当用户在结果集中滚动时，（由键集所有者或其他进程）对数据值所做的更改是可见的。只有当游标关闭并重新打开时，（由其他进程）在游标外部执行的插入才是可见的。在结果集末尾，从游标内部执行的插入是可见的。</span><span class="sxs-lookup"><span data-stu-id="c91c5-p104">Changes to data values (made either by the keyset owner or other processes) are visible as the user scrolls through the result set. Inserts made outside the cursor (by other processes) are visible only if the cursor is closed and reopened. Inserts made from inside the cursor are visible at the end of the result set.</span></span>

<span data-ttu-id="c91c5-p105">当键集驱动型游标试图检索已删除的行时，该行将以"洞"的形式出现在结果集中。虽然该行的键存在于键集中，但该行不再存在于结果集中。如果行中的键值更新，则将该行视为已被删除然后被插入，所以，这样的行也会以洞的形式出现在结果集中。键集驱动型游标总是能够检测到由其他进程删除的行，它还可以有选择地移除与它自己删除的行相对应的键。执行此操作的键集驱动型游标无法检测自己的删除，因为证据已经消失。</span><span class="sxs-lookup"><span data-stu-id="c91c5-p105">When a keyset-driven cursor attempts to retrieve a row that has been deleted, the row appears as a "hole" in the result set. The key for the row exists in the keyset, but the row no longer exists in the result set. If the key values in a row are updated, the row is considered to have been deleted and then inserted, so such rows also appear as holes in the result set. While a keyset-driven cursor can always detect rows deleted by other processes, it can optionally remove the keys for rows it deletes itself. Keyset-driven cursors that do this cannot detect their own deletes because the evidence has been removed.</span></span>

<span data-ttu-id="c91c5-p106">对键列进行更新时，其工作方式类似于删除旧键然后插入新键。如果没有通过游标进行更新，则新的键值是不可见的。如果通过游标进行更新，则在结果集的末尾可以看见新的键值。</span><span class="sxs-lookup"><span data-stu-id="c91c5-p106">An update to a key column operates like a delete of the old key followed by an insert of the new key. The new key value is not visible if the update was not made through the cursor. If the update was made through the cursor, the new key value is visible at the end of the result set.</span></span>

<span data-ttu-id="c91c5-p107">键集驱动型游标有一个称为键集驱动型标准游标的变体。在键集驱动型标准游标中，结果集中行的成员和行的顺序在游标打开时是固定的，但由游标所有者对这些值所进行的更改和由其他进程所进行的已提交更改是可见的。如果更改使某行丧失了成员资格或影响了该行的顺序，则只有关闭并重新打开游标后，该行才会消失或移动。插入的数据不会出现，但对现有数据的更改会在提取行时出现。</span><span class="sxs-lookup"><span data-stu-id="c91c5-p107">There is a variation on keyset-driven cursors called keyset-driven standard cursors. In a keyset-driven standard cursor, the membership of rows in the result set and the order of the rows are fixed at cursor open time, but changes to values that are made by the cursor owner and committed changes made by other processes are visible. If a change disqualifies a row for membership or affects the order of a row, the row does not disappear or move unless the cursor is closed and reopened. Inserted data does not appear, but changes to existing data do appear as the rows are fetched.</span></span>

<span data-ttu-id="c91c5-p108">要想正确地使用键集驱动型游标是非常困难的，因为对数据更改的灵敏度取决于许多不同的环境（如上文所述）。但是，如果并发更新对应用程序而言并不重要，应用程序能以编程方式处理坏键，而且必须直接访问某些键行，则可能适合使用键集驱动型游标。请使用 **adOpenKeyset** **CursorTypeEnum** 指示要在 ADO 中使用键集游标。</span><span class="sxs-lookup"><span data-stu-id="c91c5-p108">The keyset-driven cursor is difficult to use correctly because the sensitivity to data changes depends on many differing circumstances, as described above. However, if your application is not concerned with concurrent updates, can programmatically handle bad keys, and must directly access certain keyed rows, the keyset-driven cursor might work for you. Use the **adOpenKeyset** **CursorTypeEnum** to indicate that you want to use a keyset cursor in ADO.</span></span>

