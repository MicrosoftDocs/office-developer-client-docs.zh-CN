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
ms.openlocfilehash: da11f15dfe9d269b79f465f01f713de401584962
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430229"
---
# <a name="imapitableunadvise"></a><span data-ttu-id="6451f-103">IMAPITable::Unadvise</span><span class="sxs-lookup"><span data-stu-id="6451f-103">IMAPITable::Unadvise</span></span>

  
  
<span data-ttu-id="6451f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6451f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6451f-105">取消发送以前通过调用 [IMAPITable：：Advise](imapitable-advise.md) 方法设置的通知。</span><span class="sxs-lookup"><span data-stu-id="6451f-105">Cancels the sending of notifications previously set up with a call to the [IMAPITable::Advise](imapitable-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="6451f-106">参数</span><span class="sxs-lookup"><span data-stu-id="6451f-106">Parameters</span></span>

 <span data-ttu-id="6451f-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="6451f-107">_ulConnection_</span></span>
  
> <span data-ttu-id="6451f-108">[in]通过调用 [IMAPITable：：Advise](imapitable-advise.md)返回的注册连接数。</span><span class="sxs-lookup"><span data-stu-id="6451f-108">[in] The number of the registration connection returned by a call to [IMAPITable::Advise](imapitable-advise.md).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6451f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6451f-109">Return value</span></span>

<span data-ttu-id="6451f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6451f-110">S_OK</span></span> 
  
> <span data-ttu-id="6451f-111">调用成功。</span><span class="sxs-lookup"><span data-stu-id="6451f-111">The call succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6451f-112">备注</span><span class="sxs-lookup"><span data-stu-id="6451f-112">Remarks</span></span>

<span data-ttu-id="6451f-113">使用 **IMAPITable：：Unadvise** 方法释放指向上一次调用 **IMAPITable：：Advise** 时传入 _lpAdviseSink_ 参数中的通知接收器对象的指针，从而取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="6451f-113">Use the **IMAPITable::Unadvise** method to release the pointer to the advise sink object passed in the  _lpAdviseSink_ parameter in the previous call to **IMAPITable::Advise**, thereby canceling a notification registration.</span></span> <span data-ttu-id="6451f-114">作为放弃指向建议接收对象的指针的一部分，将调用对象的 **IUnknown：：Release** 方法。</span><span class="sxs-lookup"><span data-stu-id="6451f-114">As part of discarding the pointer to the advise sink object, the object's **IUnknown::Release** method is called.</span></span> <span data-ttu-id="6451f-115">通常 **，Release** 在 **Unadvise** 调用期间调用，但如果另一个线程正在调用建议接收器的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法，则 **Release** 调用将延迟到 **OnNotify** 方法返回。</span><span class="sxs-lookup"><span data-stu-id="6451f-115">Generally, **Release** is called during the **Unadvise** call, but if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
<span data-ttu-id="6451f-116">有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="6451f-116">For more information on the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="6451f-117">有关表通知的特定信息，请参阅关于 [表通知](about-table-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="6451f-117">For specific information about table notification, see [About Table Notifications](about-table-notifications.md).</span></span> <span data-ttu-id="6451f-118">有关使用 **IMAPISupport** 方法支持通知的信息，请参阅 [Supporting Event Notification。](supporting-event-notification.md)</span><span class="sxs-lookup"><span data-stu-id="6451f-118">For information about using the **IMAPISupport** methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6451f-119">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="6451f-119">MFCMAPI reference</span></span>

<span data-ttu-id="6451f-120">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6451f-120">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6451f-121">**文件**</span><span class="sxs-lookup"><span data-stu-id="6451f-121">**File**</span></span>|<span data-ttu-id="6451f-122">**函数**</span><span class="sxs-lookup"><span data-stu-id="6451f-122">**Function**</span></span>|<span data-ttu-id="6451f-123">**备注**</span><span class="sxs-lookup"><span data-stu-id="6451f-123">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6451f-124">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="6451f-124">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="6451f-125">CContentsTableListCtrl：：NotificationOff</span><span class="sxs-lookup"><span data-stu-id="6451f-125">CContentsTableListCtrl::NotificationOff</span></span>  <br/> |<span data-ttu-id="6451f-126">MFCMAPI 使用 **IMAPITable：：Unadvise** 方法取消表的通知。</span><span class="sxs-lookup"><span data-stu-id="6451f-126">MFCMAPI uses the **IMAPITable::Unadvise** method to cancel notifications for the table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6451f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6451f-127">See also</span></span>



[<span data-ttu-id="6451f-128">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="6451f-128">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="6451f-129">IMAPITable::Advise</span><span class="sxs-lookup"><span data-stu-id="6451f-129">IMAPITable::Advise</span></span>](imapitable-advise.md)
  
[<span data-ttu-id="6451f-130">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6451f-130">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="6451f-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6451f-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

