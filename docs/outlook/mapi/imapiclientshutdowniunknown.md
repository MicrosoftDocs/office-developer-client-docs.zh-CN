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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435332"
---
# <a name="imapiclientshutdown--iunknown"></a><span data-ttu-id="4d526-103">IMAPIClientShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4d526-103">IMAPIClientShutdown : IUnknown</span></span>

  
  
<span data-ttu-id="4d526-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d526-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4d526-105">使 MAPI 客户端可以快速关闭客户端进程。</span><span class="sxs-lookup"><span data-stu-id="4d526-105">Enables a MAPI client to carry out fast shutdown of the client process.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4d526-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4d526-106">Header file:</span></span>  <br/> |<span data-ttu-id="4d526-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4d526-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="4d526-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="4d526-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="4d526-109">[IMAPISession](imapisessioniunknown.md) 对象</span><span class="sxs-lookup"><span data-stu-id="4d526-109">[IMAPISession](imapisessioniunknown.md) object</span></span>  <br/> |
|<span data-ttu-id="4d526-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="4d526-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="4d526-111">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="4d526-111">MAPI subsystem</span></span>  <br/> |
|<span data-ttu-id="4d526-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="4d526-112">Called by:</span></span>  <br/> |<span data-ttu-id="4d526-113">MAPI 客户端</span><span class="sxs-lookup"><span data-stu-id="4d526-113">MAPI client</span></span>  <br/> |
|<span data-ttu-id="4d526-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="4d526-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="4d526-115">IID_IMAPIClientShutdown</span><span class="sxs-lookup"><span data-stu-id="4d526-115">IID_IMAPIClientShutdown</span></span>  <br/> |
|<span data-ttu-id="4d526-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="4d526-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="4d526-117">LPMAPICLIENTSHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="4d526-117">LPMAPICLIENTSHUTDOWN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="4d526-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="4d526-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="4d526-119">QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="4d526-119">QueryFastShutdown</span></span>](imapiclientshutdown-queryfastshutdown.md) <br/> |<span data-ttu-id="4d526-120">查询 MAPI 子系统，了解加载的 MAPI 提供程序提供的快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="4d526-120">Queries the MAPI subsystem for fast shutdown support that is provided by loaded MAPI providers.</span></span>  <br/> |
|[<span data-ttu-id="4d526-121">NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="4d526-121">NotifyProcessShutdown</span></span>](imapiclientshutdown-notifyprocessshutdown.md) <br/> |<span data-ttu-id="4d526-122">指示 MAPI 客户端继续关闭的意图。</span><span class="sxs-lookup"><span data-stu-id="4d526-122">Indicates the intention of the MAPI client to proceed with shut down.</span></span>  <br/> |
|[<span data-ttu-id="4d526-123">DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="4d526-123">DoFastShutdown</span></span>](imapiclientshutdown-dofastshutdown.md) <br/> |<span data-ttu-id="4d526-124">指示 MAPI 客户端打算立即退出客户端进程。</span><span class="sxs-lookup"><span data-stu-id="4d526-124">Indicates the intention of the MAPI client to exit the client process immediately.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4d526-125">备注</span><span class="sxs-lookup"><span data-stu-id="4d526-125">Remarks</span></span>

<span data-ttu-id="4d526-126">快速关闭的目的是允许 MAPI 客户端和 MAPI 客户端具有活动 MAPI 会话的任何已加载 MAPI 提供程序保存 MAPI 设置和数据。</span><span class="sxs-lookup"><span data-stu-id="4d526-126">The purpose of fast shutdown is to allow a MAPI client and any loaded MAPI provider with which the MAPI client has an active MAPI session to save MAPI settings and data.</span></span> <span data-ttu-id="4d526-127">这使 MAPI 客户端能够断开所有外部引用并退出，而不会导致任何数据丢失。</span><span class="sxs-lookup"><span data-stu-id="4d526-127">This enables the MAPI client to disconnect all external references and exit without causing any data loss.</span></span> <span data-ttu-id="4d526-128">需要执行快速关闭的 MAPI 客户端必须使用 **IMAPIClientShutdown** 接口。</span><span class="sxs-lookup"><span data-stu-id="4d526-128">A MAPI client that needs to perform fast shutdown must use the **IMAPIClientShutdown** interface.</span></span> <span data-ttu-id="4d526-129">MAPI 客户端可以通过调用任何 [IMAPISession](imapisessioniunknown.md) 对象的 IUnknown：：QueryInterface 方法来获取指向此接口的指针。</span><span class="sxs-lookup"><span data-stu-id="4d526-129">The MAPI client can obtain a pointer to this interface by calling the IUnknown::QueryInterface method on any [IMAPISession](imapisessioniunknown.md) object.</span></span> 
  
<span data-ttu-id="4d526-130">MAPI 客户端始终通过调用 **IMAPIClientShutdown：：QueryFastShutdown** 方法启动快速关闭。</span><span class="sxs-lookup"><span data-stu-id="4d526-130">A MAPI client always initiates a fast shutdown by calling the **IMAPIClientShutdown::QueryFastShutdown** method.</span></span> <span data-ttu-id="4d526-131">MAPI 子系统通过验证已加载的 MAPI 提供程序是否支持客户端的快速关闭来响应 MAPI 客户端的查询。</span><span class="sxs-lookup"><span data-stu-id="4d526-131">The MAPI subsystem responds to the MAPI client's query by verifying whether loaded MAPI providers support the client's fast shutdown.</span></span> <span data-ttu-id="4d526-132">管理员可以使用Windows设置来帮助确定 MAPI 客户端继续快速关闭所需的提供程序支持级别。</span><span class="sxs-lookup"><span data-stu-id="4d526-132">The administrator can use Windows registry settings to help determine the level of provider support that is necessary for MAPI clients to proceed with fast shutdown.</span></span> <span data-ttu-id="4d526-133">有关详细信息，请参阅快速 [关闭用户选项](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="4d526-133">For more information, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span>
  
<span data-ttu-id="4d526-134">为了继续快速关闭，客户端调用 **IMAPIClientShutdown：：NotifyProcessShutdown** 方法向 MAPI 子系统指示要关闭的意图。</span><span class="sxs-lookup"><span data-stu-id="4d526-134">To proceed with fast shutdown, the client calls the **IMAPIClientShutdown::NotifyProcessShutdown** method to indicate to the MAPI subsystem the intention to shut down.</span></span> <span data-ttu-id="4d526-135">然后，客户端调用 **IMAPIClientShutdown：:D oFastShutdown** 方法来指示客户端进程正在立即退出。</span><span class="sxs-lookup"><span data-stu-id="4d526-135">The client then calls the **IMAPIClientShutdown::DoFastShutdown** method to indicate that the client process is exiting immediately.</span></span> 
  
<span data-ttu-id="4d526-136">有关快速关闭详细信息，请参阅 [快速关闭概述](fast-shutdown-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4d526-136">For more information about fast shutdown, see [Fast Shutdown Overview](fast-shutdown-overview.md).</span></span> <span data-ttu-id="4d526-137">若要了解如何成功执行快速关闭，请参阅 [快速关闭的最佳实践](best-practices-for-fast-shutdown.md)。</span><span class="sxs-lookup"><span data-stu-id="4d526-137">For information about how to perform fast shutdown successfully, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d526-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d526-138">See also</span></span>



[<span data-ttu-id="4d526-139">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="4d526-139">MAPI Interfaces</span></span>](mapi-interfaces.md)
  
[<span data-ttu-id="4d526-140">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="4d526-140">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

