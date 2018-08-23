---
title: MAPI 会话处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3bc4aea5-ab01-4ba5-a4ad-7a9a76c6bf55
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8c82ff28dca4fc50c7801a533f7ad757b839cddf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568229"
---
# <a name="mapi-session-handling"></a><span data-ttu-id="72559-103">MAPI 会话处理</span><span class="sxs-lookup"><span data-stu-id="72559-103">MAPI Session Handling</span></span>

  
  
<span data-ttu-id="72559-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="72559-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="72559-105">您可以与服务提供商和基础消息系统通信之前，必须建立一个会话。</span><span class="sxs-lookup"><span data-stu-id="72559-105">Before you can communicate with service providers and an underlying messaging system, you must establish a session.</span></span> <span data-ttu-id="72559-106">MAPI 会话是其他 MAPI 组件从客户端的链接。</span><span class="sxs-lookup"><span data-stu-id="72559-106">A MAPI session is a link from a client to other MAPI components.</span></span> <span data-ttu-id="72559-107">成功启动会话的结果，MAPI 返回到客户端会话对象的指针 — 实现**IMAPISession**接口的对象。</span><span class="sxs-lookup"><span data-stu-id="72559-107">As the result of successfully starting a session, MAPI returns to clients a pointer to a session object — an object that implements the **IMAPISession** interface.</span></span> <span data-ttu-id="72559-108">有关详细信息，请参阅[IMAPISession: IUnknown](imapisessioniunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="72559-108">For more information, see [IMAPISession : IUnknown](imapisessioniunknown.md).</span></span> <span data-ttu-id="72559-109">**IMAPISession**接口的方法可用于访问通讯簿和消息存储提供程序的对象、 访问多个表、 显示表单、 设置传输提供程序属性和执行配置文件和消息服务管理。</span><span class="sxs-lookup"><span data-stu-id="72559-109">You can use the methods of the **IMAPISession** interface to access the objects of address book and message store providers, access several tables, display forms, set transport provider properties, and perform profile and message service administration.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="72559-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="72559-110">In this section</span></span>

[<span data-ttu-id="72559-111">启动 MAPI 会话</span><span class="sxs-lookup"><span data-stu-id="72559-111">Starting a MAPI Session</span></span>](starting-a-mapi-session.md)
  
> <span data-ttu-id="72559-112">介绍如何启动 MAPI 会话，并包括具有更多详细信息的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="72559-112">Describes how to start a MAPI session and includes links to topics with more detailed information.</span></span>
    
[<span data-ttu-id="72559-113">结束 MAPI 会话</span><span class="sxs-lookup"><span data-stu-id="72559-113">Ending a MAPI Session</span></span>](ending-a-mapi-session.md)
  
> <span data-ttu-id="72559-114">介绍如何结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="72559-114">Describes how to end a MAPI session.</span></span>
    
[<span data-ttu-id="72559-115">使用会话访问对象</span><span class="sxs-lookup"><span data-stu-id="72559-115">Accessing Objects by Using the Session</span></span>](accessing-objects-by-using-the-session.md)
  
> <span data-ttu-id="72559-116">介绍如何使用会话指针访问会话对象。</span><span class="sxs-lookup"><span data-stu-id="72559-116">Describes how to use a session pointer to access session objects.</span></span>
    
[<span data-ttu-id="72559-117">检索主要标识和提供程序标识</span><span class="sxs-lookup"><span data-stu-id="72559-117">Retrieving Primary and Provider Identity</span></span>](retrieving-primary-and-provider-identity.md)
  
> <span data-ttu-id="72559-118">介绍用于检索主属性和提供程序的标识。</span><span class="sxs-lookup"><span data-stu-id="72559-118">Describes the properties used to retrieve primary and provider identity.</span></span>
    
[<span data-ttu-id="72559-119">状态表和状态对象</span><span class="sxs-lookup"><span data-stu-id="72559-119">Status Table and Status Objects</span></span>](status-table-and-status-objects.md)
  
> <span data-ttu-id="72559-120">介绍如何访问状态表中的信息。</span><span class="sxs-lookup"><span data-stu-id="72559-120">Describes how to access information from the status table.</span></span>
    

