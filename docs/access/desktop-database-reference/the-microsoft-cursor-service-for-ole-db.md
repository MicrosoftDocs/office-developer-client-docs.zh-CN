---
title: Microsoft Cursor Service for OLE DB
TOCTitle: The Microsoft Cursor Service for OLE DB
ms:assetid: 31861eef-9860-c884-3c60-9794def7be78
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249088(v=office.15)
ms:contentKeyID: 48544057
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5b84899cc4dd8a85cc48ab26057935c9ab150361
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468218"
---
# <a name="the-microsoft-cursor-service-for-ole-db"></a><span data-ttu-id="7448c-102">Microsoft Cursor Service for OLE DB</span><span class="sxs-lookup"><span data-stu-id="7448c-102">The Microsoft Cursor Service for OLE DB</span></span>


<span data-ttu-id="7448c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7448c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7448c-p101">当选择客户端游标时，或将 **CursorLocation** 属性设置为 **adUseClient** 时，就激活了 Microsoft Cursor Service for OLE DB。您还可能看到"客户端游标引擎"的参考，该参考实际上与 ADO 上下文中的内容是相同的。此服务补充了数据提供程序的游标支持功能。这样，您就可以理解所有数据提供程序的相对统一的功能。</span><span class="sxs-lookup"><span data-stu-id="7448c-p101">When you select a client-side cursor, or set the **CursorLocation** property to **adUseClient**, you are invoking the Microsoft Cursor Service for OLE DB. You might also see references to the "Client Cursor Engine", which is essentially the same thing in the context of ADO. This service supplements the cursor-support functions of data providers. As a result, you can perceive relatively uniform functionality from all data providers.</span></span>

<span data-ttu-id="7448c-p102">Cursor Service for OLE DB 使得动态属性变为可用，并增强了某些方法的行为。例如，利用 **Optimize** 动态属性可以创建临时索引以简化某些操作，如 **Find** 方法。</span><span class="sxs-lookup"><span data-stu-id="7448c-p102">The Cursor Service for OLE DB makes dynamic properties available and enhances the behavior of certain methods. For example, the **Optimize** dynamic property enables the creation of temporary indexes to facilitate certain operations, such as the **Find** method.</span></span>

<span data-ttu-id="7448c-p103">在所有情况下，Cursor Service 都支持批更新。此外，如果数据提供程序只能提供功能不太强的游标（如静态游标），Cursor Service 还可以模拟功能较强的游标类型（如动态游标）。</span><span class="sxs-lookup"><span data-stu-id="7448c-p103">The Cursor Service enables support for batch updating in all cases. It also simulates more capable cursor types, such as dynamic cursors, when a data provider can only supply less capable cursors, such as static cursors.</span></span>

