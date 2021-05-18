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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 770ceb7af98f5271baad65043e013feb353d231a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329468"
---
# <a name="imapiformunadvise"></a><span data-ttu-id="a4e2a-103">IMAPIForm::Unadvise</span><span class="sxs-lookup"><span data-stu-id="a4e2a-103">IMAPIForm::Unadvise</span></span>

  
  
<span data-ttu-id="a4e2a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a4e2a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a4e2a-105">取消注册之前通过调用 [IMAPIForm：：Advise](imapiform-advise.md)建立的表单查看器的通知。</span><span class="sxs-lookup"><span data-stu-id="a4e2a-105">Cancels a registration for notifications with a form viewer previously established by calling [IMAPIForm::Advise](imapiform-advise.md).</span></span>
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="a4e2a-106">参数</span><span class="sxs-lookup"><span data-stu-id="a4e2a-106">Parameters</span></span>

 <span data-ttu-id="a4e2a-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="a4e2a-107">_ulConnection_</span></span>
  
> <span data-ttu-id="a4e2a-108">[in]标识要取消的通知注册的连接号码。</span><span class="sxs-lookup"><span data-stu-id="a4e2a-108">[in] A connection number that identifies the notification registration to be canceled.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a4e2a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a4e2a-109">Return value</span></span>

<span data-ttu-id="a4e2a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4e2a-110">S_OK</span></span> 
  
> <span data-ttu-id="a4e2a-111">注册已取消。</span><span class="sxs-lookup"><span data-stu-id="a4e2a-111">The registration was canceled.</span></span>
    
<span data-ttu-id="a4e2a-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a4e2a-112">E_INVALIDARG</span></span> 
  
> <span data-ttu-id="a4e2a-113">_ulConnection_ 参数中传递的连接号不表示有效的注册。</span><span class="sxs-lookup"><span data-stu-id="a4e2a-113">The connection number passed in the  _ulConnection_ parameter does not represent a valid registration.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a4e2a-114">备注</span><span class="sxs-lookup"><span data-stu-id="a4e2a-114">Remarks</span></span>

<span data-ttu-id="a4e2a-115">表单查看者调用 **IMAPIForm：：Unadvise** 方法来取消注册他们首先通过调用 **IMAPIForm：：Advise** 方法建立的通知。</span><span class="sxs-lookup"><span data-stu-id="a4e2a-115">Form viewers call the **IMAPIForm::Unadvise** method to cancel a registration for notification that they first established by calling the **IMAPIForm::Advise** method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a4e2a-116">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="a4e2a-116">Notes to implementers</span></span>

<span data-ttu-id="a4e2a-117">通过调用其 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 方法，放弃您按住的指针查看表单查看器的视图通知接收器。</span><span class="sxs-lookup"><span data-stu-id="a4e2a-117">Discard the pointer that you are holding to the form viewer's view advise sink by calling its [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method.</span></span> <span data-ttu-id="a4e2a-118">通常， **在** 非企业调用 **期间调用** Release。</span><span class="sxs-lookup"><span data-stu-id="a4e2a-118">Generally, **Release** is called during the **Unadvise** call.</span></span> <span data-ttu-id="a4e2a-119">但是，如果另一个线程正在调用视图建议接收器的 [IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md) 方法之一，请延迟 **Release** 调用，直到 **IMAPIViewAdviseSink** 方法返回。</span><span class="sxs-lookup"><span data-stu-id="a4e2a-119">However, if another thread is in the process of calling one of the [IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md) methods for the view advise sink, delay the **Release** call until the **IMAPIViewAdviseSink** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a4e2a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4e2a-120">See also</span></span>



[<span data-ttu-id="a4e2a-121">IMAPIForm::Advise</span><span class="sxs-lookup"><span data-stu-id="a4e2a-121">IMAPIForm::Advise</span></span>](imapiform-advise.md)
  
[<span data-ttu-id="a4e2a-122">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a4e2a-122">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)
  
[<span data-ttu-id="a4e2a-123">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a4e2a-123">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)

