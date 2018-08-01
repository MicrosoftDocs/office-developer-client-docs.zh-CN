---
title: 处理传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 60b3e5f4-4a9b-432f-bad4-4284225ab93f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 140fe97662f7a2ce68c18d8e0eb991d0819da6dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775032"
---
# <a name="handling-a-transport-provider"></a><span data-ttu-id="af42f-103">处理传输提供程序</span><span class="sxs-lookup"><span data-stu-id="af42f-103">Handling a transport provider</span></span>
  
<span data-ttu-id="af42f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="af42f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="af42f-105">客户端与通过状态对象由传输提供程序和 MAPI 后台处理程序提供的传输提供程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="af42f-105">Clients communicate with transport providers through status objects supplied by transport providers and the MAPI spooler.</span></span> <span data-ttu-id="af42f-106">客户端访问通过调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)检索状态表的状态的对象。</span><span class="sxs-lookup"><span data-stu-id="af42f-106">Clients access status objects by calling [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to retrieve the status table.</span></span> <span data-ttu-id="af42f-107">状态对象实现[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口，其中包含方法的配置提供程序、 刷新传入和传出消息队列、 设置密码和状态验证。</span><span class="sxs-lookup"><span data-stu-id="af42f-107">Status objects implement the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface, which has methods for configuring providers, flushing incoming and outgoing message queues, setting passwords, and state validation.</span></span> <span data-ttu-id="af42f-108">有关状态的对象的详细信息，请参阅[状态表和状态对象](status-table-and-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="af42f-108">For more information about status objects, see [Status Table and Status Objects](status-table-and-status-objects.md).</span></span>


- <span data-ttu-id="af42f-109">[发送或接收 on Demand 消息](sending-or-receiving-a-message-on-demand.md)： 介绍如何发送或接收按需型一条消息。</span><span class="sxs-lookup"><span data-stu-id="af42f-109">[Sending or Receiving a Message on Demand](sending-or-receiving-a-message-on-demand.md): Describes how to send or receive a message on demand.</span></span>
    
- <span data-ttu-id="af42f-110">[设置传输顺序](setting-transport-order.md)： 介绍如何设置传输顺序。</span><span class="sxs-lookup"><span data-stu-id="af42f-110">[Setting Transport Order](setting-transport-order.md): Describes how to set transport order.</span></span>
    
- <span data-ttu-id="af42f-111">[重新配置传输提供程序](reconfiguring-a-transport-provider.md)： 介绍如何重新配置的传输提供程序以及哪些属性可设置。</span><span class="sxs-lookup"><span data-stu-id="af42f-111">[Reconfiguring a Transport Provider](reconfiguring-a-transport-provider.md): Describes how to reconfigure a transport provider and what properties are available to set.</span></span>
    

