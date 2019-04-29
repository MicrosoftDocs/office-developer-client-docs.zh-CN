---
title: 快速关机概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a7830d73-427c-4f8b-86f4-51e040c142c3
description: 上次修改时间：2012 年 6 月 26 日
ms.openlocfilehash: 8c33214b04e7c41eab173196c09f145c20ddf219
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427204"
---
# <a name="fast-shutdown-overview"></a><span data-ttu-id="bfd33-103">快速关机概述</span><span class="sxs-lookup"><span data-stu-id="bfd33-103">Fast Shutdown Overview</span></span>

<span data-ttu-id="bfd33-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bfd33-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bfd33-105">Fast shutdown 是 MAPI 客户端启动快速关闭客户端进程的一种机制, 它会通知所有提供程序, 让客户端在客户端进程退出之前保存数据和设置。</span><span class="sxs-lookup"><span data-stu-id="bfd33-105">Fast shutdown is a mechanism for a MAPI client to initiate a quick shutdown of the client process, notifying all providers with which the client has an active MAPI session to save data and settings before the client process exits.</span></span> <span data-ttu-id="bfd33-106">本主题介绍快速关闭的基本机制。</span><span class="sxs-lookup"><span data-stu-id="bfd33-106">This topic describes the basic mechanism of fast shutdown.</span></span> 

