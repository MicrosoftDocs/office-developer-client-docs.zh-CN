---
title: IMAPISessionUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.Unadvise
api_type:
- COM
ms.assetid: 5e608cb0-808d-4418-8521-71dcbce8cdff
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3b582b48773b9f6f1a6f46f9c0e4c6dcb9782b86
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592064"
---
# <a name="imapisessionunadvise"></a><span data-ttu-id="f1fb2-103">IMAPISession::Unadvise</span><span class="sxs-lookup"><span data-stu-id="f1fb2-103">IMAPISession::Unadvise</span></span>

  
  
<span data-ttu-id="f1fb2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1fb2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1fb2-105">取消发送通知之前设置与对[IMAPISession::Advise](imapisession-advise.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="f1fb2-105">Cancels the sending of notifications previously set up with a call to the [IMAPISession::Advise](imapisession-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="f1fb2-106">参数</span><span class="sxs-lookup"><span data-stu-id="f1fb2-106">Parameters</span></span>

 <span data-ttu-id="f1fb2-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="f1fb2-107">_ulConnection_</span></span>
  
> <span data-ttu-id="f1fb2-108">[in]与活动通知注册的连接号码。</span><span class="sxs-lookup"><span data-stu-id="f1fb2-108">[in] A connection number associated with an active notification registration.</span></span> <span data-ttu-id="f1fb2-109">必须通过以前调用**IMAPISession::Advise**返回_ulConnection_的值。</span><span class="sxs-lookup"><span data-stu-id="f1fb2-109">The value of  _ulConnection_ must have been returned by a previous call to **IMAPISession::Advise**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f1fb2-110">返回值</span><span class="sxs-lookup"><span data-stu-id="f1fb2-110">Return value</span></span>

<span data-ttu-id="f1fb2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1fb2-111">S_OK</span></span> 
  
> <span data-ttu-id="f1fb2-112">成功取消注册。</span><span class="sxs-lookup"><span data-stu-id="f1fb2-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f1fb2-113">注解</span><span class="sxs-lookup"><span data-stu-id="f1fb2-113">Remarks</span></span>

<span data-ttu-id="f1fb2-114">**IMAPISession::Unadvise**方法取消注册的通知。</span><span class="sxs-lookup"><span data-stu-id="f1fb2-114">The **IMAPISession::Unadvise** method cancels a registration for notification.</span></span> <span data-ttu-id="f1fb2-115">呼叫者到其指针告知接收器，它用于注册的**Advise**调用中接收**Unadvise**版本。</span><span class="sxs-lookup"><span data-stu-id="f1fb2-115">**Unadvise** releases its pointer to the caller's advise sink, which it received in the **Advise** call used for registration.</span></span> 
  
<span data-ttu-id="f1fb2-116">通常， **Unadvise** **Unadvise**呼叫过程中调用通知接收器[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="f1fb2-116">Generally, **Unadvise** calls the advise sink's [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) method during the **Unadvise** call.</span></span> <span data-ttu-id="f1fb2-117">但是，如果另一个线程的过程中调用通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，直至**OnNotify**方法返回延迟**释放**调用。</span><span class="sxs-lookup"><span data-stu-id="f1fb2-117">However, if another thread is in the process of calling the advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f1fb2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1fb2-118">See also</span></span>



[<span data-ttu-id="f1fb2-119">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="f1fb2-119">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="f1fb2-120">IMAPISession::Advise</span><span class="sxs-lookup"><span data-stu-id="f1fb2-120">IMAPISession::Advise</span></span>](imapisession-advise.md)
  
[<span data-ttu-id="f1fb2-121">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f1fb2-121">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)

