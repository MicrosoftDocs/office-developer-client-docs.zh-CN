---
title: IAddrBookAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.Advise
api_type:
- COM
ms.assetid: 2def89ed-e4ce-446a-8b80-132d11ae8f8b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7abafafd3d4bd9618d85a7dac34e4556545167bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406274"
---
# <a name="iaddrbookadvise"></a><span data-ttu-id="487e6-103">IAddrBook::Advise</span><span class="sxs-lookup"><span data-stu-id="487e6-103">IAddrBook::Advise</span></span>

  
  
<span data-ttu-id="487e6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="487e6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="487e6-105">注册客户端或服务提供商以接收有关通讯簿中一个或多个条目更改的通知。</span><span class="sxs-lookup"><span data-stu-id="487e6-105">Registers a client or service provider to receive notifications about changes to one or more entries in the address book.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="487e6-106">参数</span><span class="sxs-lookup"><span data-stu-id="487e6-106">Parameters</span></span>

 <span data-ttu-id="487e6-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="487e6-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="487e6-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="487e6-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="487e6-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="487e6-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="487e6-110">[in]指向通讯簿容器、邮件传递用户或通讯组列表的条目标识符的指针，当  _ulEventMask_ 参数中描述的类型发生更改时将生成通知。</span><span class="sxs-lookup"><span data-stu-id="487e6-110">[in] A pointer to the entry identifier of the address book container, messaging user, or distribution list that will generate a notification when a change occurs of the type or types described in the  _ulEventMask_ parameter.</span></span> 
    
 <span data-ttu-id="487e6-111">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="487e6-111">_ulEventMask_</span></span>
  
> <span data-ttu-id="487e6-112">[in]呼叫者要注册以接收的一个或多个通知事件。</span><span class="sxs-lookup"><span data-stu-id="487e6-112">[in] One or more notification events that the caller is registering to receive.</span></span> <span data-ttu-id="487e6-113">每个事件都与一个特定的通知结构相关联，其中包含有关发生的更改的信息。</span><span class="sxs-lookup"><span data-stu-id="487e6-113">Each event is associated with a particular notification structure that contains information about the change that occurred.</span></span> <span data-ttu-id="487e6-114">下表列出了  _ulEventMask_ 的有效值及其相应的结构。</span><span class="sxs-lookup"><span data-stu-id="487e6-114">The following table lists the valid values for  _ulEventMask_ and their corresponding structures.</span></span> 
    
