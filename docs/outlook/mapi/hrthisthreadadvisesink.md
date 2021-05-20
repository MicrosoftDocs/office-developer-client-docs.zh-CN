---
title: HrThisThreadAdviseSink
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrThisThreadAdviseSink
api_type:
- COM
ms.assetid: 12c07302-472f-4e4f-8087-1bdf0dc09a5a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0fb867d662064dfe5ff7759dba4b36a4635a2914
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427725"
---
# <a name="hrthisthreadadvisesink"></a><span data-ttu-id="97da0-103">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="97da0-103">HrThisThreadAdviseSink</span></span>

  
  
<span data-ttu-id="97da0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="97da0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="97da0-105">为线程安全创建包装现有建议接收器的建议接收器。</span><span class="sxs-lookup"><span data-stu-id="97da0-105">Creates an advise sink that wraps an existing advise sink for thread safety.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="97da0-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="97da0-106">Header file:</span></span>  <br/> |<span data-ttu-id="97da0-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="97da0-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="97da0-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="97da0-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="97da0-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="97da0-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="97da0-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="97da0-110">Called by:</span></span>  <br/> |<span data-ttu-id="97da0-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="97da0-111">Client applications</span></span>  <br/> |
   
```cpp
HrThisThreadAdviseSink(
  LPMAPIADVISESINK lpAdviseSink,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a><span data-ttu-id="97da0-112">参数</span><span class="sxs-lookup"><span data-stu-id="97da0-112">Parameters</span></span>

 <span data-ttu-id="97da0-113">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="97da0-113">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="97da0-114">[in]指向要封装的建议接收器的指针。</span><span class="sxs-lookup"><span data-stu-id="97da0-114">[in] Pointer to the advise sink to be wrapped.</span></span> 
    
 <span data-ttu-id="97da0-115">_lppAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="97da0-115">_lppAdviseSink_</span></span>
  
> <span data-ttu-id="97da0-116">[out]指向新建议接收器的指针，该接收器包装  _lpAdviseSink_ 参数指向的建议接收器。</span><span class="sxs-lookup"><span data-stu-id="97da0-116">[out] Pointer to a pointer to a new advise sink that wraps the advise sink pointed to by the  _lpAdviseSink_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="97da0-117">返回值</span><span class="sxs-lookup"><span data-stu-id="97da0-117">Return value</span></span>

<span data-ttu-id="97da0-118">无。</span><span class="sxs-lookup"><span data-stu-id="97da0-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="97da0-119">说明</span><span class="sxs-lookup"><span data-stu-id="97da0-119">Remarks</span></span>

<span data-ttu-id="97da0-120">包装器的目的是确保通知在调用 **HrThisThreadAdviseSink** 函数的同一线程上调用。</span><span class="sxs-lookup"><span data-stu-id="97da0-120">The purpose of the wrapper is to make sure that notification is called on the same thread that called the **HrThisThreadAdviseSink** function.</span></span> <span data-ttu-id="97da0-121">此函数用于保护必须在特定线程上运行的通知回调。</span><span class="sxs-lookup"><span data-stu-id="97da0-121">This function is used to protect notification callbacks that must run on a particular thread.</span></span> 
  
<span data-ttu-id="97da0-122">客户端应用程序应该使用 **HrThisThreadAdviseSink** 来限制生成通知的时间，即调用客户端在之前的 **Advise** 调用中传递的建议接收器对象的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="97da0-122">Client applications should use **HrThisThreadAdviseSink** to restrict when notifications are generated, that is, when calls are made to the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method of the advise sink object passed by the client in a previous **Advise** call.</span></span> <span data-ttu-id="97da0-123">如果允许任意生成通知，通知实现可能会强制客户端执行多线程操作（如果不适合）。</span><span class="sxs-lookup"><span data-stu-id="97da0-123">If notifications are allowed to be generated arbitrarily, a notification implementation might force a client into multithreaded operation when that would not be appropriate.</span></span> <span data-ttu-id="97da0-124">例如，客户端可能使用不支持多线程调用的库（如 Microsoft Foundation 类库之一）。</span><span class="sxs-lookup"><span data-stu-id="97da0-124">For example, a client might use a library, such as one of the Microsoft Foundation Class Libraries, that does not support multithreaded calls.</span></span> <span data-ttu-id="97da0-125">其他线程上的通知会使此类客户端难以测试且容易出错。</span><span class="sxs-lookup"><span data-stu-id="97da0-125">Notification on a different thread would make such a client difficult to test and prone to error.</span></span> 
  
 <span data-ttu-id="97da0-126">**HrThisThreadAdviseSink** 确保仅在以下适当时间发生 **OnNotify** 调用：</span><span class="sxs-lookup"><span data-stu-id="97da0-126">**HrThisThreadAdviseSink** makes sure that **OnNotify** calls occur only at these appropriate times:</span></span> 
  
- <span data-ttu-id="97da0-127">在处理对任意 MAPI 方法的调用期间。</span><span class="sxs-lookup"><span data-stu-id="97da0-127">During processing of a call to any MAPI method.</span></span> 
    
- <span data-ttu-id="97da0-128">在处理邮件Windows期间。</span><span class="sxs-lookup"><span data-stu-id="97da0-128">During processing of Windows messages.</span></span> 
    
<span data-ttu-id="97da0-129">当 **实现 HrThisThreadAdviseSink** 时，在任何线程上对新通知接收器 **的 OnNotify** 方法的任何调用都会导致原始通知方法在调用 **HrThisThreadAdviseSink** 的线程上执行。</span><span class="sxs-lookup"><span data-stu-id="97da0-129">When **HrThisThreadAdviseSink** is implemented, any calls to the new advise sink's **OnNotify** method on any thread cause the original notification method to be executed on the thread on which **HrThisThreadAdviseSink** was called.</span></span> 
  
<span data-ttu-id="97da0-130">有关通知和通知接收器详细信息，请参阅 [MAPI](event-notification-in-mapi.md) 中的事件通知 [和实现通知接收对象](implementing-an-advise-sink-object.md)。</span><span class="sxs-lookup"><span data-stu-id="97da0-130">For more information about notification and advise sinks, see [Event Notification in MAPI](event-notification-in-mapi.md) and [Implementing an Advise Sink Object](implementing-an-advise-sink-object.md).</span></span> 
  

