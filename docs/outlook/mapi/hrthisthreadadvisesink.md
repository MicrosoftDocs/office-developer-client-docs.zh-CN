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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 744d9a7588bff89e9d306e516a24da2db3038d4d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775213"
---
# <a name="hrthisthreadadvisesink"></a><span data-ttu-id="ac714-103">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="ac714-103">HrThisThreadAdviseSink</span></span>

  
  
<span data-ttu-id="ac714-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ac714-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ac714-105">创建现有通知接收器线程安全的换行通知接收器。</span><span class="sxs-lookup"><span data-stu-id="ac714-105">Creates an advise sink that wraps an existing advise sink for thread safety.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ac714-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ac714-106">Header file:</span></span>  <br/> |<span data-ttu-id="ac714-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="ac714-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ac714-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ac714-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ac714-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ac714-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ac714-110">调用：</span><span class="sxs-lookup"><span data-stu-id="ac714-110">Called by:</span></span>  <br/> |<span data-ttu-id="ac714-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="ac714-111">Client applications</span></span>  <br/> |
   
```cpp
HrThisThreadAdviseSink(
  LPMAPIADVISESINK lpAdviseSink,
  LPMAPIADVISESINK FAR * lppAdviseSink
);
```

## <a name="parameters"></a><span data-ttu-id="ac714-112">参数</span><span class="sxs-lookup"><span data-stu-id="ac714-112">Parameters</span></span>

 <span data-ttu-id="ac714-113">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="ac714-113">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="ac714-114">[in]指向要包装通知接收器。</span><span class="sxs-lookup"><span data-stu-id="ac714-114">[in] Pointer to the advise sink to be wrapped.</span></span> 
    
 <span data-ttu-id="ac714-115">_lppAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="ac714-115">_lppAdviseSink_</span></span>
  
> <span data-ttu-id="ac714-116">[输出]为换行通知接收器_lpAdviseSink_参数指向新通知接收器指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ac714-116">[out] Pointer to a pointer to a new advise sink that wraps the advise sink pointed to by the  _lpAdviseSink_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ac714-117">返回值</span><span class="sxs-lookup"><span data-stu-id="ac714-117">Return value</span></span>

<span data-ttu-id="ac714-118">无。</span><span class="sxs-lookup"><span data-stu-id="ac714-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ac714-119">备注</span><span class="sxs-lookup"><span data-stu-id="ac714-119">Remarks</span></span>

<span data-ttu-id="ac714-120">包装的用途是确保通知称为调用**HrThisThreadAdviseSink**函数的同一线程。</span><span class="sxs-lookup"><span data-stu-id="ac714-120">The purpose of the wrapper is to make sure that notification is called on the same thread that called the **HrThisThreadAdviseSink** function.</span></span> <span data-ttu-id="ac714-121">此函数用于保护必须在特定线程运行的通知回调。</span><span class="sxs-lookup"><span data-stu-id="ac714-121">This function is used to protect notification callbacks that must run on a particular thread.</span></span> 
  
<span data-ttu-id="ac714-122">客户端应用程序应使用**HrThisThreadAdviseSink**时将会生成通知，即，通过在客户端在上一**Advise 传递 advise 接收器对象的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法进行呼叫时限制**呼叫。</span><span class="sxs-lookup"><span data-stu-id="ac714-122">Client applications should use **HrThisThreadAdviseSink** to restrict when notifications are generated, that is, when calls are made to the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method of the advise sink object passed by the client in a previous **Advise** call.</span></span> <span data-ttu-id="ac714-123">如果允许任意生成通知，通知实现可能强制客户端进入多线程操作时，不会相应。</span><span class="sxs-lookup"><span data-stu-id="ac714-123">If notifications are allowed to be generated arbitrarily, a notification implementation might force a client into multithreaded operation when that would not be appropriate.</span></span> <span data-ttu-id="ac714-124">例如，客户端可能使用库，如 Microsoft 基础类库，不支持多线程的呼叫的之一。</span><span class="sxs-lookup"><span data-stu-id="ac714-124">For example, a client might use a library, such as one of the Microsoft Foundation Class Libraries, that does not support multithreaded calls.</span></span> <span data-ttu-id="ac714-125">在不同线程上的通知应这样的客户端中测试困难，而且容易出错。</span><span class="sxs-lookup"><span data-stu-id="ac714-125">Notification on a different thread would make such a client difficult to test and prone to error.</span></span> 
  
 <span data-ttu-id="ac714-126">**HrThisThreadAdviseSink**可确保**OnNotify**呼叫发生仅在这些适当的时间：</span><span class="sxs-lookup"><span data-stu-id="ac714-126">**HrThisThreadAdviseSink** makes sure that **OnNotify** calls occur only at these appropriate times:</span></span> 
  
- <span data-ttu-id="ac714-127">在过程中处理任何 MAPI 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="ac714-127">During processing of a call to any MAPI method.</span></span> 
    
- <span data-ttu-id="ac714-128">在 Windows 消息处理。</span><span class="sxs-lookup"><span data-stu-id="ac714-128">During processing of Windows messages.</span></span> 
    
<span data-ttu-id="ac714-129">当实现**HrThisThreadAdviseSink**时，任何调用任何线程上的新通知接收器**OnNotify**方法会导致在其调用**HrThisThreadAdviseSink**的线程上执行的原始通知方法。</span><span class="sxs-lookup"><span data-stu-id="ac714-129">When **HrThisThreadAdviseSink** is implemented, any calls to the new advise sink's **OnNotify** method on any thread cause the original notification method to be executed on the thread on which **HrThisThreadAdviseSink** was called.</span></span> 
  
<span data-ttu-id="ac714-130">有关通知的详细信息和建议接收器，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[实现接收器告知对象](implementing-an-advise-sink-object.md)。</span><span class="sxs-lookup"><span data-stu-id="ac714-130">For more information about notification and advise sinks, see [Event Notification in MAPI](event-notification-in-mapi.md) and [Implementing an Advise Sink Object](implementing-an-advise-sink-object.md).</span></span> 
  

