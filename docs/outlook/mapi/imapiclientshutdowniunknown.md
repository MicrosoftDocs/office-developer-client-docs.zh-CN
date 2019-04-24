---
title: IMAPIClientShutdown IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIClientShutdown
api_type:
- COM
ms.assetid: b6a5096f-ad27-48b3-b569-f33efc20fa72
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 279d6109e8c29de204c4fb58da51de84b4fbe183
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350874"
---
# <a name="imapiclientshutdown--iunknown"></a><span data-ttu-id="92c0f-103">IMAPIClientShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="92c0f-103">IMAPIClientShutdown : IUnknown</span></span>

  
  
<span data-ttu-id="92c0f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="92c0f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="92c0f-105">使 MAPI 客户端能够快速关闭客户端进程。</span><span class="sxs-lookup"><span data-stu-id="92c0f-105">Enables a MAPI client to carry out fast shutdown of the client process.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="92c0f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="92c0f-106">Header file:</span></span>  <br/> |<span data-ttu-id="92c0f-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="92c0f-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="92c0f-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="92c0f-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="92c0f-109">[IMAPISession](imapisessioniunknown.md)对象</span><span class="sxs-lookup"><span data-stu-id="92c0f-109">[IMAPISession](imapisessioniunknown.md) object</span></span>  <br/> |
|<span data-ttu-id="92c0f-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="92c0f-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="92c0f-111">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="92c0f-111">MAPI subsystem</span></span>  <br/> |
|<span data-ttu-id="92c0f-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="92c0f-112">Called by:</span></span>  <br/> |<span data-ttu-id="92c0f-113">MAPI 客户端</span><span class="sxs-lookup"><span data-stu-id="92c0f-113">MAPI client</span></span>  <br/> |
|<span data-ttu-id="92c0f-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="92c0f-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="92c0f-115">IID_IMAPIClientShutdown</span><span class="sxs-lookup"><span data-stu-id="92c0f-115">IID_IMAPIClientShutdown</span></span>  <br/> |
|<span data-ttu-id="92c0f-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="92c0f-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="92c0f-117">LPMAPICLIENTSHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="92c0f-117">LPMAPICLIENTSHUTDOWN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="92c0f-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="92c0f-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="92c0f-119">QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="92c0f-119">QueryFastShutdown</span></span>](imapiclientshutdown-queryfastshutdown.md) <br/> |<span data-ttu-id="92c0f-120">查询 mapi 子系统以获取加载的 mapi 提供程序提供的快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="92c0f-120">Queries the MAPI subsystem for fast shutdown support that is provided by loaded MAPI providers.</span></span>  <br/> |
|[<span data-ttu-id="92c0f-121">NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="92c0f-121">NotifyProcessShutdown</span></span>](imapiclientshutdown-notifyprocessshutdown.md) <br/> |<span data-ttu-id="92c0f-122">指示 MAPI 客户端的意向继续关闭。</span><span class="sxs-lookup"><span data-stu-id="92c0f-122">Indicates the intention of the MAPI client to proceed with shut down.</span></span>  <br/> |
|[<span data-ttu-id="92c0f-123">DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="92c0f-123">DoFastShutdown</span></span>](imapiclientshutdown-dofastshutdown.md) <br/> |<span data-ttu-id="92c0f-124">指示 MAPI 客户端在立即退出客户端进程的意图。</span><span class="sxs-lookup"><span data-stu-id="92c0f-124">Indicates the intention of the MAPI client to exit the client process immediately.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="92c0f-125">注解</span><span class="sxs-lookup"><span data-stu-id="92c0f-125">Remarks</span></span>

