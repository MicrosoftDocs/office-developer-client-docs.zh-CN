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
# <a name="iablogonunadvise"></a><span data-ttu-id="d760a-103">IABLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="d760a-103">IABLogon::Unadvise</span></span>

  
  
<span data-ttu-id="d760a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d760a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d760a-105">取消之前通过调用 [IABLogon：：Advise](iablogon-advise.md) 方法设置的通知。</span><span class="sxs-lookup"><span data-stu-id="d760a-105">Cancels notifications that were previously set up with a call to the [IABLogon::Advise](iablogon-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="d760a-106">参数</span><span class="sxs-lookup"><span data-stu-id="d760a-106">Parameters</span></span>

 <span data-ttu-id="d760a-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="d760a-107">_ulConnection_</span></span>
  
> <span data-ttu-id="d760a-108">[in]与活动通知注册关联的连接号。</span><span class="sxs-lookup"><span data-stu-id="d760a-108">[in] The connection number associated with an active notification registration.</span></span> <span data-ttu-id="d760a-109">之前对 **Advise** 的调用必须已返回  _ulConnection 的值_。</span><span class="sxs-lookup"><span data-stu-id="d760a-109">A previous call to **Advise** must have returned the value of  _ulConnection_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d760a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d760a-110">Return value</span></span>

<span data-ttu-id="d760a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d760a-111">S_OK</span></span> 
  
> <span data-ttu-id="d760a-112">通知注册已成功取消。</span><span class="sxs-lookup"><span data-stu-id="d760a-112">The notification registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d760a-113">备注</span><span class="sxs-lookup"><span data-stu-id="d760a-113">Remarks</span></span>

<span data-ttu-id="d760a-114">MAPI 调用 **Unadvise** 方法以取消容器、邮件传递用户或通讯组列表对象的通知注册。</span><span class="sxs-lookup"><span data-stu-id="d760a-114">MAPI calls the **Unadvise** method to cancel a notification registration for a container, messaging user, or distribution list object.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="d760a-115">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="d760a-115">Notes to implementers</span></span>

<span data-ttu-id="d760a-116">非企业 **实现将取决于** 是支持使用 MAPI 的帮助通知，还是支持手动通知。</span><span class="sxs-lookup"><span data-stu-id="d760a-116">Your implementation of **Unadvise** will depend on whether you support notification with MAPI's help or manually.</span></span> <span data-ttu-id="d760a-117">如果 MAPI 提供支持，请调用 [IMAPISupport：：Unsubscribe](imapisupport-unsubscribe.md) 方法来取消注册。</span><span class="sxs-lookup"><span data-stu-id="d760a-117">If MAPI provides your support, call the [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md) method to cancel the registration.</span></span> <span data-ttu-id="d760a-118">如果另一个线程正在调用通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法，则它会延迟到 **OnNotify** 返回。</span><span class="sxs-lookup"><span data-stu-id="d760a-118">If another thread is in the process of calling the advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method, it can be delayed until **OnNotify** has returned.</span></span> 
  
<span data-ttu-id="d760a-119">有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="d760a-119">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="d760a-120">有关如何使用 [IMAPISupport ： IUnknown](imapisupportiunknown.md) 方法支持通知的信息，请参阅 [Supporting Event Notification](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="d760a-120">For information about how to use the [IMAPISupport : IUnknown](imapisupportiunknown.md) methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d760a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d760a-121">See also</span></span>



[<span data-ttu-id="d760a-122">IABLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="d760a-122">IABLogon::Advise</span></span>](iablogon-advise.md)
  
[<span data-ttu-id="d760a-123">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="d760a-123">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="d760a-124">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d760a-124">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