<span data-ttu-id="bfd33-107">从 microsoft outlook 2010 开始, 现在包括 microsoft outlook 2013, MAPI 子系统提供了[IMAPIClientShutdown: IUnknown](imapiclientshutdowniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="bfd33-107">Starting in Microsoft Outlook 2010 and now including Microsoft Outlook 2013, the MAPI subsystem provides the [IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md) interface.</span></span> <span data-ttu-id="bfd33-108">Outlook 和其他 MAPI 客户端可以采用快速关闭作为默认机制, 以退出客户端进程。</span><span class="sxs-lookup"><span data-stu-id="bfd33-108">Outlook and other MAPI clients can adopt fast shutdown as the default mechanism to exit the client process.</span></span> <span data-ttu-id="bfd33-109">客户端计算机的 Windows 注册表中的用户级别设置控制该计算机上该用户的所有 MAPI 客户端的采用速度。</span><span class="sxs-lookup"><span data-stu-id="bfd33-109">A user-level setting in the Windows registry of the client computer controls the adoption of fast shutdown for all MAPI clients for that user on that computer.</span></span> <span data-ttu-id="bfd33-110">有关注册表设置的详细信息, 请参阅[Fast Shutdown User Options](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="bfd33-110">For details about the registry settings, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span>
  
<span data-ttu-id="bfd33-111">如果 MAPI 客户端需要采用快速关闭, 则必须使用**IMAPIClientShutdown: IUnknown**接口。</span><span class="sxs-lookup"><span data-stu-id="bfd33-111">If a MAPI client needs to adopt fast shutdown, it must use the **IMAPIClientShutdown : IUnknown** interface.</span></span> <span data-ttu-id="bfd33-112">以下是客户端尝试关闭时的典型事件过程:</span><span class="sxs-lookup"><span data-stu-id="bfd33-112">The following is the typical course of events when the client attempts to shut down:</span></span> 
  
1. <span data-ttu-id="bfd33-113">mapi 客户端通过调用[IMAPIClientShutdown:: QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法来确定 mapi 子系统是否支持快速关闭来启动关机。</span><span class="sxs-lookup"><span data-stu-id="bfd33-113">The MAPI client initiates the shutdown by calling the [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) method to determine whether the MAPI subsystem supports fast shutdown.</span></span> 
    
2. <span data-ttu-id="bfd33-114">通过以下过程, MAPI 子系统使用对客户端的**IMAPIClientShutdown:: QueryFastShutdown**调用的可用快速关闭支持进行响应:</span><span class="sxs-lookup"><span data-stu-id="bfd33-114">The MAPI subsystem responds with the available fast shutdown support to the client's **IMAPIClientShutdown::QueryFastShutdown** call by using the following procedure:</span></span> 
    
    1. <span data-ttu-id="bfd33-115">如果提供程序已实现[IMAPIProviderShutdown: IUnknown](imapiprovidershutdowniunknown.md) , 则 mapi 子系统将为 mapi 客户端进程具有活动 mapi 会话的每个 mapi 提供程序调用[IMAPIProviderShutdown:: QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md)方法。交互.</span><span class="sxs-lookup"><span data-stu-id="bfd33-115">The MAPI subsystem calls the [IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) method for each MAPI provider with which the MAPI client process has an active MAPI session, if the provider has implemented the [IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md) interface.</span></span> 
        
       > [!NOTE]
       >  <span data-ttu-id="bfd33-116">mapi 子系统始终按以下顺序在每个 mapi 会话中通过**IMAPIProviderShutdown: IUnknown**接口查询和通知 mapi 提供程序:</span><span class="sxs-lookup"><span data-stu-id="bfd33-116">The MAPI subsystem always queries and notifies MAPI providers through the **IMAPIProviderShutdown : IUnknown** interface within each MAPI session in the following order:</span></span>
       > 1. <span data-ttu-id="bfd33-117">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="bfd33-117">Transport providers</span></span>
       > 2. <span data-ttu-id="bfd33-118">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="bfd33-118">Address book providers</span></span>
       > 3. <span data-ttu-id="bfd33-119">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="bfd33-119">Store providers</span></span> 
    
    2. <span data-ttu-id="bfd33-120">根据客户端计算机上该用户的 fast shutdown 注册表设置, MAPI 子系统将为**IMAPIClientShutdown:: QueryFastShutdown**指定适当的返回代码。</span><span class="sxs-lookup"><span data-stu-id="bfd33-120">Depending on the fast shutdown registry setting for that user on the client computer, the MAPI subsystem specifies the appropriate return code to **IMAPIClientShutdown::QueryFastShutdown**.</span></span> <span data-ttu-id="bfd33-121">返回代码为 S_OK 或 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="bfd33-121">The return code is either S_OK or MAPI_E_NO_SUPPORT.</span></span>
        
    3. <span data-ttu-id="bfd33-122">mapi 客户端调用[IMAPIClientShutdown:: NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)方法向 MAPI 子系统指明关闭的意图。</span><span class="sxs-lookup"><span data-stu-id="bfd33-122">The MAPI client calls the [IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) method to indicate to the MAPI subsystem the intention to shut down.</span></span> 
        
    4. <span data-ttu-id="bfd33-123">mapi 子系统向每个已加载的 mapi 提供程序指明 mapi 客户端将关闭的。</span><span class="sxs-lookup"><span data-stu-id="bfd33-123">The MAPI subsystem indicates to each loaded MAPI provider that the MAPI client will shut down.</span></span> <span data-ttu-id="bfd33-124">对于已实现**IMAPIProviderShutdown: IUnknown**接口的那些提供程序, MAPI 子系统将调用相应的[IMAPIProviderShutdown:: NotifyProcessShutdown](imapiprovidershutdown-notifyprocessshutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bfd33-124">For those providers that have implemented the **IMAPIProviderShutdown : IUnknown** interface, the MAPI subsystem calls the corresponding [IMAPIProviderShutdown::NotifyProcessShutdown](imapiprovidershutdown-notifyprocessshutdown.md) method.</span></span> 
        
    5. <span data-ttu-id="bfd33-125">MAPI 客户端调用[IMAPIClientShutdown::D ofastshutdown](imapiclientshutdown-dofastshutdown.md)方法, 以向 MAPI 子系统指示客户端进程立即退出。</span><span class="sxs-lookup"><span data-stu-id="bfd33-125">The MAPI client calls the [IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md) method to indicate to the MAPI subsystem that the client process is exiting immediately.</span></span> 
        
    6. <span data-ttu-id="bfd33-126">mapi 子系统向每个已加载的 mapi 提供程序指示 mapi 客户端进程正在退出。</span><span class="sxs-lookup"><span data-stu-id="bfd33-126">The MAPI subsystem indicates to each loaded MAPI provider that the MAPI client process is exiting.</span></span> <span data-ttu-id="bfd33-127">对于已实现**IMAPIProviderShutdown: IUnknown**接口的那些提供程序, MAPI 子系统将调用相应的[IMAPIProviderShutdown::D ofastshutdown](imapiprovidershutdown-dofastshutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bfd33-127">For those providers that have implemented the **IMAPIProviderShutdown : IUnknown** interface, the MAPI subsystem calls the corresponding [IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md) method.</span></span> <span data-ttu-id="bfd33-128">在这种情况下, 这些 MAPI 提供程序应验证所有必要的操作 (如保存数据和设置) 是否已完成, 以便 MAPI 客户端立即断开所有引用并退出。</span><span class="sxs-lookup"><span data-stu-id="bfd33-128">At this point, these MAPI providers should verify that all necessary actions, such as saving data and settings, are complete in preparation for the MAPI client to immediately disconnect all references and exit.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="bfd33-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfd33-129">See also</span></span>

- [<span data-ttu-id="bfd33-130">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="bfd33-130">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)
- [<span data-ttu-id="bfd33-131">快速关闭用户选项</span><span class="sxs-lookup"><span data-stu-id="bfd33-131">Fast Shutdown User Options</span></span>](fast-shutdown-user-options.md)
- [<span data-ttu-id="bfd33-132">快速关闭最佳做法</span><span class="sxs-lookup"><span data-stu-id="bfd33-132">Best Practices for Fast Shutdown</span></span>](best-practices-for-fast-shutdown.md)

