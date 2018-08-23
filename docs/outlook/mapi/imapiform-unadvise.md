---
title: IMAPIFormUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.Unadvise
api_type:
- COM
ms.assetid: fdda45e2-631d-404c-8af4-bce68df0968b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 33287d8ac6b1faeba8b8746a95850f6fd1c37462
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579485"
---
# <a name="imapiformunadvise"></a><span data-ttu-id="24e54-103">IMAPIForm::Unadvise</span><span class="sxs-lookup"><span data-stu-id="24e54-103">IMAPIForm::Unadvise</span></span>

  
  
<span data-ttu-id="24e54-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24e54-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24e54-105">使用窗体查看器通过调用[IMAPIForm::Advise](imapiform-advise.md)以前建立取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="24e54-105">Cancels a registration for notifications with a form viewer previously established by calling [IMAPIForm::Advise](imapiform-advise.md).</span></span>
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="24e54-106">参数</span><span class="sxs-lookup"><span data-stu-id="24e54-106">Parameters</span></span>

 <span data-ttu-id="24e54-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="24e54-107">_ulConnection_</span></span>
  
> <span data-ttu-id="24e54-108">[in]标识要取消此事件的通知注册连接数。</span><span class="sxs-lookup"><span data-stu-id="24e54-108">[in] A connection number that identifies the notification registration to be canceled.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="24e54-109">返回值</span><span class="sxs-lookup"><span data-stu-id="24e54-109">Return value</span></span>

<span data-ttu-id="24e54-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="24e54-110">S_OK</span></span> 
  
> <span data-ttu-id="24e54-111">取消注册。</span><span class="sxs-lookup"><span data-stu-id="24e54-111">The registration was canceled.</span></span>
    
<span data-ttu-id="24e54-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="24e54-112">E_INVALIDARG</span></span> 
  
> <span data-ttu-id="24e54-113">_UlConnection_参数中传递的连接数不代表有效的注册。</span><span class="sxs-lookup"><span data-stu-id="24e54-113">The connection number passed in the  _ulConnection_ parameter does not represent a valid registration.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="24e54-114">注解</span><span class="sxs-lookup"><span data-stu-id="24e54-114">Remarks</span></span>

<span data-ttu-id="24e54-115">表单查看器调用**IMAPIForm::Unadvise**方法取消其第一次调用**IMAPIForm::Advise**方法来建立的通知的注册。</span><span class="sxs-lookup"><span data-stu-id="24e54-115">Form viewers call the **IMAPIForm::Unadvise** method to cancel a registration for notification that they first established by calling the **IMAPIForm::Advise** method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="24e54-116">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="24e54-116">Notes to implementers</span></span>

<span data-ttu-id="24e54-117">放弃指针是保存到表单查看器的视图通过调用其[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法通知接收器。</span><span class="sxs-lookup"><span data-stu-id="24e54-117">Discard the pointer that you are holding to the form viewer's view advise sink by calling its [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) method.</span></span> <span data-ttu-id="24e54-118">通常，调用**Release** **Unadvise**呼叫过程中。</span><span class="sxs-lookup"><span data-stu-id="24e54-118">Generally, **Release** is called during the **Unadvise** call.</span></span> <span data-ttu-id="24e54-119">但是，如果正在调用[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md)方法之一，另一个线程视图告知接收器，直至**IMAPIViewAdviseSink**方法返回延迟**释放**调用。</span><span class="sxs-lookup"><span data-stu-id="24e54-119">However, if another thread is in the process of calling one of the [IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md) methods for the view advise sink, delay the **Release** call until the **IMAPIViewAdviseSink** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="24e54-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24e54-120">See also</span></span>



[<span data-ttu-id="24e54-121">IMAPIForm::Advise</span><span class="sxs-lookup"><span data-stu-id="24e54-121">IMAPIForm::Advise</span></span>](imapiform-advise.md)
  
[<span data-ttu-id="24e54-122">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="24e54-122">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)
  
[<span data-ttu-id="24e54-123">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="24e54-123">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)

