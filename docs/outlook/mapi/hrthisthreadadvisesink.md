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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346835"
---
# <a name="hrthisthreadadvisesink"></a><span data-ttu-id="64777-103">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="64777-103">HrThisThreadAdviseSink</span></span>

  
  
<span data-ttu-id="64777-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64777-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64777-105">创建为线程安全包装现有建议接收器的通知接收器。</span><span class="sxs-lookup"><span data-stu-id="64777-105">Creates an advise sink that wraps an existing advise sink for thread safety.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="64777-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="64777-106">Header file:</span></span>  <br/> |<span data-ttu-id="64777-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="64777-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="64777-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="64777-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="64777-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="64777-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="64777-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="64777-110">Called by:</span></span>  <br/> |<span data-ttu-id="64777-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="64777-111">Client applications</span></span>  <br/> |
   
```cpp
HrThisThreadAdviseSink(
  LPMAPIADVISESINK lpAdviseSink,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a><span data-ttu-id="64777-112">参数</span><span class="sxs-lookup"><span data-stu-id="64777-112">Parameters</span></span>

 <span data-ttu-id="64777-113">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="64777-113">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="64777-114">实时指向要包装的通知接收器的指针。</span><span class="sxs-lookup"><span data-stu-id="64777-114">[in] Pointer to the advise sink to be wrapped.</span></span> 
    
 <span data-ttu-id="64777-115">_lppAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="64777-115">_lppAdviseSink_</span></span>
  
> <span data-ttu-id="64777-116">排除指向新的通知接收器的指针, 该通知接收器将由_lpAdviseSink_参数指向的通知接收器进行包装。</span><span class="sxs-lookup"><span data-stu-id="64777-116">[out] Pointer to a pointer to a new advise sink that wraps the advise sink pointed to by the  _lpAdviseSink_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="64777-117">返回值</span><span class="sxs-lookup"><span data-stu-id="64777-117">Return value</span></span>

<span data-ttu-id="64777-118">无。</span><span class="sxs-lookup"><span data-stu-id="64777-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="64777-119">注解</span><span class="sxs-lookup"><span data-stu-id="64777-119">Remarks</span></span>

<span data-ttu-id="64777-120">包装的目的是确保在调用**HrThisThreadAdviseSink**函数的同一线程上调用通知。</span><span class="sxs-lookup"><span data-stu-id="64777-120">The purpose of the wrapper is to make sure that notification is called on the same thread that called the **HrThisThreadAdviseSink** function.</span></span> <span data-ttu-id="64777-121">此函数用于保护必须在特定线程上运行的通知回调。</span><span class="sxs-lookup"><span data-stu-id="64777-121">This function is used to protect notification callbacks that must run on a particular thread.</span></span> 
  
<span data-ttu-id="64777-122">客户端应用程序应使用**HrThisThreadAdviseSink**来限制生成通知的时间, 即在上一次建议中对客户端传递的建议接收器对象的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法进行调用\*\*\*\* 调用。</span><span class="sxs-lookup"><span data-stu-id="64777-122">Client applications should use **HrThisThreadAdviseSink** to restrict when notifications are generated, that is, when calls are made to the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method of the advise sink object passed by the client in a previous **Advise** call.</span></span> <span data-ttu-id="64777-123">如果允许任意生成通知, 则通知实现可能会在不适当的情况下强制客户端进入多线程操作。</span><span class="sxs-lookup"><span data-stu-id="64777-123">If notifications are allowed to be generated arbitrarily, a notification implementation might force a client into multithreaded operation when that would not be appropriate.</span></span> <span data-ttu-id="64777-124">例如, 客户端可能使用不支持多线程调用的某个库, 如 Microsoft 基础类库中的一个。</span><span class="sxs-lookup"><span data-stu-id="64777-124">For example, a client might use a library, such as one of the Microsoft Foundation Class Libraries, that does not support multithreaded calls.</span></span> <span data-ttu-id="64777-125">在不同线程上的通知将导致客户端难以测试且容易出错。</span><span class="sxs-lookup"><span data-stu-id="64777-125">Notification on a different thread would make such a client difficult to test and prone to error.</span></span> 
  
 <span data-ttu-id="64777-126">**HrThisThreadAdviseSink**确保**OnNotify**调用仅在以下适当的时间发生:</span><span class="sxs-lookup"><span data-stu-id="64777-126">**HrThisThreadAdviseSink** makes sure that **OnNotify** calls occur only at these appropriate times:</span></span> 
  
- <span data-ttu-id="64777-127">在处理对任何 MAPI 方法的调用的过程中。</span><span class="sxs-lookup"><span data-stu-id="64777-127">During processing of a call to any MAPI method.</span></span> 
    
- <span data-ttu-id="64777-128">在 Windows 消息的处理过程中。</span><span class="sxs-lookup"><span data-stu-id="64777-128">During processing of Windows messages.</span></span> 
    
<span data-ttu-id="64777-129">在实现**HrThisThreadAdviseSink**时, 任何线程上对新的通知接收器的**OnNotify**方法的任何调用都会导致在调用**HrThisThreadAdviseSink**的线程上执行原始通知方法。</span><span class="sxs-lookup"><span data-stu-id="64777-129">When **HrThisThreadAdviseSink** is implemented, any calls to the new advise sink's **OnNotify** method on any thread cause the original notification method to be executed on the thread on which **HrThisThreadAdviseSink** was called.</span></span> 
  
<span data-ttu-id="64777-130">有关通知和建议接收器的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[实现建议接收器对象](implementing-an-advise-sink-object.md)。</span><span class="sxs-lookup"><span data-stu-id="64777-130">For more information about notification and advise sinks, see [Event Notification in MAPI](event-notification-in-mapi.md) and [Implementing an Advise Sink Object](implementing-an-advise-sink-object.md).</span></span> 
  

