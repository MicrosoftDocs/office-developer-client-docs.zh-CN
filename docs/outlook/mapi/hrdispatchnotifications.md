---
title: HrDispatchNotifications
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrDispatchNotifications
api_type:
- COM
ms.assetid: 42ec4266-67b9-416e-8b9b-163c95011626
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f4af3f2fd094942c48e02849c60f3e46acb1a5f7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348095"
---
# <a name="hrdispatchnotifications"></a><span data-ttu-id="896b6-103">HrDispatchNotifications</span><span class="sxs-lookup"><span data-stu-id="896b6-103">HrDispatchNotifications</span></span>

  
  
<span data-ttu-id="896b6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="896b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="896b6-105">强制调度所有已排队的通知。</span><span class="sxs-lookup"><span data-stu-id="896b6-105">Forces dispatching of all queued notifications.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="896b6-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="896b6-106">Header file:</span></span>  <br/> |<span data-ttu-id="896b6-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="896b6-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="896b6-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="896b6-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="896b6-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="896b6-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="896b6-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="896b6-110">Called by:</span></span>  <br/> |<span data-ttu-id="896b6-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="896b6-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrDispatchNotifications(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="896b6-112">参数</span><span class="sxs-lookup"><span data-stu-id="896b6-112">Parameters</span></span>

 <span data-ttu-id="896b6-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="896b6-113">_ulFlags_</span></span>
  
> <span data-ttu-id="896b6-114">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="896b6-114">[in] Reserved; must be zero.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="896b6-115">返回值</span><span class="sxs-lookup"><span data-stu-id="896b6-115">Return value</span></span>

<span data-ttu-id="896b6-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="896b6-116">S_OK</span></span>
  
> <span data-ttu-id="896b6-117">已调度所有排队的通知。</span><span class="sxs-lookup"><span data-stu-id="896b6-117">All queued notifications have been dispatched.</span></span>
    
<span data-ttu-id="896b6-118">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="896b6-118">MAPI_E_USER_CANCEL</span></span>
  
> <span data-ttu-id="896b6-119">已收到 WM_QUIT、WM_QUERYENDSESSION 或 WM_ENDSESSION。</span><span class="sxs-lookup"><span data-stu-id="896b6-119">WM_QUIT, WM_QUERYENDSESSION, or WM_ENDSESSION was received.</span></span>
    
<span data-ttu-id="896b6-120">MAPI_E_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="896b6-120">MAPI_E_NOT_INITIALIZED</span></span>
  
> <span data-ttu-id="896b6-121">MAPI 未初始化。</span><span class="sxs-lookup"><span data-stu-id="896b6-121">MAPI was not initialized.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="896b6-122">注解</span><span class="sxs-lookup"><span data-stu-id="896b6-122">Remarks</span></span>

<span data-ttu-id="896b6-123">**HrDispatchNotifications**函数会导致 mapi 调度当前在 MAPI 通知引擎中排队的所有通知, 而无需等待邮件调度。</span><span class="sxs-lookup"><span data-stu-id="896b6-123">The **HrDispatchNotifications** function causes MAPI to dispatch all notifications that are currently queued in the MAPI notification engine without waiting for a message dispatch.</span></span> <span data-ttu-id="896b6-124">这可能会对内存使用率产生有益的影响。</span><span class="sxs-lookup"><span data-stu-id="896b6-124">This can have a beneficial effect on memory utilization.</span></span> <span data-ttu-id="896b6-125">有关详细信息, 请参阅[强制发出通知](forcing-a-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="896b6-125">For more information, see [Forcing a Notification](forcing-a-notification.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="896b6-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="896b6-126">Notes to callers</span></span>

<span data-ttu-id="896b6-127">某些应用程序使用 Windows [PeekMessage](https://msdn.microsoft.com/library/ms644943.aspx)和[DispatchMessage](https://msdn.microsoft.com/library/ms644934.aspx)函数在超时循环中等待通知消息。</span><span class="sxs-lookup"><span data-stu-id="896b6-127">Some applications wait for a notification message in a timeout loop using the Windows [PeekMessage](https://msdn.microsoft.com/library/ms644943.aspx) and [DispatchMessage](https://msdn.microsoft.com/library/ms644934.aspx) functions.</span></span> <span data-ttu-id="896b6-128">除了最快的平台之外, 此类应用程序可能会遇到较差的性能甚至通知。</span><span class="sxs-lookup"><span data-stu-id="896b6-128">On all but the fastest platforms, such applications might experience poor performance or even blockage of notifications.</span></span> <span data-ttu-id="896b6-129">使用**HrDispatchNotifications**不仅可以减少代码, 还可提高性能。</span><span class="sxs-lookup"><span data-stu-id="896b6-129">Using **HrDispatchNotifications** not only reduces code but improves performance.</span></span> 
  

