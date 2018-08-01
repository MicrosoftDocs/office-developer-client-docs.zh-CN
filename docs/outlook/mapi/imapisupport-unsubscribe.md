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
ms.openlocfilehash: 9ee071bb303c7518a23c5e57909f8618b7aebdde
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775679"
---
# <a name="imapisupportunsubscribe"></a><span data-ttu-id="4118c-103">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="4118c-103">IMAPISupport::Unsubscribe</span></span>

  
  
<span data-ttu-id="4118c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4118c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4118c-105">取消以前建立与调用[IMAPISupport::Subscribe](imapisupport-subscribe.md)方法发送通知的责任。</span><span class="sxs-lookup"><span data-stu-id="4118c-105">Cancels the responsibility for sending notifications that was previously established with a call to the [IMAPISupport::Subscribe](imapisupport-subscribe.md) method.</span></span> 
  
```cpp
HRESULT Unsubscribe(
ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="4118c-106">参数</span><span class="sxs-lookup"><span data-stu-id="4118c-106">Parameters</span></span>

 <span data-ttu-id="4118c-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="4118c-107">_ulConnection_</span></span>
  
> <span data-ttu-id="4118c-108">[in]代表通过**IMAPISupport::Subscribe**以前建立通知注册的非零值的连接数。</span><span class="sxs-lookup"><span data-stu-id="4118c-108">[in] The nonzero connection number that represents the notification registration previously established through **IMAPISupport::Subscribe**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4118c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4118c-109">Return value</span></span>

<span data-ttu-id="4118c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4118c-110">S_OK</span></span> 
  
> <span data-ttu-id="4118c-111">通知注册已取消。</span><span class="sxs-lookup"><span data-stu-id="4118c-111">The notification registration was canceled.</span></span>
    
<span data-ttu-id="4118c-112">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="4118c-112">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="4118c-113">不存在_ulConnection_参数中传递的连接数。</span><span class="sxs-lookup"><span data-stu-id="4118c-113">The connection number passed in the  _ulConnection_ parameter does not exist.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="4118c-114">说明</span><span class="sxs-lookup"><span data-stu-id="4118c-114">Remarks</span></span>

<span data-ttu-id="4118c-115">**IMAPISupport::Unsubscribe**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="4118c-115">The **IMAPISupport::Unsubscribe** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="4118c-116">服务提供商调用**Unsubscribe**取消以前设置**订阅**通知注册。</span><span class="sxs-lookup"><span data-stu-id="4118c-116">Service providers call **Unsubscribe** to cancel a notification registration previously set up by **Subscribe**.</span></span> <span data-ttu-id="4118c-117">**取消订阅**通过释放传入**Subscribe**呼叫的通知接收器指针取消注册。</span><span class="sxs-lookup"><span data-stu-id="4118c-117">**Unsubscribe** cancels the registration by releasing the advise sink pointer passed in the **Subscribe** call.</span></span> 
  
<span data-ttu-id="4118c-118">通常，调用通知接收器**IUnknown::Release**方法**取消**呼叫过程中。</span><span class="sxs-lookup"><span data-stu-id="4118c-118">Generally, the advise sink's **IUnknown::Release** method is called during the **Unsubscribe** call.</span></span> <span data-ttu-id="4118c-119">但是，如果 advise 接收器对象调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法处于另一个线程，直至**OnNotify**方法返回延迟**释放**调用。</span><span class="sxs-lookup"><span data-stu-id="4118c-119">However, if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4118c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4118c-120">See also</span></span>



[<span data-ttu-id="4118c-121">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="4118c-121">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="4118c-122">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="4118c-122">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)
  
[<span data-ttu-id="4118c-123">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4118c-123">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