<span data-ttu-id="92c0f-126">快速关闭的目的是允许 mapi 客户端和任何已加载的 mapi 提供程序与 mapi 客户端具有活动的 mapi 会话, 以保存 mapi 设置和数据。</span><span class="sxs-lookup"><span data-stu-id="92c0f-126">The purpose of fast shutdown is to allow a MAPI client and any loaded MAPI provider with which the MAPI client has an active MAPI session to save MAPI settings and data.</span></span> <span data-ttu-id="92c0f-127">这使 MAPI 客户端可以断开所有外部引用并退出, 而不会导致任何数据丢失。</span><span class="sxs-lookup"><span data-stu-id="92c0f-127">This enables the MAPI client to disconnect all external references and exit without causing any data loss.</span></span> <span data-ttu-id="92c0f-128">需要执行快速关机的 MAPI 客户端必须使用**IMAPIClientShutdown**接口。</span><span class="sxs-lookup"><span data-stu-id="92c0f-128">A MAPI client that needs to perform fast shutdown must use the **IMAPIClientShutdown** interface.</span></span> <span data-ttu-id="92c0f-129">MAPI 客户端可以通过在任何[IMAPISession](imapisessioniunknown.md)对象上调用 IUnknown:: QueryInterface 方法来获取指向此接口的指针。</span><span class="sxs-lookup"><span data-stu-id="92c0f-129">The MAPI client can obtain a pointer to this interface by calling the IUnknown::QueryInterface method on any [IMAPISession](imapisessioniunknown.md) object.</span></span> 
  
<span data-ttu-id="92c0f-130">MAPI 客户端总是通过调用**IMAPIClientShutdown:: QueryFastShutdown**方法启动快速关机。</span><span class="sxs-lookup"><span data-stu-id="92c0f-130">A MAPI client always initiates a fast shutdown by calling the **IMAPIClientShutdown::QueryFastShutdown** method.</span></span> <span data-ttu-id="92c0f-131">mapi 子系统通过验证加载的 mapi 提供程序是否支持客户端快速关闭来响应 mapi 客户端的查询。</span><span class="sxs-lookup"><span data-stu-id="92c0f-131">The MAPI subsystem responds to the MAPI client's query by verifying whether loaded MAPI providers support the client's fast shutdown.</span></span> <span data-ttu-id="92c0f-132">管理员可以使用 Windows 注册表设置来帮助确定 MAPI 客户端进行快速关机所需的提供程序支持级别。</span><span class="sxs-lookup"><span data-stu-id="92c0f-132">The administrator can use Windows registry settings to help determine the level of provider support that is necessary for MAPI clients to proceed with fast shutdown.</span></span> <span data-ttu-id="92c0f-133">有关详细信息, 请参阅[Fast Shutdown User Options](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="92c0f-133">For more information, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span>
  
<span data-ttu-id="92c0f-134">若要继续快速关闭, 客户端会调用**IMAPIClientShutdown:: NotifyProcessShutdown**方法, 以指示 MAPI 子系统关闭的意图。</span><span class="sxs-lookup"><span data-stu-id="92c0f-134">To proceed with fast shutdown, the client calls the **IMAPIClientShutdown::NotifyProcessShutdown** method to indicate to the MAPI subsystem the intention to shut down.</span></span> <span data-ttu-id="92c0f-135">然后, 客户端调用**IMAPIClientShutdown::D ofastshutdown**方法, 以指示客户端进程立即退出。</span><span class="sxs-lookup"><span data-stu-id="92c0f-135">The client then calls the **IMAPIClientShutdown::DoFastShutdown** method to indicate that the client process is exiting immediately.</span></span> 
  
<span data-ttu-id="92c0f-136">有关快速关闭的详细信息, 请参阅[fast shutdown 概述](fast-shutdown-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="92c0f-136">For more information about fast shutdown, see [Fast Shutdown Overview](fast-shutdown-overview.md).</span></span> <span data-ttu-id="92c0f-137">有关如何成功执行快速关机的信息, 请参阅[fast shutdown 的最佳实践](best-practices-for-fast-shutdown.md)。</span><span class="sxs-lookup"><span data-stu-id="92c0f-137">For information about how to perform fast shutdown successfully, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92c0f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92c0f-138">See also</span></span>



[<span data-ttu-id="92c0f-139">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="92c0f-139">MAPI Interfaces</span></span>](mapi-interfaces.md)
  
[<span data-ttu-id="92c0f-140">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="92c0f-140">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

