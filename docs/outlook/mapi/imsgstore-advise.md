---
title: IMsgStoreAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.Advise
api_type:
- COM
ms.assetid: 8c57e743-a798-4e39-a61a-46dff8b1ac7c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b4abef731541e308b2c2ebc6f4aaddf4458e257
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317323"
---
# <a name="imsgstoreadvise"></a><span data-ttu-id="8cf11-103">IMsgStore::Advise</span><span class="sxs-lookup"><span data-stu-id="8cf11-103">IMsgStore::Advise</span></span>

  
  
<span data-ttu-id="8cf11-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8cf11-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8cf11-105">注册以接收对邮件存储区产生影响的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-105">Registers to receive notification of specified events that affect the message store.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="8cf11-106">参数</span><span class="sxs-lookup"><span data-stu-id="8cf11-106">Parameters</span></span>

 <span data-ttu-id="8cf11-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="8cf11-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="8cf11-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="8cf11-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="8cf11-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="8cf11-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="8cf11-110">实时一个指针, 指向有关应生成其通知的文件夹或消息的条目标识符, 或**为 null**。</span><span class="sxs-lookup"><span data-stu-id="8cf11-110">[in] A pointer to the entry identifier of the folder or message about which notifications should be generated, or **null**.</span></span> <span data-ttu-id="8cf11-111">如果将_lpEntryID_设置为 NULL,**建议**在整个邮件存储区上注册通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-111">If  _lpEntryID_ is set to NULL, **Advise** registers for notifications on the entire message store.</span></span> 
    
 <span data-ttu-id="8cf11-112">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="8cf11-112">_ulEventMask_</span></span>
  
> <span data-ttu-id="8cf11-113">实时指示呼叫者感兴趣且应包含在注册中的通知事件类型的值掩码。</span><span class="sxs-lookup"><span data-stu-id="8cf11-113">[in] A mask of values that indicate the types of notification events that the caller is interested in and should be included in the registration.</span></span> <span data-ttu-id="8cf11-114">有与每种类型的事件相关联的相应[通知](notification.md)结构, 其中包含有关该事件的信息。</span><span class="sxs-lookup"><span data-stu-id="8cf11-114">There is a corresponding [NOTIFICATION](notification.md) structure associated with each type of event that holds information about the event.</span></span> <span data-ttu-id="8cf11-115">以下是_ulEventMask_参数的有效值:</span><span class="sxs-lookup"><span data-stu-id="8cf11-115">The following are valid values for the  _ulEventMask_ parameter:</span></span> 
    
 <span data-ttu-id="8cf11-116">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="8cf11-116">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="8cf11-117">注册有关严重错误 (如内存不足) 的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-117">Registers for notifications about severe errors, such as insufficient memory.</span></span>
    
 <span data-ttu-id="8cf11-118">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="8cf11-118">_fnevExtended_</span></span>
  
> <span data-ttu-id="8cf11-119">注册有关特定邮件存储提供程序特定的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-119">Registers for notifications about events specific to the particular message store provider.</span></span>
    
 <span data-ttu-id="8cf11-120">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="8cf11-120">_fnevNewMail_</span></span>
  
> <span data-ttu-id="8cf11-121">注册有关新邮件到达的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-121">Registers for notifications about the arrival of new messages.</span></span> 
    
 <span data-ttu-id="8cf11-122">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="8cf11-122">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="8cf11-123">注册有关创建新文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-123">Registers for notifications about the creation of a new folder or message.</span></span>
    
 <span data-ttu-id="8cf11-124">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="8cf11-124">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="8cf11-125">注册有关要复制的文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-125">Registers for notifications about a folder or message being copied.</span></span>
    
 <span data-ttu-id="8cf11-126">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="8cf11-126">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="8cf11-127">注册有关要删除的文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-127">Registers for notifications about a folder or message being deleted.</span></span>
    
 <span data-ttu-id="8cf11-128">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="8cf11-128">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="8cf11-129">注册有关要修改的文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-129">Registers for notifications about a folder or message being modified.</span></span>
    
 <span data-ttu-id="8cf11-130">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="8cf11-130">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="8cf11-131">注册有关要移动的文件夹或邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-131">Registers for notifications about a folder or message being moved.</span></span>
    
 <span data-ttu-id="8cf11-132">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="8cf11-132">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="8cf11-133">注册有关搜索操作完成的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-133">Registers for notifications about the completion of a search operation.</span></span>
    
 <span data-ttu-id="8cf11-134">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="8cf11-134">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="8cf11-135">实时指向接收后续通知的通知接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8cf11-135">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="8cf11-136">此通知接收器对象必须已分配。</span><span class="sxs-lookup"><span data-stu-id="8cf11-136">This advise sink object must have already been allocated.</span></span>
    
 <span data-ttu-id="8cf11-137">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="8cf11-137">_lpulConnection_</span></span>
  
