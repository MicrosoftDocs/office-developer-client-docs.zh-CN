---
title: IABLogonUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.Unadvise
api_type:
- COM
ms.assetid: 3e506b29-c7e3-40d6-a08b-22fa87088c2d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fe87de4466413e317edea5d358c9e4769d0c5593
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424075"
---
# <a name="iablogonunadvise"></a><span data-ttu-id="bfe98-103">IABLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="bfe98-103">IABLogon::Unadvise</span></span>

  
  
<span data-ttu-id="bfe98-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bfe98-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bfe98-105">取消以前通过调用[IABLogon:: Advise](iablogon-advise.md)方法设置的通知。</span><span class="sxs-lookup"><span data-stu-id="bfe98-105">Cancels notifications that were previously set up with a call to the [IABLogon::Advise](iablogon-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="bfe98-106">参数</span><span class="sxs-lookup"><span data-stu-id="bfe98-106">Parameters</span></span>

 <span data-ttu-id="bfe98-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="bfe98-107">_ulConnection_</span></span>
  
> <span data-ttu-id="bfe98-108">实时与活动通知注册相关联的连接号码。</span><span class="sxs-lookup"><span data-stu-id="bfe98-108">[in] The connection number associated with an active notification registration.</span></span> <span data-ttu-id="bfe98-109">之前对 "**建议**" 的调用必须返回_ulConnection_的值。</span><span class="sxs-lookup"><span data-stu-id="bfe98-109">A previous call to **Advise** must have returned the value of  _ulConnection_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bfe98-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bfe98-110">Return value</span></span>

<span data-ttu-id="bfe98-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfe98-111">S_OK</span></span> 
  
> <span data-ttu-id="bfe98-112">通知注册已成功取消。</span><span class="sxs-lookup"><span data-stu-id="bfe98-112">The notification registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bfe98-113">说明</span><span class="sxs-lookup"><span data-stu-id="bfe98-113">Remarks</span></span>

<span data-ttu-id="bfe98-114">MAPI 调用**Unadvise**方法来取消对容器、邮件用户或通讯组列表对象的通知注册。</span><span class="sxs-lookup"><span data-stu-id="bfe98-114">MAPI calls the **Unadvise** method to cancel a notification registration for a container, messaging user, or distribution list object.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="bfe98-115">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="bfe98-115">Notes to implementers</span></span>

<span data-ttu-id="bfe98-116">您的**Unadvise**实现将取决于您是否支持 MAPI 帮助或手动的通知。</span><span class="sxs-lookup"><span data-stu-id="bfe98-116">Your implementation of **Unadvise** will depend on whether you support notification with MAPI's help or manually.</span></span> <span data-ttu-id="bfe98-117">如果 MAPI 提供支持, 请调用[IMAPISupport:: 退订](imapisupport-unsubscribe.md)方法取消注册。</span><span class="sxs-lookup"><span data-stu-id="bfe98-117">If MAPI provides your support, call the [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md) method to cancel the registration.</span></span> <span data-ttu-id="bfe98-118">如果另一个线程正在调用通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 则可以将其延迟到**OnNotify**返回为止。</span><span class="sxs-lookup"><span data-stu-id="bfe98-118">If another thread is in the process of calling the advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method, it can be delayed until **OnNotify** has returned.</span></span> 
  
<span data-ttu-id="bfe98-119">有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe98-119">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="bfe98-120">有关如何使用[IMAPISupport: IUnknown](imapisupportiunknown.md)方法支持通知的信息, 请参阅[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe98-120">For information about how to use the [IMAPISupport : IUnknown](imapisupportiunknown.md) methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bfe98-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfe98-121">See also</span></span>



[<span data-ttu-id="bfe98-122">IABLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="bfe98-122">IABLogon::Advise</span></span>](iablogon-advise.md)
  
[<span data-ttu-id="bfe98-123">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="bfe98-123">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="bfe98-124">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bfe98-124">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

