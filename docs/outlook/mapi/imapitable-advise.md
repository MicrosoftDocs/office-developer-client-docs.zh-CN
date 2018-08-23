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
ms.openlocfilehash: cd6b119bd88fccf80bf2488592a24b3398e6e8af
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594241"
---
# <a name="imapitableadvise"></a><span data-ttu-id="1ce9e-103">IMAPITable::Advise</span><span class="sxs-lookup"><span data-stu-id="1ce9e-103">IMAPITable::Advise</span></span>

  
  
<span data-ttu-id="1ce9e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ce9e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1ce9e-105">注册接收通知的影响表指定事件的 advise 接收器对象。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-105">Registers an advise sink object to receive notification of specified events affecting the table.</span></span>
  
```cpp
HRESULT Advise(
ULONG ulEventMask,
LPMAPIADVISESINK lpAdviseSink,
ULONG_PTR FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="1ce9e-106">参数</span><span class="sxs-lookup"><span data-stu-id="1ce9e-106">Parameters</span></span>

 <span data-ttu-id="1ce9e-107">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="1ce9e-107">_ulEventMask_</span></span>
  
> <span data-ttu-id="1ce9e-108">[in]指示将生成通知的事件类型的值。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-108">[in] Value indicating the type of event that will generate the notification.</span></span> <span data-ttu-id="1ce9e-109">下面的值是有效的：</span><span class="sxs-lookup"><span data-stu-id="1ce9e-109">Only the following value is valid:</span></span>
    
 `fnevTableModified`
  
 <span data-ttu-id="1ce9e-110">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="1ce9e-110">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="1ce9e-111">[in]指向 advise 接收器对象接收随后进行通知的指针。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-111">[in] Pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="1ce9e-112">此 advise 接收器对象必须已分配。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-112">This advise sink object must have been already allocated.</span></span>
    
 <span data-ttu-id="1ce9e-113">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="1ce9e-113">_lpulConnection_</span></span>
  
> <span data-ttu-id="1ce9e-114">[输出]为非零值，该值代表成功通知注册的指针。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-114">[out] Pointer to a nonzero value that represents the successful notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1ce9e-115">返回值</span><span class="sxs-lookup"><span data-stu-id="1ce9e-115">Return value</span></span>

<span data-ttu-id="1ce9e-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ce9e-116">S_OK</span></span> 
  
> <span data-ttu-id="1ce9e-117">成功完成通知注册。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-117">The notification registration successfully completed.</span></span>
    
<span data-ttu-id="1ce9e-118">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="1ce9e-118">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="1ce9e-119">表实现不支持为其行和列的更改，或不支持通知。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-119">The table implementation either does not support changes to its rows and columns or does not support notification.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1ce9e-120">注解</span><span class="sxs-lookup"><span data-stu-id="1ce9e-120">Remarks</span></span>

<span data-ttu-id="1ce9e-121">使用**IMAPITable::Advise**方法注册的提供程序通知回调中实现一个 table 对象。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-121">Use the **IMAPITable::Advise** method to register a table object implemented in the provider for notification callbacks.</span></span> <span data-ttu-id="1ce9e-122">当对 table 对象发生了更改时，提供程序将检查以了解哪些事件掩码位_ulEventMask_参数中的设置，因此发生更改的类型。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-122">Whenever a change occurs to the table object, the provider checks to see what event mask bit was set in the  _ulEventMask_ parameter and thus what type of change occurred.</span></span> <span data-ttu-id="1ce9e-123">如果位设置，然后提供程序调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法所指示的报告，事件将_lpAdviseSink_参数 advise 接收器对象。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-123">If a bit is set, then the provider calls the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object indicated by the  _lpAdviseSink_ parameter to report the event.</span></span> <span data-ttu-id="1ce9e-124">数据传递给**OnNotify**例程通知结构中介绍的事件。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-124">Data passed in the notification structure to the **OnNotify** routine describes the event.</span></span> 
  
<span data-ttu-id="1ce9e-125">更改该对象，该调用期间或任何以下时，可能会发生**OnNotify**调用。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-125">The call to **OnNotify** can occur during the call that changes the object, or at any following time.</span></span> <span data-ttu-id="1ce9e-126">支持多个线程的执行系统，在调用**OnNotify**可以发生任何线程上。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-126">On systems that support multiple threads of execution, the call to **OnNotify** can occur on any thread.</span></span> <span data-ttu-id="1ce9e-127">若要打开到一个处理更安全的时机在可能发生的**OnNotify**调用一种方法，为提供程序应使用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-127">For a way to turn a call to **OnNotify** that might happen at an inopportune time into one that is safer to handle, a provider should use the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> 
  
<span data-ttu-id="1ce9e-128">若要提供通知，提供程序实施**Advise**需要保留一份指针到_lpAdviseSink_告知接收器对象;为此，请调用通知接收器来维护其对象的指针，直到[IMAPITable::Unadvise](imapitable-unadvise.md)方法的调用被取消通知注册的**IUnknown::AddRef**方法。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-128">To provide notifications, the provider implementing **Advise** needs to keep a copy of the pointer to the  _lpAdviseSink_ advise sink object; to do so, it calls the **IUnknown::AddRef** method for the advise sink to maintain its object pointer until notification registration is canceled with a call to the [IMAPITable::Unadvise](imapitable-unadvise.md) method.</span></span> <span data-ttu-id="1ce9e-129">**Advise**实现应分配的通知注册的连接数并返回_lpulConnection_参数中之前调用此连接号码**AddRef** 。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-129">The **Advise** implementation should assign a connection number to the notification registration and call **AddRef** on this connection number before returning it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="1ce9e-130">服务提供商可以释放 advise 接收器对象之前取消注册，但他们必须释放直到连接数 * * Unadvise * * 已被调用。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-130">Service providers can release the advise sink object before the registration is canceled, but they must not release the connection number until ** Unadvise ** has been called.</span></span> 
  
<span data-ttu-id="1ce9e-131">调用**Advise**已成功完成之后，并在 * * Unadvise * * 已调用，客户端必须先为准备 advise 接收器对象，必须释放。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-131">After a call to **Advise** has succeeded and before ** Unadvise ** has been called, clients must be prepared for the advise sink object to be released.</span></span> <span data-ttu-id="1ce9e-132">**Advise**返回，除非它为其具有特定的长期使用后，客户端应因此释放其 advise 接收器对象。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-132">A client should therefore release its advise sink object after **Advise** returns unless it has a specific long-term use for it.</span></span> 
  
<span data-ttu-id="1ce9e-133">通知的异步行为，由于更改表列设置的实现可以接收通知与上一列顺序组织的信息。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-133">Because of the asynchronous behavior of notification, implementations that change table column settings can receive notifications with information organized in a previous column order.</span></span> <span data-ttu-id="1ce9e-134">例如，可能只需已从容器中删除一条消息的返回表格行。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-134">For instance, a table row might be returned for a message that has just been deleted from the container.</span></span> <span data-ttu-id="1ce9e-135">此类将通知发送时所做更改列设置和发送有关该产品的信息但尚未该信息尚未更新通知表视图。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-135">Such a notification is sent when the column setting change has been made and information about it sent but the notification table view has not been updated with that information yet.</span></span>
  
<span data-ttu-id="1ce9e-136">通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-136">For more information on the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="1ce9e-137">有关表通知的特定信息，请参阅[有关表通知](about-table-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-137">For specific information about table notification, see [About Table Notifications](about-table-notifications.md).</span></span> <span data-ttu-id="1ce9e-138">有关使用**IMAPISupport**方法以支持通知的信息，请参阅[支持的事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-138">For information about using the **IMAPISupport** methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1ce9e-139">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1ce9e-139">MFCMAPI reference</span></span>

<span data-ttu-id="1ce9e-140">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1ce9e-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="1ce9e-141">**File**</span></span>|<span data-ttu-id="1ce9e-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="1ce9e-142">**Function**</span></span>|<span data-ttu-id="1ce9e-143">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1ce9e-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ce9e-144">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="1ce9e-144">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="1ce9e-145">CContestTableListCtrl::NotificationOn</span><span class="sxs-lookup"><span data-stu-id="1ce9e-145">CContestTableListCtrl::NotificationOn</span></span>  <br/> |<span data-ttu-id="1ce9e-146">MFCMAPI 使用**IMAPITable::Advise**方法注册通知，以允许保持当前表视图。</span><span class="sxs-lookup"><span data-stu-id="1ce9e-146">MFCMAPI uses the **IMAPITable::Advise** method to register for notifications to allow the table view to stay current.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1ce9e-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ce9e-147">See also</span></span>



[<span data-ttu-id="1ce9e-148">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="1ce9e-148">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="1ce9e-149">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="1ce9e-149">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="1ce9e-150">IMAPITable::Unadvise</span><span class="sxs-lookup"><span data-stu-id="1ce9e-150">IMAPITable::Unadvise</span></span>](imapitable-unadvise.md)
  
[<span data-ttu-id="1ce9e-151">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="1ce9e-151">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="1ce9e-152">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1ce9e-152">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="1ce9e-153">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1ce9e-153">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

