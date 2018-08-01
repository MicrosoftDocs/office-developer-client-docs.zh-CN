---
title: 快速关闭概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a7830d73-427c-4f8b-86f4-51e040c142c3
description: 上次修改时间： 2012 年 6 月 26 日
ms.openlocfilehash: 17b1307427af2c35fe9ba8ee40dc78958e6b4a21
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774897"
---
# <a name="fast-shutdown-overview"></a><span data-ttu-id="6a949-103">快速关闭概述</span><span class="sxs-lookup"><span data-stu-id="6a949-103">Fast Shutdown Overview</span></span>

<span data-ttu-id="6a949-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6a949-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6a949-105">快速关闭是一种机制，MAPI 客户端启动的快速关闭通知与客户端有活动 MAPI 会话保存数据和设置在客户端进程退出之前的所有提供程序的客户端过程。</span><span class="sxs-lookup"><span data-stu-id="6a949-105">Fast shutdown is a mechanism for a MAPI client to initiate a quick shutdown of the client process, notifying all providers with which the client has an active MAPI session to save data and settings before the client process exits.</span></span> <span data-ttu-id="6a949-106">本主题介绍快速关闭的基本机制。</span><span class="sxs-lookup"><span data-stu-id="6a949-106">This topic describes the basic mechanism of fast shutdown.</span></span> 

