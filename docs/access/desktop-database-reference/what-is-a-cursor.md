---
title: 什么是游标？  （访问桌面数据库参考 （英文）
TOCTitle: What is a Cursor?
ms:assetid: cc70d941-05e0-9b14-1c5d-6b1a5802f546
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250013(v=office.15)
ms:contentKeyID: 48547738
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2023b39620f80e6f770153e381c74d5285d027c6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718936"
---
# <a name="what-is-a-cursor"></a><span data-ttu-id="bbc6f-103">什么是游标？</span><span class="sxs-lookup"><span data-stu-id="bbc6f-103">What is a cursor?</span></span>


<span data-ttu-id="bbc6f-104">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bbc6f-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bbc6f-p102">游标是关系数据库中作用于完整行集的操作。SELECT 语句返回的行集由满足该语句中 WHERE 子句条件的所有行组成。该语句返回的完整行集称为结果集。应用程序（特别是那些处于交互和联机模式的应用程序）不能总是有效地将整个结果集作为一个整体来处理。这些应用程序需要一个机制，以便一次处理一行或一小块行。游标是提供该机制的结果集的扩展。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-p102">Operations in a relational database act on a complete set of rows. The set of rows returned by a SELECT statement consists of all the rows that satisfy the conditions in the WHERE clause of the statement. This complete set of rows returned by the statement is known as the result set. Applications, especially those that are interactive and online, cannot always work effectively with the entire result set as a unit. These applications need a mechanism to work with one row or a small block of rows at a time. Cursors are an extension to result sets that provide that mechanism.</span></span>

<span data-ttu-id="bbc6f-p103">游标由游标库实现。游标库是一个软件，通常作为数据库系统的一部分或数据访问 API 来实现，用于管理从数据源（结果集）所返回数据的属性。这些属性包括并发管理、结果集内的位置、返回的行数以及是否可以在结果集中向前/向后移动（可滚动性）。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-p103">A cursor is implemented by a cursor library. A cursor library is software, often implemented as a part of a database system or a data access API, that is used to manage attributes of data returned from a data source (a result set). These attributes include concurrency management, position in the result set, number of rows returned, and whether or not you can move forward and/or backward through the result set (scrollability).</span></span>

<span data-ttu-id="bbc6f-p104">游标可跟踪结果集内的位置，并允许您针对结果集逐行执行多种操作，可以返回初始表也可以不返回到初始表。换言之，在概念上，游标基于数据库中的表返回结果集。之所以这样命名，是因为游标指示结果集内的当前位置，正如计算机屏幕上的光标指示当前位置一样。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-p104">A cursor keeps track of the position in the result set, and allows you to perform multiple operations row by row against a result set, with or without returning to the original table. In other words, cursors conceptually return a result set based on tables within the databases. The cursor is so named because it indicates the current position in the result set, just as the cursor on a computer screen indicates current position.</span></span>

<span data-ttu-id="bbc6f-117">一定要先熟悉游标的概念，然后再接着了解有关它们在 ADO 中用法的详细说明。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-117">It is important to become familiar with the concept of cursors before moving on to learn the specifics of their usage in ADO.</span></span>

<span data-ttu-id="bbc6f-118">使用游标，您可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bbc6f-118">Using cursors, you can:</span></span>

  - <span data-ttu-id="bbc6f-119">指定特定行在结果集内的位置。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-119">Specify positioning at specific rows in the result set.</span></span>

  - <span data-ttu-id="bbc6f-120">基于结果集内的当前位置来检索一行或一个行块。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-120">Retrieve one row or a block of rows based on the current result set position.</span></span>

  - <span data-ttu-id="bbc6f-121">修改位于结果集内当前位置的行中的数据。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-121">Modify data in the rows at the current position in the result set.</span></span>

  - <span data-ttu-id="bbc6f-122">定义对其他用户所做的数据更改的不同敏感度级别。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-122">Define different levels of sensitivity to data changes made by other users.</span></span>

<span data-ttu-id="bbc6f-p105">例如，假设有一个向潜在购买者显示可用产品列表的应用程序。购买者浏览该列表，查看产品的详细信息和价格，并最终选择要购买的产品。对于该列表中的其余部分，还会进行其他滚动和选择。随着购买者的滚动，应用程序会一次显示一个产品，实际上它是使用可滚动的游标在结果集内上下浏览。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-p105">For example, consider an application that displays a list of available products to a potential buyer. The buyer scrolls through the list to see product details and cost, and finally selects a product for purchase. Additional scrolling and selection occurs for the remainder of the list. As far as the buyer is concerned, the products appear one at a time, but the application uses a scrollable cursor to browse up and down through the result set.</span></span>

