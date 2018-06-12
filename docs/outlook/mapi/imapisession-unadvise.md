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
ms.openlocfilehash: 25f80ddce60ab5a8966a62761d234accafbb54be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775580"
---
# <a name="imapisessionunadvise"></a><span data-ttu-id="868e0-103">IMAPISession::Unadvise</span><span class="sxs-lookup"><span data-stu-id="868e0-103">IMAPISession::Unadvise</span></span>

  
  
<span data-ttu-id="868e0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="868e0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="868e0-105">取消发送通知之前设置与对[IMAPISession::Advise](imapisession-advise.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="868e0-105">Cancels the sending of notifications previously set up with a call to the [IMAPISession::Advise](imapisession-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="868e0-106">参数</span><span class="sxs-lookup"><span data-stu-id="868e0-106">Parameters</span></span>

 <span data-ttu-id="868e0-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="868e0-107">_ulConnection_</span></span>
  
> <span data-ttu-id="868e0-108">[in]与活动通知注册的连接号码。</span><span class="sxs-lookup"><span data-stu-id="868e0-108">[in] A connection number associated with an active notification registration.</span></span> <span data-ttu-id="868e0-109">必须通过以前调用**IMAPISession::Advise**返回_ulConnection_的值。</span><span class="sxs-lookup"><span data-stu-id="868e0-109">The value of  _ulConnection_ must have been returned by a previous call to **IMAPISession::Advise**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="868e0-110">返回值</span><span class="sxs-lookup"><span data-stu-id="868e0-110">Return value</span></span>

<span data-ttu-id="868e0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="868e0-111">S_OK</span></span> 
  
> <span data-ttu-id="868e0-112">成功取消注册。</span><span class="sxs-lookup"><span data-stu-id="868e0-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="868e0-113">备注</span><span class="sxs-lookup"><span data-stu-id="868e0-113">Remarks</span></span>

<span data-ttu-id="868e0-114">**IMAPISession::Unadvise**方法取消注册的通知。</span><span class="sxs-lookup"><span data-stu-id="868e0-114">The **IMAPISession::Unadvise** method cancels a registration for notification.</span></span> <span data-ttu-id="868e0-115">呼叫者到其指针告知接收器，它用于注册的**Advise**调用中接收**Unadvise**版本。</span><span class="sxs-lookup"><span data-stu-id="868e0-115">**Unadvise** releases its pointer to the caller's advise sink, which it received in the **Advise** call used for registration.</span></span> 
  
<span data-ttu-id="868e0-116">通常， **Unadvise** **Unadvise**呼叫过程中调用通知接收器[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="868e0-116">Generally, **Unadvise** calls the advise sink's [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) method during the **Unadvise** call.</span></span> <span data-ttu-id="868e0-117">但是，如果另一个线程的过程中调用通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，直至**OnNotify**方法返回延迟**释放**调用。</span><span class="sxs-lookup"><span data-stu-id="868e0-117">However, if another thread is in the process of calling the advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="868e0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="868e0-118">See also</span></span>



[<span data-ttu-id="868e0-119">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="868e0-119">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="868e0-120">IMAPISession::Advise</span><span class="sxs-lookup"><span data-stu-id="868e0-120">IMAPISession::Advise</span></span>](imapisession-advise.md)
  
[<span data-ttu-id="868e0-121">IMAPISession: IUnknown</span><span class="sxs-lookup"><span data-stu-id="868e0-121">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)

