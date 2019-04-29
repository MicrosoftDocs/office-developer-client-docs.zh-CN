---
title: 快速关闭的最佳实践
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ae8a9214-e53f-4c57-8dbe-aa7cc6903aa8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8c7225427b80d89c6dd8adfa85f7d91885850365
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426966"
---
# <a name="best-practices-for-fast-shutdown"></a><span data-ttu-id="17103-103">快速关闭的最佳实践</span><span class="sxs-lookup"><span data-stu-id="17103-103">Best Practices for Fast Shutdown</span></span>

  
  
<span data-ttu-id="17103-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="17103-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="17103-105">本主题为管理员、mapi 客户端和 mapi 提供程序推荐了使用 Windows 注册表设置和 fast shutdown 接口的最佳做法, 以最大限度地减少客户端关闭期间的数据丢失。</span><span class="sxs-lookup"><span data-stu-id="17103-105">This topic recommends best practices for administrators, MAPI clients, and MAPI providers to use Windows registry settings and the fast shutdown interfaces to minimize data loss during client shutdown.</span></span>
  
- <span data-ttu-id="17103-106">为了使 mapi 客户端成功执行快速关机, 以便提供程序进程不会丢失数据, MAPI 客户端应首先调用[IMAPIClientShutdown:: QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="17103-106">For a MAPI client to carry out fast shutdown successfully so that provider processes do not incur data loss, the MAPI client should first call the [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) method.</span></span> <span data-ttu-id="17103-107">然后, 客户端应继续[IMAPIClientShutdown:: NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)和[IMAPIClientShutdown:](imapiclientshutdown-dofastshutdown.md)基于 MAPI 子系统支持快速关机的 ofastshutdown 方法, 如返回值**为IMAPIClientShutdown:: QueryFastShutdown**。</span><span class="sxs-lookup"><span data-stu-id="17103-107">The client should then proceed with the [IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) and [IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md) methods based on the MAPI subsystem's support for fast shutdown, as indicated by the return value of **IMAPIClientShutdown::QueryFastShutdown**.</span></span> <span data-ttu-id="17103-108">作为 MAPI 客户端, Microsoft Outlook 不会调用**IMAPIClientShutdown:: NotifyProcessShutdown**或**IMAPIClientShutdown::D ofastshutdown**如果**IMAPIClientShutdown:: QueryFastShutdown**返回错误。</span><span class="sxs-lookup"><span data-stu-id="17103-108">As a MAPI client, Microsoft Outlook does not call **IMAPIClientShutdown::NotifyProcessShutdown** or **IMAPIClientShutdown::DoFastShutdown** if **IMAPIClientShutdown::QueryFastShutdown** returns an error.</span></span> <span data-ttu-id="17103-109">如果管理员已在 Windows 注册表中禁用 fast shutdown, MAPI 子系统将返回 MAPI_E_NO_SUPPORT to **IMAPIClientShutdown:: QueryFastShutdown**。</span><span class="sxs-lookup"><span data-stu-id="17103-109">If the administrator has disabled fast shutdown in the Windows registry, the MAPI subsystem would return MAPI_E_NO_SUPPORT to **IMAPIClientShutdown::QueryFastShutdown**.</span></span> <span data-ttu-id="17103-110">在这种情况下, mapi 子系统不会通知 mapi 提供程序即时客户端进程退出。</span><span class="sxs-lookup"><span data-stu-id="17103-110">In this case, the MAPI subsystem would not inform MAPI providers of an immediate client process exit.</span></span> <span data-ttu-id="17103-111">因此, 如果 MAPI 客户端忽略此错误, 则会继续快速关闭并断开所有外部引用, 所有加载的 MAPI 提供程序都将丢失数据。</span><span class="sxs-lookup"><span data-stu-id="17103-111">Therefore, if a MAPI client disregards this error return code, proceeds to do fast shutdown, and disconnects all external references, all loaded MAPI providers will have data loss.</span></span> 
    
- <span data-ttu-id="17103-112">MAPI 提供程序应实现[IMAPIProviderShutdown: IUnknown](imapiprovidershutdowniunknown.md)接口, 以执行及时和必要的步骤, 以避免由于客户端在客户端退出前断开外部引用而导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="17103-112">MAPI providers should implement the [IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md) interface to carry out timely and necessary steps to avoid data loss due to the client disconnecting external references before the client exits.</span></span> <span data-ttu-id="17103-113">提供程序应将数据保存到其主数据存储区中不必要的所有其他项。</span><span class="sxs-lookup"><span data-stu-id="17103-113">A provider should postpone everything else that is nonessential to saving data to its primary data store.</span></span> <span data-ttu-id="17103-114">例如, 传输提供程序应推迟检查新邮件的不必要的后台操作, 通讯簿提供程序应延迟从其服务器下载最近更改, 并且存储提供程序应延迟维护任务, 例如压缩或编制索引。</span><span class="sxs-lookup"><span data-stu-id="17103-114">For example, a transport provider should postpone unnecessary background operations that check for new mail, an address book provider should postpone downloading recent changes from its server, and a store provider should postpone maintenance tasks such as compacting or indexing.</span></span> 
    
- <span data-ttu-id="17103-115">希望 MAPI 客户端在关闭时立即退出的用户应使用默认注册表设置, 除非提供程序弹出, 否则启用快速关机。</span><span class="sxs-lookup"><span data-stu-id="17103-115">Users who want MAPI clients to exit as soon as they close them should use the default registry setting that enables fast shutdown unless a provider opts out.</span></span>
    
- <span data-ttu-id="17103-116">MAPI 客户端调用**IMAPIClientShutdown::D ofastshutdown**后, 它不应对 MAPI 进行任何其他调用, 包括[MAPIUninitialize](mapiuninitialize.md)函数。</span><span class="sxs-lookup"><span data-stu-id="17103-116">Once a MAPI client calls **IMAPIClientShutdown::DoFastShutdown**, it should not make any additional calls to MAPI, including the [MAPIUninitialize](mapiuninitialize.md) function.</span></span> <span data-ttu-id="17103-117">客户端不应将 MAPI 用于其他客户端进程的生存期。</span><span class="sxs-lookup"><span data-stu-id="17103-117">The client should not use MAPI for the rest of the client process's lifetime.</span></span> 
    
- <span data-ttu-id="17103-118">MAPI 客户端决不应直接调用提供程序的**IMAPIProviderShutdown**接口。</span><span class="sxs-lookup"><span data-stu-id="17103-118">A MAPI client should never directly call a provider's **IMAPIProviderShutdown** interface.</span></span> <span data-ttu-id="17103-119">MAPI 客户端应始终使用[IMAPIClientShutdown: IUnknown](imapiclientshutdowniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="17103-119">MAPI clients should always use the [IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md) interface.</span></span> 
    
- <span data-ttu-id="17103-120">如果 MAPI 提供程序需要确保在加载过程中不使用 fast shutdown, 它应实现**IMAPIProviderShutdown**接口, 并返回 MAPI_E_NO_SUPPORT for the **IMAPIProviderShutdown:: QueryFastShutdown**方法。</span><span class="sxs-lookup"><span data-stu-id="17103-120">If a MAPI provider needs to ensure that fast shutdown is not used while it is loaded, it should implement the **IMAPIProviderShutdown** interface and return MAPI_E_NO_SUPPORT for the **IMAPIProviderShutdown::QueryFastShutdown** method.</span></span> <span data-ttu-id="17103-121">但是, 对于 Outlook 这样的 MAPI 客户端, 这将导致客户端放弃快速关机并花费更长的时间来关闭。</span><span class="sxs-lookup"><span data-stu-id="17103-121">However, for MAPI clients such as Outlook, this will cause the client to abandon fast shutdown and take a longer time to shut down.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="17103-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17103-122">See also</span></span>



[<span data-ttu-id="17103-123">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="17103-123">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)
  
[<span data-ttu-id="17103-124">快速关闭概述</span><span class="sxs-lookup"><span data-stu-id="17103-124">Fast Shutdown Overview</span></span>](fast-shutdown-overview.md)
  
[<span data-ttu-id="17103-125">快速关闭用户选项</span><span class="sxs-lookup"><span data-stu-id="17103-125">Fast Shutdown User Options</span></span>](fast-shutdown-user-options.md)

