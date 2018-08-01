---
title: IMAPIFormAdvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.Advise
api_type:
- COM
ms.assetid: 961318d6-bebe-4f4b-98ff-921cafc68d24
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b5347205e10b44d62a7e11cbe2f4179970f1bd64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775367"
---
# <a name="imapiformadvise"></a><span data-ttu-id="a4a30-103">IMAPIForm::Advise</span><span class="sxs-lookup"><span data-stu-id="a4a30-103">IMAPIForm::Advise</span></span>

  
  
<span data-ttu-id="a4a30-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a4a30-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a4a30-105">注册的窗体查看有关影响窗体的事件通知。</span><span class="sxs-lookup"><span data-stu-id="a4a30-105">Registers a form viewer for notifications about events that affect the form.</span></span>
  
```cpp
HRESULT Advise(
  LPMAPIVIEWADVISESINK pAdvise,
  ULONG FAR * pulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="a4a30-106">参数</span><span class="sxs-lookup"><span data-stu-id="a4a30-106">Parameters</span></span>

 <span data-ttu-id="a4a30-107">_pAdvise_</span><span class="sxs-lookup"><span data-stu-id="a4a30-107">_pAdvise_</span></span>
  
> <span data-ttu-id="a4a30-108">[in]指向视图的建议接收器对象接收随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="a4a30-108">[in] A pointer to a view advise sink object to receive the subsequent notifications.</span></span> 
    
 <span data-ttu-id="a4a30-109">_pulConnection_</span><span class="sxs-lookup"><span data-stu-id="a4a30-109">_pulConnection_</span></span>
  
> <span data-ttu-id="a4a30-110">[输出]指向为非零值，该值代表成功的通知注册的指针。</span><span class="sxs-lookup"><span data-stu-id="a4a30-110">[out] A pointer to a nonzero value that represents a successful notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a4a30-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a4a30-111">Return value</span></span>

<span data-ttu-id="a4a30-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4a30-112">S_OK</span></span> 
  
> <span data-ttu-id="a4a30-113">注册成功。</span><span class="sxs-lookup"><span data-stu-id="a4a30-113">The registration was successful.</span></span>
    
<span data-ttu-id="a4a30-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a4a30-114">E_OUTOFMEMORY</span></span> 
  
> <span data-ttu-id="a4a30-115">由于内存不足，注册成功。</span><span class="sxs-lookup"><span data-stu-id="a4a30-115">The registration was unsuccessful because of insufficient memory.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a4a30-116">说明</span><span class="sxs-lookup"><span data-stu-id="a4a30-116">Remarks</span></span>

<span data-ttu-id="a4a30-117">表单查看器调用窗体**IMAPIForm::Advise**方法来注册到窗体发生更改时通知。</span><span class="sxs-lookup"><span data-stu-id="a4a30-117">Form viewers call a form's **IMAPIForm::Advise** method to register for notification when changes occur to the form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a4a30-118">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="a4a30-118">Notes to implementers</span></span>

<span data-ttu-id="a4a30-119">保留副本的视图的建议，以便您可以使用该事件发生时调用相应的[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md)方法_pAdvise_参数中传递的接收器指针。</span><span class="sxs-lookup"><span data-stu-id="a4a30-119">Keep a copy of the view advise sink pointer passed in the  _pAdvise_ parameter so that you can use it to call the appropriate [IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md) method when an event occurs.</span></span> <span data-ttu-id="a4a30-120">呼叫视图建议接收器的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx)方法保留指针，直到通知注册被取消。</span><span class="sxs-lookup"><span data-stu-id="a4a30-120">Call the view advise sink's [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx) method to retain the pointer until notification registration is canceled.</span></span> <span data-ttu-id="a4a30-121">设为非零值数_pulConnection_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="a4a30-121">Set the contents of the  _pulConnection_ parameter to a nonzero number.</span></span> 
  
<span data-ttu-id="a4a30-122">多个窗体实现帮助程序对象来处理注册和事件的后续的通知。</span><span class="sxs-lookup"><span data-stu-id="a4a30-122">Many forms implement a helper object to handle the registration and subsequent notification of events.</span></span> 
  
<span data-ttu-id="a4a30-123">有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="a4a30-123">For more information about the notification process in general, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
<span data-ttu-id="a4a30-124">有关通知和窗体的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="a4a30-124">For more information about notification and forms, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4a30-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4a30-125">See also</span></span>



[<span data-ttu-id="a4a30-126">IMAPIForm::Unadvise</span><span class="sxs-lookup"><span data-stu-id="a4a30-126">IMAPIForm::Unadvise</span></span>](imapiform-unadvise.md)
  
[<span data-ttu-id="a4a30-127">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a4a30-127">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)
  
[<span data-ttu-id="a4a30-128">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a4a30-128">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)


[<span data-ttu-id="a4a30-129">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="a4a30-129">Event Notification in MAPI</span></span>](event-notification-in-mapi.md)
  
[<span data-ttu-id="a4a30-130">发送和接收表单通知</span><span class="sxs-lookup"><span data-stu-id="a4a30-130">Sending and Receiving Form Notifications</span></span>](sending-and-receiving-form-notifications.md)

