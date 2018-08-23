---
title: 快速关闭的最佳实践
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ae8a9214-e53f-4c57-8dbe-aa7cc6903aa8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c92347ab1a786196e7f0d99b286e8f4134ce7c24
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590699"
---
# <a name="best-practices-for-fast-shutdown"></a><span data-ttu-id="37125-103">快速关闭的最佳实践</span><span class="sxs-lookup"><span data-stu-id="37125-103">Best Practices for Fast Shutdown</span></span>

  
  
<span data-ttu-id="37125-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="37125-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="37125-105">本主题建议为管理员、 MAPI 客户端和 MAPI 提供程序使用 Windows 注册表设置和快速关闭接口客户端关闭期间减少数据丢失的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="37125-105">This topic recommends best practices for administrators, MAPI clients, and MAPI providers to use Windows registry settings and the fast shutdown interfaces to minimize data loss during client shutdown.</span></span>
  
- <span data-ttu-id="37125-106">MAPI 客户端执行快速关闭成功，以便提供程序进程不会导致数据丢失的 MAPI 客户端应首先调用[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="37125-106">For a MAPI client to carry out fast shutdown successfully so that provider processes do not incur data loss, the MAPI client should first call the [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) method.</span></span> <span data-ttu-id="37125-107">客户端应然后继续进行基于 MAPI 子系统的支持的快速关闭[IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)和[IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md)方法由**的返回值IMAPIClientShutdown::QueryFastShutdown**。</span><span class="sxs-lookup"><span data-stu-id="37125-107">The client should then proceed with the [IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) and [IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md) methods based on the MAPI subsystem's support for fast shutdown, as indicated by the return value of **IMAPIClientShutdown::QueryFastShutdown**.</span></span> <span data-ttu-id="37125-108">作为 MAPI 客户端，Microsoft Outlook 不会调用**IMAPIClientShutdown::NotifyProcessShutdown**或**IMAPIClientShutdown::DoFastShutdown**如果**IMAPIClientShutdown::QueryFastShutdown**将返回错误。</span><span class="sxs-lookup"><span data-stu-id="37125-108">As a MAPI client, Microsoft Outlook does not call **IMAPIClientShutdown::NotifyProcessShutdown** or **IMAPIClientShutdown::DoFastShutdown** if **IMAPIClientShutdown::QueryFastShutdown** returns an error.</span></span> <span data-ttu-id="37125-109">如果管理员已禁用 Windows 注册表中的快速关闭，MAPI 子系统应返回**IMAPIClientShutdown::QueryFastShutdown**MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="37125-109">If the administrator has disabled fast shutdown in the Windows registry, the MAPI subsystem would return MAPI_E_NO_SUPPORT to **IMAPIClientShutdown::QueryFastShutdown**.</span></span> <span data-ttu-id="37125-110">在这种情况下，MAPI 子系统不会通知 MAPI 提供程序即时客户过程的退出。</span><span class="sxs-lookup"><span data-stu-id="37125-110">In this case, the MAPI subsystem would not inform MAPI providers of an immediate client process exit.</span></span> <span data-ttu-id="37125-111">因此，如果 MAPI 客户端将忽略此错误返回代码，继续执行快速关闭，并且断开所有外部引用，所有加载的 MAPI 提供程序将会丢失数据。</span><span class="sxs-lookup"><span data-stu-id="37125-111">Therefore, if a MAPI client disregards this error return code, proceeds to do fast shutdown, and disconnects all external references, all loaded MAPI providers will have data loss.</span></span> 
    
- <span data-ttu-id="37125-112">MAPI 提供程序应实现[IMAPIProviderShutdown: IUnknown](imapiprovidershutdowniunknown.md)接口执行及时和所需的步骤，以避免由于客户端断开外部引用客户端退出之前的数据丢失。</span><span class="sxs-lookup"><span data-stu-id="37125-112">MAPI providers should implement the [IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md) interface to carry out timely and necessary steps to avoid data loss due to the client disconnecting external references before the client exits.</span></span> <span data-ttu-id="37125-113">提供程序应推迟的其他内容是将数据保存到其主数据存储区不重要。</span><span class="sxs-lookup"><span data-stu-id="37125-113">A provider should postpone everything else that is nonessential to saving data to its primary data store.</span></span> <span data-ttu-id="37125-114">例如，传输提供程序应推迟检查新邮件，通讯簿提供程序应从其服务器上，下载最新更改推迟的不必要的后台操作和存储提供程序应如推迟维护任务在压缩或索引。</span><span class="sxs-lookup"><span data-stu-id="37125-114">For example, a transport provider should postpone unnecessary background operations that check for new mail, an address book provider should postpone downloading recent changes from its server, and a store provider should postpone maintenance tasks such as compacting or indexing.</span></span> 
    
- <span data-ttu-id="37125-115">要退出只要它们关闭它们的 MAPI 客户端的用户应使用默认注册表设置，使快速关闭，除非将提供程序。</span><span class="sxs-lookup"><span data-stu-id="37125-115">Users who want MAPI clients to exit as soon as they close them should use the default registry setting that enables fast shutdown unless a provider opts out.</span></span>
    
- <span data-ttu-id="37125-116">一旦 MAPI 客户端呼叫**IMAPIClientShutdown::DoFastShutdown**，它不应为 MAPI，包括[MAPIUninitialize](mapiuninitialize.md)函数的任何其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="37125-116">Once a MAPI client calls **IMAPIClientShutdown::DoFastShutdown**, it should not make any additional calls to MAPI, including the [MAPIUninitialize](mapiuninitialize.md) function.</span></span> <span data-ttu-id="37125-117">客户端不应使用 MAPI 客户端进程的生存期的其余部分。</span><span class="sxs-lookup"><span data-stu-id="37125-117">The client should not use MAPI for the rest of the client process's lifetime.</span></span> 
    
- <span data-ttu-id="37125-118">MAPI 客户端应永远不会直接调用提供商的**IMAPIProviderShutdown**接口。</span><span class="sxs-lookup"><span data-stu-id="37125-118">A MAPI client should never directly call a provider's **IMAPIProviderShutdown** interface.</span></span> <span data-ttu-id="37125-119">MAPI 客户端应始终使用[IMAPIClientShutdown: IUnknown](imapiclientshutdowniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="37125-119">MAPI clients should always use the [IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md) interface.</span></span> 
    
- <span data-ttu-id="37125-120">如果 MAPI 提供程序需要以确保它加载时未使用的快速关闭，应实现**IMAPIProviderShutdown**接口并返回 MAPI_E_NO_SUPPORT **IMAPIProviderShutdown::QueryFastShutdown**方法。</span><span class="sxs-lookup"><span data-stu-id="37125-120">If a MAPI provider needs to ensure that fast shutdown is not used while it is loaded, it should implement the **IMAPIProviderShutdown** interface and return MAPI_E_NO_SUPPORT for the **IMAPIProviderShutdown::QueryFastShutdown** method.</span></span> <span data-ttu-id="37125-121">但是，如 Outlook 的 MAPI 客户端，这将导致客户端放弃快速关闭并需要很长时间关闭。</span><span class="sxs-lookup"><span data-stu-id="37125-121">However, for MAPI clients such as Outlook, this will cause the client to abandon fast shutdown and take a longer time to shut down.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="37125-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37125-122">See also</span></span>



[<span data-ttu-id="37125-123">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="37125-123">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)
  
[<span data-ttu-id="37125-124">快速关闭概述</span><span class="sxs-lookup"><span data-stu-id="37125-124">Fast Shutdown Overview</span></span>](fast-shutdown-overview.md)
  
[<span data-ttu-id="37125-125">快速关闭用户选项</span><span class="sxs-lookup"><span data-stu-id="37125-125">Fast Shutdown User Options</span></span>](fast-shutdown-user-options.md)

