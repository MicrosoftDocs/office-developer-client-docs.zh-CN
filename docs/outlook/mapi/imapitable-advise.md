---
title: IMAPITableAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Advise
api_type:
- COM
ms.assetid: e8b5d21e-dc14-4b61-96b3-a51bcfa0d232
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c9401c163c74ab303ec39c147e0432d1979426b8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418811"
---
# <a name="imapitableadvise"></a><span data-ttu-id="0ee06-103">IMAPITable::Advise</span><span class="sxs-lookup"><span data-stu-id="0ee06-103">IMAPITable::Advise</span></span>

  
  
<span data-ttu-id="0ee06-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0ee06-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0ee06-105">注册通知接收对象以接收影响表的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="0ee06-105">Registers an advise sink object to receive notification of specified events affecting the table.</span></span>
  
```cpp
HRESULT Advise(
ULONG ulEventMask,
LPMAPIADVISESINK lpAdviseSink,
ULONG_PTR FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="0ee06-106">参数</span><span class="sxs-lookup"><span data-stu-id="0ee06-106">Parameters</span></span>

 <span data-ttu-id="0ee06-107">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="0ee06-107">_ulEventMask_</span></span>
  
> <span data-ttu-id="0ee06-108">[in]指示将生成通知的事件类型的值。</span><span class="sxs-lookup"><span data-stu-id="0ee06-108">[in] Value indicating the type of event that will generate the notification.</span></span> <span data-ttu-id="0ee06-109">只有以下值有效：</span><span class="sxs-lookup"><span data-stu-id="0ee06-109">Only the following value is valid:</span></span>
    
 `fnevTableModified`
  
 <span data-ttu-id="0ee06-110">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="0ee06-110">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="0ee06-111">[in]指向接收后续通知的建议接收对象的指针。</span><span class="sxs-lookup"><span data-stu-id="0ee06-111">[in] Pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="0ee06-112">此通知接收器对象必须已分配。</span><span class="sxs-lookup"><span data-stu-id="0ee06-112">This advise sink object must have been already allocated.</span></span>
    
 <span data-ttu-id="0ee06-113">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="0ee06-113">_lpulConnection_</span></span>
  
> <span data-ttu-id="0ee06-114">[out]指向表示成功通知注册的非零值的指针。</span><span class="sxs-lookup"><span data-stu-id="0ee06-114">[out] Pointer to a nonzero value that represents the successful notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0ee06-115">返回值</span><span class="sxs-lookup"><span data-stu-id="0ee06-115">Return value</span></span>

<span data-ttu-id="0ee06-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ee06-116">S_OK</span></span> 
  
> <span data-ttu-id="0ee06-117">通知注册成功完成。</span><span class="sxs-lookup"><span data-stu-id="0ee06-117">The notification registration successfully completed.</span></span>
    
<span data-ttu-id="0ee06-118">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="0ee06-118">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="0ee06-119">表实现要么不支持更改其行和列，要么不支持通知。</span><span class="sxs-lookup"><span data-stu-id="0ee06-119">The table implementation either does not support changes to its rows and columns or does not support notification.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0ee06-120">备注</span><span class="sxs-lookup"><span data-stu-id="0ee06-120">Remarks</span></span>

<span data-ttu-id="0ee06-121">使用 **IMAPITable：：Advise** 方法注册在提供程序中实现的表对象，以用于通知回调。</span><span class="sxs-lookup"><span data-stu-id="0ee06-121">Use the **IMAPITable::Advise** method to register a table object implemented in the provider for notification callbacks.</span></span> <span data-ttu-id="0ee06-122">每当表对象发生变化时，提供程序都会检查在  _ulEventMask_ 参数中设置了哪些事件掩码位，从而查看发生了哪种类型的更改。</span><span class="sxs-lookup"><span data-stu-id="0ee06-122">Whenever a change occurs to the table object, the provider checks to see what event mask bit was set in the  _ulEventMask_ parameter and thus what type of change occurred.</span></span> <span data-ttu-id="0ee06-123">如果设置了位，则提供程序将调用 _由 lpAdviseSink_ 参数指示的建议接收器对象的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法以报告事件。</span><span class="sxs-lookup"><span data-stu-id="0ee06-123">If a bit is set, then the provider calls the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object indicated by the  _lpAdviseSink_ parameter to report the event.</span></span> <span data-ttu-id="0ee06-124">在通知结构中传递给 **OnNotify** 例程的数据描述事件。</span><span class="sxs-lookup"><span data-stu-id="0ee06-124">Data passed in the notification structure to the **OnNotify** routine describes the event.</span></span> 
  
<span data-ttu-id="0ee06-125">调用 **OnNotify** 可以在更改对象的调用期间或以下任何时间发生。</span><span class="sxs-lookup"><span data-stu-id="0ee06-125">The call to **OnNotify** can occur during the call that changes the object, or at any following time.</span></span> <span data-ttu-id="0ee06-126">在支持多个执行线程的系统上，对 **OnNotify** 的调用可以在任何线程上发生。</span><span class="sxs-lookup"><span data-stu-id="0ee06-126">On systems that support multiple threads of execution, the call to **OnNotify** can occur on any thread.</span></span> <span data-ttu-id="0ee06-127">为了能够将可能在不及时发生的 **OnNotify** 调用转换为更安全地处理调用，提供程序应该使用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="0ee06-127">For a way to turn a call to **OnNotify** that might happen at an inopportune time into one that is safer to handle, a provider should use the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> 
  
<span data-ttu-id="0ee06-128">若要提供通知，实现 **Advise** 的提供程序需要保留指向  _lpAdviseSink_ advise 接收器对象的指针的副本;为此，它会调用通知接收器的 **IUnknown：：AddRef** 方法，以维护其对象指针，直到通过调用 [IMAPITable：：Unadvise](imapitable-unadvise.md) 方法取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="0ee06-128">To provide notifications, the provider implementing **Advise** needs to keep a copy of the pointer to the  _lpAdviseSink_ advise sink object; to do so, it calls the **IUnknown::AddRef** method for the advise sink to maintain its object pointer until notification registration is canceled with a call to the [IMAPITable::Unadvise](imapitable-unadvise.md) method.</span></span> <span data-ttu-id="0ee06-129">Advise 实现应为通知注册分配一个连接号码，并在此连接号码上调用 **AddRef，** 然后再在 _lpulConnection_ 参数中返回它。</span><span class="sxs-lookup"><span data-stu-id="0ee06-129">The **Advise** implementation should assign a connection number to the notification registration and call **AddRef** on this connection number before returning it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="0ee06-130">服务提供商可以在取消注册之前释放通知接收器对象，但在调用 \*\* Unadvise \*\* 之前，它们不得释放连接号。</span><span class="sxs-lookup"><span data-stu-id="0ee06-130">Service providers can release the advise sink object before the registration is canceled, but they must not release the connection number until \*\* Unadvise \*\* has been called.</span></span> 
  
<span data-ttu-id="0ee06-131">在成功调用 **Advise** 之后，在调用 \*\* Unadvise \*\* 之前，必须准备客户端以释放通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="0ee06-131">After a call to **Advise** has succeeded and before \*\* Unadvise \*\* has been called, clients must be prepared for the advise sink object to be released.</span></span> <span data-ttu-id="0ee06-132">因此，客户端应在 Advise 返回后释放其 **advise** 接收器对象，除非它具有特定的长期用途。</span><span class="sxs-lookup"><span data-stu-id="0ee06-132">A client should therefore release its advise sink object after **Advise** returns unless it has a specific long-term use for it.</span></span> 
  
<span data-ttu-id="0ee06-133">由于通知的异步行为，更改表列设置的实现可以接收具有按上一列顺序组织的信息的通知。</span><span class="sxs-lookup"><span data-stu-id="0ee06-133">Because of the asynchronous behavior of notification, implementations that change table column settings can receive notifications with information organized in a previous column order.</span></span> <span data-ttu-id="0ee06-134">例如，对于刚刚从容器中删除的邮件，可能会返回一个表行。</span><span class="sxs-lookup"><span data-stu-id="0ee06-134">For instance, a table row might be returned for a message that has just been deleted from the container.</span></span> <span data-ttu-id="0ee06-135">当列设置更改和有关它的信息已发送，但尚未使用该信息更新通知表视图时，将发送此类通知。</span><span class="sxs-lookup"><span data-stu-id="0ee06-135">Such a notification is sent when the column setting change has been made and information about it sent but the notification table view has not been updated with that information yet.</span></span>
  
<span data-ttu-id="0ee06-136">有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="0ee06-136">For more information on the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="0ee06-137">有关表通知的特定信息，请参阅关于 [表通知](about-table-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="0ee06-137">For specific information about table notification, see [About Table Notifications](about-table-notifications.md).</span></span> <span data-ttu-id="0ee06-138">有关使用 **IMAPISupport** 方法支持通知的信息，请参阅 [Supporting Event Notification。](supporting-event-notification.md)</span><span class="sxs-lookup"><span data-stu-id="0ee06-138">For information about using the **IMAPISupport** methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="0ee06-139">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="0ee06-139">MFCMAPI reference</span></span>

<span data-ttu-id="0ee06-140">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="0ee06-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="0ee06-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="0ee06-141">**File**</span></span>|<span data-ttu-id="0ee06-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="0ee06-142">**Function**</span></span>|<span data-ttu-id="0ee06-143">**备注**</span><span class="sxs-lookup"><span data-stu-id="0ee06-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0ee06-144">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="0ee06-144">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="0ee06-145">CContestTableListCtrl：：NotificationOn</span><span class="sxs-lookup"><span data-stu-id="0ee06-145">CContestTableListCtrl::NotificationOn</span></span>  <br/> |<span data-ttu-id="0ee06-146">MFCMAPI 使用 **IMAPITable：：Advise** 方法注册通知，以允许表视图保持最新。</span><span class="sxs-lookup"><span data-stu-id="0ee06-146">MFCMAPI uses the **IMAPITable::Advise** method to register for notifications to allow the table view to stay current.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0ee06-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ee06-147">See also</span></span>



[<span data-ttu-id="0ee06-148">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="0ee06-148">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="0ee06-149">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="0ee06-149">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="0ee06-150">IMAPITable::Unadvise</span><span class="sxs-lookup"><span data-stu-id="0ee06-150">IMAPITable::Unadvise</span></span>](imapitable-unadvise.md)
  
[<span data-ttu-id="0ee06-151">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="0ee06-151">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="0ee06-152">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0ee06-152">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="0ee06-153">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="0ee06-153">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

