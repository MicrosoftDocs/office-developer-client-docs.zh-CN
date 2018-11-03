---
title: 断开和重新连接记录集
TOCTitle: Disconnecting and reconnecting the Recordset
ms:assetid: d608d95d-9a4e-17a1-107a-b88b77f3774c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250077(v=office.15)
ms:contentKeyID: 48547975
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ac1bc4c9c9d6d149faeb18d73f17539e63a4147e
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25943939"
---
# <a name="disconnecting-and-reconnecting-the-recordset"></a><span data-ttu-id="fc608-102">断开和重新连接记录集</span><span class="sxs-lookup"><span data-stu-id="fc608-102">Disconnecting and reconnecting the Recordset</span></span>


<span data-ttu-id="fc608-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fc608-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="disconnecting-and-reconnecting-the-recordset"></a><span data-ttu-id="fc608-104">断开并重新连接记录集</span><span class="sxs-lookup"><span data-stu-id="fc608-104">Disconnecting and Reconnecting the Recordset</span></span>

<span data-ttu-id="fc608-p101">ADO 的一项最强大功能是您能够从数据源打开一个客户端 **Recordset**，然后将该 **Recordset** 与数据源*断开*。一旦 **Recordset** 已断开，即可关闭与数据源的连接，从而释放用来维护该连接的服务器资源。您可以在 **Recordset** 断开的情况下继续查看和编辑其中的数据，随后再重新连接到数据源，并在批模式下发送更新。</span><span class="sxs-lookup"><span data-stu-id="fc608-p101">One of the most powerful features found in ADO is the capability to open a client-side **Recordset** from a data source and then *disconnect* the **Recordset** from the data source. Once the **Recordset** has been disconnected, the connection to the data source can be closed, thereby releasing the resources on the server used to maintain it. You can continue to view and edit the data in the **Recordset** while it is disconnected and later reconnect to the data source and send your updates in batch mode.</span></span>

<span data-ttu-id="fc608-p102">若要断开 **Recordset**，请用 **adUseClient** 的游标位置将它打开，然后将 **ActiveConnection** 属性设置为等于 *Nothing*。（C++ 用户应当将 **ActiveConnection** 设置为等于 NULL 才能断开连接。）</span><span class="sxs-lookup"><span data-stu-id="fc608-p102">To disconnect a **Recordset**, open it with a cursor location of **adUseClient**, and then set the **ActiveConnection** property equal to *Nothing*. (C++ users should set the **ActiveConnection** equal to NULL to disconnect.)</span></span>

<span data-ttu-id="fc608-110">在某些情况下，我们需要在客户端计算机不连接网络时让应用程序可以使用 **Recordset** 中的数据，本章随后将针对该情况讨论 **Recordset** 持久化，到时将使用断开的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="fc608-110">We will use a disconnected **Recordset** later in this chapter when we discuss **Recordset** persistence to address a scenario in which we need to have the data in a **Recordset** available to an application while the client computer is not connected to a network.</span></span>

