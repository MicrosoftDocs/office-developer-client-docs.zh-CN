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
ms.openlocfilehash: 17b038fea2dd1614f94f005e32b9e6ba4423dbda
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566262"
---
# <a name="notifcallback"></a><span data-ttu-id="dde7c-103">NOTIFCALLBACK</span><span class="sxs-lookup"><span data-stu-id="dde7c-103">NOTIFCALLBACK</span></span>

  
  
<span data-ttu-id="dde7c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dde7c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dde7c-105">定义一个 MAPI 调用发送事件通知的回调函数。</span><span class="sxs-lookup"><span data-stu-id="dde7c-105">Defines a callback function that MAPI calls to send an event notification.</span></span> <span data-ttu-id="dde7c-106">仅，可通过调用[HrAllocAdviseSink](hrallocadvisesink.md)函数创建 advise 接收器对象中自动换行时使用此回调函数。</span><span class="sxs-lookup"><span data-stu-id="dde7c-106">This callback function can only be used when wrapped in an advise sink object created by calling the [HrAllocAdviseSink](hrallocadvisesink.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dde7c-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="dde7c-107">Header file:</span></span>  <br/> |<span data-ttu-id="dde7c-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dde7c-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="dde7c-109">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="dde7c-109">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="dde7c-110">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="dde7c-110">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="dde7c-111">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="dde7c-111">Defined function called by:</span></span>  <br/> |<span data-ttu-id="dde7c-112">MAPI</span><span class="sxs-lookup"><span data-stu-id="dde7c-112">MAPI</span></span>  <br/> |
   
```cpp
ULONG (STDAPICALLTYPE NOTIFCALLBACK)(
  LPVOID lpvContext,
  ULONG cNotification,
  LPNOTIFICATION lpNotifications
);
```

## <a name="parameters"></a><span data-ttu-id="dde7c-113">参数</span><span class="sxs-lookup"><span data-stu-id="dde7c-113">Parameters</span></span>

 <span data-ttu-id="dde7c-114">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="dde7c-114">_lpvContext_</span></span>
  
> <span data-ttu-id="dde7c-115">[in]MAPI 调用它时，为任意值的指针传递给回调函数。</span><span class="sxs-lookup"><span data-stu-id="dde7c-115">[in] Pointer to an arbitrary value passed to the callback function when MAPI calls it.</span></span> <span data-ttu-id="dde7c-116">此值可表示的有效位倍数客户端应用程序或服务提供商的地址。</span><span class="sxs-lookup"><span data-stu-id="dde7c-116">This value can represent an address of significance to the client application or service provider.</span></span> <span data-ttu-id="dde7c-117">通常，c + + 代码_lpvContext_参数对 c + + 对象表示的指针。</span><span class="sxs-lookup"><span data-stu-id="dde7c-117">Typically, for C++ code, the  _lpvContext_ parameter represents a pointer to a C++ object.</span></span> 
    
 <span data-ttu-id="dde7c-118">_cNotification_</span><span class="sxs-lookup"><span data-stu-id="dde7c-118">_cNotification_</span></span>
  
> <span data-ttu-id="dde7c-119">[in]由_lpNotifications_参数指示在阵列中的事件通知的计数。</span><span class="sxs-lookup"><span data-stu-id="dde7c-119">[in] Count of event notifications in the array indicated by the  _lpNotifications_ parameter.</span></span> 
    
 <span data-ttu-id="dde7c-120">_lpNotifications_</span><span class="sxs-lookup"><span data-stu-id="dde7c-120">_lpNotifications_</span></span>
  
> <span data-ttu-id="dde7c-121">[输出]其中此函数写入的[通知](notification.md)结构数组的位置的指针包含事件通知。</span><span class="sxs-lookup"><span data-stu-id="dde7c-121">[out] Pointer to the location where this function writes an array of [NOTIFICATION](notification.md) structures that contains the event notifications.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="dde7c-122">返回值</span><span class="sxs-lookup"><span data-stu-id="dde7c-122">Return value</span></span>

<span data-ttu-id="dde7c-123">**NOTIFCALLBACK**函数原型返回值有效的集取决于是否由客户端应用程序或服务提供商实现函数。</span><span class="sxs-lookup"><span data-stu-id="dde7c-123">The set of valid return values for the **NOTIFCALLBACK** function prototype depends on whether the function is implemented by a client application or a service provider.</span></span> <span data-ttu-id="dde7c-124">客户端应始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="dde7c-124">Clients should always return S_OK.</span></span> <span data-ttu-id="dde7c-125">提供程序可以返回 S_OK 或 CALLBACK_DISCONTINUE。</span><span class="sxs-lookup"><span data-stu-id="dde7c-125">Providers can return either S_OK or CALLBACK_DISCONTINUE.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="dde7c-126">注解</span><span class="sxs-lookup"><span data-stu-id="dde7c-126">Remarks</span></span>

<span data-ttu-id="dde7c-127">CALLBACK_DISCONTINUE 是同步的回调函数仅; 有效的返回值它请求 MAPI 立即停止处理此通知的回调。</span><span class="sxs-lookup"><span data-stu-id="dde7c-127">CALLBACK_DISCONTINUE is a valid return value for synchronous callback functions only; it requests that MAPI immediately stop processing the callbacks for this notification.</span></span> <span data-ttu-id="dde7c-128">返回 CALLBACK_DISCONTINUE 时，MAPI _lpUlFlags_将参数设置为 NOTIFY_CANCELED 从[IMAPISupport::Notify](imapisupport-notify.md)返回时。</span><span class="sxs-lookup"><span data-stu-id="dde7c-128">When CALLBACK_DISCONTINUE is returned, MAPI sets the  _lpUlFlags_ parameter to NOTIFY_CANCELED when it returns from [IMAPISupport::Notify](imapisupport-notify.md).</span></span> 
  
<span data-ttu-id="dde7c-129">下面是同步的回调函数可以执行的操作的限制：</span><span class="sxs-lookup"><span data-stu-id="dde7c-129">The following are limitations on what a synchronous callback function can do:</span></span>
  
- <span data-ttu-id="dde7c-130">它不会导致要生成的其他同步通知。</span><span class="sxs-lookup"><span data-stu-id="dde7c-130">It cannot cause another synchronous notification to be generated.</span></span>
    
- <span data-ttu-id="dde7c-131">它不能显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="dde7c-131">It cannot display a user interface.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dde7c-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dde7c-132">See also</span></span>



[<span data-ttu-id="dde7c-133">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="dde7c-133">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)

