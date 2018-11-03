---
title: 游标位置的重要性
TOCTitle: The Significance of Cursor Location
ms:assetid: 57cf91a0-2612-b1ca-1c03-9c1ccb396b2e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249296(v=office.15)
ms:contentKeyID: 48544978
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7054e25cd5768a8016ae7ea58f551be7dbb90cec
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944394"
---
# <a name="significance-of-cursor-location"></a><span data-ttu-id="83e73-102">游标位置的重要性</span><span class="sxs-lookup"><span data-stu-id="83e73-102">Significance of cursor location</span></span>

<span data-ttu-id="83e73-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="83e73-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="83e73-104">每个游标都使用临时资源保存其数据。</span><span class="sxs-lookup"><span data-stu-id="83e73-104">Every cursor uses temporary resources to hold its data.</span></span> <span data-ttu-id="83e73-105">这些资源可以是内存、磁盘页面文件、临时磁盘文件甚至可以是数据库中的临时存储区。</span><span class="sxs-lookup"><span data-stu-id="83e73-105">These resources can be memory, a disk paging file, temporary disk files, or even temporary storage in the database.</span></span> <span data-ttu-id="83e73-106">当这些资源位于客户端计算机上时，光标被称为*客户端*游标。</span><span class="sxs-lookup"><span data-stu-id="83e73-106">The cursor is called a *client-side* cursor when these resources are located on the client computer.</span></span> <span data-ttu-id="83e73-107">光标时这些资源位于服务器上调用*服务器端*游标。</span><span class="sxs-lookup"><span data-stu-id="83e73-107">The cursor is called a *server-side* cursor when these resources are located on the server.</span></span>

## <a name="client-side-cursors"></a><span data-ttu-id="83e73-108">客户端游标</span><span class="sxs-lookup"><span data-stu-id="83e73-108">Client-Side Cursors</span></span>

<span data-ttu-id="83e73-p102">在 ADO 中，使用 **adUseClient** **CursorLocationEnum** 调用客户端游标。利用非键集客户端游标，服务器将整个结果集通过网络发送给客户端计算机。客户端计算机提供游标和结果集所需的临时资源并对这些资源进行管理。客户端应用程序可以浏览整个结果集以确定所需的行。</span><span class="sxs-lookup"><span data-stu-id="83e73-p102">In ADO, call for a client-side cursor by using the **adUseClient** **CursorLocationEnum**. With a non-keyset client-side cursor, the server sends the entire result set across the network to the client computer. The client computer provides and manages the temporary resources needed by the cursor and result set. The client-side application can browse through the entire result set to determine which rows it requires.</span></span>

<span data-ttu-id="83e73-p103">如果静态和键集驱动的客户端游标包括过多的行，它们可能会成为工作站上重大的负载。尽管所有游标库都能够构建包含数以千计的行的游标，设计用于提取如此大的行集的应用程序也可能会表现不佳。当然，也存在例外情况。对于某些应用程序，大客户端游标可能非常合适，而性能可能不再是问题。</span><span class="sxs-lookup"><span data-stu-id="83e73-p103">Static and keyset-driven client-side cursors may place a significant load on your workstation if they include too many rows. While all of the cursor libraries are capable of building cursors with thousands of rows, applications designed to fetch such large rowsets may perform poorly. There are exceptions, of course. For some applications, a large client-side cursor might be perfectly appropriate and performance might not be an issue.</span></span>

<span data-ttu-id="83e73-p104">客户端游标的一个明显优势是快速响应。将结果集下载到客户端计算机后，可以非常快速地浏览行。使用客户端游标的应用程序的伸缩性通常会更大，因为游标的资源要求被放置在每个单独的客户端上，而不是在服务器上。</span><span class="sxs-lookup"><span data-stu-id="83e73-p104">One obvious benefit of the client-side cursor is quick response. After the result set has been downloaded to the client computer, browsing through the rows is very fast. Your application is generally more scalable with client-side cursors because the cursor's resource requirements are placed on each separate client and not on the server.</span></span>

## <a name="server-side-cursors"></a><span data-ttu-id="83e73-120">服务器端游标</span><span class="sxs-lookup"><span data-stu-id="83e73-120">Server-Side Cursors</span></span>

<span data-ttu-id="83e73-p105">在 ADO 中，使用 **adUseServer** **CursorLocationEnum** 调用服务器端游标。利用服务器端游标，服务器使用服务器计算机所提供的资源管理结果集。服务器端游标仅返回通过网络请求的数据。有时，这种游标会比客户端游标提供更好的性能，尤其是存在网络流量过大的问题时。</span><span class="sxs-lookup"><span data-stu-id="83e73-p105">In ADO, call for a server-side cursor by using the **adUseServer** **CursorLocationEnum.** With a server-side cursor, the server manages the result set using resources provided by the server computer. The server-side cursor returns only the requested data over the network. This type of cursor can sometimes provide better performance than the client-side cursor, especially in situations where excessive network traffic is a problem.</span></span>

<span data-ttu-id="83e73-p106">但是，必须指出：对于每个活动客户端，服务器端游标至少会临时消耗宝贵的服务器资源。您必须作出相应的计划以确保服务器硬件有能力管理活动客户端请求的所有服务器端游标。另外，由于服务器端游标只提供单行访问，不存在批游标，服务器游标可能会很慢。</span><span class="sxs-lookup"><span data-stu-id="83e73-p106">However, it is important to point out that a server-side cursor is — at least temporarily — consuming precious server resources for every active client. You must plan accordingly to ensure that your server hardware is capable of managing all of the server-side cursors requested by active clients. Also, a server-side cursor can be slow because it provides only single row access — there is no batch cursor available.</span></span>

<span data-ttu-id="83e73-p107">在插入、更新或删除记录时，服务器端游标非常有用。利用服务器游标，可以在同一连接上使用多个活动语句。</span><span class="sxs-lookup"><span data-stu-id="83e73-p107">Server-side cursors are useful when inserting, updating, or deleting records. With server-side cursors, you can have multiple active statements on the same connection.</span></span>

