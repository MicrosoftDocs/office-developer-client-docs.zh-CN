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
ms.openlocfilehash: a679d04f7697abbe0172105febf87082c0cd9946
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775573"
---
# <a name="imapiprovidershutdown--iunknown"></a><span data-ttu-id="b08af-103">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b08af-103">IMAPIProviderShutdown : IUnknown</span></span>

  
  
<span data-ttu-id="b08af-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b08af-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b08af-105">允许 MAPI 子系统通知的 MAPI 客户端，快速关闭 MAPI 提供程序，以便 MAPI 提供程序可以响应关闭。</span><span class="sxs-lookup"><span data-stu-id="b08af-105">Allows the MAPI subsystem to inform a MAPI provider of the fast shutdown of a MAPI client, so that the MAPI provider can respond to the shutdown.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b08af-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b08af-106">Header file:</span></span>  <br/> |<span data-ttu-id="b08af-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b08af-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="b08af-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="b08af-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="b08af-109">提供商对象： [IXPProvider](ixpprovideriunknown.md)、 [IABProvider](iabprovideriunknown.md)或[IMSProvider](imsprovideriunknown.md)</span><span class="sxs-lookup"><span data-stu-id="b08af-109">Provider objects: [IXPProvider](ixpprovideriunknown.md), [IABProvider](iabprovideriunknown.md), or [IMSProvider](imsprovideriunknown.md)</span></span> <br/> |
|<span data-ttu-id="b08af-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="b08af-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="b08af-111">MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="b08af-111">MAPI provider</span></span>  <br/> |
|<span data-ttu-id="b08af-112">调用：</span><span class="sxs-lookup"><span data-stu-id="b08af-112">Called by:</span></span>  <br/> |<span data-ttu-id="b08af-113">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="b08af-113">MAPI subsystem</span></span>  <br/> |
|<span data-ttu-id="b08af-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="b08af-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="b08af-115">IID_IMAPIProviderShutdown</span><span class="sxs-lookup"><span data-stu-id="b08af-115">IID_IMAPIProviderShutdown</span></span>  <br/> |
|<span data-ttu-id="b08af-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="b08af-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="b08af-117">LPMAPIPROVIDERSHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="b08af-117">LPMAPIPROVIDERSHUTDOWN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="b08af-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="b08af-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="b08af-119">QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="b08af-119">QueryFastShutdown</span></span>](imapiprovidershutdown-queryfastshutdown.md) <br/> |<span data-ttu-id="b08af-120">查询快速关闭 MAPI 提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="b08af-120">Queries the MAPI provider for fast shutdown support.</span></span>  <br/> |
|[<span data-ttu-id="b08af-121">NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="b08af-121">NotifyProcessShutdown</span></span>](imapiprovidershutdown-notifyprocessshutdown.md) <br/> |<span data-ttu-id="b08af-122">表示的 MAPI 提供程序，MAPI 客户端将要执行快速关闭，以便提供程序可以执行操作，以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="b08af-122">Indicates to the MAPI provider that a MAPI client is going to do a fast shutdown, so that the provider can take actions to prevent data loss.</span></span>  <br/> |
|[<span data-ttu-id="b08af-123">DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="b08af-123">DoFastShutdown</span></span>](imapiprovidershutdown-dofastshutdown.md) <br/> |<span data-ttu-id="b08af-124">指示到 MAPI 提供程序 MAPI 客户端立即退出以便 MAPI 提供程序将保留更改以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="b08af-124">Indicates to the MAPI provider that the MAPI client is exiting immediately, so that the MAPI provider will persist changes to prevent data loss.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b08af-125">说明</span><span class="sxs-lookup"><span data-stu-id="b08af-125">Remarks</span></span>

