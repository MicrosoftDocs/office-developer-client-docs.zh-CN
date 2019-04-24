---
title: IMAPIProviderShutdown IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProviderShutdown
api_type:
- COM
ms.assetid: fd86c8a5-f251-46c3-ace9-515e94e504ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 92067b5badfb2aab40f3b3735a164bc09321702c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322402"
---
# <a name="imapiprovidershutdown--iunknown"></a><span data-ttu-id="dc3e6-103">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="dc3e6-103">IMAPIProviderShutdown : IUnknown</span></span>

  
  
<span data-ttu-id="dc3e6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc3e6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc3e6-105">允许 mapi 子系统将 mapi 客户端的快速关闭通知给 mapi 提供程序, 以便 mapi 提供程序可以响应关闭操作。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-105">Allows the MAPI subsystem to inform a MAPI provider of the fast shutdown of a MAPI client, so that the MAPI provider can respond to the shutdown.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dc3e6-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="dc3e6-106">Header file:</span></span>  <br/> |<span data-ttu-id="dc3e6-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="dc3e6-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="dc3e6-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="dc3e6-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="dc3e6-109">Provider 对象: [IXPProvider](ixpprovideriunknown.md)、 [IABProvider](iabprovideriunknown.md)或[IMSProvider](imsprovideriunknown.md)</span><span class="sxs-lookup"><span data-stu-id="dc3e6-109">Provider objects: [IXPProvider](ixpprovideriunknown.md), [IABProvider](iabprovideriunknown.md), or [IMSProvider](imsprovideriunknown.md)</span></span> <br/> |
|<span data-ttu-id="dc3e6-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="dc3e6-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="dc3e6-111">MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="dc3e6-111">MAPI provider</span></span>  <br/> |
|<span data-ttu-id="dc3e6-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="dc3e6-112">Called by:</span></span>  <br/> |<span data-ttu-id="dc3e6-113">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="dc3e6-113">MAPI subsystem</span></span>  <br/> |
|<span data-ttu-id="dc3e6-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="dc3e6-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="dc3e6-115">IID_IMAPIProviderShutdown</span><span class="sxs-lookup"><span data-stu-id="dc3e6-115">IID_IMAPIProviderShutdown</span></span>  <br/> |
|<span data-ttu-id="dc3e6-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="dc3e6-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="dc3e6-117">LPMAPIPROVIDERSHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="dc3e6-117">LPMAPIPROVIDERSHUTDOWN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="dc3e6-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="dc3e6-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="dc3e6-119">QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="dc3e6-119">QueryFastShutdown</span></span>](imapiprovidershutdown-queryfastshutdown.md) <br/> |<span data-ttu-id="dc3e6-120">查询 MAPI 提供程序以获取快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-120">Queries the MAPI provider for fast shutdown support.</span></span>  <br/> |
|[<span data-ttu-id="dc3e6-121">NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="dc3e6-121">NotifyProcessShutdown</span></span>](imapiprovidershutdown-notifyprocessshutdown.md) <br/> |<span data-ttu-id="dc3e6-122">向 mapi 提供程序指示 mapi 客户端即将执行快速关闭, 以便提供程序可以采取措施来防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-122">Indicates to the MAPI provider that a MAPI client is going to do a fast shutdown, so that the provider can take actions to prevent data loss.</span></span>  <br/> |
|[<span data-ttu-id="dc3e6-123">DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="dc3e6-123">DoFastShutdown</span></span>](imapiprovidershutdown-dofastshutdown.md) <br/> |<span data-ttu-id="dc3e6-124">向 mapi 提供程序指示 mapi 客户端立即退出, 以便 mapi 提供程序将保留所做的更改以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-124">Indicates to the MAPI provider that the MAPI client is exiting immediately, so that the MAPI provider will persist changes to prevent data loss.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dc3e6-125">注解</span><span class="sxs-lookup"><span data-stu-id="dc3e6-125">Remarks</span></span>

