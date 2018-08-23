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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3fbf8b423cfd4206a0143b5639c85dbcacce2fae
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570980"
---
# <a name="iablogonunadvise"></a><span data-ttu-id="21b67-103">IABLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="21b67-103">IABLogon::Unadvise</span></span>

  
  
<span data-ttu-id="21b67-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="21b67-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="21b67-105">取消以前已设置为[IABLogon::Advise](iablogon-advise.md)方法的调用的通知。</span><span class="sxs-lookup"><span data-stu-id="21b67-105">Cancels notifications that were previously set up with a call to the [IABLogon::Advise](iablogon-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="21b67-106">参数</span><span class="sxs-lookup"><span data-stu-id="21b67-106">Parameters</span></span>

 <span data-ttu-id="21b67-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="21b67-107">_ulConnection_</span></span>
  
> <span data-ttu-id="21b67-108">[in]与活动通知注册连接数。</span><span class="sxs-lookup"><span data-stu-id="21b67-108">[in] The connection number associated with an active notification registration.</span></span> <span data-ttu-id="21b67-109">必须具有以前调用**Advise**返回_ulConnection_的值。</span><span class="sxs-lookup"><span data-stu-id="21b67-109">A previous call to **Advise** must have returned the value of  _ulConnection_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="21b67-110">返回值</span><span class="sxs-lookup"><span data-stu-id="21b67-110">Return value</span></span>

<span data-ttu-id="21b67-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="21b67-111">S_OK</span></span> 
  
> <span data-ttu-id="21b67-112">已成功取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="21b67-112">The notification registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="21b67-113">注解</span><span class="sxs-lookup"><span data-stu-id="21b67-113">Remarks</span></span>

<span data-ttu-id="21b67-114">MAPI 调用**Unadvise**方法取消容器，通知注册消息用户或通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="21b67-114">MAPI calls the **Unadvise** method to cancel a notification registration for a container, messaging user, or distribution list object.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="21b67-115">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="21b67-115">Notes to implementers</span></span>

<span data-ttu-id="21b67-116">**Unadvise**的实现将取决于是否支持 MAPI 的帮助或手动通知。</span><span class="sxs-lookup"><span data-stu-id="21b67-116">Your implementation of **Unadvise** will depend on whether you support notification with MAPI's help or manually.</span></span> <span data-ttu-id="21b67-117">如果 MAPI 提供了您的支持，调用[IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)方法取消注册。</span><span class="sxs-lookup"><span data-stu-id="21b67-117">If MAPI provides your support, call the [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md) method to cancel the registration.</span></span> <span data-ttu-id="21b67-118">如果另一个线程的过程中调用通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，可返回了**OnNotify**之前延迟。</span><span class="sxs-lookup"><span data-stu-id="21b67-118">If another thread is in the process of calling the advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method, it can be delayed until **OnNotify** has returned.</span></span> 
  
<span data-ttu-id="21b67-119">有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="21b67-119">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="21b67-120">有关如何使用[IMAPISupport: IUnknown](imapisupportiunknown.md)方法以支持通知，请参阅[支持的事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="21b67-120">For information about how to use the [IMAPISupport : IUnknown](imapisupportiunknown.md) methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21b67-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21b67-121">See also</span></span>



[<span data-ttu-id="21b67-122">IABLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="21b67-122">IABLogon::Advise</span></span>](iablogon-advise.md)
  
[<span data-ttu-id="21b67-123">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="21b67-123">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="21b67-124">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="21b67-124">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

