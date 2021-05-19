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
# <a name="best-practices-for-fast-shutdown"></a><span data-ttu-id="7f50f-103">快速关闭的最佳实践</span><span class="sxs-lookup"><span data-stu-id="7f50f-103">Best Practices for Fast Shutdown</span></span>

  
  
<span data-ttu-id="7f50f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7f50f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7f50f-105">本主题建议管理员、MAPI 客户端和 MAPI 提供程序使用 Windows 注册表设置和快速关闭接口以在客户端关闭期间最大程度地减少数据丢失的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="7f50f-105">This topic recommends best practices for administrators, MAPI clients, and MAPI providers to use Windows registry settings and the fast shutdown interfaces to minimize data loss during client shutdown.</span></span>
  
- <span data-ttu-id="7f50f-106">若要使 MAPI 客户端成功执行快速关闭，以便提供程序进程不会丢失数据，MAPI 客户端应首先调用 [IMAPIClientShutdown：：QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="7f50f-106">For a MAPI client to carry out fast shutdown successfully so that provider processes do not incur data loss, the MAPI client should first call the [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) method.</span></span> <span data-ttu-id="7f50f-107">然后，客户端应基于 MAPI 子系统对快速关闭的支持继续执行 [IMAPIClientShutdown：：NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) 和 [IMAPIClientShutdown：:D oFastShutdown](imapiclientshutdown-dofastshutdown.md) 方法，如 **IMAPIClientShutdown：：QueryFastShutdown** 的返回值所指示。</span><span class="sxs-lookup"><span data-stu-id="7f50f-107">The client should then proceed with the [IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) and [IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md) methods based on the MAPI subsystem's support for fast shutdown, as indicated by the return value of **IMAPIClientShutdown::QueryFastShutdown**.</span></span> <span data-ttu-id="7f50f-108">作为 MAPI 客户端，如果 **IMAPIClientShutdown：：QueryFastShutdown 返回错误，Microsoft Outlook 不会调用 IMAPIClientShutdown：：NotifyProcessShutdown** 或 **IMAPIClientShutdown：:D oFastShutdown。** </span><span class="sxs-lookup"><span data-stu-id="7f50f-108">As a MAPI client, Microsoft Outlook does not call **IMAPIClientShutdown::NotifyProcessShutdown** or **IMAPIClientShutdown::DoFastShutdown** if **IMAPIClientShutdown::QueryFastShutdown** returns an error.</span></span> <span data-ttu-id="7f50f-109">如果管理员在注册表中禁用了快速关闭Windows，MAPI 子系统将MAPI_E_NO_SUPPORT **IMAPIClientShutdown：：QueryFastShutdown**。</span><span class="sxs-lookup"><span data-stu-id="7f50f-109">If the administrator has disabled fast shutdown in the Windows registry, the MAPI subsystem would return MAPI_E_NO_SUPPORT to **IMAPIClientShutdown::QueryFastShutdown**.</span></span> <span data-ttu-id="7f50f-110">在这种情况下，MAPI 子系统不会通知 MAPI 提供程序立即退出客户端进程。</span><span class="sxs-lookup"><span data-stu-id="7f50f-110">In this case, the MAPI subsystem would not inform MAPI providers of an immediate client process exit.</span></span> <span data-ttu-id="7f50f-111">因此，如果 MAPI 客户端忽略此错误返回代码，继续执行快速关闭操作并断开所有外部引用，则所有加载的 MAPI 提供程序都将丢失数据。</span><span class="sxs-lookup"><span data-stu-id="7f50f-111">Therefore, if a MAPI client disregards this error return code, proceeds to do fast shutdown, and disconnects all external references, all loaded MAPI providers will have data loss.</span></span> 
    
- <span data-ttu-id="7f50f-112">MAPI 提供程序应实现 [IMAPIProviderShutdown ： IUnknown](imapiprovidershutdowniunknown.md) 接口，以执行及时的必要步骤，以避免由于客户端在客户端退出之前断开外部引用而丢失数据。</span><span class="sxs-lookup"><span data-stu-id="7f50f-112">MAPI providers should implement the [IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md) interface to carry out timely and necessary steps to avoid data loss due to the client disconnecting external references before the client exits.</span></span> <span data-ttu-id="7f50f-113">提供程序应推迟将数据保存至其主数据存储不重要的一切其他操作。</span><span class="sxs-lookup"><span data-stu-id="7f50f-113">A provider should postpone everything else that is nonessential to saving data to its primary data store.</span></span> <span data-ttu-id="7f50f-114">例如，传输提供程序应推迟检查新邮件的不必要的后台操作，通讯簿提供程序应推迟从服务器下载最近更改，存储提供程序应推迟维护任务，如压缩或索引。</span><span class="sxs-lookup"><span data-stu-id="7f50f-114">For example, a transport provider should postpone unnecessary background operations that check for new mail, an address book provider should postpone downloading recent changes from its server, and a store provider should postpone maintenance tasks such as compacting or indexing.</span></span> 
    
- <span data-ttu-id="7f50f-115">希望 MAPI 客户端在关闭后立即退出的用户应该使用默认注册表设置，此设置可启用快速关闭，除非提供程序选择退出。</span><span class="sxs-lookup"><span data-stu-id="7f50f-115">Users who want MAPI clients to exit as soon as they close them should use the default registry setting that enables fast shutdown unless a provider opts out.</span></span>
    
- <span data-ttu-id="7f50f-116">一旦 MAPI 客户端调用 **IMAPIClientShutdown：:D oFastShutdown，** 它不应对 MAPI（包括 [MAPIUninitialize](mapiuninitialize.md) 函数）进行任何其他调用。</span><span class="sxs-lookup"><span data-stu-id="7f50f-116">Once a MAPI client calls **IMAPIClientShutdown::DoFastShutdown**, it should not make any additional calls to MAPI, including the [MAPIUninitialize](mapiuninitialize.md) function.</span></span> <span data-ttu-id="7f50f-117">客户端不应在客户端进程的生存期的其余部分使用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="7f50f-117">The client should not use MAPI for the rest of the client process's lifetime.</span></span> 
    
- <span data-ttu-id="7f50f-118">MAPI 客户端永远不应直接调用提供程序的 **IMAPIProviderShutdown** 接口。</span><span class="sxs-lookup"><span data-stu-id="7f50f-118">A MAPI client should never directly call a provider's **IMAPIProviderShutdown** interface.</span></span> <span data-ttu-id="7f50f-119">MAPI 客户端应始终使用 [IMAPIClientShutdown ： IUnknown](imapiclientshutdowniunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="7f50f-119">MAPI clients should always use the [IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md) interface.</span></span> 
    
- <span data-ttu-id="7f50f-120">如果 MAPI 提供程序需要确保在加载时不会使用快速关闭，它应实现 **IMAPIProviderShutdown** 接口，并针对 **IMAPIProviderShutdown：：QueryFastShutdown** 方法返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="7f50f-120">If a MAPI provider needs to ensure that fast shutdown is not used while it is loaded, it should implement the **IMAPIProviderShutdown** interface and return MAPI_E_NO_SUPPORT for the **IMAPIProviderShutdown::QueryFastShutdown** method.</span></span> <span data-ttu-id="7f50f-121">但是，对于 MAPI Outlook，这会使客户端放弃快速关闭，并需要较长时间来关闭。</span><span class="sxs-lookup"><span data-stu-id="7f50f-121">However, for MAPI clients such as Outlook, this will cause the client to abandon fast shutdown and take a longer time to shut down.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="7f50f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f50f-122">See also</span></span>



[<span data-ttu-id="7f50f-123">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="7f50f-123">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)
  
[<span data-ttu-id="7f50f-124">快速关闭概述</span><span class="sxs-lookup"><span data-stu-id="7f50f-124">Fast Shutdown Overview</span></span>](fast-shutdown-overview.md)
  
[<span data-ttu-id="7f50f-125">快速关闭用户选项</span><span class="sxs-lookup"><span data-stu-id="7f50f-125">Fast Shutdown User Options</span></span>](fast-shutdown-user-options.md)

