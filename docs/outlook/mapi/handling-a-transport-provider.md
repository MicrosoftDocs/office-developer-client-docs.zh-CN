---
title: 处理传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 60b3e5f4-4a9b-432f-bad4-4284225ab93f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0fe21cea26c956f8a03a51e2f302b040fc89e751
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416536"
---
# <a name="handling-a-transport-provider"></a><span data-ttu-id="2f5e1-103">处理传输提供程序</span><span class="sxs-lookup"><span data-stu-id="2f5e1-103">Handling a transport provider</span></span>
  
<span data-ttu-id="2f5e1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f5e1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f5e1-105">客户端通过传输提供程序和 MAPI 后台处理程序提供的状态对象与传输提供程序通信。</span><span class="sxs-lookup"><span data-stu-id="2f5e1-105">Clients communicate with transport providers through status objects supplied by transport providers and the MAPI spooler.</span></span> <span data-ttu-id="2f5e1-106">客户端通过调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 来检索状态表来访问状态对象。</span><span class="sxs-lookup"><span data-stu-id="2f5e1-106">Clients access status objects by calling [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to retrieve the status table.</span></span> <span data-ttu-id="2f5e1-107">Status 对象实现 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md) 接口，该接口具有用于配置提供程序、刷新传入和传出邮件队列、设置密码和状态验证的方法。</span><span class="sxs-lookup"><span data-stu-id="2f5e1-107">Status objects implement the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface, which has methods for configuring providers, flushing incoming and outgoing message queues, setting passwords, and state validation.</span></span> <span data-ttu-id="2f5e1-108">有关状态对象的信息，请参阅状态 [表和状态对象](status-table-and-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="2f5e1-108">For more information about status objects, see [Status Table and Status Objects](status-table-and-status-objects.md).</span></span>


- <span data-ttu-id="2f5e1-109">[按需发送或接收邮件](sending-or-receiving-a-message-on-demand.md)：介绍如何按需发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="2f5e1-109">[Sending or Receiving a Message on Demand](sending-or-receiving-a-message-on-demand.md): Describes how to send or receive a message on demand.</span></span>
    
- <span data-ttu-id="2f5e1-110">[设置传输顺序](setting-transport-order.md)：介绍如何设置传输顺序。</span><span class="sxs-lookup"><span data-stu-id="2f5e1-110">[Setting Transport Order](setting-transport-order.md): Describes how to set transport order.</span></span>
    
- <span data-ttu-id="2f5e1-111">[重新配置传输提供程序](reconfiguring-a-transport-provider.md)：介绍如何重新配置传输提供程序以及可以设置的属性。</span><span class="sxs-lookup"><span data-stu-id="2f5e1-111">[Reconfiguring a Transport Provider](reconfiguring-a-transport-provider.md): Describes how to reconfigure a transport provider and what properties are available to set.</span></span>
    

