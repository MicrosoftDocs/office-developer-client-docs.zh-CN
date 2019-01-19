---
title: 快速关闭用户选项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
api_type:
- COM
ms.assetid: 220aeab5-20f6-4520-96c9-8aaa0e8ea15b
description: 上次修改时间：2012 年 6 月 26 日
localization_priority: Priority
ms.openlocfilehash: 3c60862733c6b38e60650ae9daba9bba578fcd58
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716367"
---
# <a name="fast-shutdown-user-options"></a><span data-ttu-id="88f8d-103">快速关闭用户选项</span><span class="sxs-lookup"><span data-stu-id="88f8d-103">Fast shutdown user options</span></span>

<span data-ttu-id="88f8d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88f8d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="88f8d-105">本主题介绍了从 Microsoft Outlook 2010 起（现包括 Microsoft Outlook 2013）用于快速关闭用户的 MAPI 客户端的三个 Windows 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="88f8d-105">This topic describes the three Windows registry settings that are available, starting in Microsoft Outlook 2010 and now including Microsoft Outlook 2013, for fast shutdown of a user's MAPI clients.</span></span> <span data-ttu-id="88f8d-106">根据 MAPI 提供程序对客户端快速关闭的支持，管理员可以使用这些注册表设置来指定首选客户端关闭行为。</span><span class="sxs-lookup"><span data-stu-id="88f8d-106">Administrators can use these registry settings to specify the preferred client shutdown behavior depending on the MAPI providers' support for client fast shutdown.</span></span> <span data-ttu-id="88f8d-107">反过来，管理员设置将决定 MAPI 子系统如何按照可用快速关闭支持来响应 MAPI 客户端对 [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) 的调用。</span><span class="sxs-lookup"><span data-stu-id="88f8d-107">The administrator's setting, in turn, determines how the MAPI subsystem responds to the MAPI client's call to [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) in terms of available fast shutdown support.</span></span> 
  
<span data-ttu-id="88f8d-108">即便注册表设置可以反映管理员在用户级别对所有 MAPI 客户端快速关闭的首选项，MAPI 客户端开发人员也可以决定客户端是否支持独立快速关闭其他 MAPI 客户端以及管理员的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="88f8d-108">Even though a registry setting reflects the administrator's preference at the user level for fast shutdown for all MAPI clients, a MAPI client developer can decide whether the client supports fast shutdown independently of other MAPI clients and the administrator's registry setting.</span></span> <span data-ttu-id="88f8d-109">尽管如此，如需成功快速关闭，用户必须对注册表进行必要的设置，MAPI 客户端必须通过使用 [IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md) 接口启动快速关闭，并且与客户端搭配使用的 MAPI 提供程序应使用 [IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md) 接口支持客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="88f8d-109">Nonetheless, for fast shutdown to take place successfully, the user must have the necessary registry setting, a MAPI client must initiate the fast shutdown by using the [IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md) interface, and MAPI providers that work with the client should implement the [IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md) interface to support client fast shutdown.</span></span> 
  
<span data-ttu-id="88f8d-110">以下列表介绍了三个用户级别选项。</span><span class="sxs-lookup"><span data-stu-id="88f8d-110">The following list describes the three user-level options.</span></span>
  
### <a name="option-1-the-mapi-subsystem-enables-fast-shutdown-unless-mapi-providers-explicitly-opt-out"></a><span data-ttu-id="88f8d-111">选项 1：MAPI 子系统支持快速关闭，除非 MAPI 提供程序显式选择退出</span><span class="sxs-lookup"><span data-stu-id="88f8d-111">Option 1: The MAPI subsystem enables fast shutdown, unless MAPI providers explicitly opt out</span></span> 
    
<span data-ttu-id="88f8d-112">从 Outlook 2010 起，如果 Outlook 为 MAPI 客户端，则这为默认行为；但如果是其他 MAPI 客户端，则这不一定是默认行为。</span><span class="sxs-lookup"><span data-stu-id="88f8d-112">Starting in Outlook 2010, this is the default behavior when Outlook is the MAPI client; it is not necessarily the default behavior for other MAPI clients.</span></span> <span data-ttu-id="88f8d-113">若要为 Outlook 显式指定此选项，则管理员可以选择设置以下注册表项和值。</span><span class="sxs-lookup"><span data-stu-id="88f8d-113">To explicitly specify this option for Outlook, administrators can choose to set the following registry key and value.</span></span>
    
