---
title: IMAPISupportUnsubscribe
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Unsubscribe
api_type:
- COM
ms.assetid: 3f2870f7-1c08-4d0f-b9d8-7644f5e55b78
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 01ea05eb864c78f3ded39ca3ebc62578076b9d37
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584658"
---
# <a name="imapisupportunsubscribe"></a><span data-ttu-id="c4b5a-103">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="c4b5a-103">IMAPISupport::Unsubscribe</span></span>

  
  
<span data-ttu-id="c4b5a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c4b5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c4b5a-105">取消以前建立与调用[IMAPISupport::Subscribe](imapisupport-subscribe.md)方法发送通知的责任。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-105">Cancels the responsibility for sending notifications that was previously established with a call to the [IMAPISupport::Subscribe](imapisupport-subscribe.md) method.</span></span> 
  
```cpp
HRESULT Unsubscribe(
ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="c4b5a-106">参数</span><span class="sxs-lookup"><span data-stu-id="c4b5a-106">Parameters</span></span>

 <span data-ttu-id="c4b5a-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="c4b5a-107">_ulConnection_</span></span>
  
> <span data-ttu-id="c4b5a-108">[in]代表通过**IMAPISupport::Subscribe**以前建立通知注册的非零值的连接数。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-108">[in] The nonzero connection number that represents the notification registration previously established through **IMAPISupport::Subscribe**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c4b5a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c4b5a-109">Return value</span></span>

<span data-ttu-id="c4b5a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4b5a-110">S_OK</span></span> 
  
> <span data-ttu-id="c4b5a-111">通知注册已取消。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-111">The notification registration was canceled.</span></span>
    
<span data-ttu-id="c4b5a-112">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="c4b5a-112">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="c4b5a-113">不存在_ulConnection_参数中传递的连接数。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-113">The connection number passed in the  _ulConnection_ parameter does not exist.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c4b5a-114">注解</span><span class="sxs-lookup"><span data-stu-id="c4b5a-114">Remarks</span></span>

<span data-ttu-id="c4b5a-115">**IMAPISupport::Unsubscribe**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-115">The **IMAPISupport::Unsubscribe** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="c4b5a-116">服务提供商调用**Unsubscribe**取消以前设置**订阅**通知注册。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-116">Service providers call **Unsubscribe** to cancel a notification registration previously set up by **Subscribe**.</span></span> <span data-ttu-id="c4b5a-117">**取消订阅**通过释放传入**Subscribe**呼叫的通知接收器指针取消注册。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-117">**Unsubscribe** cancels the registration by releasing the advise sink pointer passed in the **Subscribe** call.</span></span> 
  
<span data-ttu-id="c4b5a-118">通常，调用通知接收器**IUnknown::Release**方法**取消**呼叫过程中。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-118">Generally, the advise sink's **IUnknown::Release** method is called during the **Unsubscribe** call.</span></span> <span data-ttu-id="c4b5a-119">但是，如果 advise 接收器对象调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法处于另一个线程，直至**OnNotify**方法返回延迟**释放**调用。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-119">However, if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c4b5a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b5a-120">See also</span></span>



[<span data-ttu-id="c4b5a-121">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="c4b5a-121">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="c4b5a-122">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="c4b5a-122">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)
  
[<span data-ttu-id="c4b5a-123">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c4b5a-123">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

