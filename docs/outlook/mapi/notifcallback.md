---
title: NOTIFCALLBACK
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.NOTIFCALLBACK
api_type:
- COM
ms.assetid: 416008b4-13aa-4387-8c12-f8f2ca252391
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0e2a1a582894e082722d73422fc8bafe34c4230c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334473"
---
# <a name="notifcallback"></a><span data-ttu-id="cae95-103">NOTIFCALLBACK</span><span class="sxs-lookup"><span data-stu-id="cae95-103">NOTIFCALLBACK</span></span>

  
  
<span data-ttu-id="cae95-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cae95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cae95-105">定义用于接收事件通知的 MAPI 调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="cae95-105">Defines a callback function that MAPI calls to send an event notification.</span></span> <span data-ttu-id="cae95-106">仅当在通过调用[HrAllocAdviseSink](hrallocadvisesink.md)函数创建的通知接收器对象中包装时, 才能使用此回调函数。</span><span class="sxs-lookup"><span data-stu-id="cae95-106">This callback function can only be used when wrapped in an advise sink object created by calling the [HrAllocAdviseSink](hrallocadvisesink.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cae95-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="cae95-107">Header file:</span></span>  <br/> |<span data-ttu-id="cae95-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="cae95-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="cae95-109">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="cae95-109">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="cae95-110">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="cae95-110">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="cae95-111">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="cae95-111">Defined function called by:</span></span>  <br/> |<span data-ttu-id="cae95-112">MAPI</span><span class="sxs-lookup"><span data-stu-id="cae95-112">MAPI</span></span>  <br/> |
   
```cpp
ULONG (STDAPICALLTYPE NOTIFCALLBACK)(
  LPVOID lpvContext,
  ULONG cNotification,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a><span data-ttu-id="cae95-113">参数</span><span class="sxs-lookup"><span data-stu-id="cae95-113">Parameters</span></span>

 <span data-ttu-id="cae95-114">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="cae95-114">_lpvContext_</span></span>
  
> <span data-ttu-id="cae95-115">实时指向在 MAPI 调用回调函数时传递给该函数的任意值的指针。</span><span class="sxs-lookup"><span data-stu-id="cae95-115">[in] Pointer to an arbitrary value passed to the callback function when MAPI calls it.</span></span> <span data-ttu-id="cae95-116">此值可以表示对客户端应用程序或服务提供程序的重要性的地址。</span><span class="sxs-lookup"><span data-stu-id="cae95-116">This value can represent an address of significance to the client application or service provider.</span></span> <span data-ttu-id="cae95-117">通常, 对于 c + + 代码, _lpvContext_参数表示指向 c + + 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="cae95-117">Typically, for C++ code, the  _lpvContext_ parameter represents a pointer to a C++ object.</span></span> 
    
 <span data-ttu-id="cae95-118">_cNotification_</span><span class="sxs-lookup"><span data-stu-id="cae95-118">_cNotification_</span></span>
  
> <span data-ttu-id="cae95-119">实时由_lpNotifications_参数指示的数组中的事件通知数。</span><span class="sxs-lookup"><span data-stu-id="cae95-119">[in] Count of event notifications in the array indicated by the  _lpNotifications_ parameter.</span></span> 
    
 <span data-ttu-id="cae95-120">_lpNotifications_</span><span class="sxs-lookup"><span data-stu-id="cae95-120">_lpNotifications_</span></span>
  
> <span data-ttu-id="cae95-121">排除指向此函数写入包含事件通知的[通知](notification.md)结构数组的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="cae95-121">[out] Pointer to the location where this function writes an array of [NOTIFICATION](notification.md) structures that contains the event notifications.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="cae95-122">返回值</span><span class="sxs-lookup"><span data-stu-id="cae95-122">Return value</span></span>

<span data-ttu-id="cae95-123">**NOTIFCALLBACK**函数原型的有效返回值集取决于函数是否由客户端应用程序或服务提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="cae95-123">The set of valid return values for the **NOTIFCALLBACK** function prototype depends on whether the function is implemented by a client application or a service provider.</span></span> <span data-ttu-id="cae95-124">客户端应始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="cae95-124">Clients should always return S_OK.</span></span> <span data-ttu-id="cae95-125">提供程序可以返回 S_OK 或 CALLBACK_DISCONTINUE。</span><span class="sxs-lookup"><span data-stu-id="cae95-125">Providers can return either S_OK or CALLBACK_DISCONTINUE.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="cae95-126">注解</span><span class="sxs-lookup"><span data-stu-id="cae95-126">Remarks</span></span>

<span data-ttu-id="cae95-127">CALLBACK_DISCONTINUE 是仅适用于同步回调函数的有效返回值;它请求 MAPI 立即停止处理此通知的回调。</span><span class="sxs-lookup"><span data-stu-id="cae95-127">CALLBACK_DISCONTINUE is a valid return value for synchronous callback functions only; it requests that MAPI immediately stop processing the callbacks for this notification.</span></span> <span data-ttu-id="cae95-128">当返回 CALLBACK_DISCONTINUE 时, MAPI 在从[IMAPISupport:: NOTIFY](imapisupport-notify.md)返回时将_lpUlFlags_参数设置为 NOTIFY_CANCELED。</span><span class="sxs-lookup"><span data-stu-id="cae95-128">When CALLBACK_DISCONTINUE is returned, MAPI sets the  _lpUlFlags_ parameter to NOTIFY_CANCELED when it returns from [IMAPISupport::Notify](imapisupport-notify.md).</span></span> 
  
<span data-ttu-id="cae95-129">以下是同步回调函数可以执行的操作的限制:</span><span class="sxs-lookup"><span data-stu-id="cae95-129">The following are limitations on what a synchronous callback function can do:</span></span>
  
- <span data-ttu-id="cae95-130">它不会导致生成另一个同步通知。</span><span class="sxs-lookup"><span data-stu-id="cae95-130">It cannot cause another synchronous notification to be generated.</span></span>
    
- <span data-ttu-id="cae95-131">它无法显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="cae95-131">It cannot display a user interface.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cae95-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cae95-132">See also</span></span>



[<span data-ttu-id="cae95-133">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="cae95-133">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)

