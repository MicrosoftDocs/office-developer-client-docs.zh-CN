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
ms.openlocfilehash: d5cb43bfa3acd912e397644657223c177d6afb30
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589320"
---
# <a name="hrallocadvisesink"></a><span data-ttu-id="5d067-103">HrAllocAdviseSink</span><span class="sxs-lookup"><span data-stu-id="5d067-103">HrAllocAdviseSink</span></span>

  
  
<span data-ttu-id="5d067-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d067-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d067-105">创建 advise 接收器对象，由指定的呼叫的实现，回调函数以触发的事件通知的上下文。</span><span class="sxs-lookup"><span data-stu-id="5d067-105">Creates an advise sink object, given a context specified by the calling implementation and a callback function to be triggered by an event notification.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5d067-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="5d067-106">Header file:</span></span>  <br/> |<span data-ttu-id="5d067-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="5d067-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="5d067-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="5d067-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="5d067-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="5d067-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="5d067-110">调用：</span><span class="sxs-lookup"><span data-stu-id="5d067-110">Called by:</span></span>  <br/> |<span data-ttu-id="5d067-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="5d067-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
STDAPI HrAllocAdviseSink(
  LPNOTIFCALLBACK lpfnCallback,
  LPVOID lpvContext,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a><span data-ttu-id="5d067-112">参数</span><span class="sxs-lookup"><span data-stu-id="5d067-112">Parameters</span></span>

 <span data-ttu-id="5d067-113">_lpfnCallback_</span><span class="sxs-lookup"><span data-stu-id="5d067-113">_lpfnCallback_</span></span>
  
> <span data-ttu-id="5d067-114">[in]指向[NOTIFCALLBACK](notifcallback.md)原型的 MAPI 调用的新创建的通知事件发生时所基于的回调函数建议接收器。</span><span class="sxs-lookup"><span data-stu-id="5d067-114">[in] Pointer to a callback function based on the [NOTIFCALLBACK](notifcallback.md) prototype that MAPI is to call when a notification event occurs for the newly created advise sink.</span></span> 
    
 <span data-ttu-id="5d067-115">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="5d067-115">_lpvContext_</span></span>
  
> <span data-ttu-id="5d067-116">[in]MAPI 调用它时，呼叫者数据的指针传递给回调函数。</span><span class="sxs-lookup"><span data-stu-id="5d067-116">[in] Pointer to caller data passed to the callback function when MAPI calls it.</span></span> <span data-ttu-id="5d067-117">呼叫者数据可以表示为客户端或提供程序的有效位倍数的地址。</span><span class="sxs-lookup"><span data-stu-id="5d067-117">The caller data can represent an address of significance to the client or provider.</span></span> <span data-ttu-id="5d067-118">通常情况下，c + + 代码_lpvContext_参数为地址的对象表示的指针。</span><span class="sxs-lookup"><span data-stu-id="5d067-118">Typically, for C++ code, the  _lpvContext_ parameter represents a pointer to the address of an object.</span></span> 
    
 <span data-ttu-id="5d067-119">_lppAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="5d067-119">_lppAdviseSink_</span></span>
  
> <span data-ttu-id="5d067-120">[输出]指向 advise 接收器对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5d067-120">[out] Pointer to a pointer to an advise sink object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5d067-121">返回值</span><span class="sxs-lookup"><span data-stu-id="5d067-121">Return value</span></span>

<span data-ttu-id="5d067-122">无。</span><span class="sxs-lookup"><span data-stu-id="5d067-122">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5d067-123">注解</span><span class="sxs-lookup"><span data-stu-id="5d067-123">Remarks</span></span>

<span data-ttu-id="5d067-124">若要使用**HrAllocAdviseSink**函数，客户端应用程序或服务提供商创建一个对象，以接收通知，创建基于[NOTIFCALLBACK](notifcallback.md)函数原型对象，该对象与对应的通知回调函数和一个指针传递给作为_lpvContext_值的**HrAllocAdviseSink**函数中的对象。</span><span class="sxs-lookup"><span data-stu-id="5d067-124">To use the **HrAllocAdviseSink** function, a client application or service provider creates an object to receive notifications, creates a notification callback function based on the [NOTIFCALLBACK](notifcallback.md) function prototype that goes with that object, and passes a pointer to the object in the **HrAllocAdviseSink** function as the  _lpvContext_ value.</span></span> <span data-ttu-id="5d067-125">这样执行通知;并作为通知过程的一部分，MAPI 调用的回调函数与作为上下文的对象指针。</span><span class="sxs-lookup"><span data-stu-id="5d067-125">Doing so performs a notification; and as part of the notification process, MAPI calls the callback function with the object pointer as the context.</span></span> 
  
<span data-ttu-id="5d067-126">MAPI 异步实现其通知引擎。</span><span class="sxs-lookup"><span data-stu-id="5d067-126">MAPI implements its notification engine asynchronously.</span></span> <span data-ttu-id="5d067-127">在 c + +，通知回调可以是对象的方法。</span><span class="sxs-lookup"><span data-stu-id="5d067-127">In C++, the notification callback can be an object method.</span></span> <span data-ttu-id="5d067-128">如果生成通知的对象不存在，客户端或提供程序请求通知必须保留的对象的对象的单独引用计数建议接收器。</span><span class="sxs-lookup"><span data-stu-id="5d067-128">If the object generating the notification is not present, the client or provider requesting notification must keep a separate reference count for that object for the object's advise sink.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="5d067-129">应谨慎; 使用**HrAllocAdviseSink**它是为客户端创建自己的 advise 接收器更安全。</span><span class="sxs-lookup"><span data-stu-id="5d067-129">**HrAllocAdviseSink** should be used sparingly; it is safer for clients to create their own advise sinks.</span></span> 
  

