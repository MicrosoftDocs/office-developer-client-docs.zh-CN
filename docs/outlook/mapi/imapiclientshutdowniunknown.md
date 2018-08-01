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
ms.openlocfilehash: e68211049bc0f958ae24975f4ab4063953eef567
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775333"
---
# <a name="imapiclientshutdown--iunknown"></a><span data-ttu-id="ce06f-103">IMAPIClientShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ce06f-103">IMAPIClientShutdown : IUnknown</span></span>

  
  
<span data-ttu-id="ce06f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ce06f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ce06f-105">允许执行快速关闭的客户端进程的 MAPI 客户端。</span><span class="sxs-lookup"><span data-stu-id="ce06f-105">Enables a MAPI client to carry out fast shutdown of the client process.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ce06f-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ce06f-106">Header file:</span></span>  <br/> |<span data-ttu-id="ce06f-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ce06f-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="ce06f-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="ce06f-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="ce06f-109">[IMAPISession](imapisessioniunknown.md)对象</span><span class="sxs-lookup"><span data-stu-id="ce06f-109">[IMAPISession](imapisessioniunknown.md) object</span></span>  <br/> |
|<span data-ttu-id="ce06f-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ce06f-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="ce06f-111">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="ce06f-111">MAPI subsystem</span></span>  <br/> |
|<span data-ttu-id="ce06f-112">调用：</span><span class="sxs-lookup"><span data-stu-id="ce06f-112">Called by:</span></span>  <br/> |<span data-ttu-id="ce06f-113">MAPI 客户端</span><span class="sxs-lookup"><span data-stu-id="ce06f-113">MAPI client</span></span>  <br/> |
|<span data-ttu-id="ce06f-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="ce06f-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="ce06f-115">IID_IMAPIClientShutdown</span><span class="sxs-lookup"><span data-stu-id="ce06f-115">IID_IMAPIClientShutdown</span></span>  <br/> |
|<span data-ttu-id="ce06f-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="ce06f-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="ce06f-117">LPMAPICLIENTSHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="ce06f-117">LPMAPICLIENTSHUTDOWN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="ce06f-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="ce06f-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="ce06f-119">QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="ce06f-119">QueryFastShutdown</span></span>](imapiclientshutdown-queryfastshutdown.md) <br/> |<span data-ttu-id="ce06f-120">查询的 MAPI 子系统的快速关闭支持提供的加载 MAPI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="ce06f-120">Queries the MAPI subsystem for fast shutdown support that is provided by loaded MAPI providers.</span></span>  <br/> |
|[<span data-ttu-id="ce06f-121">NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="ce06f-121">NotifyProcessShutdown</span></span>](imapiclientshutdown-notifyprocessshutdown.md) <br/> |<span data-ttu-id="ce06f-122">表示的 MAPI 客户端的目的，继续执行关闭。</span><span class="sxs-lookup"><span data-stu-id="ce06f-122">Indicates the intention of the MAPI client to proceed with shut down.</span></span>  <br/> |
|[<span data-ttu-id="ce06f-123">DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="ce06f-123">DoFastShutdown</span></span>](imapiclientshutdown-dofastshutdown.md) <br/> |<span data-ttu-id="ce06f-124">指示的 MAPI 客户端的目的立即退出该客户端进程。</span><span class="sxs-lookup"><span data-stu-id="ce06f-124">Indicates the intention of the MAPI client to exit the client process immediately.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ce06f-125">说明</span><span class="sxs-lookup"><span data-stu-id="ce06f-125">Remarks</span></span>