<span data-ttu-id="bbc6f-127">可以通过多种方式使用游标：</span><span class="sxs-lookup"><span data-stu-id="bbc6f-127">You can use cursors in a variety of ways:</span></span>

  - <span data-ttu-id="bbc6f-128">不用于任何行。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-128">With no rows at all.</span></span>

  - <span data-ttu-id="bbc6f-129">用于一个表中的部分行或所有行。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-129">With some or all of the rows in a single table.</span></span>

  - <span data-ttu-id="bbc6f-130">用于逻辑联接表中的所有行或部分行。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-130">With some or all of the rows from logically joined tables.</span></span>

  - <span data-ttu-id="bbc6f-131">在游标或字段级别是只读或可更新的。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-131">As read-only or updateable at the cursor or field level.</span></span>

  - <span data-ttu-id="bbc6f-132">仅向前或完全可滚动。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-132">As forward-only or fully scrollable.</span></span>

  - <span data-ttu-id="bbc6f-133">用于服务器中的游标键集。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-133">With the cursor keyset located on the server.</span></span>

  - <span data-ttu-id="bbc6f-134">对其他应用程序所导致的基础表更改（如成员关系、排序、插入、更新和删除）敏感。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-134">Sensitive to underlying table changes caused by other applications (such as membership, sort, inserts, updates, and deletes).</span></span>

  - <span data-ttu-id="bbc6f-135">存在于服务器或客户端上。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-135">Existing on either the server or the client.</span></span>

<span data-ttu-id="bbc6f-p106">只读游标可帮助用户浏览结果集，可读/写游标可用来实现单个行更新。复杂游标可以用指回到基表中行的键集来定义。某些游标在向前方向上是只读的，而另一些游标可以前后移动，并基于其他应用程序对数据库进行的更改来提供对结果集的动态刷新。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-p106">Read-only cursors help users browse through the result set, and read/write cursors can implement individual row updates. Complex cursors can be defined with keysets that point back to base table rows. While some cursors are read-only in a forward direction, others can move back and forth and provide a dynamic refresh of the result set based on changes that other applications are making to the database.</span></span>

<span data-ttu-id="bbc6f-p107">并非所有的应用程序都需要使用游标来访问或更新数据。一些查询完全不需要通过使用游标来直接更新行。在您检索数据时，应尽量选择除游标以外的其他技术；即使您使用游标技术，也应当选择影响最小的游标。当您使用存储过程创建结果集时，使用游标的编辑或更新方法不能更新结果集。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-p107">Not all applications need to use cursors to access or update data. Some queries simply do not require direct row updating by using a cursor. Cursors should be one of the last techniques you choose to retrieve data — and then you should choose the lowest impact cursor possible. When you create a result set by using a stored procedure, the result set is not updateable using cursor edit or update methods.</span></span>

## <a name="concurrency"></a><span data-ttu-id="bbc6f-143">并发</span><span class="sxs-lookup"><span data-stu-id="bbc6f-143">Concurrency</span></span>

<span data-ttu-id="bbc6f-p108">在某些多用户应用程序中，至关重要的是使显示给最终用户的数据尽可能最新。航空订票系统就是此类系统的一个典型示例，在该系统中，许多用户可能会争着预订给定航班上的同一个座位（也就是单个记录）。在这种情况下，应用程序在设计上必需能够处理针对单个记录的并发操作。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-p108">In some multi-user applications it is vitally important for the data presented to the end user to be as current as possible. A classic example of such a system is an airline reservation system, where many users might be contending for the same seat on a given flight (and thus, a single record). In a case like this, the application design must handle concurrent operations on a single record.</span></span>

<span data-ttu-id="bbc6f-p109">在其他应用程序中，并发不是那么重要。在这种情况下，使数据随时保持最新所涉及的资源耗费并无意义。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-p109">In other applications, concurrency is not as important. In such cases, the expense involved in keeping the data current at all times cannot be justified.</span></span>

## <a name="position"></a><span data-ttu-id="bbc6f-149">位置</span><span class="sxs-lookup"><span data-stu-id="bbc6f-149">Position</span></span>

<span data-ttu-id="bbc6f-p110">游标还跟踪结果集内的当前位置。请将游标位置视为指向当前记录的指针，这与数组索引指向数组中特定位置的值的方式类似。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-p110">A cursor also keeps track of the current position in a result set. Think of the cursor position as a pointer to the current record, similar to the way an array index points to the value at that particular location in the array.</span></span>

## <a name="scrollability"></a><span data-ttu-id="bbc6f-152">可滚动性</span><span class="sxs-lookup"><span data-stu-id="bbc6f-152">Scrollability</span></span>

<span data-ttu-id="bbc6f-153">应用程序所使用的游标类型还影响在结果集内的行之间能否向前和向后移动；有时，这也称为可滚动性。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-153">The type of cursor employed by your application also affects the ability to move forward and backward through the rows in a result set; this is sometimes called scrollability.</span></span> <span data-ttu-id="bbc6f-154">将移动向前*和*向后在结果集中的功能将添加到游标的复杂性，因此增加实现成本。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-154">The ability to move forward *and* backward through a result set adds to the complexity of the cursor, and is therefore more expensive to implement.</span></span> <span data-ttu-id="bbc6f-155">因此，应当只在必要时才使用具有该功能的游标。</span><span class="sxs-lookup"><span data-stu-id="bbc6f-155">For this reason, you should ask for a cursor with this functionality only when necessary.</span></span>

