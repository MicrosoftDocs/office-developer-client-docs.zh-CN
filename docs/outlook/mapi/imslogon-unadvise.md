---
title: IMSLogonUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.Unadvise
api_type:
- COM
ms.assetid: 440d61c4-b69a-4010-a22b-0c9c5c376fbc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 34c15ca4f7d81eeeee71fb0cb7e31085c75e5492
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775947"
---
# <a name="imslogonunadvise"></a><span data-ttu-id="4df56-103">IMSLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="4df56-103">IMSLogon::Unadvise</span></span>

  
  
<span data-ttu-id="4df56-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4df56-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4df56-105">删除以前使用调用[IMSLogon::Advise](imslogon-advise.md)方法建立的邮件存储更改的通知的对象的注册。</span><span class="sxs-lookup"><span data-stu-id="4df56-105">Removes an object's registration for notification of message store changes previously established by using a call to the [IMSLogon::Advise](imslogon-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="4df56-106">参数</span><span class="sxs-lookup"><span data-stu-id="4df56-106">Parameters</span></span>

 <span data-ttu-id="4df56-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="4df56-107">_ulConnection_</span></span>
  
> <span data-ttu-id="4df56-108">[in]通过调用**IMSLogon::Advise**返回注册连接数。</span><span class="sxs-lookup"><span data-stu-id="4df56-108">[in] The number of the registration connection returned by a call to **IMSLogon::Advise**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4df56-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4df56-109">Return value</span></span>

<span data-ttu-id="4df56-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4df56-110">S_OK</span></span> 
  
> <span data-ttu-id="4df56-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="4df56-111">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4df56-112">说明</span><span class="sxs-lookup"><span data-stu-id="4df56-112">Remarks</span></span>

<span data-ttu-id="4df56-113">消息存储提供程序实现发行版中**IMSLogon::Advise**，从而取消通知到以前的呼叫在_lpAdviseSink_参数中传递 advise 接收器对象的指针的**IMSLogon::Unadvise**方法注册。</span><span class="sxs-lookup"><span data-stu-id="4df56-113">Message store providers implement the **IMSLogon::Unadvise** method to release the pointer to the advise sink object passed in the  _lpAdviseSink_ parameter in the previous call to **IMSLogon::Advise**, thereby canceling a notification registration.</span></span> <span data-ttu-id="4df56-114">作为放弃 advise 接收器对象的指针的一部分，调用对象的[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="4df56-114">As part of discarding the pointer to the advise sink object, the object's [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) method is called.</span></span> <span data-ttu-id="4df56-115">通常，调用**Release** **Unadvise**呼叫过程中。</span><span class="sxs-lookup"><span data-stu-id="4df56-115">Generally, **Release** is called during the **Unadvise** call.</span></span> <span data-ttu-id="4df56-116">但是，如果 advise 接收器对象调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法处于另一个线程，直至**OnNotify**方法返回延迟**释放**调用。</span><span class="sxs-lookup"><span data-stu-id="4df56-116">However, if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4df56-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4df56-117">See also</span></span>



[<span data-ttu-id="4df56-118">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="4df56-118">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="4df56-119">IMSLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="4df56-119">IMSLogon::Advise</span></span>](imslogon-advise.md)
  
[<span data-ttu-id="4df56-120">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4df56-120">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

