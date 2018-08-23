---
title: 快速关闭用户选项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 220aeab5-20f6-4520-96c9-8aaa0e8ea15b
description: 上次修改时间： 2012 年 6 月 26 日
ms.openlocfilehash: bd541ed09bc661f3697408d3f475928b9ef0bcc1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585190"
---
# <a name="fast-shutdown-user-options"></a><span data-ttu-id="2d490-103">快速关闭用户选项</span><span class="sxs-lookup"><span data-stu-id="2d490-103">Fast shutdown user options</span></span>

<span data-ttu-id="2d490-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2d490-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2d490-105">本主题介绍的三个 Windows 注册表设置的可用，Microsoft Outlook 2010 中启动和现在包括 Microsoft Outlook 2013 的用户的 MAPI 客户端的快速关闭。</span><span class="sxs-lookup"><span data-stu-id="2d490-105">This topic describes the three Windows registry settings that are available, starting in Microsoft Outlook 2010 and now including Microsoft Outlook 2013, for fast shutdown of a user's MAPI clients.</span></span> <span data-ttu-id="2d490-106">管理员可以使用这些注册表设置来指定根据 MAPI 提供程序支持的客户端快速关闭的首选的客户端关闭行为。</span><span class="sxs-lookup"><span data-stu-id="2d490-106">Administrators can use these registry settings to specify the preferred client shutdown behavior depending on the MAPI providers' support for client fast shutdown.</span></span> <span data-ttu-id="2d490-107">反过来，管理员的设置确定如何 MAPI 子系统响应[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方面提供快速关闭支持 MAPI 客户端的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2d490-107">The administrator's setting, in turn, determines how the MAPI subsystem responds to the MAPI client's call to [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) in terms of available fast shutdown support.</span></span> 
  
<span data-ttu-id="2d490-108">即使注册表设置的所有 MAPI 客户端反映在用户级别的快速关闭的管理员的首选项，MAPI 客户端开发人员可以决定是否在客户端支持快速关闭独立于其他 MAPI 客户端和管理员的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="2d490-108">Even though a registry setting reflects the administrator's preference at the user level for fast shutdown for all MAPI clients, a MAPI client developer can decide whether the client supports fast shutdown independently of other MAPI clients and the administrator's registry setting.</span></span> <span data-ttu-id="2d490-109">不过的快速关闭执行成功，用户必须拥有所需的注册表设置，MAPI 客户端必须使用启动快速关闭[IMAPIClientShutdown: IUnknown](imapiclientshutdowniunknown.md)接口，并使用的 MAPI 提供程序客户端应实现[IMAPIProviderShutdown: IUnknown](imapiprovidershutdowniunknown.md)接口以支持客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="2d490-109">Nonetheless, for fast shutdown to take place successfully, the user must have the necessary registry setting, a MAPI client must initiate the fast shutdown by using the [IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md) interface, and MAPI providers that work with the client should implement the [IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md) interface to support client fast shutdown.</span></span> 
  
<span data-ttu-id="2d490-110">以下列表介绍的三个用户级别选项。</span><span class="sxs-lookup"><span data-stu-id="2d490-110">The following list describes the three user-level options.</span></span>
  
### <a name="option-1-the-mapi-subsystem-enables-fast-shutdown-unless-mapi-providers-explicitly-opt-out"></a><span data-ttu-id="2d490-111">选项 1: MAPI 子系统启用快速关闭，除非明确退出 MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="2d490-111">Option 1: The MAPI subsystem enables fast shutdown, unless MAPI providers explicitly opt out</span></span> 
    
<span data-ttu-id="2d490-112">启动 Outlook 2010 中，这是默认行为 Outlook MAPI 客户端，则时它不一定是其他 MAPI 客户端的默认行为。</span><span class="sxs-lookup"><span data-stu-id="2d490-112">Starting in Outlook 2010, this is the default behavior when Outlook is the MAPI client; it is not necessarily the default behavior for other MAPI clients.</span></span> <span data-ttu-id="2d490-113">若要显式指定 Outlook 此选项，管理员可以选择设置以下注册表项和值。</span><span class="sxs-lookup"><span data-stu-id="2d490-113">To explicitly specify this option for Outlook, administrators can choose to set the following registry key and value.</span></span>
    
<span data-ttu-id="2d490-114">注册表项：</span><span class="sxs-lookup"><span data-stu-id="2d490-114">Registry key:</span></span>
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
<span data-ttu-id="2d490-115">值：</span><span class="sxs-lookup"><span data-stu-id="2d490-115">Value:</span></span>
  
>  `"FastShutdownBehavior"=dword:00000000`
    
<span data-ttu-id="2d490-116">在 MAPI 客户端发起快速关闭，并调用**IMAPIClientShutdown::QueryFastShutdown**查询快速关闭支持，MAPI 子系统响应查询通过返回 S\_会长达具有活动的 MAPI 没有 MAPI 提供程序单击确定与 MAPI 客户端会话已明确选择出快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="2d490-116">When a MAPI client initiates a fast shutdown and calls **IMAPIClientShutdown::QueryFastShutdown** to query for fast shutdown support, the MAPI subsystem responds to the query by returning S\_OK as long as no MAPI provider that has an active MAPI session with the MAPI client has explicitly opted out of fast shutdown support.</span></span> 

<span data-ttu-id="2d490-117">MAPI 提供程序将超出快速关闭通过实现[IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md)方法返回的错误 (MAPI\_E\_无\_支持)。</span><span class="sxs-lookup"><span data-stu-id="2d490-117">A MAPI provider opts out of fast shutdown by implementing the [IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) method to return an error (MAPI\_E\_NO\_SUPPORT).</span></span> <span data-ttu-id="2d490-118">如果一个或多个 MAPI 提供程序中**IMAPIProviderShutdown::QueryFastShutdown**返回错误，MAPI 子系统返回 MAPI_\E_\NO\_ **IMAPIClientShutdown::QueryFastShutdown**支持。</span><span class="sxs-lookup"><span data-stu-id="2d490-118">If one or more MAPI providers return an error in **IMAPIProviderShutdown::QueryFastShutdown**, the MAPI subsystem returns MAPI_\E_\NO\_SUPPORT to **IMAPIClientShutdown::QueryFastShutdown**.</span></span> 

<span data-ttu-id="2d490-119">除非将 MAPI 提供程序，MAPI 子系统返回 S\_单击确定，即使未实现一个或多个提供程序**IMAPIProviderShutdown: IUnknown**接口。</span><span class="sxs-lookup"><span data-stu-id="2d490-119">Unless a MAPI provider opts out, the MAPI subsystem returns S\_OK, even if one or more providers have not implemented the **IMAPIProviderShutdown : IUnknown** interface.</span></span> 
    
### <a name="option-2-the-mapi-subsystem-enables-fast-shutdown-only-if-every-mapi-provider-explicitly-opts-in"></a><span data-ttu-id="2d490-120">选项 2: MAPI 子系统启用快速关闭才中明确将每个 MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="2d490-120">Option 2: The MAPI subsystem enables fast shutdown only if every MAPI provider explicitly opts in</span></span> 
    
<span data-ttu-id="2d490-121">管理员必须明确设置以下注册表项和值，以指定的客户端快速关闭此首选项。</span><span class="sxs-lookup"><span data-stu-id="2d490-121">Administrators must explicitly set the following registry key and value to specify this preference for client fast shutdown.</span></span>
    
<span data-ttu-id="2d490-122">注册表项：</span><span class="sxs-lookup"><span data-stu-id="2d490-122">Registry key:</span></span>
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
<span data-ttu-id="2d490-123">值：</span><span class="sxs-lookup"><span data-stu-id="2d490-123">Value:</span></span>
  
>  `"FastShutdownBehavior"=dword:00000001`
    
<span data-ttu-id="2d490-124">在 MAPI 客户端发起快速关闭，并调用**IMAPIClientShutdown::QueryFastShutdown**查询快速关闭支持，MAPI 子系统响应查询通过返回 S\_单击确定如果所有 MAPI 提供程序都具有与活动会话MAPI 客户端支持快速关闭。</span><span class="sxs-lookup"><span data-stu-id="2d490-124">When a MAPI client initiates a fast shutdown and calls **IMAPIClientShutdown::QueryFastShutdown** to query for fast shutdown support, the MAPI subsystem responds to the query by returning S\_OK if all MAPI providers that have active sessions with the MAPI client support fast shutdown.</span></span> <span data-ttu-id="2d490-125">MAPI 提供程序说明其支持通过实现**IMAPIProviderShutdown::QueryFastShutdown**返回非错误代码 (S\_确定)。</span><span class="sxs-lookup"><span data-stu-id="2d490-125">A MAPI provider demonstrates its support by implementing **IMAPIProviderShutdown::QueryFastShutdown** to return a non-error code (S\_OK).</span></span> 

<span data-ttu-id="2d490-126">如果一个或多个此类 MAPI 提供程序返回 MAPI\_E\_无\_支持或不实现**IMAPIProviderShutdown::QueryFastShutdown**，MAPI 子系统到**IMAPIClientShutdown::QueryFastShutdown**返回错误代码.</span><span class="sxs-lookup"><span data-stu-id="2d490-126">If one or more such MAPI providers return MAPI\_E\_NO\_SUPPORT, or do not implement **IMAPIProviderShutdown::QueryFastShutdown**, the MAPI subsystem returns an error code to **IMAPIClientShutdown::QueryFastShutdown**.</span></span>
    
### <a name="option-3-an-administrator-disables-support-for-client-fast-shutdown"></a><span data-ttu-id="2d490-127">选项 3： 管理员禁用支持的客户端快速关闭</span><span class="sxs-lookup"><span data-stu-id="2d490-127">Option 3: An administrator disables support for client fast shutdown</span></span>
    
<span data-ttu-id="2d490-128">管理员必须明确设置以下注册表项和值，以禁用支持的客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="2d490-128">Administrators must explicitly set the following registry key and value to disable support for client fast shutdown.</span></span>
    
<span data-ttu-id="2d490-129">注册表项：</span><span class="sxs-lookup"><span data-stu-id="2d490-129">Registry key:</span></span>
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
<span data-ttu-id="2d490-130">值：</span><span class="sxs-lookup"><span data-stu-id="2d490-130">Value:</span></span>
  
>  `"FastShutdownBehavior"=dword:00000002`
    
<span data-ttu-id="2d490-131">在 MAPI 客户端发起快速关闭，并调用**IMAPIClientShutdown::QueryFastShutdown**查询快速关闭支持，MAPI 子系统响应查询通过无论是否返回 MAPI_E_NO_SUPPORT，任何 MAPI 提供程序支持快速关闭。</span><span class="sxs-lookup"><span data-stu-id="2d490-131">When a MAPI client initiates a fast shutdown and calls **IMAPIClientShutdown::QueryFastShutdown** to query for fast shutdown support, the MAPI subsystem responds to the query by returning MAPI_E_NO_SUPPORT, regardless of whether any MAPI provider supports fast shutdown.</span></span> <span data-ttu-id="2d490-132">在此注册表设置下, MAPI 子系统永远不会调用的任何提供程序的**IMAPIProviderShutdown::QueryFastShutdown**或[IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2d490-132">Under this registry setting, the MAPI subsystem never calls the **IMAPIProviderShutdown::QueryFastShutdown** or [IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md) method of any of the providers.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="2d490-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d490-133">See also</span></span>

- [<span data-ttu-id="2d490-134">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="2d490-134">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)
- [<span data-ttu-id="2d490-135">快速关闭概述</span><span class="sxs-lookup"><span data-stu-id="2d490-135">Fast Shutdown Overview</span></span>](fast-shutdown-overview.md)
- [<span data-ttu-id="2d490-136">快速关闭的最佳实践</span><span class="sxs-lookup"><span data-stu-id="2d490-136">Best Practices for Fast Shutdown</span></span>](best-practices-for-fast-shutdown.md)

