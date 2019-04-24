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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328803"
---
# <a name="imapitableunadvise"></a><span data-ttu-id="46e55-103">IMAPITable::Unadvise</span><span class="sxs-lookup"><span data-stu-id="46e55-103">IMAPITable::Unadvise</span></span>

  
  
<span data-ttu-id="46e55-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="46e55-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="46e55-105">取消之前为对[IMAPITable:: Advise](imapitable-advise.md)方法的调用而设置的通知发送。</span><span class="sxs-lookup"><span data-stu-id="46e55-105">Cancels the sending of notifications previously set up with a call to the [IMAPITable::Advise](imapitable-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="46e55-106">参数</span><span class="sxs-lookup"><span data-stu-id="46e55-106">Parameters</span></span>

 <span data-ttu-id="46e55-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="46e55-107">_ulConnection_</span></span>
  
> <span data-ttu-id="46e55-108">实时对[IMAPITable:: Advise](imapitable-advise.md)的调用返回的注册连接数。</span><span class="sxs-lookup"><span data-stu-id="46e55-108">[in] The number of the registration connection returned by a call to [IMAPITable::Advise](imapitable-advise.md).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="46e55-109">返回值</span><span class="sxs-lookup"><span data-stu-id="46e55-109">Return value</span></span>

<span data-ttu-id="46e55-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="46e55-110">S_OK</span></span> 
  
> <span data-ttu-id="46e55-111">调用成功。</span><span class="sxs-lookup"><span data-stu-id="46e55-111">The call succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="46e55-112">注解</span><span class="sxs-lookup"><span data-stu-id="46e55-112">Remarks</span></span>

<span data-ttu-id="46e55-113">使用**imapitable:: Unadvise**方法释放指向在上一次调用**IMAPITable:: advise**的_lpAdviseSink_参数中传递的通知接收器对象的指针, 从而取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="46e55-113">Use the **IMAPITable::Unadvise** method to release the pointer to the advise sink object passed in the  _lpAdviseSink_ parameter in the previous call to **IMAPITable::Advise**, thereby canceling a notification registration.</span></span> <span data-ttu-id="46e55-114">在舍弃指向通知接收器对象的指针的过程中, 将调用对象的**IUnknown:: Release**方法。</span><span class="sxs-lookup"><span data-stu-id="46e55-114">As part of discarding the pointer to the advise sink object, the object's **IUnknown::Release** method is called.</span></span> <span data-ttu-id="46e55-115">通常, **release**在**Unadvise**调用期间调用, 但如果另一个线程正在调用通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 则**释放**调用将延迟到**OnNotify**方法返回。</span><span class="sxs-lookup"><span data-stu-id="46e55-115">Generally, **Release** is called during the **Unadvise** call, but if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
<span data-ttu-id="46e55-116">有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="46e55-116">For more information on the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="46e55-117">有关表通知的具体信息, 请参阅[关于表通知](about-table-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="46e55-117">For specific information about table notification, see [About Table Notifications](about-table-notifications.md).</span></span> <span data-ttu-id="46e55-118">有关使用**IMAPISupport**方法支持通知的信息, 请参阅[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="46e55-118">For information about using the **IMAPISupport** methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="46e55-119">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="46e55-119">MFCMAPI reference</span></span>

<span data-ttu-id="46e55-120">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="46e55-120">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="46e55-121">**文件**</span><span class="sxs-lookup"><span data-stu-id="46e55-121">**File**</span></span>|<span data-ttu-id="46e55-122">**函数**</span><span class="sxs-lookup"><span data-stu-id="46e55-122">**Function**</span></span>|<span data-ttu-id="46e55-123">**备注**</span><span class="sxs-lookup"><span data-stu-id="46e55-123">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46e55-124">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="46e55-124">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="46e55-125">CContentsTableListCtrl:: NotificationOff</span><span class="sxs-lookup"><span data-stu-id="46e55-125">CContentsTableListCtrl::NotificationOff</span></span>  <br/> |<span data-ttu-id="46e55-126">MFCMAPI 使用**IMAPITable:: Unadvise**方法取消对表的通知。</span><span class="sxs-lookup"><span data-stu-id="46e55-126">MFCMAPI uses the **IMAPITable::Unadvise** method to cancel notifications for the table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="46e55-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46e55-127">See also</span></span>



[<span data-ttu-id="46e55-128">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="46e55-128">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="46e55-129">IMAPITable::Advise</span><span class="sxs-lookup"><span data-stu-id="46e55-129">IMAPITable::Advise</span></span>](imapitable-advise.md)
  
[<span data-ttu-id="46e55-130">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="46e55-130">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="46e55-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="46e55-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

