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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2ed8bace97dee3842243ed835769e80e8aaf6b03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329482"
---
# <a name="imapiformadvise"></a><span data-ttu-id="26894-103">IMAPIForm::Advise</span><span class="sxs-lookup"><span data-stu-id="26894-103">IMAPIForm::Advise</span></span>

  
  
<span data-ttu-id="26894-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="26894-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="26894-105">注册表单查看器, 以获取有关影响表单的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="26894-105">Registers a form viewer for notifications about events that affect the form.</span></span>
  
```cpp
HRESULT Advise(
  LPMAPIVIEWADVISESINK pAdvise,
  ULONG FAR * pulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="26894-106">参数</span><span class="sxs-lookup"><span data-stu-id="26894-106">Parameters</span></span>

 <span data-ttu-id="26894-107">_pAdvise_</span><span class="sxs-lookup"><span data-stu-id="26894-107">_pAdvise_</span></span>
  
> <span data-ttu-id="26894-108">实时指向用于接收后续通知的视图建议接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="26894-108">[in] A pointer to a view advise sink object to receive the subsequent notifications.</span></span> 
    
 <span data-ttu-id="26894-109">_pulConnection_</span><span class="sxs-lookup"><span data-stu-id="26894-109">_pulConnection_</span></span>
  
> <span data-ttu-id="26894-110">排除指向表示成功的通知注册的非零值的指针。</span><span class="sxs-lookup"><span data-stu-id="26894-110">[out] A pointer to a nonzero value that represents a successful notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="26894-111">返回值</span><span class="sxs-lookup"><span data-stu-id="26894-111">Return value</span></span>

<span data-ttu-id="26894-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="26894-112">S_OK</span></span> 
  
> <span data-ttu-id="26894-113">注册成功。</span><span class="sxs-lookup"><span data-stu-id="26894-113">The registration was successful.</span></span>
    
<span data-ttu-id="26894-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="26894-114">E_OUTOFMEMORY</span></span> 
  
> <span data-ttu-id="26894-115">由于内存不足, 注册未成功。</span><span class="sxs-lookup"><span data-stu-id="26894-115">The registration was unsuccessful because of insufficient memory.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="26894-116">注解</span><span class="sxs-lookup"><span data-stu-id="26894-116">Remarks</span></span>

<span data-ttu-id="26894-117">表单查看者调用表单的**IMAPIForm:: Advise**方法, 以便在表单发生更改时注册通知。</span><span class="sxs-lookup"><span data-stu-id="26894-117">Form viewers call a form's **IMAPIForm::Advise** method to register for notification when changes occur to the form.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="26894-118">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="26894-118">Notes to implementers</span></span>

<span data-ttu-id="26894-119">保留在_pAdvise_参数中传递的视图建议接收器指针的副本, 以便在事件发生时可以使用该副本调用相应的[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="26894-119">Keep a copy of the view advise sink pointer passed in the  _pAdvise_ parameter so that you can use it to call the appropriate [IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md) method when an event occurs.</span></span> <span data-ttu-id="26894-120">调用 view advise sink [IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)方法以保留指针, 直到通知注册被取消。</span><span class="sxs-lookup"><span data-stu-id="26894-120">Call the view advise sink's [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) method to retain the pointer until notification registration is canceled.</span></span> <span data-ttu-id="26894-121">将_pulConnection_参数的内容设置为非零数字。</span><span class="sxs-lookup"><span data-stu-id="26894-121">Set the contents of the  _pulConnection_ parameter to a nonzero number.</span></span> 
  
<span data-ttu-id="26894-122">许多窗体都实现帮助程序对象来处理注册和随后发生的事件通知。</span><span class="sxs-lookup"><span data-stu-id="26894-122">Many forms implement a helper object to handle the registration and subsequent notification of events.</span></span> 
  
<span data-ttu-id="26894-123">有关常规通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="26894-123">For more information about the notification process in general, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
<span data-ttu-id="26894-124">有关通知和窗体的详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="26894-124">For more information about notification and forms, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="26894-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26894-125">See also</span></span>



[<span data-ttu-id="26894-126">IMAPIForm::Unadvise</span><span class="sxs-lookup"><span data-stu-id="26894-126">IMAPIForm::Unadvise</span></span>](imapiform-unadvise.md)
  
[<span data-ttu-id="26894-127">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="26894-127">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)
  
[<span data-ttu-id="26894-128">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="26894-128">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)


[<span data-ttu-id="26894-129">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="26894-129">Event Notification in MAPI</span></span>](event-notification-in-mapi.md)
  
[<span data-ttu-id="26894-130">发送和接收表单通知</span><span class="sxs-lookup"><span data-stu-id="26894-130">Sending and Receiving Form Notifications</span></span>](sending-and-receiving-form-notifications.md)