<span data-ttu-id="6a949-107">启动 Microsoft Outlook 2010 中，现在包括 Microsoft Outlook 2013 MAPI 子系统提供[IMAPIClientShutdown: IUnknown](imapiclientshutdowniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="6a949-107">Starting in Microsoft Outlook 2010 and now including Microsoft Outlook 2013, the MAPI subsystem provides the [IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md) interface.</span></span> <span data-ttu-id="6a949-108">Outlook 和其他 MAPI 客户端可以作为默认机制退出客户端进程采用快速关闭。</span><span class="sxs-lookup"><span data-stu-id="6a949-108">Outlook and other MAPI clients can adopt fast shutdown as the default mechanism to exit the client process.</span></span> <span data-ttu-id="6a949-109">客户端计算机的 Windows 注册表中的用户级别设置控制采用快速关闭该计算机上的用户的所有 MAPI 客户端。</span><span class="sxs-lookup"><span data-stu-id="6a949-109">A user-level setting in the Windows registry of the client computer controls the adoption of fast shutdown for all MAPI clients for that user on that computer.</span></span> <span data-ttu-id="6a949-110">有关注册表设置的详细信息，请参阅[Fast 关闭用户选项](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="6a949-110">For details about the registry settings, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span>
  
<span data-ttu-id="6a949-111">如果需要采用快速关闭 MAPI 客户端，它必须使用**IMAPIClientShutdown: IUnknown**接口。</span><span class="sxs-lookup"><span data-stu-id="6a949-111">If a MAPI client needs to adopt fast shutdown, it must use the **IMAPIClientShutdown : IUnknown** interface.</span></span> <span data-ttu-id="6a949-112">下面是典型课程客户端尝试关闭时的事件：</span><span class="sxs-lookup"><span data-stu-id="6a949-112">The following is the typical course of events when the client attempts to shut down:</span></span> 
  
1. <span data-ttu-id="6a949-113">MAPI 客户端启动关闭通过调用[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法以确定是否 MAPI 子系统支持快速关闭。</span><span class="sxs-lookup"><span data-stu-id="6a949-113">The MAPI client initiates the shutdown by calling the [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) method to determine whether the MAPI subsystem supports fast shutdown.</span></span> 
    
2. <span data-ttu-id="6a949-114">MAPI 子系统响应可用的快速关闭支持客户端的**IMAPIClientShutdown::QueryFastShutdown**呼叫通过使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="6a949-114">The MAPI subsystem responds with the available fast shutdown support to the client's **IMAPIClientShutdown::QueryFastShutdown** call by using the following procedure:</span></span> 
    
    1. <span data-ttu-id="6a949-115">MAPI 子系统在如果提供程序已实现与 MAPI 客户端进程具有活动的 MAPI 会话，每个 MAPI 提供程序调用[IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md)方法[IMAPIProviderShutdown: IUnknown](imapiprovidershutdowniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="6a949-115">The MAPI subsystem calls the [IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) method for each MAPI provider with which the MAPI client process has an active MAPI session, if the provider has implemented the [IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md) interface.</span></span> 
        
       > [!NOTE]
       >  <span data-ttu-id="6a949-116">MAPI 子系统始终查询，并通知通过 MAPI 提供程序**IMAPIProviderShutdown: IUnknown**中按以下顺序每个 MAPI 会话接口：</span><span class="sxs-lookup"><span data-stu-id="6a949-116">The MAPI subsystem always queries and notifies MAPI providers through the **IMAPIProviderShutdown : IUnknown** interface within each MAPI session in the following order:</span></span>
       > 1. <span data-ttu-id="6a949-117">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="6a949-117">Transport providers</span></span>
       > 2. <span data-ttu-id="6a949-118">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="6a949-118">Address book providers</span></span>
       > 3. <span data-ttu-id="6a949-119">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="6a949-119">Store providers</span></span> 
    
    2. <span data-ttu-id="6a949-120">根据客户端计算机上该用户的快速关闭注册表设置，MAPI 子系统指定相应到**IMAPIClientShutdown::QueryFastShutdown**的返回代码。</span><span class="sxs-lookup"><span data-stu-id="6a949-120">Depending on the fast shutdown registry setting for that user on the client computer, the MAPI subsystem specifies the appropriate return code to **IMAPIClientShutdown::QueryFastShutdown**.</span></span> <span data-ttu-id="6a949-121">返回的代码是 S_OK 或 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="6a949-121">The return code is either S_OK or MAPI_E_NO_SUPPORT.</span></span>
        
    3. <span data-ttu-id="6a949-122">MAPI 客户端调用[IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)方法，以指示到 MAPI 子系统关闭的目的。</span><span class="sxs-lookup"><span data-stu-id="6a949-122">The MAPI client calls the [IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) method to indicate to the MAPI subsystem the intention to shut down.</span></span> 
        
    4. <span data-ttu-id="6a949-123">MAPI 子系统表示 MAPI 客户端将关闭每个加载 MAPI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="6a949-123">The MAPI subsystem indicates to each loaded MAPI provider that the MAPI client will shut down.</span></span> <span data-ttu-id="6a949-124">已实现这些提供程序**IMAPIProviderShutdown: IUnknown**接口，MAPI 子系统调用相应的[IMAPIProviderShutdown::NotifyProcessShutdown](imapiprovidershutdown-notifyprocessshutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6a949-124">For those providers that have implemented the **IMAPIProviderShutdown : IUnknown** interface, the MAPI subsystem calls the corresponding [IMAPIProviderShutdown::NotifyProcessShutdown](imapiprovidershutdown-notifyprocessshutdown.md) method.</span></span> 
        
    5. <span data-ttu-id="6a949-125">MAPI 客户端调用[IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md)方法向 MAPI 子系统指示客户端进程正在立即退出。</span><span class="sxs-lookup"><span data-stu-id="6a949-125">The MAPI client calls the [IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md) method to indicate to the MAPI subsystem that the client process is exiting immediately.</span></span> 
        
    6. <span data-ttu-id="6a949-126">MAPI 子系统指示每个加载的 MAPI 提供程序，退出 MAPI 客户端进程。</span><span class="sxs-lookup"><span data-stu-id="6a949-126">The MAPI subsystem indicates to each loaded MAPI provider that the MAPI client process is exiting.</span></span> <span data-ttu-id="6a949-127">已实现这些提供程序**IMAPIProviderShutdown: IUnknown**接口，MAPI 子系统调用相应的[IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6a949-127">For those providers that have implemented the **IMAPIProviderShutdown : IUnknown** interface, the MAPI subsystem calls the corresponding [IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md) method.</span></span> <span data-ttu-id="6a949-128">此时，这些 MAPI 提供程序应验证所有必要的操作，如保存数据和设置，已完成在准备 MAPI 客户端立即断开连接的所有引用并退出。</span><span class="sxs-lookup"><span data-stu-id="6a949-128">At this point, these MAPI providers should verify that all necessary actions, such as saving data and settings, are complete in preparation for the MAPI client to immediately disconnect all references and exit.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6a949-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a949-129">See also</span></span>

- [<span data-ttu-id="6a949-130">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="6a949-130">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)
- [<span data-ttu-id="6a949-131">快速关闭用户选项</span><span class="sxs-lookup"><span data-stu-id="6a949-131">Fast Shutdown User Options</span></span>](fast-shutdown-user-options.md)
- [<span data-ttu-id="6a949-132">快速关闭的最佳实践</span><span class="sxs-lookup"><span data-stu-id="6a949-132">Best Practices for Fast Shutdown</span></span>](best-practices-for-fast-shutdown.md)

