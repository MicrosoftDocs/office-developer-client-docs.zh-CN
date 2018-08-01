---
title: IMAPITableUnadvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Unadvise
api_type:
- COM
ms.assetid: 19f0dad9-9704-4bbe-a689-9531e7198351
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e9d8565cfaa17764e92bddafb29e744d23872515
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775737"
---
# <a name="imapitableunadvise"></a><span data-ttu-id="c6d90-103">IMAPITable::Unadvise</span><span class="sxs-lookup"><span data-stu-id="c6d90-103">IMAPITable::Unadvise</span></span>

  
  
<span data-ttu-id="c6d90-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c6d90-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c6d90-105">取消发送通知之前设置与对[IMAPITable::Advise](imapitable-advise.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="c6d90-105">Cancels the sending of notifications previously set up with a call to the [IMAPITable::Advise](imapitable-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="c6d90-106">参数</span><span class="sxs-lookup"><span data-stu-id="c6d90-106">Parameters</span></span>

 <span data-ttu-id="c6d90-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="c6d90-107">_ulConnection_</span></span>
  
> <span data-ttu-id="c6d90-108">[in]通过调用[IMAPITable::Advise](imapitable-advise.md)返回注册连接数。</span><span class="sxs-lookup"><span data-stu-id="c6d90-108">[in] The number of the registration connection returned by a call to [IMAPITable::Advise](imapitable-advise.md).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c6d90-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c6d90-109">Return value</span></span>

<span data-ttu-id="c6d90-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6d90-110">S_OK</span></span> 
  
> <span data-ttu-id="c6d90-111">调用成功。</span><span class="sxs-lookup"><span data-stu-id="c6d90-111">The call succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c6d90-112">说明</span><span class="sxs-lookup"><span data-stu-id="c6d90-112">Remarks</span></span>

<span data-ttu-id="c6d90-113">使用**IMAPITable::Unadvise**方法释放中**IMAPITable::Advise**，从而取消通知注册到以前的呼叫在_lpAdviseSink_参数中传递 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c6d90-113">Use the **IMAPITable::Unadvise** method to release the pointer to the advise sink object passed in the  _lpAdviseSink_ parameter in the previous call to **IMAPITable::Advise**, thereby canceling a notification registration.</span></span> <span data-ttu-id="c6d90-114">作为放弃 advise 接收器对象的指针的一部分，调用对象的**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="c6d90-114">As part of discarding the pointer to the advise sink object, the object's **IUnknown::Release** method is called.</span></span> <span data-ttu-id="c6d90-115">通常，调用**Release** **Unadvise**呼叫期间，但另一个线程如果正在为通知接收器，调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法**释放**调用推迟到**OnNotify**方法返回。</span><span class="sxs-lookup"><span data-stu-id="c6d90-115">Generally, **Release** is called during the **Unadvise** call, but if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
<span data-ttu-id="c6d90-116">通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="c6d90-116">For more information on the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="c6d90-117">有关表通知的特定信息，请参阅[有关表通知](about-table-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="c6d90-117">For specific information about table notification, see [About Table Notifications](about-table-notifications.md).</span></span> <span data-ttu-id="c6d90-118">有关使用**IMAPISupport**方法以支持通知的信息，请参阅[支持的事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="c6d90-118">For information about using the **IMAPISupport** methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c6d90-119">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="c6d90-119">MFCMAPI reference</span></span>

<span data-ttu-id="c6d90-120">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c6d90-120">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c6d90-121">**文件**</span><span class="sxs-lookup"><span data-stu-id="c6d90-121">**File**</span></span>|<span data-ttu-id="c6d90-122">**函数**</span><span class="sxs-lookup"><span data-stu-id="c6d90-122">**Function**</span></span>|<span data-ttu-id="c6d90-123">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c6d90-123">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6d90-124">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="c6d90-124">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="c6d90-125">CContentsTableListCtrl::NotificationOff</span><span class="sxs-lookup"><span data-stu-id="c6d90-125">CContentsTableListCtrl::NotificationOff</span></span>  <br/> |<span data-ttu-id="c6d90-126">MFCMAPI 使用**IMAPITable::Unadvise**方法取消表的通知。</span><span class="sxs-lookup"><span data-stu-id="c6d90-126">MFCMAPI uses the **IMAPITable::Unadvise** method to cancel notifications for the table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c6d90-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6d90-127">See also</span></span>



[<span data-ttu-id="c6d90-128">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="c6d90-128">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="c6d90-129">IMAPITable::Advise</span><span class="sxs-lookup"><span data-stu-id="c6d90-129">IMAPITable::Advise</span></span>](imapitable-advise.md)
  
[<span data-ttu-id="c6d90-130">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c6d90-130">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="c6d90-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c6d90-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