<span data-ttu-id="dc3e6-126">Fast shutdown 允许 MAPI 客户端在短时间内退出其进程, 因此在客户端和加载的 mapi 提供程序保存了 mapi 设置和数据之后, 也是如此。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-126">Fast shutdown allows a MAPI client to exit its process within a short time, hopefully after the client and loaded MAPI providers have saved MAPI settings and data.</span></span> <span data-ttu-id="dc3e6-127">mapi 客户端总是启动快速关闭, 并应查询 mapi 子系统, 以便从加载的 MAPI 提供程序中快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-127">The MAPI client always initiates a fast shutdown and should query the MAPI subsystem for fast shutdown support from the loaded MAPI providers.</span></span> <span data-ttu-id="dc3e6-128">管理员可以在用户级别设置 Windows 注册表, 以指定允许快速关闭所有 MAPI 客户端所必需的提供程序支持级别。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-128">An administrator can set the Windows registry at the user level to specify the level of provider support that is necessary to allow fast shutdown of all MAPI clients.</span></span> <span data-ttu-id="dc3e6-129">有关注册表设置的详细信息, 请参阅[Fast Shutdown User Options](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-129">For more information about the registry settings, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span> <span data-ttu-id="dc3e6-130">但是, 为了使快速关闭在不丢失数据的情况下成功进行, MAPI 提供程序应实现**IMAPIProviderShutdown**接口。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-130">However, for fast shutdown to successfully occur without data loss, MAPI providers should implement the **IMAPIProviderShutdown** interface.</span></span> 
  
<span data-ttu-id="dc3e6-131">需要支持客户端快速关闭的 MAPI 提供程序应将 S_OK 返回到**IMAPIProviderShutdown:: QueryFastShutdown**方法中的 MAPI 子系统。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-131">A MAPI provider that needs to support client fast shutdown should return S_OK to the MAPI subsystem in the **IMAPIProviderShutdown::QueryFastShutdown** method.</span></span> <span data-ttu-id="dc3e6-132">当 mapi 子系统随后调用**IMAPIProviderShutdown:: NotifyProcessShutdown**和**IMAPIProviderShutdown::D ofastshutdown**方法时, mapi 提供程序应执行必要的操作以保存 MAPI 设置和数据, 并准备客户端退出。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-132">When the MAPI subsystem subsequently calls the **IMAPIProviderShutdown::NotifyProcessShutdown** and **IMAPIProviderShutdown::DoFastShutdown** methods, the MAPI provider should take necessary actions to save MAPI settings and data and prepare for the client's exit.</span></span> 
  
<span data-ttu-id="dc3e6-133">如果 MAPI 提供程序不需要支持客户端快速关闭, 则仍应实现**IMAPIProviderShutdown**接口, 并让**IMAPIProviderShutdown:: QueryFastShutdown**方法返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-133">MAPI providers that do not need to support client fast shutdown should still implement the **IMAPIProviderShutdown** interface, and have the **IMAPIProviderShutdown::QueryFastShutdown** method return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="dc3e6-134">对于 outlook 作为 MAPI 客户端, 这会导致 Outlook 等待所有外部引用在退出之前发布。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-134">For Outlook as a MAPI client, this causes Outlook to wait for all external references to be released before it exits.</span></span> 
  
<span data-ttu-id="dc3e6-135">根据用户的 Windows 注册表设置快速关闭, 不实现**IMAPIProviderShutdown**接口不一定会阻止客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-135">Depending on the user's Windows registry setting for fast shutdown, not implementing the **IMAPIProviderShutdown** interface does not necessarily prevent a client fast shutdown.</span></span> 
  
<span data-ttu-id="dc3e6-136">有关快速关机过程的详细信息, 请参阅[fast shutdown 概述](fast-shutdown-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-136">For more information about the process of fast shutdown, see [Fast Shutdown Overview](fast-shutdown-overview.md).</span></span> <span data-ttu-id="dc3e6-137">有关如何成功执行快速关机的信息, 请参阅[fast shutdown 的最佳实践](best-practices-for-fast-shutdown.md)。</span><span class="sxs-lookup"><span data-stu-id="dc3e6-137">For information about how to carry out fast shutdown successfully, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc3e6-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc3e6-138">See also</span></span>



[<span data-ttu-id="dc3e6-139">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="dc3e6-139">MAPI Interfaces</span></span>](mapi-interfaces.md)
  
[<span data-ttu-id="dc3e6-140">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="dc3e6-140">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