> <span data-ttu-id="8cf11-138">排除一个指向非零数字的指针, 该数字表示呼叫者的通知接收器对象和会话之间的连接。</span><span class="sxs-lookup"><span data-stu-id="8cf11-138">[out] A pointer to a nonzero number that represents the connection between the caller's advise sink object and the session.</span></span> 
    
 <span data-ttu-id="8cf11-139">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="8cf11-139">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="8cf11-140">实时指向接收后续通知的通知接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8cf11-140">[in] A pointer to an advise sink object to receive the subsequent notifications.</span></span> <span data-ttu-id="8cf11-141">此通知接收器对象必须已分配。</span><span class="sxs-lookup"><span data-stu-id="8cf11-141">This advise sink object must have already been allocated.</span></span> 
    
 <span data-ttu-id="8cf11-142">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="8cf11-142">_lpulConnection_</span></span>
  
> <span data-ttu-id="8cf11-143">排除一个指针, 指向表示呼叫者的通知接收器对象和邮件存储区之间的连接的非零连接号码。</span><span class="sxs-lookup"><span data-stu-id="8cf11-143">[out] A pointer to a nonzero connection number that represents the connection between the caller's advise sink object and the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8cf11-144">返回值</span><span class="sxs-lookup"><span data-stu-id="8cf11-144">Return value</span></span>

<span data-ttu-id="8cf11-145">S_OK</span><span class="sxs-lookup"><span data-stu-id="8cf11-145">S_OK</span></span> 
  
> <span data-ttu-id="8cf11-146">注册成功。</span><span class="sxs-lookup"><span data-stu-id="8cf11-146">The registration was successful.</span></span>
    
<span data-ttu-id="8cf11-147">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="8cf11-147">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="8cf11-148">邮件存储提供程序不支持通过邮件存储区注册通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-148">The message store provider does not support registration for notification through the message store.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8cf11-149">注解</span><span class="sxs-lookup"><span data-stu-id="8cf11-149">Remarks</span></span>

<span data-ttu-id="8cf11-150">**IMsgStore:: Advise**方法在调用方的通知接收器对象与邮件存储区或邮件存储区中的对象之间建立连接。</span><span class="sxs-lookup"><span data-stu-id="8cf11-150">The **IMsgStore::Advise** method establishes a connection between the caller's advise sink object and either the message store or an object in the message store.</span></span> <span data-ttu-id="8cf11-151">此连接用于在通知源对象发生一个或多个事件 (如_ulEventMask_参数中指定) 时, 将通知发送到通知接收器。</span><span class="sxs-lookup"><span data-stu-id="8cf11-151">This connection is used to send notifications to the advise sink when one or more events, as specified in the  _ulEventMask_ parameter, occur to the advise source object.</span></span> <span data-ttu-id="8cf11-152">当_lpEntryID_参数指向有效的条目标识符时, 建议源为此条目标识符标识的对象。</span><span class="sxs-lookup"><span data-stu-id="8cf11-152">When the  _lpEntryID_ parameter points to a valid entry identifier, the advise source is the object identified by this entry identifier.</span></span> <span data-ttu-id="8cf11-153">当_lpEntryID_为 NULL 时, 建议源为邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="8cf11-153">When  _lpEntryID_ is NULL, the advise source is the message store.</span></span> 
  
<span data-ttu-id="8cf11-154">若要发送通知, 邮件存储提供程序或 MAPI 将调用已注册的通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8cf11-154">To send a notification, either the message store provider or MAPI calls the registered advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="8cf11-155">**OnNotify**的参数之一是通知结构, 它包含描述特定事件的信息。</span><span class="sxs-lookup"><span data-stu-id="8cf11-155">One of the parameters to **OnNotify**, a notification structure, contains information that describes the specific event.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="8cf11-156">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="8cf11-156">Notes to implementers</span></span>

<span data-ttu-id="8cf11-157">你可以在 MAPI 中支持带有或没有帮助的通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-157">You can support notification with or without help from MAPI.</span></span> <span data-ttu-id="8cf11-158">MAPI 具有三个用于帮助服务提供程序实现通知的支持对象方法: [IMAPISupport:: 订阅](imapisupport-subscribe.md)、 [IMAPISupport:: 退订](imapisupport-unsubscribe.md)和[IMAPISupport:: Notify](imapisupport-notify.md)。</span><span class="sxs-lookup"><span data-stu-id="8cf11-158">MAPI has three support object methods for helping service providers implement notification: [IMAPISupport::Subscribe](imapisupport-subscribe.md), [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md), and [IMAPISupport::Notify](imapisupport-notify.md).</span></span> <span data-ttu-id="8cf11-159">如果选择使用 MAPI 支持方法, 请在调用**Advise**方法时呼叫**订阅**, 并释放_lpAdviseSink_指针。</span><span class="sxs-lookup"><span data-stu-id="8cf11-159">If you elect to use the MAPI support methods, call **Subscribe** when your **Advise** method is called and release the  _lpAdviseSink_ pointer.</span></span> 
  
