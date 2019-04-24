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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329014"
---
# <a name="imapitableadvise"></a><span data-ttu-id="c6a02-103">IMAPITable::Advise</span><span class="sxs-lookup"><span data-stu-id="c6a02-103">IMAPITable::Advise</span></span>

  
  
<span data-ttu-id="c6a02-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c6a02-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c6a02-105">注册一个建议接收器对象, 以接收影响表的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="c6a02-105">Registers an advise sink object to receive notification of specified events affecting the table.</span></span>
  
```cpp
HRESULT Advise(
ULONG ulEventMask,
LPMAPIADVISESINK lpAdviseSink,
ULONG_PTR FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="c6a02-106">参数</span><span class="sxs-lookup"><span data-stu-id="c6a02-106">Parameters</span></span>

 <span data-ttu-id="c6a02-107">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="c6a02-107">_ulEventMask_</span></span>
  
> <span data-ttu-id="c6a02-108">实时值, 该值指示将生成通知的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="c6a02-108">[in] Value indicating the type of event that will generate the notification.</span></span> <span data-ttu-id="c6a02-109">仅以下值是有效的:</span><span class="sxs-lookup"><span data-stu-id="c6a02-109">Only the following value is valid:</span></span>
    
 `fnevTableModified`
  
 <span data-ttu-id="c6a02-110">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="c6a02-110">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="c6a02-111">实时指向要接收后续通知的通知接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c6a02-111">[in] Pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="c6a02-112">此通知接收器对象必须已分配。</span><span class="sxs-lookup"><span data-stu-id="c6a02-112">This advise sink object must have been already allocated.</span></span>
    
 <span data-ttu-id="c6a02-113">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="c6a02-113">_lpulConnection_</span></span>
  
> <span data-ttu-id="c6a02-114">排除指向表示成功的通知注册的非零值的指针。</span><span class="sxs-lookup"><span data-stu-id="c6a02-114">[out] Pointer to a nonzero value that represents the successful notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c6a02-115">返回值</span><span class="sxs-lookup"><span data-stu-id="c6a02-115">Return value</span></span>

<span data-ttu-id="c6a02-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6a02-116">S_OK</span></span> 
  
> <span data-ttu-id="c6a02-117">通知注册已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c6a02-117">The notification registration successfully completed.</span></span>
    
<span data-ttu-id="c6a02-118">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="c6a02-118">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="c6a02-119">表实现不支持对其行和列进行更改, 也不支持通知。</span><span class="sxs-lookup"><span data-stu-id="c6a02-119">The table implementation either does not support changes to its rows and columns or does not support notification.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c6a02-120">注解</span><span class="sxs-lookup"><span data-stu-id="c6a02-120">Remarks</span></span>

<span data-ttu-id="c6a02-121">使用**IMAPITable:: Advise**方法注册在提供程序中实现的用于通知回调的 table 对象。</span><span class="sxs-lookup"><span data-stu-id="c6a02-121">Use the **IMAPITable::Advise** method to register a table object implemented in the provider for notification callbacks.</span></span> <span data-ttu-id="c6a02-122">每当 table 对象发生更改时, 提供程序都会检查在_ulEventMask_参数中设置的事件掩码位, 从而确定发生的更改类型。</span><span class="sxs-lookup"><span data-stu-id="c6a02-122">Whenever a change occurs to the table object, the provider checks to see what event mask bit was set in the  _ulEventMask_ parameter and thus what type of change occurred.</span></span> <span data-ttu-id="c6a02-123">如果设置了一个位, 则提供程序将调用由_lpAdviseSink_参数指示的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 以报告事件。</span><span class="sxs-lookup"><span data-stu-id="c6a02-123">If a bit is set, then the provider calls the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object indicated by the  _lpAdviseSink_ parameter to report the event.</span></span> <span data-ttu-id="c6a02-124">通知结构中传递给**OnNotify**例程的数据描述了该事件。</span><span class="sxs-lookup"><span data-stu-id="c6a02-124">Data passed in the notification structure to the **OnNotify** routine describes the event.</span></span> 
  
<span data-ttu-id="c6a02-125">调用**OnNotify**可能会在更改对象的调用过程中或在任何时间发生。</span><span class="sxs-lookup"><span data-stu-id="c6a02-125">The call to **OnNotify** can occur during the call that changes the object, or at any following time.</span></span> <span data-ttu-id="c6a02-126">在支持多个执行线程的系统上, 对**OnNotify**的调用可以出现在任何线程上。</span><span class="sxs-lookup"><span data-stu-id="c6a02-126">On systems that support multiple threads of execution, the call to **OnNotify** can occur on any thread.</span></span> <span data-ttu-id="c6a02-127">若要对可能在 inopportune 时发生的**OnNotify**的调用进行更安全地处理的方法, 请参阅[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数。</span><span class="sxs-lookup"><span data-stu-id="c6a02-127">For a way to turn a call to **OnNotify** that might happen at an inopportune time into one that is safer to handle, a provider should use the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> 
  
<span data-ttu-id="c6a02-128">若要提供通知, 提供程序实现**建议**需要将指针副本保存到_lpAdviseSink_建议接收器对象;为此, 它会调用通知接收器的**IUnknown:: AddRef**方法来维护其对象指针, 直到使用对[IMAPITable:: Unadvise](imapitable-unadvise.md)方法的调用取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="c6a02-128">To provide notifications, the provider implementing **Advise** needs to keep a copy of the pointer to the  _lpAdviseSink_ advise sink object; to do so, it calls the **IUnknown::AddRef** method for the advise sink to maintain its object pointer until notification registration is canceled with a call to the [IMAPITable::Unadvise](imapitable-unadvise.md) method.</span></span> <span data-ttu-id="c6a02-129">**建议**实现应为通知注册分配一个连接号码, 并在此连接号码上调用**AddRef** , 然后再将其返回到_lpulConnection_参数中。</span><span class="sxs-lookup"><span data-stu-id="c6a02-129">The **Advise** implementation should assign a connection number to the notification registration and call **AddRef** on this connection number before returning it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="c6a02-130">服务提供程序可以在取消注册之前释放通知接收器对象, 但在调用 \* \* Unadvise \* \* 之前, 它们不能释放连接号码。</span><span class="sxs-lookup"><span data-stu-id="c6a02-130">Service providers can release the advise sink object before the registration is canceled, but they must not release the connection number until \*\* Unadvise \*\* has been called.</span></span> 
  
<span data-ttu-id="c6a02-131">在调用了 "**建议**已成功" 且在 "\* \* Unadvise \* \*" 之前调用之后, 客户端必须准备就绪, 才能释放通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="c6a02-131">After a call to **Advise** has succeeded and before \*\* Unadvise \*\* has been called, clients must be prepared for the advise sink object to be released.</span></span> <span data-ttu-id="c6a02-132">因此, 客户端应在**建议**返回后释放其建议接收器对象, 除非它对其具有特定的长期使用。</span><span class="sxs-lookup"><span data-stu-id="c6a02-132">A client should therefore release its advise sink object after **Advise** returns unless it has a specific long-term use for it.</span></span> 
  
<span data-ttu-id="c6a02-133">由于通知的异步行为, 因此更改表列设置的实现可以接收按上一列顺序组织的信息的通知。</span><span class="sxs-lookup"><span data-stu-id="c6a02-133">Because of the asynchronous behavior of notification, implementations that change table column settings can receive notifications with information organized in a previous column order.</span></span> <span data-ttu-id="c6a02-134">例如, 对于刚刚从容器中删除的邮件, 可能会返回一个表行。</span><span class="sxs-lookup"><span data-stu-id="c6a02-134">For instance, a table row might be returned for a message that has just been deleted from the container.</span></span> <span data-ttu-id="c6a02-135">当列设置发生更改时, 将发送此类通知, 并在通知表视图尚未使用该信息更新的情况中对其发送信息。</span><span class="sxs-lookup"><span data-stu-id="c6a02-135">Such a notification is sent when the column setting change has been made and information about it sent but the notification table view has not been updated with that information yet.</span></span>
  
<span data-ttu-id="c6a02-136">有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a02-136">For more information on the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> <span data-ttu-id="c6a02-137">有关表通知的具体信息, 请参阅[关于表通知](about-table-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a02-137">For specific information about table notification, see [About Table Notifications](about-table-notifications.md).</span></span> <span data-ttu-id="c6a02-138">有关使用**IMAPISupport**方法支持通知的信息, 请参阅[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a02-138">For information about using the **IMAPISupport** methods to support notification, see [Supporting Event Notification](supporting-event-notification.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c6a02-139">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c6a02-139">MFCMAPI reference</span></span>

<span data-ttu-id="c6a02-140">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c6a02-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c6a02-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="c6a02-141">**File**</span></span>|<span data-ttu-id="c6a02-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="c6a02-142">**Function**</span></span>|<span data-ttu-id="c6a02-143">**备注**</span><span class="sxs-lookup"><span data-stu-id="c6a02-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6a02-144">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="c6a02-144">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="c6a02-145">CContestTableListCtrl:: NotificationOn</span><span class="sxs-lookup"><span data-stu-id="c6a02-145">CContestTableListCtrl::NotificationOn</span></span>  <br/> |<span data-ttu-id="c6a02-146">MFCMAPI 使用**IMAPITable:: Advise**方法注册通知, 以允许表视图保持最新。</span><span class="sxs-lookup"><span data-stu-id="c6a02-146">MFCMAPI uses the **IMAPITable::Advise** method to register for notifications to allow the table view to stay current.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c6a02-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a02-147">See also</span></span>



[<span data-ttu-id="c6a02-148">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="c6a02-148">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="c6a02-149">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="c6a02-149">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="c6a02-150">IMAPITable::Unadvise</span><span class="sxs-lookup"><span data-stu-id="c6a02-150">IMAPITable::Unadvise</span></span>](imapitable-unadvise.md)
  
[<span data-ttu-id="c6a02-151">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c6a02-151">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="c6a02-152">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c6a02-152">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="c6a02-153">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c6a02-153">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