<span data-ttu-id="ce06f-126">快速关闭的用途是允许 MAPI 客户端和与 MAPI 客户端有活动 MAPI 会话保存 MAPI 设置和数据任何加载的 MAPI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="ce06f-126">The purpose of fast shutdown is to allow a MAPI client and any loaded MAPI provider with which the MAPI client has an active MAPI session to save MAPI settings and data.</span></span> <span data-ttu-id="ce06f-127">这样 MAPI 客户端断开所有外部引用并退出不会导致丢失数据。</span><span class="sxs-lookup"><span data-stu-id="ce06f-127">This enables the MAPI client to disconnect all external references and exit without causing any data loss.</span></span> <span data-ttu-id="ce06f-128">需要执行快速关闭 MAPI 客户端必须使用**IMAPIClientShutdown**接口。</span><span class="sxs-lookup"><span data-stu-id="ce06f-128">A MAPI client that needs to perform fast shutdown must use the **IMAPIClientShutdown** interface.</span></span> <span data-ttu-id="ce06f-129">MAPI 客户端可以通过在任何[IMAPISession](imapisessioniunknown.md)对象上调用 IUnknown::QueryInterface 方法获取指向此接口的指针。</span><span class="sxs-lookup"><span data-stu-id="ce06f-129">The MAPI client can obtain a pointer to this interface by calling the IUnknown::QueryInterface method on any [IMAPISession](imapisessioniunknown.md) object.</span></span> 
  
<span data-ttu-id="ce06f-130">MAPI 客户端总是初始化快速关闭通过调用**IMAPIClientShutdown::QueryFastShutdown**方法。</span><span class="sxs-lookup"><span data-stu-id="ce06f-130">A MAPI client always initiates a fast shutdown by calling the **IMAPIClientShutdown::QueryFastShutdown** method.</span></span> <span data-ttu-id="ce06f-131">MAPI 子系统响应通过验证加载的 MAPI 提供程序是否支持客户端的快速关闭的 MAPI 客户端的查询。</span><span class="sxs-lookup"><span data-stu-id="ce06f-131">The MAPI subsystem responds to the MAPI client's query by verifying whether loaded MAPI providers support the client's fast shutdown.</span></span> <span data-ttu-id="ce06f-132">管理员可以使用 Windows 注册表设置来帮助确定所需的 MAPI 客户端可以继续进行快速关闭提供程序支持的级别。</span><span class="sxs-lookup"><span data-stu-id="ce06f-132">The administrator can use Windows registry settings to help determine the level of provider support that is necessary for MAPI clients to proceed with fast shutdown.</span></span> <span data-ttu-id="ce06f-133">有关详细信息，请参阅[Fast 关闭用户选项](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="ce06f-133">For more information, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span>
  
<span data-ttu-id="ce06f-134">若要继续进行快速关闭，客户端调用**IMAPIClientShutdown::NotifyProcessShutdown**方法，以指示到 MAPI 子系统想要关闭。</span><span class="sxs-lookup"><span data-stu-id="ce06f-134">To proceed with fast shutdown, the client calls the **IMAPIClientShutdown::NotifyProcessShutdown** method to indicate to the MAPI subsystem the intention to shut down.</span></span> <span data-ttu-id="ce06f-135">然后，客户端调用**IMAPIClientShutdown::DoFastShutdown**方法来指示客户端进程正在立即退出。</span><span class="sxs-lookup"><span data-stu-id="ce06f-135">The client then calls the **IMAPIClientShutdown::DoFastShutdown** method to indicate that the client process is exiting immediately.</span></span> 
  
<span data-ttu-id="ce06f-136">有关快速关闭的详细信息，请参阅[快速关闭 Overview](fast-shutdown-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ce06f-136">For more information about fast shutdown, see [Fast Shutdown Overview](fast-shutdown-overview.md).</span></span> <span data-ttu-id="ce06f-137">有关如何成功执行快速关闭的信息，请参阅[快速关闭的最佳实践](best-practices-for-fast-shutdown.md)。</span><span class="sxs-lookup"><span data-stu-id="ce06f-137">For information about how to perform fast shutdown successfully, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ce06f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce06f-138">See also</span></span>



[<span data-ttu-id="ce06f-139">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="ce06f-139">MAPI Interfaces</span></span>](mapi-interfaces.md)
  
[<span data-ttu-id="ce06f-140">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="ce06f-140">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