<span data-ttu-id="88f8d-114">注册表项：</span><span class="sxs-lookup"><span data-stu-id="88f8d-114">Registry Key</span></span>
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
<span data-ttu-id="88f8d-115">值:</span><span class="sxs-lookup"><span data-stu-id="88f8d-115">Value</span></span>
  
>  `"FastShutdownBehavior"=dword:00000000`
    
<span data-ttu-id="88f8d-116">只要具有活动 MAPI 会话及 MAPI 客户端的所有 MAPI 提供程序均未显式选择退出快速关闭支持，则当 MAPI 客户端启动快速关闭并调用 **IMAPIClientShutdown::QueryFastShutdown** 以查询快速关闭支持，MAPI 子系统将返回 S\_OK 以响应查询。</span><span class="sxs-lookup"><span data-stu-id="88f8d-116">When a MAPI client initiates a fast shutdown and calls **IMAPIClientShutdown::QueryFastShutdown** to query for fast shutdown support, the MAPI subsystem responds to the query by returning S\_OK as long as no MAPI provider that has an active MAPI session with the MAPI client has explicitly opted out of fast shutdown support.</span></span> 

<span data-ttu-id="88f8d-117">MAPI 提供程序通过使用 [IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) 方法返回错误 (MAPI\_E\_NO\_SUPPORT) 来选择退出快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="88f8d-117">A MAPI provider opts out of fast shutdown by implementing the [IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) method to return an error (MAPI\_E\_NO\_SUPPORT).</span></span> <span data-ttu-id="88f8d-118">如果一个或多个 MAPI 提供程序在 **IMAPIProviderShutdown::QueryFastShutdown** 中返回错误，则 MAPI 子系统将返回 MAPI_\E_\NO\_SUPPORT 至 **IMAPIClientShutdown::QueryFastShutdown**。</span><span class="sxs-lookup"><span data-stu-id="88f8d-118">If one or more MAPI providers return an error in **IMAPIProviderShutdown::QueryFastShutdown**, the MAPI subsystem returns MAPI_\E_\NO\_SUPPORT to **IMAPIClientShutdown::QueryFastShutdown**.</span></span> 

<span data-ttu-id="88f8d-119">除非 MAPI 提供程序选择退出，否则即便一个或多个提供程序未使用 **IMAPIProviderShutdown : IUnknown** 接口，MAPI 子系统也会返回 S\_OK。</span><span class="sxs-lookup"><span data-stu-id="88f8d-119">Unless a MAPI provider opts out, the MAPI subsystem returns S\_OK, even if one or more providers have not implemented the **IMAPIProviderShutdown : IUnknown** interface.</span></span> 
    
### <a name="option-2-the-mapi-subsystem-enables-fast-shutdown-only-if-every-mapi-provider-explicitly-opts-in"></a><span data-ttu-id="88f8d-120">选项 2：仅当每个 MAPI 提供程序显式选择加入时，MAPI 子系统才支持快速关闭</span><span class="sxs-lookup"><span data-stu-id="88f8d-120">Option 2: The MAPI subsystem enables fast shutdown only if every MAPI provider explicitly opts in</span></span> 
    
<span data-ttu-id="88f8d-121">管理员必须显式设置以下注册表项和值才能为客户端快速关闭指定此首选项。</span><span class="sxs-lookup"><span data-stu-id="88f8d-121">Administrators must explicitly set the following registry key and value to specify this preference for client fast shutdown.</span></span>
    
<span data-ttu-id="88f8d-122">注册表项：</span><span class="sxs-lookup"><span data-stu-id="88f8d-122">Registry Key</span></span>
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
<span data-ttu-id="88f8d-123">值:</span><span class="sxs-lookup"><span data-stu-id="88f8d-123">Value</span></span>
  
>  `"FastShutdownBehavior"=dword:00000001`
    
