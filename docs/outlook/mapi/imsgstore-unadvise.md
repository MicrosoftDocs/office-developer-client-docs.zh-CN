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
ms.openlocfilehash: f85b662b7fe710c66a2e69dd3cd3db22e3283ddb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398015"
---
# <a name="imsgstoreunadvise"></a><span data-ttu-id="bf3c2-103">IMsgStore::Unadvise</span><span class="sxs-lookup"><span data-stu-id="bf3c2-103">IMsgStore::Unadvise</span></span>

  
  
<span data-ttu-id="bf3c2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bf3c2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bf3c2-105">取消发送通知之前设置与对[IMsgStore::Advise](imsgstore-advise.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-105">Cancels the sending of notifications previously set up with a call to the [IMsgStore::Advise](imsgstore-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="bf3c2-106">参数</span><span class="sxs-lookup"><span data-stu-id="bf3c2-106">Parameters</span></span>

 <span data-ttu-id="bf3c2-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="bf3c2-107">_ulConnection_</span></span>
  
> <span data-ttu-id="bf3c2-108">[in]与活动通知注册连接数。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-108">[in] The connection number associated with an active notification registration.</span></span> <span data-ttu-id="bf3c2-109">必须在之前调用**IMsgStore::Advise**方法返回的_ulConnection_值。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-109">The value of  _ulConnection_ must have been returned by a previous call to the **IMsgStore::Advise** method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="bf3c2-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bf3c2-110">Return value</span></span>

<span data-ttu-id="bf3c2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf3c2-111">S_OK</span></span> 
  
> <span data-ttu-id="bf3c2-112">成功取消注册。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bf3c2-113">说明</span><span class="sxs-lookup"><span data-stu-id="bf3c2-113">Remarks</span></span>

<span data-ttu-id="bf3c2-114">**IMsgStore::Unadvise**方法取消注册的通知。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-114">The **IMsgStore::Unadvise** method cancels a registration for notification.</span></span> <span data-ttu-id="bf3c2-115">呼叫者到其指针告知接收器，它用于注册的**Advise**调用中接收**Unadvise**版本。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-115">**Unadvise** releases its pointer to the caller's advise sink, which it received in the **Advise** call used for registration.</span></span> 
  
<span data-ttu-id="bf3c2-116">通常， **Unadvise** **Unadvise**呼叫过程中调用通知接收器[IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-116">Generally, **Unadvise** calls the advise sink's [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method during the **Unadvise** call.</span></span> <span data-ttu-id="bf3c2-117">但是，如果另一个线程的过程中调用通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，直至**OnNotify**方法返回延迟**释放**调用。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-117">However, if another thread is in the process of calling the advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bf3c2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf3c2-118">See also</span></span>



[<span data-ttu-id="bf3c2-119">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="bf3c2-119">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="bf3c2-120">IMsgStore::Advise</span><span class="sxs-lookup"><span data-stu-id="bf3c2-120">IMsgStore::Advise</span></span>](imsgstore-advise.md)
  
[<span data-ttu-id="bf3c2-121">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="bf3c2-121">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

