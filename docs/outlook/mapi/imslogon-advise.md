---
title: IMSLogonAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.Advise
api_type:
- COM
ms.assetid: a3c5d937-642b-463b-b5a0-5d099e651895
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: abe4867b965f05e781f931d2e72920474d007d78
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317309"
---
# <a name="imslogonadvise"></a><span data-ttu-id="e0aef-103">IMSLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="e0aef-103">IMSLogon::Advise</span></span>

  
  
<span data-ttu-id="e0aef-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e0aef-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e0aef-105">向邮件存储提供程序注册对象, 以获取有关邮件存储区中的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="e0aef-105">Registers an object with a message store provider for notifications about changes in the message store.</span></span> <span data-ttu-id="e0aef-106">然后, 邮件存储将发送有关已注册对象的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="e0aef-106">The message store will then send notifications about changes to the registered object.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="e0aef-107">参数</span><span class="sxs-lookup"><span data-stu-id="e0aef-107">Parameters</span></span>

 <span data-ttu-id="e0aef-108">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="e0aef-108">_cbEntryID_</span></span>
  
> <span data-ttu-id="e0aef-109">实时由_lpEntryID_参数指向的条目标识符的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="e0aef-109">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="e0aef-110">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="e0aef-110">_lpEntryID_</span></span>
  
> <span data-ttu-id="e0aef-111">实时一个指针, 指向有关应生成其通知的对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e0aef-111">[in] A pointer to the entry identifier of the object about which notifications should be generated.</span></span> <span data-ttu-id="e0aef-112">该对象可以是文件夹、邮件或邮件存储区中的任何其他对象。</span><span class="sxs-lookup"><span data-stu-id="e0aef-112">This object can be a folder, a message, or any other object in the message store.</span></span> <span data-ttu-id="e0aef-113">或者, 如果 MAPI 将_cbEntryID_参数设置为0并为_lpEntryID_传递**null** , 则建议接收器提供有关对整个邮件存储区所做更改的通知。</span><span class="sxs-lookup"><span data-stu-id="e0aef-113">Alternatively, if MAPI sets the  _cbEntryID_ parameter to 0 and passes **null** for  _lpEntryID_, the advise sink provides notifications about changes to the entire message store.</span></span>
    
 <span data-ttu-id="e0aef-114">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="e0aef-114">_ulEventMask_</span></span>
  
> <span data-ttu-id="e0aef-115">实时关于 MAPI 将生成通知的对象发生的通知事件类型的事件掩码。</span><span class="sxs-lookup"><span data-stu-id="e0aef-115">[in] An event mask of the types of notification events occurring for the object about which MAPI will generate notifications.</span></span> <span data-ttu-id="e0aef-116">掩码筛选特定事例。</span><span class="sxs-lookup"><span data-stu-id="e0aef-116">The mask filters specific cases.</span></span> <span data-ttu-id="e0aef-117">每个事件类型都有一个与之相关联的结构, 其中包含有关事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e0aef-117">Each event type has a structure associated with it that contains additional information about the event.</span></span> <span data-ttu-id="e0aef-118">下表列出了可能的事件类型及其对应的结构。</span><span class="sxs-lookup"><span data-stu-id="e0aef-118">The following table lists the possible event types along with their corresponding structures.</span></span>
    