<span data-ttu-id="b08af-126">快速关闭允许 MAPI 客户端退出短时间内的其进程，希望客户端后，并加载 MAPI 提供程序已保存 MAPI 设置和数据。</span><span class="sxs-lookup"><span data-stu-id="b08af-126">Fast shutdown allows a MAPI client to exit its process within a short time, hopefully after the client and loaded MAPI providers have saved MAPI settings and data.</span></span> <span data-ttu-id="b08af-127">MAPI 客户端始终发起快速关闭，并应查询的 MAPI 子系统的快速关闭加载 MAPI 提供程序的支持。</span><span class="sxs-lookup"><span data-stu-id="b08af-127">The MAPI client always initiates a fast shutdown and should query the MAPI subsystem for fast shutdown support from the loaded MAPI providers.</span></span> <span data-ttu-id="b08af-128">管理员可以设置在用户级别指定的所需允许快速关闭所有 MAPI 客户端提供程序支持级别的 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="b08af-128">An administrator can set the Windows registry at the user level to specify the level of provider support that is necessary to allow fast shutdown of all MAPI clients.</span></span> <span data-ttu-id="b08af-129">有关注册表设置的详细信息，请参阅[Fast 关闭用户选项](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="b08af-129">For more information about the registry settings, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span> <span data-ttu-id="b08af-130">但是，对于快速关闭成功发生丢失数据，MAPI 提供程序应实现**IMAPIProviderShutdown**接口。</span><span class="sxs-lookup"><span data-stu-id="b08af-130">However, for fast shutdown to successfully occur without data loss, MAPI providers should implement the **IMAPIProviderShutdown** interface.</span></span> 
  
<span data-ttu-id="b08af-131">需要支持客户端快速关闭 MAPI 提供程序应到 MAPI 子系统在**IMAPIProviderShutdown::QueryFastShutdown**方法返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b08af-131">A MAPI provider that needs to support client fast shutdown should return S_OK to the MAPI subsystem in the **IMAPIProviderShutdown::QueryFastShutdown** method.</span></span> <span data-ttu-id="b08af-132">MAPI 提供程序的 MAPI 子系统随后呼叫的**IMAPIProviderShutdown::NotifyProcessShutdown**和**IMAPIProviderShutdown::DoFastShutdown**方法时, 应采取必要的操作以保存 MAPI 设置和数据和准备客户端的退出。</span><span class="sxs-lookup"><span data-stu-id="b08af-132">When the MAPI subsystem subsequently calls the **IMAPIProviderShutdown::NotifyProcessShutdown** and **IMAPIProviderShutdown::DoFastShutdown** methods, the MAPI provider should take necessary actions to save MAPI settings and data and prepare for the client's exit.</span></span> 
  
<span data-ttu-id="b08af-133">MAPI 提供程序不需要支持客户端快速关闭仍应实现**IMAPIProviderShutdown**接口，并让 MAPI_E_NO_SUPPORT **IMAPIProviderShutdown::QueryFastShutdown**方法。</span><span class="sxs-lookup"><span data-stu-id="b08af-133">MAPI providers that do not need to support client fast shutdown should still implement the **IMAPIProviderShutdown** interface, and have the **IMAPIProviderShutdown::QueryFastShutdown** method return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="b08af-134">对于作为 MAPI 客户端的 Outlook，这会导致 Outlook 等待它退出之前，必须释放的所有外部引用。</span><span class="sxs-lookup"><span data-stu-id="b08af-134">For Outlook as a MAPI client, this causes Outlook to wait for all external references to be released before it exits.</span></span> 
  
<span data-ttu-id="b08af-135">根据用户的 Windows 注册表设置的快速关闭不实现**IMAPIProviderShutdown**接口不一定是阻止客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="b08af-135">Depending on the user's Windows registry setting for fast shutdown, not implementing the **IMAPIProviderShutdown** interface does not necessarily prevent a client fast shutdown.</span></span> 
  
<span data-ttu-id="b08af-136">有关的快速关闭进程的详细信息，请参阅[快速关闭概述](fast-shutdown-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b08af-136">For more information about the process of fast shutdown, see [Fast Shutdown Overview](fast-shutdown-overview.md).</span></span> <span data-ttu-id="b08af-137">有关如何成功执行快速关闭的信息，请参阅[快速关闭的最佳实践](best-practices-for-fast-shutdown.md)。</span><span class="sxs-lookup"><span data-stu-id="b08af-137">For information about how to carry out fast shutdown successfully, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b08af-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b08af-138">See also</span></span>



[<span data-ttu-id="b08af-139">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="b08af-139">MAPI Interfaces</span></span>](mapi-interfaces.md)
  
[<span data-ttu-id="b08af-140">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="b08af-140">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