|<span data-ttu-id="487e6-115">**通知事件**</span><span class="sxs-lookup"><span data-stu-id="487e6-115">**Notification event**</span></span>|<span data-ttu-id="487e6-116">**相应的结构**</span><span class="sxs-lookup"><span data-stu-id="487e6-116">**Corresponding structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="487e6-117">**fnevCriticalError**</span><span class="sxs-lookup"><span data-stu-id="487e6-117">**fnevCriticalError**</span></span> <br/> |[<span data-ttu-id="487e6-118">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="487e6-118">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="487e6-119">**fnevObjectCreated**</span><span class="sxs-lookup"><span data-stu-id="487e6-119">**fnevObjectCreated**</span></span> <br/> |[<span data-ttu-id="487e6-120">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="487e6-120">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="487e6-121">**fnevObjectDeleted**</span><span class="sxs-lookup"><span data-stu-id="487e6-121">**fnevObjectDeleted**</span></span> <br/> |[<span data-ttu-id="487e6-122">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="487e6-122">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="487e6-123">**fnevObjectModified**</span><span class="sxs-lookup"><span data-stu-id="487e6-123">**fnevObjectModified**</span></span> <br/> |[<span data-ttu-id="487e6-124">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="487e6-124">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="487e6-125">**fnevObjectCopied**</span><span class="sxs-lookup"><span data-stu-id="487e6-125">**fnevObjectCopied**</span></span> <br/> |[<span data-ttu-id="487e6-126">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="487e6-126">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="487e6-127">**fnevObjectMoved**</span><span class="sxs-lookup"><span data-stu-id="487e6-127">**fnevObjectMoved**</span></span> <br/> |[<span data-ttu-id="487e6-128">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="487e6-128">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="487e6-129">**fnevTableModified**</span><span class="sxs-lookup"><span data-stu-id="487e6-129">**fnevTableModified**</span></span> <br/> |[<span data-ttu-id="487e6-130">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="487e6-130">TABLE_NOTIFICATION</span></span>](table_notification.md) <br/> |
   
 <span data-ttu-id="487e6-131">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="487e6-131">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="487e6-132">[in]指向通知接收器对象的指针，当发生请求通知的事件时将调用该对象。</span><span class="sxs-lookup"><span data-stu-id="487e6-132">[in] A pointer to the advise sink object to be called when the event for which notification has been requested occurs.</span></span>
    
 <span data-ttu-id="487e6-133">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="487e6-133">_lpulConnection_</span></span>
  
> <span data-ttu-id="487e6-134">[out]指向表示通知注册的非零连接号的指针。</span><span class="sxs-lookup"><span data-stu-id="487e6-134">[out] A pointer to a nonzero connection number that represents the notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="487e6-135">返回值</span><span class="sxs-lookup"><span data-stu-id="487e6-135">Return value</span></span>

<span data-ttu-id="487e6-136">S_OK</span><span class="sxs-lookup"><span data-stu-id="487e6-136">S_OK</span></span> 
  
> <span data-ttu-id="487e6-137">通知注册成功。</span><span class="sxs-lookup"><span data-stu-id="487e6-137">The notification registration was successful.</span></span>
    
<span data-ttu-id="487e6-138">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="487e6-138">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="487e6-139">负责在  _lpEntryID_ 中传递的条目标识符的通讯簿提供程序无法为相应的条目注册通知。</span><span class="sxs-lookup"><span data-stu-id="487e6-139">The address book provider responsible for the entry identifier passed in  _lpEntryID_ could not register a notification for the corresponding entry.</span></span> 
    
<span data-ttu-id="487e6-140">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="487e6-140">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="487e6-141">负责由传入  _lpEntryID_ 参数中的条目标识符标识的对象的通讯簿提供程序不支持通知。</span><span class="sxs-lookup"><span data-stu-id="487e6-141">Notification is not supported by the address book provider responsible for the object identified by the entry identifier passed in the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="487e6-142">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="487e6-142">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="487e6-143">_lpEntryID_ 中传递的条目标识符无法由配置文件中的任一通讯簿提供程序处理。</span><span class="sxs-lookup"><span data-stu-id="487e6-143">The entry identifier passed in  _lpEntryID_ cannot be handled by any of the address book providers in the profile.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="487e6-144">备注</span><span class="sxs-lookup"><span data-stu-id="487e6-144">Remarks</span></span>

<span data-ttu-id="487e6-145">客户端和服务提供商调用 **Advise** 方法，以注册通讯簿条目上的特定通知类型。</span><span class="sxs-lookup"><span data-stu-id="487e6-145">Clients and service providers call the **Advise** method to register for a particular type or types of notification on an address book entry.</span></span> <span data-ttu-id="487e6-146">通知类型由使用  _ulEventMask_ 参数传入的事件掩码指示。</span><span class="sxs-lookup"><span data-stu-id="487e6-146">The types of notification are indicated by the event mask passed in with the  _ulEventMask_ parameter.</span></span> 
  
<span data-ttu-id="487e6-147">MAPI 将 **此 Advise** 调用转发到负责条目的通讯簿提供程序，如  _lpEntryID_ 参数中的条目标识符所指示。</span><span class="sxs-lookup"><span data-stu-id="487e6-147">MAPI forwards this **Advise** call to the address book provider that is responsible for the entry as indicated by the entry identifier in the  _lpEntryID_ parameter.</span></span> <span data-ttu-id="487e6-148">通讯簿提供程序要么处理注册本身，要么调用支持方法 [IMAPISupport：：Subscribe](imapisupport-subscribe.md)来提示 MAPI 注册呼叫者。</span><span class="sxs-lookup"><span data-stu-id="487e6-148">The address book provider either handles the registration itself or calls the support method, [IMAPISupport::Subscribe](imapisupport-subscribe.md), to prompt MAPI to register the caller.</span></span> <span data-ttu-id="487e6-149">返回非零连接号以表示注册成功。</span><span class="sxs-lookup"><span data-stu-id="487e6-149">A nonzero connection number is returned to represent the successful registration.</span></span>
  
<span data-ttu-id="487e6-150">每当通知注册所指示类型的条目发生变化时，通讯簿提供程序都会为 _lpAdviseSink_ 参数中指定的通知接收器对象调用 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="487e6-150">Whenever a change occurs to the entry of the type indicated by the notification registration, the address book provider calls the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object specified in the  _lpAdviseSink_ parameter.</span></span> <span data-ttu-id="487e6-151">**OnNotify** 方法包括 [NOTIFICATION](notification.md)结构作为输入参数，其中包含用于描述事件的数据。</span><span class="sxs-lookup"><span data-stu-id="487e6-151">The **OnNotify** method includes a [NOTIFICATION](notification.md) structure as an input parameter that contains data to describe the event.</span></span> 
  
<span data-ttu-id="487e6-152">根据通讯簿提供程序，对 **OnNotify** 的调用可以在注册对象更改后立即发生，或稍后发生。</span><span class="sxs-lookup"><span data-stu-id="487e6-152">Depending on the address book provider, the call to **OnNotify** can occur immediately following the change to the registered object or at a later time.</span></span> <span data-ttu-id="487e6-153">在支持多个执行线程的系统上，对 **OnNotify** 的调用可以在任何线程上发生。</span><span class="sxs-lookup"><span data-stu-id="487e6-153">On systems that support multiple threads of execution, the call to **OnNotify** can occur on any thread.</span></span> <span data-ttu-id="487e6-154">客户端可以通过调用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数来创建传递给 Advise 的建议接收对象，来请求这些通知出现在特定 **线程上**。</span><span class="sxs-lookup"><span data-stu-id="487e6-154">Clients can request that these notifications occur on a particular thread by calling the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function to create the advise sink object that is passed to **Advise**.</span></span> 
  
<span data-ttu-id="487e6-155">由于通讯簿提供程序可以在 **Advise** 调用成功完成后 [、IAddrBook：：Unadvise](iaddrbook-unadvise.md) 调用取消通知之前随时释放客户端传入的建议接收对象，因此当 **Advise** 返回时，客户端应释放其通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="487e6-155">Because an address book provider can release the advise sink object passed in by clients at any time after the successful completion of the **Advise** call and before an [IAddrBook::Unadvise](iaddrbook-unadvise.md) call to cancel the notification, clients should release their advise sink objects when **Advise** returns.</span></span> 
  
<span data-ttu-id="487e6-156">有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="487e6-156">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="487e6-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="487e6-157">See also</span></span>



[<span data-ttu-id="487e6-158">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="487e6-158">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="487e6-159">IAddrBook::Unadvise</span><span class="sxs-lookup"><span data-stu-id="487e6-159">IAddrBook::Unadvise</span></span>](iaddrbook-unadvise.md)
  
[<span data-ttu-id="487e6-160">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="487e6-160">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="487e6-161">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="487e6-161">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="487e6-162">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="487e6-162">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

