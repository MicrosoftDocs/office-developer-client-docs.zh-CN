---
title: 锁定 （访问桌面数据库引用） 的类型
TOCTitle: Types of Locks
ms:assetid: 8276edca-f603-2487-a2ca-73e618c0f11e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249565(v=office.15)
ms:contentKeyID: 48545978
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e141abdd915257abdb8499efea1aded3cee4cb1c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467006"
---
# <a name="types-of-locks"></a><span data-ttu-id="0c812-102">锁定的类型</span><span class="sxs-lookup"><span data-stu-id="0c812-102">Types of Locks</span></span>


<span data-ttu-id="0c812-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0c812-103">**Applies to**: Access 2013 | Office 2013</span></span>



## <a name="adlockbatchoptimistic"></a><span data-ttu-id="0c812-104">adLockBatchOptimistic</span><span class="sxs-lookup"><span data-stu-id="0c812-104">adLockBatchOptimistic</span></span>

<span data-ttu-id="0c812-p101">指示开放式批更新。这是批更新模式所必需的。</span><span class="sxs-lookup"><span data-stu-id="0c812-p101">Indicates optimistic batch updates. Required for batch update mode.</span></span>

<span data-ttu-id="0c812-p102">许多应用程序都一次提取大量行，然后要进行一致的更新，这些更新包括对整个行集进行插入、更新或删除。使用批处理游标，只需在服务器之间往返一次，从而改善了更新性能并减少了网络流量。使用批处理游标库，可以创建静态游标，然后断开与数据源的连接。此时，可以对行进行更改，再重新连接到数据源并成批发布对数据源进行的更改。</span><span class="sxs-lookup"><span data-stu-id="0c812-p102">Many applications fetch a number of rows at once and then need to make coordinated updates that include the entire set of rows to be inserted, updated, or deleted. With batch cursors, only one round trip to the server is needed, thus improving update performance and decreasing network traffic. Using a batch cursor library, you can create a static cursor and then disconnect from the data source. At this point you can make changes to the rows and subsequently reconnect and post the changes to the data source in a batch.</span></span>

## <a name="adlockoptimistic"></a><span data-ttu-id="0c812-111">adLockOptimistic</span><span class="sxs-lookup"><span data-stu-id="0c812-111">adLockOptimistic</span></span>

<span data-ttu-id="0c812-p103">指示提供程序使用开放式锁定，只有调用 **Update** 方法时才锁定记录。这意味着，在您编辑记录到您调用 **Update** 的时间间隔内，其他用户可能会更改数据，从而导致冲突。这种锁定类型用于很少出现冲突或者冲突易于解决的情形。</span><span class="sxs-lookup"><span data-stu-id="0c812-p103">Indicates that the provider uses optimistic locking — locking records only when you call the **Update** method. This means that there is a chance that the data may be changed by another user between the time you edit the record and when you call **Update**, which creates conflicts. Use this lock type in situations where the chances of a collision are low or where collisions can be readily resolved.</span></span>

## <a name="adlockpessimistic"></a><span data-ttu-id="0c812-115">adLockPessimistic</span><span class="sxs-lookup"><span data-stu-id="0c812-115">adLockPessimistic</span></span>

<span data-ttu-id="0c812-p104">指示以保守方式逐个锁定记录。提供程序执行必要的操作以确保成功编辑记录，通常是通过在编辑之前先在数据源锁定记录来实现。当然，这意味着在您开始编辑之后，其他用户将无法使用这些记录，直到您通过调用 **Update** 来解除锁定。这种类型的锁定用在无法承受对数据进行并发更改的系统（如预订系统）中。</span><span class="sxs-lookup"><span data-stu-id="0c812-p104">Indicates pessimistic locking, record by record. The provider does what is necessary to ensure successful editing of the records, usually by locking records at the data source immediately before editing. Of course, this means that the records are unavailable to other users once you begin to edit, until you release the lock by calling **Update.** Use this type of lock in a system where you cannot afford to have concurrent changes to data, such as in a reservation system.</span></span>

## <a name="adlockreadonly"></a><span data-ttu-id="0c812-120">adLockReadOnly</span><span class="sxs-lookup"><span data-stu-id="0c812-120">adLockReadOnly</span></span>

<span data-ttu-id="0c812-p105">指示只读记录。您不能修改数据。只读锁定是"最快"类型的锁定，因为它不需要服务器维护对记录的锁定。</span><span class="sxs-lookup"><span data-stu-id="0c812-p105">Indicates read-only records. You cannot alter the data. A read-only lock is the "fastest" type of lock because it does not require the server to maintain a lock on the records.</span></span>

## <a name="adlockunspecified"></a><span data-ttu-id="0c812-124">adLockUnspecified</span><span class="sxs-lookup"><span data-stu-id="0c812-124">adLockUnspecified</span></span>

<span data-ttu-id="0c812-125">不指定锁定类型。</span><span class="sxs-lookup"><span data-stu-id="0c812-125">Does not specify a type of lock.</span></span>

