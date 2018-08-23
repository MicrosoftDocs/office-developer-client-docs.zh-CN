---
title: IMsgStoreUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.Unadvise
api_type:
- COM
ms.assetid: 1394039b-d509-49a5-8421-b7362d906879
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 72a26875802b2b7f94261f11e78fe560e9cc49d3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583426"
---
# <a name="imsgstoreunadvise"></a><span data-ttu-id="59eb9-103">IMsgStore::Unadvise</span><span class="sxs-lookup"><span data-stu-id="59eb9-103">IMsgStore::Unadvise</span></span>

  
  
<span data-ttu-id="59eb9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="59eb9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="59eb9-105">取消发送通知之前设置与对[IMsgStore::Advise](imsgstore-advise.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="59eb9-105">Cancels the sending of notifications previously set up with a call to the [IMsgStore::Advise](imsgstore-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="59eb9-106">参数</span><span class="sxs-lookup"><span data-stu-id="59eb9-106">Parameters</span></span>

 <span data-ttu-id="59eb9-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="59eb9-107">_ulConnection_</span></span>
  
> <span data-ttu-id="59eb9-108">[in]与活动通知注册连接数。</span><span class="sxs-lookup"><span data-stu-id="59eb9-108">[in] The connection number associated with an active notification registration.</span></span> <span data-ttu-id="59eb9-109">必须在之前调用**IMsgStore::Advise**方法返回的_ulConnection_值。</span><span class="sxs-lookup"><span data-stu-id="59eb9-109">The value of  _ulConnection_ must have been returned by a previous call to the **IMsgStore::Advise** method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="59eb9-110">返回值</span><span class="sxs-lookup"><span data-stu-id="59eb9-110">Return value</span></span>

<span data-ttu-id="59eb9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="59eb9-111">S_OK</span></span> 
  
> <span data-ttu-id="59eb9-112">成功取消注册。</span><span class="sxs-lookup"><span data-stu-id="59eb9-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="59eb9-113">注解</span><span class="sxs-lookup"><span data-stu-id="59eb9-113">Remarks</span></span>

<span data-ttu-id="59eb9-114">**IMsgStore::Unadvise**方法取消注册的通知。</span><span class="sxs-lookup"><span data-stu-id="59eb9-114">The **IMsgStore::Unadvise** method cancels a registration for notification.</span></span> <span data-ttu-id="59eb9-115">呼叫者到其指针告知接收器，它用于注册的**Advise**调用中接收**Unadvise**版本。</span><span class="sxs-lookup"><span data-stu-id="59eb9-115">**Unadvise** releases its pointer to the caller's advise sink, which it received in the **Advise** call used for registration.</span></span> 
  
<span data-ttu-id="59eb9-116">通常， **Unadvise** **Unadvise**呼叫过程中调用通知接收器[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="59eb9-116">Generally, **Unadvise** calls the advise sink's [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) method during the **Unadvise** call.</span></span> <span data-ttu-id="59eb9-117">但是，如果另一个线程的过程中调用通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，直至**OnNotify**方法返回延迟**释放**调用。</span><span class="sxs-lookup"><span data-stu-id="59eb9-117">However, if another thread is in the process of calling the advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="59eb9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59eb9-118">See also</span></span>



[<span data-ttu-id="59eb9-119">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="59eb9-119">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="59eb9-120">IMsgStore::Advise</span><span class="sxs-lookup"><span data-stu-id="59eb9-120">IMsgStore::Advise</span></span>](imsgstore-advise.md)
  
[<span data-ttu-id="59eb9-121">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="59eb9-121">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

