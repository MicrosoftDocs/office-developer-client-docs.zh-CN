---
title: 第 5 章：更新和暂留数据
TOCTitle: 'Chapter 5: Updating and persisting data'
ms:assetid: 77acb763-1c60-1945-791d-3e83d684fb0d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249493(v=office.15)
ms:contentKeyID: 48545732
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 18dd63acd733624fba522ee7382f305d34019905
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296428"
---
# <a name="chapter-5-updating-and-persisting-data"></a><span data-ttu-id="1b2be-102">第 5 章：更新和暂留数据</span><span class="sxs-lookup"><span data-stu-id="1b2be-102">Chapter 5: Updating and persisting data</span></span>

<span data-ttu-id="1b2be-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1b2be-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1b2be-p101">前面几章讨论了如何使用 ADO 来获取数据源中的数据、如何在数据中移动以及如何编辑数据。当然，如果您的应用程序的目标是允许用户对数据进行更改，那么，您将需要了解如何保存这些更改。可以使用 **Save** 方法持久化对文件进行的 **Recordset** 更改，或者使用 **Update** 或 **UpdateBatch** 方法将所做的更改发回到数据源进行存储。</span><span class="sxs-lookup"><span data-stu-id="1b2be-p101">The preceding chapters have discussed how to use ADO to get to data in a data source, how to move around in the data, and even how to edit the data. Of course, if the goal of your application is to allow users to make changes to the data, you will need to understand how to save those changes. You can either persist the **Recordset** changes to a file using the **Save** method, or you can send the changes back to the data source for storage using the **Update** or **UpdateBatch** methods.</span></span>

<span data-ttu-id="1b2be-p102">在前面的几章中，您更改了 **Recordset** 的若干行中的数据。ADO 支持两个与添加、删除和修改数据行相关的基本理念。</span><span class="sxs-lookup"><span data-stu-id="1b2be-p102">In the preceding chapters, you changed the data in several rows of the **Recordset**. ADO supports two basic notions relating to the addition, deletion, and modification of rows of data.</span></span>

<span data-ttu-id="1b2be-p103">第一个理念是，更改不是直接针对 **Recordset** 进行的；而是针对内部*复制缓冲区*进行的。如果您决定不进行这些更改，则复制缓冲区中的修改将被放弃。如果您决定保留这些更改，则复制缓冲区中的更改将应用于 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="1b2be-p103">The first notion is that changes aren't immediately made to the **Recordset**; instead, they are made to an internal *copy buffer*. If you decide you don't want the changes, the modifications in the copy buffer are discarded. If you decide to keep the changes, the changes in the copy buffer are applied to the **Recordset**.</span></span>

<span data-ttu-id="1b2be-p104">第二个理念是，一旦您声明已完成对某一行的工作，所做的更改将立即传播到数据源（即，*即时*模式），或者收集对行集进行的所有更改，直到您声明已完成记录集工作（即，*批处理*模式）。**LockType** 属性确定何时对基础数据源进行更改。**adLockOptimistic** 或 **adLockPessimistic** 指定即时模式，而 **adLockBatchOptimistic** 指定批处理模式。**CursorLocation** 属性可以影响哪些 **LockType** 设置可用。例如，如果 **CursorLocation** 属性设置为 **adUseClient**，则 **adLockPessimistic** 设置不受支持。</span><span class="sxs-lookup"><span data-stu-id="1b2be-p104">The second notion is that changes are either propagated to the data source as soon as you declare the work on a row complete (that is, *immediate* mode), or all changes to a set of rows are collected until you declare the work for the set complete (that is, *batch* mode). The **LockType** property determines when the changes are made to the underlying data source. **adLockOptimistic** or **adLockPessimistic** specifies immediate mode, while **adLockBatchOptimistic** specifies batch mode. The **CursorLocation** property can affect which **LockType** settings are available. For instance, the **adLockPessimistic** setting is not supported if the **CursorLocation** property is set to **adUseClient**.</span></span>

<span data-ttu-id="1b2be-p105">在即时模式下，每次调用 **Update** 方法都会将所做的更改传播到数据源。在批处理模式下，每次调用 **Update** 或者每次移动当前行的位置时，都会保存对复制缓冲区进行的更改，但是，只有 **UpdateBatch** 方法才将所做的更改传播到数据源。</span><span class="sxs-lookup"><span data-stu-id="1b2be-p105">In immediate mode, each invocation of the **Update** method propagates the changes to the data source. In batch mode, each invocation of **Update** or movement of the current row position saves the changes to the copy buffer, but only the **UpdateBatch** method propagates the changes to the data source.</span></span>

<span data-ttu-id="1b2be-119">本章包含以下主题：</span><span class="sxs-lookup"><span data-stu-id="1b2be-119">This chapter covers the following topics:</span></span>

- [<span data-ttu-id="1b2be-120">更新数据 (ADO)</span><span class="sxs-lookup"><span data-stu-id="1b2be-120">Updating data (ADO)</span></span>](updating-data.md)
- [<span data-ttu-id="1b2be-121">持久化数据 (ADO)</span><span class="sxs-lookup"><span data-stu-id="1b2be-121">Persisting data (ADO)</span></span>](persisting-data.md)
