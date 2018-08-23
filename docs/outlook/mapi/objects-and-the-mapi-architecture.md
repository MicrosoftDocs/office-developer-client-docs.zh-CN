---
title: 对象和 MAPI 体系结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c3bcbda5-820d-4ef5-bffd-c254eea9dff6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 29a61ff8f7894c5582d31895bacd74e1ebcaa49c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583874"
---
# <a name="objects-and-the-mapi-architecture"></a><span data-ttu-id="607cc-103">对象和 MAPI 体系结构</span><span class="sxs-lookup"><span data-stu-id="607cc-103">Objects and the MAPI architecture</span></span>

<span data-ttu-id="607cc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="607cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="607cc-105">MAPI 体系结构中的一个或多个图层属于的所有 MAPI 定义对象。</span><span class="sxs-lookup"><span data-stu-id="607cc-105">All of the objects that MAPI defines fall into one or more layers in the MAPI architecture.</span></span> <span data-ttu-id="607cc-106">客户端接口层包含客户端应用程序、 窗体查看器或窗体服务器可以实现的所有对象。</span><span class="sxs-lookup"><span data-stu-id="607cc-106">The client interface layer contains all the objects that a client application, form viewer, or form server can implement.</span></span> <span data-ttu-id="607cc-107">服务提供程序接口层包含任何类型的服务提供商可以实现的对象。</span><span class="sxs-lookup"><span data-stu-id="607cc-107">The service provider interface layer contains the objects that a service provider of any type can implement.</span></span> <span data-ttu-id="607cc-108">该层包括实现通过通讯簿、 消息存储、 传输提供程序和表单库的对象。</span><span class="sxs-lookup"><span data-stu-id="607cc-108">This layer includes objects implemented by address books, message stores, transport providers, and form libraries.</span></span> <span data-ttu-id="607cc-109">代表 MAPI 子系统层位于客户端与服务提供程序界面层之间。</span><span class="sxs-lookup"><span data-stu-id="607cc-109">The layer that represents the MAPI subsystem is positioned between the client and service provider interface layers.</span></span> <span data-ttu-id="607cc-110">MAPI 层包含的所有客户端或服务提供商使用 MAPI 实现的对象。</span><span class="sxs-lookup"><span data-stu-id="607cc-110">The MAPI layer contains all of the objects that MAPI implements for clients or service providers to use.</span></span> 
  
<span data-ttu-id="607cc-111">下图显示了每个 MAPI 对象到 MAPI 体系结构适合的位置。</span><span class="sxs-lookup"><span data-stu-id="607cc-111">The following illustration shows where each of the MAPI objects fits into the MAPI architecture.</span></span> <span data-ttu-id="607cc-112">对象表示与及其派生接口的名称。</span><span class="sxs-lookup"><span data-stu-id="607cc-112">The objects are represented with the names of their derived interfaces.</span></span> <span data-ttu-id="607cc-113">例如，advise 接收器对象显示为[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)，从[iunknown 导出](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)派生并在每个 advise 接收器对象实现的接口。</span><span class="sxs-lookup"><span data-stu-id="607cc-113">For example, an advise sink object is shown as [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md), the interface that derives from [IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) and that every advise sink object implements.</span></span> <span data-ttu-id="607cc-114">桥接图层的接口是或使用由多个组件实现。</span><span class="sxs-lookup"><span data-stu-id="607cc-114">The interfaces that bridge layers are either used or implemented by multiple components.</span></span> <span data-ttu-id="607cc-115">尽管 MAPI 层显示到单独的客户端和提供程序层，这意味着所有通信必须都流过 MAPI，但这不是这种情况。</span><span class="sxs-lookup"><span data-stu-id="607cc-115">Although the MAPI layer appears to separate the client and provider layers, implying that all communication must flow through MAPI, this is not the case.</span></span> <span data-ttu-id="607cc-116">客户端可以和执行通信直接向服务提供商对象。</span><span class="sxs-lookup"><span data-stu-id="607cc-116">Clients can and do communicate directly to service provider objects.</span></span> 
  
<span data-ttu-id="607cc-117">**MAPI 中的对象层**</span><span class="sxs-lookup"><span data-stu-id="607cc-117">**Object layers in MAPI**</span></span>
  
<span data-ttu-id="607cc-118">![MAPI 中的对象层](media/amapi_38.gif "MAPI 中的对象层")</span><span class="sxs-lookup"><span data-stu-id="607cc-118">![Object layers in MAPI](media/amapi_38.gif "Object layers in MAPI")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="607cc-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="607cc-119">See also</span></span>

- [<span data-ttu-id="607cc-120">IMAPIAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="607cc-120">IMAPIAdviseSink : IUnknown</span></span>](imapiadvisesinkiunknown.md)
- [<span data-ttu-id="607cc-121">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="607cc-121">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

