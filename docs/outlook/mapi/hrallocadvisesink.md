---
title: HrAllocAdviseSink
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrAllocAdviseSink
api_type:
- HeaderDef
ms.assetid: 1dd460e6-ce95-4fef-bb5e-8d778c9716d5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7f9873fe8e1825c68d4540cc1d093171e9f95727
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428898"
---
# <a name="hrallocadvisesink"></a><span data-ttu-id="3357c-103">HrAllocAdviseSink</span><span class="sxs-lookup"><span data-stu-id="3357c-103">HrAllocAdviseSink</span></span>

  
  
<span data-ttu-id="3357c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3357c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3357c-105">在给定由调用实现指定的上下文和要由事件通知触发的回调函数的情况下，创建建议接收对象。</span><span class="sxs-lookup"><span data-stu-id="3357c-105">Creates an advise sink object, given a context specified by the calling implementation and a callback function to be triggered by an event notification.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3357c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3357c-106">Header file:</span></span>  <br/> |<span data-ttu-id="3357c-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="3357c-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="3357c-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="3357c-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="3357c-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="3357c-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="3357c-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="3357c-110">Called by:</span></span>  <br/> |<span data-ttu-id="3357c-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="3357c-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
STDAPI HrAllocAdviseSink(
  LPNOTIFCALLBACK lpfnCallback,
  LPVOID lpvContext,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a><span data-ttu-id="3357c-112">参数</span><span class="sxs-lookup"><span data-stu-id="3357c-112">Parameters</span></span>

 <span data-ttu-id="3357c-113">_lpfnCallback_</span><span class="sxs-lookup"><span data-stu-id="3357c-113">_lpfnCallback_</span></span>
  
> <span data-ttu-id="3357c-114">[in]指向基于 [NOTIFCALLBACK](notifcallback.md) 原型的回调函数的指针，MAPI 在针对新创建的通知接收器发生通知事件时将调用该原型。</span><span class="sxs-lookup"><span data-stu-id="3357c-114">[in] Pointer to a callback function based on the [NOTIFCALLBACK](notifcallback.md) prototype that MAPI is to call when a notification event occurs for the newly created advise sink.</span></span> 
    
 <span data-ttu-id="3357c-115">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="3357c-115">_lpvContext_</span></span>
  
> <span data-ttu-id="3357c-116">[in]指向在 MAPI 调用回调函数时传递给回调函数的调用方数据的指针。</span><span class="sxs-lookup"><span data-stu-id="3357c-116">[in] Pointer to caller data passed to the callback function when MAPI calls it.</span></span> <span data-ttu-id="3357c-117">呼叫者数据可以表示对客户端或提供程序有意义的地址。</span><span class="sxs-lookup"><span data-stu-id="3357c-117">The caller data can represent an address of significance to the client or provider.</span></span> <span data-ttu-id="3357c-118">通常，对于 C++ 代码  _，lpvContext_ 参数表示指向对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3357c-118">Typically, for C++ code, the  _lpvContext_ parameter represents a pointer to the address of an object.</span></span> 
    
 <span data-ttu-id="3357c-119">_lppAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="3357c-119">_lppAdviseSink_</span></span>
  
> <span data-ttu-id="3357c-120">[out]指向建议接收对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3357c-120">[out] Pointer to a pointer to an advise sink object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3357c-121">返回值</span><span class="sxs-lookup"><span data-stu-id="3357c-121">Return value</span></span>

<span data-ttu-id="3357c-122">无。</span><span class="sxs-lookup"><span data-stu-id="3357c-122">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3357c-123">说明</span><span class="sxs-lookup"><span data-stu-id="3357c-123">Remarks</span></span>

<span data-ttu-id="3357c-124">若要使用 **HrAllocAdviseSink** 函数，客户端应用程序或服务提供商会创建一个对象以接收通知，基于随该对象一起发送的 [NOTIFCALLBACK](notifcallback.md) 函数原型创建通知回调函数，将指向 **HrAllocAdviseSink** 函数中的对象的指针作为  _lpvContext_ 值传递。</span><span class="sxs-lookup"><span data-stu-id="3357c-124">To use the **HrAllocAdviseSink** function, a client application or service provider creates an object to receive notifications, creates a notification callback function based on the [NOTIFCALLBACK](notifcallback.md) function prototype that goes with that object, and passes a pointer to the object in the **HrAllocAdviseSink** function as the  _lpvContext_ value.</span></span> <span data-ttu-id="3357c-125">执行此操作将执行通知;作为通知过程的一部分，MAPI 将对象指针作为上下文调用回调函数。</span><span class="sxs-lookup"><span data-stu-id="3357c-125">Doing so performs a notification; and as part of the notification process, MAPI calls the callback function with the object pointer as the context.</span></span> 
  
<span data-ttu-id="3357c-126">MAPI 异步实现其通知引擎。</span><span class="sxs-lookup"><span data-stu-id="3357c-126">MAPI implements its notification engine asynchronously.</span></span> <span data-ttu-id="3357c-127">在 C++ 中，通知回调可以是对象方法。</span><span class="sxs-lookup"><span data-stu-id="3357c-127">In C++, the notification callback can be an object method.</span></span> <span data-ttu-id="3357c-128">如果生成通知的对象不存在，则请求通知的客户端或提供程序必须针对对象的通知接收器为该对象保留单独的引用计数。</span><span class="sxs-lookup"><span data-stu-id="3357c-128">If the object generating the notification is not present, the client or provider requesting notification must keep a separate reference count for that object for the object's advise sink.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="3357c-129">**应谨慎使用 HrAllocAdviseSink;** 客户端创建自己的建议接收器会更安全。</span><span class="sxs-lookup"><span data-stu-id="3357c-129">**HrAllocAdviseSink** should be used sparingly; it is safer for clients to create their own advise sinks.</span></span> 
  

