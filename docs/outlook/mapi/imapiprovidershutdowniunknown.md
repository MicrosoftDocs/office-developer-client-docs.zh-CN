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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409655"
---
# <a name="imapiprovidershutdown--iunknown"></a><span data-ttu-id="4d589-103">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4d589-103">IMAPIProviderShutdown : IUnknown</span></span>

  
  
<span data-ttu-id="4d589-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d589-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4d589-105">允许 MAPI 子系统通知 MAPI 提供程序快速关闭 MAPI 客户端，以便 MAPI 提供程序可以响应关闭。</span><span class="sxs-lookup"><span data-stu-id="4d589-105">Allows the MAPI subsystem to inform a MAPI provider of the fast shutdown of a MAPI client, so that the MAPI provider can respond to the shutdown.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4d589-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4d589-106">Header file:</span></span>  <br/> |<span data-ttu-id="4d589-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4d589-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="4d589-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="4d589-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="4d589-109">提供程序对象[：IXPProvider、IABProvider](ixpprovideriunknown.md)或[IMSProvider](imsprovideriunknown.md) [](iabprovideriunknown.md)</span><span class="sxs-lookup"><span data-stu-id="4d589-109">Provider objects: [IXPProvider](ixpprovideriunknown.md), [IABProvider](iabprovideriunknown.md), or [IMSProvider](imsprovideriunknown.md)</span></span> <br/> |
|<span data-ttu-id="4d589-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="4d589-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="4d589-111">MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="4d589-111">MAPI provider</span></span>  <br/> |
|<span data-ttu-id="4d589-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="4d589-112">Called by:</span></span>  <br/> |<span data-ttu-id="4d589-113">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="4d589-113">MAPI subsystem</span></span>  <br/> |
|<span data-ttu-id="4d589-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="4d589-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="4d589-115">IID_IMAPIProviderShutdown</span><span class="sxs-lookup"><span data-stu-id="4d589-115">IID_IMAPIProviderShutdown</span></span>  <br/> |
|<span data-ttu-id="4d589-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="4d589-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="4d589-117">LPMAPIPROVIDERSHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="4d589-117">LPMAPIPROVIDERSHUTDOWN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="4d589-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="4d589-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="4d589-119">QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="4d589-119">QueryFastShutdown</span></span>](imapiprovidershutdown-queryfastshutdown.md) <br/> |<span data-ttu-id="4d589-120">向 MAPI 提供程序查询快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="4d589-120">Queries the MAPI provider for fast shutdown support.</span></span>  <br/> |
|[<span data-ttu-id="4d589-121">NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="4d589-121">NotifyProcessShutdown</span></span>](imapiprovidershutdown-notifyprocessshutdown.md) <br/> |<span data-ttu-id="4d589-122">向 MAPI 提供程序指示 MAPI 客户端将快速关闭，以便提供程序可以采取措施防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="4d589-122">Indicates to the MAPI provider that a MAPI client is going to do a fast shutdown, so that the provider can take actions to prevent data loss.</span></span>  <br/> |
|[<span data-ttu-id="4d589-123">DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="4d589-123">DoFastShutdown</span></span>](imapiprovidershutdown-dofastshutdown.md) <br/> |<span data-ttu-id="4d589-124">向 MAPI 提供程序指示 MAPI 客户端正在立即退出，以便 MAPI 提供程序将保留更改以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="4d589-124">Indicates to the MAPI provider that the MAPI client is exiting immediately, so that the MAPI provider will persist changes to prevent data loss.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4d589-125">备注</span><span class="sxs-lookup"><span data-stu-id="4d589-125">Remarks</span></span>