<span data-ttu-id="88f8d-124">如果具有活动会话及 MAPI 客户端的所有 MAPI 提供程序支持快速关闭，则当 MAPI 客户端启动快速关闭并调用 **IMAPIClientShutdown::QueryFastShutdown** 以查询快速关闭支持时，MAPI 子系统将返回 S\_OK 以响应查询。</span><span class="sxs-lookup"><span data-stu-id="88f8d-124">When a MAPI client initiates a fast shutdown and calls **IMAPIClientShutdown::QueryFastShutdown** to query for fast shutdown support, the MAPI subsystem responds to the query by returning S\_OK if all MAPI providers that have active sessions with the MAPI client support fast shutdown.</span></span> <span data-ttu-id="88f8d-125">MAPI 提供程序通过使用 **IMAPIProviderShutdown::QueryFastShutdown** 以返回非错误代码 (S\_OK) 来演示其支持。</span><span class="sxs-lookup"><span data-stu-id="88f8d-125">A MAPI provider demonstrates its support by implementing **IMAPIProviderShutdown::QueryFastShutdown** to return a non-error code (S\_OK).</span></span> 

<span data-ttu-id="88f8d-126">如果一个或多个 MAPI 提供程序返回 MAPI\_E\_NO\_SUPPORT，或者未使用 **IMAPIProviderShutdown::QueryFastShutdown**，则 MAPI 子系统将返回错误代码至 **IMAPIClientShutdown::QueryFastShutdown**。</span><span class="sxs-lookup"><span data-stu-id="88f8d-126">If one or more such MAPI providers return MAPI\_E\_NO\_SUPPORT, or do not implement **IMAPIProviderShutdown::QueryFastShutdown**, the MAPI subsystem returns an error code to **IMAPIClientShutdown::QueryFastShutdown**.</span></span>
    
### <a name="option-3-an-administrator-disables-support-for-client-fast-shutdown"></a><span data-ttu-id="88f8d-127">选项 3：管理员禁用客户端快速关闭支持</span><span class="sxs-lookup"><span data-stu-id="88f8d-127">Option 3: An administrator disables support for client fast shutdown</span></span>
    
<span data-ttu-id="88f8d-128">管理员必须显式设置以下注册表项和值才能禁用客户端快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="88f8d-128">Administrators must explicitly set the following registry key and value to disable support for client fast shutdown.</span></span>
    
<span data-ttu-id="88f8d-129">注册表项：</span><span class="sxs-lookup"><span data-stu-id="88f8d-129">Registry Key</span></span>
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
<span data-ttu-id="88f8d-130">值:</span><span class="sxs-lookup"><span data-stu-id="88f8d-130">Value</span></span>
  
>  `"FastShutdownBehavior"=dword:00000002`
    
<span data-ttu-id="88f8d-131">无论任何 MAPI 提供程序是否支持快速关闭，当 MAPI 客户端启动快速关闭并调用 **IMAPIClientShutdown::QueryFastShutdown** 以响应快速关闭支持时，MAPI 子系统均会返回 MAPI_E_NO_SUPPORT 以响应查询。</span><span class="sxs-lookup"><span data-stu-id="88f8d-131">When a MAPI client initiates a fast shutdown and calls **IMAPIClientShutdown::QueryFastShutdown** to query for fast shutdown support, the MAPI subsystem responds to the query by returning MAPI_E_NO_SUPPORT, regardless of whether any MAPI provider supports fast shutdown.</span></span> <span data-ttu-id="88f8d-132">在此注册表设置下，MAPI 子系统永远不会调用任何提供程序的 **IMAPIProviderShutdown::QueryFastShutdown** 或 [IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="88f8d-132">Under this registry setting, the MAPI subsystem never calls the **IMAPIProviderShutdown::QueryFastShutdown** or [IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md) method of any of the providers.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="88f8d-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88f8d-133">See also</span></span>

- [<span data-ttu-id="88f8d-134">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="88f8d-134">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)
- [<span data-ttu-id="88f8d-135">快速关闭概述</span><span class="sxs-lookup"><span data-stu-id="88f8d-135">Fast shutdown overview</span></span>](fast-shutdown-overview.md)
- [<span data-ttu-id="88f8d-136">快速关闭最佳做法</span><span class="sxs-lookup"><span data-stu-id="88f8d-136">Best practices for fast shutdown</span></span>](best-practices-for-fast-shutdown.md)