|<span data-ttu-id="e0aef-119">**通知事件类型**</span><span class="sxs-lookup"><span data-stu-id="e0aef-119">**Notification event type**</span></span>|<span data-ttu-id="e0aef-120">**对应的结构**</span><span class="sxs-lookup"><span data-stu-id="e0aef-120">**Corresponding structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e0aef-121">fnevCriticalError</span><span class="sxs-lookup"><span data-stu-id="e0aef-121">fnevCriticalError</span></span>  <br/> |[<span data-ttu-id="e0aef-122">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-122">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="e0aef-123">fnevNewMail</span><span class="sxs-lookup"><span data-stu-id="e0aef-123">fnevNewMail</span></span>  <br/> |[<span data-ttu-id="e0aef-124">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-124">NEWMAIL_NOTIFICATION</span></span>](newmail_notification.md) <br/> |
|<span data-ttu-id="e0aef-125">fnevObjectCreated</span><span class="sxs-lookup"><span data-stu-id="e0aef-125">fnevObjectCreated</span></span>  <br/> |[<span data-ttu-id="e0aef-126">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-126">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e0aef-127">fnevObjectDeleted</span><span class="sxs-lookup"><span data-stu-id="e0aef-127">fnevObjectDeleted</span></span>  <br/> |[<span data-ttu-id="e0aef-128">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-128">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e0aef-129">fnevObjectModified</span><span class="sxs-lookup"><span data-stu-id="e0aef-129">fnevObjectModified</span></span>  <br/> |[<span data-ttu-id="e0aef-130">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-130">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e0aef-131">fnevObjectCopied</span><span class="sxs-lookup"><span data-stu-id="e0aef-131">fnevObjectCopied</span></span>  <br/> |[<span data-ttu-id="e0aef-132">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-132">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e0aef-133">fnevObjectMoved</span><span class="sxs-lookup"><span data-stu-id="e0aef-133">fnevObjectMoved</span></span>  <br/> |[<span data-ttu-id="e0aef-134">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-134">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e0aef-135">fnevSearchComplete</span><span class="sxs-lookup"><span data-stu-id="e0aef-135">fnevSearchComplete</span></span>  <br/> |[<span data-ttu-id="e0aef-136">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-136">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="e0aef-137">fnevStatusObjectModified</span><span class="sxs-lookup"><span data-stu-id="e0aef-137">fnevStatusObjectModified</span></span>  <br/> |[<span data-ttu-id="e0aef-138">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-138">STATUS_OBJECT_NOTIFICATION</span></span>](status_object_notification.md) <br/> |
   
 <span data-ttu-id="e0aef-139">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="e0aef-139">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="e0aef-140">实时一个指针, 指向有关已请求其通知的 session 对象发生事件时要调用的通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="e0aef-140">[in] A pointer to an advise sink object to be called when an event occurs for the session object about which notification has been requested.</span></span> <span data-ttu-id="e0aef-141">此建议接收器对象必须已经存在。</span><span class="sxs-lookup"><span data-stu-id="e0aef-141">This advise sink object must already exist.</span></span>
    
 <span data-ttu-id="e0aef-142">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="e0aef-142">_lpulConnection_</span></span>
  
> <span data-ttu-id="e0aef-143">排除一个指向成功返回的变量的指针, 其中包含通知注册的连接号。</span><span class="sxs-lookup"><span data-stu-id="e0aef-143">[out] A pointer to a variable that upon a successful return holds the connection number for the notification registration.</span></span> <span data-ttu-id="e0aef-144">连接号码必须为非零值。</span><span class="sxs-lookup"><span data-stu-id="e0aef-144">The connection number must be nonzero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e0aef-145">返回值</span><span class="sxs-lookup"><span data-stu-id="e0aef-145">Return value</span></span>

<span data-ttu-id="e0aef-146">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0aef-146">S_OK</span></span> 
  
> <span data-ttu-id="e0aef-147">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="e0aef-147">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="e0aef-148">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="e0aef-148">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="e0aef-149">MAPI 或一个或多个服务提供商不支持该操作。</span><span class="sxs-lookup"><span data-stu-id="e0aef-149">The operation is not supported by MAPI or by one or more service providers.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e0aef-150">注解</span><span class="sxs-lookup"><span data-stu-id="e0aef-150">Remarks</span></span>

<span data-ttu-id="e0aef-151">邮件存储提供程序实现**IMSLogon:: Advise**方法, 以注册用于通知回调的对象。</span><span class="sxs-lookup"><span data-stu-id="e0aef-151">Message store providers implement the **IMSLogon::Advise** method to register an object for notification callbacks.</span></span> <span data-ttu-id="e0aef-152">每当指定的对象发生更改时, 提供程序都会检查在_ulEventMask_参数中设置了什么事件掩码位, 因此会发生更改的类型。</span><span class="sxs-lookup"><span data-stu-id="e0aef-152">Whenever a change occurs to the indicated object, the provider checks to see what event mask bit was set in the  _ulEventMask_ parameter and, therefore, what type of change occurred.</span></span> <span data-ttu-id="e0aef-153">如果设置了一个位, 则提供程序将调用由_lpAdviseSink_参数指示的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 以报告事件。</span><span class="sxs-lookup"><span data-stu-id="e0aef-153">If a bit is set, the provider calls the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object indicated by the  _lpAdviseSink_ parameter to report the event.</span></span> <span data-ttu-id="e0aef-154">通知结构中传递给**OnNotify**例程的数据描述了该事件。</span><span class="sxs-lookup"><span data-stu-id="e0aef-154">Data passed in the notification structure to the **OnNotify** routine describes the event.</span></span> 
  
<span data-ttu-id="e0aef-155">对**OnNotify**的调用可以在更改对象的调用过程中发生, 也可以在以后的任何时间进行。</span><span class="sxs-lookup"><span data-stu-id="e0aef-155">The call to **OnNotify** can occur during the call that changes the object, or at any later time.</span></span> <span data-ttu-id="e0aef-156">在支持多个执行线程的系统上, 对**OnNotify**的调用可以出现在任何线程上。</span><span class="sxs-lookup"><span data-stu-id="e0aef-156">On systems that support multiple threads of execution, the call to **OnNotify** can occur on any thread.</span></span> <span data-ttu-id="e0aef-157">若要安全地处理对可能在 inopportune 时可能发生的**OnNotify**的调用, 客户端应用程序应使用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数。</span><span class="sxs-lookup"><span data-stu-id="e0aef-157">To safely handle a call to **OnNotify** that might happen at an inopportune time, a client application should use the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function.</span></span> 
  
<span data-ttu-id="e0aef-158">若要提供通知, 实现**建议**的邮件存储提供程序需要将指针的副本保存到_lpAdviseSink_建议接收器对象;为执行此操作, 提供程序调用了通知接收器的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来维护其对象指针, 直到通过调用[IMSLogon:: Unadvise](imslogon-unadvise.md)方法取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="e0aef-158">To provide notifications, the message store provider that implements **Advise** needs to keep a copy of the pointer to the  _lpAdviseSink_ advise sink object; to do so, the provider calls the [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method for the advise sink to maintain its object pointer until notification registration is canceled with a call to the [IMSLogon::Unadvise](imslogon-unadvise.md) method.</span></span> <span data-ttu-id="e0aef-159">**建议**实现应为通知注册分配一个连接号码, 并在此连接号码上调用**AddRef** , 然后再将其返回到_lpulConnection_参数中。</span><span class="sxs-lookup"><span data-stu-id="e0aef-159">The **Advise** implementation should assign a connection number to the notification registration and call **AddRef** on this connection number before returning it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="e0aef-160">服务提供程序可以在取消注册之前释放通知接收器对象, 但在调用**Unadvise**之前, 服务提供程序不能释放连接号码。</span><span class="sxs-lookup"><span data-stu-id="e0aef-160">Service providers can release the advise sink object before the registration is canceled, but they must not release the connection number until **Unadvise** has been called.</span></span> 
  
<span data-ttu-id="e0aef-161">在对**建议**的调用成功之后和**Unadvise**调用之前, 必须为通知接收器对象准备好提供程序来释放通知。</span><span class="sxs-lookup"><span data-stu-id="e0aef-161">After a call to **Advise** has succeeded and before **Unadvise** has been called, providers must be prepared for the advise sink object to be released.</span></span> <span data-ttu-id="e0aef-162">因此, 提供程序应在**建议**返回后释放其建议接收器对象, 除非它对其具有特定的长期使用。</span><span class="sxs-lookup"><span data-stu-id="e0aef-162">Therefore, a provider should release its advise sink object after **Advise** returns, unless it has a specific long-term use for it.</span></span> 
  
<span data-ttu-id="e0aef-163">有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="e0aef-163">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e0aef-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0aef-164">See also</span></span>



[<span data-ttu-id="e0aef-165">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="e0aef-165">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="e0aef-166">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="e0aef-166">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="e0aef-167">IMSLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="e0aef-167">IMSLogon::Unadvise</span></span>](imslogon-unadvise.md)
  
[<span data-ttu-id="e0aef-168">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e0aef-168">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="e0aef-169">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e0aef-169">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

