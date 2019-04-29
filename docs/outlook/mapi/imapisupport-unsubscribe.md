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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f27da216b9c474aa31503917a6d3c7a74eab9c4b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421212"
---
# <a name="imapisupportunsubscribe"></a><span data-ttu-id="16278-103">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="16278-103">IMAPISupport::Unsubscribe</span></span>

  
  
<span data-ttu-id="16278-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="16278-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="16278-105">取消发送以前通过调用[IMAPISupport:: 订阅](imapisupport-subscribe.md)方法建立的通知的责任。</span><span class="sxs-lookup"><span data-stu-id="16278-105">Cancels the responsibility for sending notifications that was previously established with a call to the [IMAPISupport::Subscribe](imapisupport-subscribe.md) method.</span></span> 
  
```cpp
HRESULT Unsubscribe(
ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="16278-106">参数</span><span class="sxs-lookup"><span data-stu-id="16278-106">Parameters</span></span>

 <span data-ttu-id="16278-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="16278-107">_ulConnection_</span></span>
  
> <span data-ttu-id="16278-108">实时表示以前通过**IMAPISupport:: 订阅**建立的通知注册的非零连接号码。</span><span class="sxs-lookup"><span data-stu-id="16278-108">[in] The nonzero connection number that represents the notification registration previously established through **IMAPISupport::Subscribe**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="16278-109">返回值</span><span class="sxs-lookup"><span data-stu-id="16278-109">Return value</span></span>

<span data-ttu-id="16278-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="16278-110">S_OK</span></span> 
  
> <span data-ttu-id="16278-111">通知注册已取消。</span><span class="sxs-lookup"><span data-stu-id="16278-111">The notification registration was canceled.</span></span>
    
<span data-ttu-id="16278-112">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="16278-112">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="16278-113">在_ulConnection_参数中传递的连接号码不存在。</span><span class="sxs-lookup"><span data-stu-id="16278-113">The connection number passed in the  _ulConnection_ parameter does not exist.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="16278-114">说明</span><span class="sxs-lookup"><span data-stu-id="16278-114">Remarks</span></span>

<span data-ttu-id="16278-115">**IMAPISupport:: 退订**方法是为所有服务提供程序支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="16278-115">The **IMAPISupport::Unsubscribe** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="16278-116">服务提供商呼叫**取消订阅**以取消之前通过**订阅**设置的通知注册。</span><span class="sxs-lookup"><span data-stu-id="16278-116">Service providers call **Unsubscribe** to cancel a notification registration previously set up by **Subscribe**.</span></span> <span data-ttu-id="16278-117">**取消订阅**通过释放在**订阅**呼叫中传递的通知接收器指针来取消注册。</span><span class="sxs-lookup"><span data-stu-id="16278-117">**Unsubscribe** cancels the registration by releasing the advise sink pointer passed in the **Subscribe** call.</span></span> 
  
<span data-ttu-id="16278-118">通常情况下, 在**取消订阅**呼叫过程中会调用通知接收器的**IUnknown:: Release**方法。</span><span class="sxs-lookup"><span data-stu-id="16278-118">Generally, the advise sink's **IUnknown::Release** method is called during the **Unsubscribe** call.</span></span> <span data-ttu-id="16278-119">但是, 如果另一个线程在调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法的建议接收器对象的过程中, 则**释放**调用将延迟到**OnNotify**方法返回为止。</span><span class="sxs-lookup"><span data-stu-id="16278-119">However, if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="16278-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16278-120">See also</span></span>



[<span data-ttu-id="16278-121">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="16278-121">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="16278-122">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="16278-122">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)
  
[<span data-ttu-id="16278-123">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="16278-123">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