<span data-ttu-id="4d589-126">快速关闭允许 MAPI 客户端在短时间内退出其进程，希望在客户端和加载的 MAPI 提供程序保存 MAPI 设置和数据之后。</span><span class="sxs-lookup"><span data-stu-id="4d589-126">Fast shutdown allows a MAPI client to exit its process within a short time, hopefully after the client and loaded MAPI providers have saved MAPI settings and data.</span></span> <span data-ttu-id="4d589-127">MAPI 客户端始终启动快速关闭，并且应查询 MAPI 子系统，以从已加载的 MAPI 提供程序获得快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="4d589-127">The MAPI client always initiates a fast shutdown and should query the MAPI subsystem for fast shutdown support from the loaded MAPI providers.</span></span> <span data-ttu-id="4d589-128">管理员可以在用户级别Windows注册表，以指定允许快速关闭所有 MAPI 客户端所需的提供程序支持级别。</span><span class="sxs-lookup"><span data-stu-id="4d589-128">An administrator can set the Windows registry at the user level to specify the level of provider support that is necessary to allow fast shutdown of all MAPI clients.</span></span> <span data-ttu-id="4d589-129">有关注册表设置的详细信息，请参阅快速 [关闭用户选项](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="4d589-129">For more information about the registry settings, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span> <span data-ttu-id="4d589-130">但是，若要在未丢失数据的情况下成功成功关闭，MAPI 提供程序应实现 **IMAPIProviderShutdown** 接口。</span><span class="sxs-lookup"><span data-stu-id="4d589-130">However, for fast shutdown to successfully occur without data loss, MAPI providers should implement the **IMAPIProviderShutdown** interface.</span></span> 
  
<span data-ttu-id="4d589-131">需要支持客户端快速关闭的 MAPI 提供程序应S_OK **IMAPIProviderShutdown：：QueryFastShutdown** 方法中的 MAPI 子系统。</span><span class="sxs-lookup"><span data-stu-id="4d589-131">A MAPI provider that needs to support client fast shutdown should return S_OK to the MAPI subsystem in the **IMAPIProviderShutdown::QueryFastShutdown** method.</span></span> <span data-ttu-id="4d589-132">当 MAPI 子系统随后调用 **IMAPIProviderShutdown：：NotifyProcessShutdown** 和 **IMAPIProviderShutdown：:D oFastShutdown** 方法时，MAPI 提供程序应执行必要的操作来保存 MAPI 设置和数据，并准备客户端退出。</span><span class="sxs-lookup"><span data-stu-id="4d589-132">When the MAPI subsystem subsequently calls the **IMAPIProviderShutdown::NotifyProcessShutdown** and **IMAPIProviderShutdown::DoFastShutdown** methods, the MAPI provider should take necessary actions to save MAPI settings and data and prepare for the client's exit.</span></span> 
  
<span data-ttu-id="4d589-133">无需支持客户端快速关闭的 MAPI 提供程序仍应实现 **IMAPIProviderShutdown** 接口，并且让 **IMAPIProviderShutdown：：QueryFastShutdown** 方法返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="4d589-133">MAPI providers that do not need to support client fast shutdown should still implement the **IMAPIProviderShutdown** interface, and have the **IMAPIProviderShutdown::QueryFastShutdown** method return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="4d589-134">对于Outlook MAPI 客户端，这将导致Outlook等待所有外部引用在退出之前释放。</span><span class="sxs-lookup"><span data-stu-id="4d589-134">For Outlook as a MAPI client, this causes Outlook to wait for all external references to be released before it exits.</span></span> 
  
<span data-ttu-id="4d589-135">根据用户的快速关闭Windows设置，不实现 **IMAPIProviderShutdown** 接口不一定阻止客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="4d589-135">Depending on the user's Windows registry setting for fast shutdown, not implementing the **IMAPIProviderShutdown** interface does not necessarily prevent a client fast shutdown.</span></span> 
  
<span data-ttu-id="4d589-136">有关快速关闭过程详细信息，请参阅 [快速关闭概述](fast-shutdown-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4d589-136">For more information about the process of fast shutdown, see [Fast Shutdown Overview](fast-shutdown-overview.md).</span></span> <span data-ttu-id="4d589-137">若要了解如何成功执行快速关闭，请参阅[Best Practices for Fast Shutdown。](best-practices-for-fast-shutdown.md)</span><span class="sxs-lookup"><span data-stu-id="4d589-137">For information about how to carry out fast shutdown successfully, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d589-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d589-138">See also</span></span>



[<span data-ttu-id="4d589-139">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="4d589-139">MAPI Interfaces</span></span>](mapi-interfaces.md)
  
[<span data-ttu-id="4d589-140">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="4d589-140">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