<span data-ttu-id="8cf11-160">如果选择支持自己的通知, 请调用_lpAdviseSink_参数所代表的 "通知接收器" 的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法, 以保留此指针的副本。</span><span class="sxs-lookup"><span data-stu-id="8cf11-160">If you elect to support notification yourself, call the [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method of the advise sink represented by the  _lpAdviseSink_ parameter to keep a copy of this pointer.</span></span> <span data-ttu-id="8cf11-161">维护此副本, 直到调用[IMsgStore:: Unadvise](imsgstore-unadvise.md)方法以取消注册。</span><span class="sxs-lookup"><span data-stu-id="8cf11-161">Maintain this copy until your [IMsgStore::Unadvise](imsgstore-unadvise.md) method is called to cancel the registration.</span></span> 
  
<span data-ttu-id="8cf11-162">无论您如何支持通知, 请为通知注册分配非零连接号码, 并将其返回到_lpulConnection_参数中。</span><span class="sxs-lookup"><span data-stu-id="8cf11-162">Regardless of how you support notification, assign a nonzero connection number to the notification registration and return it in the  _lpulConnection_ parameter.</span></span> <span data-ttu-id="8cf11-163">在**Unadvise**已被调用并完成之前, 请勿释放此连接号码。</span><span class="sxs-lookup"><span data-stu-id="8cf11-163">Do not release this connection number until **Unadvise** has been called and has completed.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="8cf11-164">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8cf11-164">Notes to callers</span></span>

<span data-ttu-id="8cf11-165">在支持多个执行线程的系统上, 也可以随时在任何线程上对**OnNotify**进行调用。</span><span class="sxs-lookup"><span data-stu-id="8cf11-165">On systems that support multiple threads of execution, the call to **OnNotify** can also occur on any thread at any time.</span></span> <span data-ttu-id="8cf11-166">如果您必须确保仅在特定的线程上的特定时间发生通知, 请调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数来生成您传递给**建议**的建议接收器对象。</span><span class="sxs-lookup"><span data-stu-id="8cf11-166">If you must be assured that notifications occur only at a particular time on a particular thread, call the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function to generate the advise sink object that you pass to **Advise**.</span></span> 
  
<span data-ttu-id="8cf11-167">在对**建议**的调用成功且已调用**Unadvise**以取消注册之前, 请准备好要释放的通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="8cf11-167">After a call to **Advise** has succeeded and before **Unadvise** has been called to cancel the registration, be prepared for the advise sink object to be released.</span></span> <span data-ttu-id="8cf11-168">除非您有特定的长期用途, 否则应在**建议**返回后释放建议的接收器对象。</span><span class="sxs-lookup"><span data-stu-id="8cf11-168">You should release your advise sink object after **Advise** returns unless you have a specific long-term use for it.</span></span> 
  
<span data-ttu-id="8cf11-169">有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="8cf11-169">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span> 
  
<span data-ttu-id="8cf11-170">有关处理通知的详细信息, 请参阅[处理通知](handling-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="8cf11-170">For more information about handling notifications, see [Handling Notifications](handling-notifications.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="8cf11-171">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="8cf11-171">MFCMAPI reference</span></span>

<span data-ttu-id="8cf11-172">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="8cf11-172">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="8cf11-173">**文件**</span><span class="sxs-lookup"><span data-stu-id="8cf11-173">**File**</span></span>|<span data-ttu-id="8cf11-174">**函数**</span><span class="sxs-lookup"><span data-stu-id="8cf11-174">**Function**</span></span>|<span data-ttu-id="8cf11-175">**备注**</span><span class="sxs-lookup"><span data-stu-id="8cf11-175">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8cf11-176">BaseDialog</span><span class="sxs-lookup"><span data-stu-id="8cf11-176">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="8cf11-177">CBaseDialog:: OnNotificationsOn</span><span class="sxs-lookup"><span data-stu-id="8cf11-177">CBaseDialog::OnNotificationsOn</span></span>  <br/> |<span data-ttu-id="8cf11-178">MFCMAPI 使用**IMsgStore:: Advise**方法为整个邮件存储区注册通知。</span><span class="sxs-lookup"><span data-stu-id="8cf11-178">MFCMAPI uses the **IMsgStore::Advise** method to register for notifications on the entire message store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8cf11-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf11-179">See also</span></span>



[<span data-ttu-id="8cf11-180">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="8cf11-180">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="8cf11-181">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="8cf11-181">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="8cf11-182">IMsgStore::Unadvise</span><span class="sxs-lookup"><span data-stu-id="8cf11-182">IMsgStore::Unadvise</span></span>](imsgstore-unadvise.md)
  
[<span data-ttu-id="8cf11-183">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="8cf11-183">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="8cf11-184">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="8cf11-184">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="8cf11-185">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="8cf11-185">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

