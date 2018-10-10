---
title: 游标位置的重要性
TOCTitle: The Significance of Cursor Location
ms:assetid: 57cf91a0-2612-b1ca-1c03-9c1ccb396b2e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249296(v=office.15)
ms:contentKeyID: 48544978
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e1b552ac2774fe0c5d47c19924219800e5bdf865
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466390"
---
# <a name="the-significance-of-cursor-location"></a>游标位置的重要性


**适用于**： Access 2013 |Office 2013

每个游标都使用临时资源保存其数据。 这些资源可以是内存、磁盘页面文件、临时磁盘文件甚至可以是数据库中的临时存储区。 当这些资源位于客户端计算机上时，光标被称为*客户端*游标。 光标时这些资源位于服务器上调用*服务器端*游标。

## <a name="client-side-cursors"></a>客户端游标

在 ADO 中，使用 **adUseClient** **CursorLocationEnum** 调用客户端游标。利用非键集客户端游标，服务器将整个结果集通过网络发送给客户端计算机。客户端计算机提供游标和结果集所需的临时资源并对这些资源进行管理。客户端应用程序可以浏览整个结果集以确定所需的行。

如果静态和键集驱动的客户端游标包括过多的行，它们可能会成为工作站上重大的负载。尽管所有游标库都能够构建包含数以千计的行的游标，设计用于提取如此大的行集的应用程序也可能会表现不佳。当然，也存在例外情况。对于某些应用程序，大客户端游标可能非常合适，而性能可能不再是问题。

客户端游标的一个明显优势是快速响应。将结果集下载到客户端计算机后，可以非常快速地浏览行。使用客户端游标的应用程序的伸缩性通常会更大，因为游标的资源要求被放置在每个单独的客户端上，而不是在服务器上。

## <a name="server-side-cursors"></a>服务器端游标

在 ADO 中，使用 **adUseServer** **CursorLocationEnum** 调用服务器端游标。利用服务器端游标，服务器使用服务器计算机所提供的资源管理结果集。服务器端游标仅返回通过网络请求的数据。有时，这种游标会比客户端游标提供更好的性能，尤其是存在网络流量过大的问题时。

但是，必须指出：对于每个活动客户端，服务器端游标至少会临时消耗宝贵的服务器资源。您必须作出相应的计划以确保服务器硬件有能力管理活动客户端请求的所有服务器端游标。另外，由于服务器端游标只提供单行访问，不存在批游标，服务器游标可能会很慢。

在插入、更新或删除记录时，服务器端游标非常有用。利用服务器游标，可以在同一连接上使用多个活动语句。

