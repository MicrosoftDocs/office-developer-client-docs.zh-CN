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
ms.openlocfilehash: 8214390af883432d72f608452b8b944417884fd2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775243"
---
# <a name="iaddrbookadvise"></a><span data-ttu-id="ab7d3-103">IAddrBook::Advise</span><span class="sxs-lookup"><span data-stu-id="ab7d3-103">IAddrBook::Advise</span></span>

  
  
<span data-ttu-id="ab7d3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ab7d3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ab7d3-105">注册接收有关对一个或多个条目的更改的通知通讯簿中的客户端或服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-105">Registers a client or service provider to receive notifications about changes to one or more entries in the address book.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="ab7d3-106">参数</span><span class="sxs-lookup"><span data-stu-id="ab7d3-106">Parameters</span></span>

 <span data-ttu-id="ab7d3-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="ab7d3-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="ab7d3-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="ab7d3-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="ab7d3-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="ab7d3-110">[in]指向通讯簿容器，消息用户或通讯组列表的_ulEventMask_参数中描述的类型发生更改时，将生成通知的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-110">[in] A pointer to the entry identifier of the address book container, messaging user, or distribution list that will generate a notification when a change occurs of the type or types described in the  _ulEventMask_ parameter.</span></span> 
    
 <span data-ttu-id="ab7d3-111">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="ab7d3-111">_ulEventMask_</span></span>
  
> <span data-ttu-id="ab7d3-112">[in]呼叫者注册接收的一个或多个通知事件。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-112">[in] One or more notification events that the caller is registering to receive.</span></span> <span data-ttu-id="ab7d3-113">每个事件相关联的特定通知结构包含有关发生的更改的信息。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-113">Each event is associated with a particular notification structure that contains information about the change that occurred.</span></span> <span data-ttu-id="ab7d3-114">下表列出的有效值_ulEventMask_和其对应的结构。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-114">The following table lists the valid values for  _ulEventMask_ and their corresponding structures.</span></span> 
    
|<span data-ttu-id="ab7d3-115">**通知事件**</span><span class="sxs-lookup"><span data-stu-id="ab7d3-115">**Notification event**</span></span>|<span data-ttu-id="ab7d3-116">**相应的结构**</span><span class="sxs-lookup"><span data-stu-id="ab7d3-116">**Corresponding structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ab7d3-117">**fnevCriticalError**</span><span class="sxs-lookup"><span data-stu-id="ab7d3-117">**fnevCriticalError**</span></span> <br/> |[<span data-ttu-id="ab7d3-118">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ab7d3-118">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="ab7d3-119">**fnevObjectCreated**</span><span class="sxs-lookup"><span data-stu-id="ab7d3-119">**fnevObjectCreated**</span></span> <br/> |[<span data-ttu-id="ab7d3-120">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ab7d3-120">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="ab7d3-121">**fnevObjectDeleted**</span><span class="sxs-lookup"><span data-stu-id="ab7d3-121">**fnevObjectDeleted**</span></span> <br/> |[<span data-ttu-id="ab7d3-122">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ab7d3-122">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="ab7d3-123">**fnevObjectModified**</span><span class="sxs-lookup"><span data-stu-id="ab7d3-123">**fnevObjectModified**</span></span> <br/> |[<span data-ttu-id="ab7d3-124">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ab7d3-124">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="ab7d3-125">**fnevObjectCopied**</span><span class="sxs-lookup"><span data-stu-id="ab7d3-125">**fnevObjectCopied**</span></span> <br/> |[<span data-ttu-id="ab7d3-126">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ab7d3-126">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="ab7d3-127">**fnevObjectMoved**</span><span class="sxs-lookup"><span data-stu-id="ab7d3-127">**fnevObjectMoved**</span></span> <br/> |[<span data-ttu-id="ab7d3-128">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ab7d3-128">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="ab7d3-129">**fnevTableModified**</span><span class="sxs-lookup"><span data-stu-id="ab7d3-129">**fnevTableModified**</span></span> <br/> |[<span data-ttu-id="ab7d3-130">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ab7d3-130">TABLE_NOTIFICATION</span></span>](table_notification.md) <br/> |
   
 <span data-ttu-id="ab7d3-131">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="ab7d3-131">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="ab7d3-132">[in]指向要为其请求通知事件发生时调用的 advise 接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-132">[in] A pointer to the advise sink object to be called when the event for which notification has been requested occurs.</span></span>
    
 <span data-ttu-id="ab7d3-133">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="ab7d3-133">_lpulConnection_</span></span>
  
> <span data-ttu-id="ab7d3-134">[输出]一个指向代表通知注册非零值的连接数。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-134">[out] A pointer to a nonzero connection number that represents the notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ab7d3-135">返回值</span><span class="sxs-lookup"><span data-stu-id="ab7d3-135">Return value</span></span>

<span data-ttu-id="ab7d3-136">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab7d3-136">S_OK</span></span> 
  
> <span data-ttu-id="ab7d3-137">通知注册成功。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-137">The notification registration was successful.</span></span>
    
<span data-ttu-id="ab7d3-138">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="ab7d3-138">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="ab7d3-139">负责_lpEntryID_中传递的项标识符的地址簿提供程序无法注册相应的项的通知。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-139">The address book provider responsible for the entry identifier passed in  _lpEntryID_ could not register a notification for the corresponding entry.</span></span> 
    
<span data-ttu-id="ab7d3-140">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="ab7d3-140">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="ab7d3-141">通讯簿提供程序负责标识_lpEntryID_参数中传递的项标识符的对象不支持通知。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-141">Notification is not supported by the address book provider responsible for the object identified by the entry identifier passed in the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="ab7d3-142">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="ab7d3-142">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="ab7d3-143">不能由任何配置文件中的地址簿提供程序处理_lpEntryID_中传递的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-143">The entry identifier passed in  _lpEntryID_ cannot be handled by any of the address book providers in the profile.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ab7d3-144">说明</span><span class="sxs-lookup"><span data-stu-id="ab7d3-144">Remarks</span></span>

<span data-ttu-id="ab7d3-145">客户端和服务提供商调用**Advise**方法注册特定类型或上的通讯簿条目的通知的类型。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-145">Clients and service providers call the **Advise** method to register for a particular type or types of notification on an address book entry.</span></span> <span data-ttu-id="ab7d3-146">通过使用_ulEventMask_参数传递的事件掩码表示通知的类型。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-146">The types of notification are indicated by the event mask passed in with the  _ulEventMask_ parameter.</span></span> 
  
<span data-ttu-id="ab7d3-147">MAPI 转发到的地址簿提供程序负责由_lpEntryID_参数中的项标识符的条目此**Advise**呼叫。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-147">MAPI forwards this **Advise** call to the address book provider that is responsible for the entry as indicated by the entry identifier in the  _lpEntryID_ parameter.</span></span> <span data-ttu-id="ab7d3-148">通讯簿提供程序处理的注册本身，或调用支持方法， [IMAPISupport::Subscribe](imapisupport-subscribe.md)，提示 MAPI 注册呼叫者。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-148">The address book provider either handles the registration itself or calls the support method, [IMAPISupport::Subscribe](imapisupport-subscribe.md), to prompt MAPI to register the caller.</span></span> <span data-ttu-id="ab7d3-149">返回非零值的连接数来表示成功注册。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-149">A nonzero connection number is returned to represent the successful registration.</span></span>
  
<span data-ttu-id="ab7d3-150">当指示通知注册的类型的项发生更改时，通讯簿提供程序为_lpAdviseSink_参数中指定的 advise 接收器对象调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-150">Whenever a change occurs to the entry of the type indicated by the notification registration, the address book provider calls the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object specified in the  _lpAdviseSink_ parameter.</span></span> <span data-ttu-id="ab7d3-151">**OnNotify**方法包括作为输入参数包含数据描述该事件[通知](notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-151">The **OnNotify** method includes a [NOTIFICATION](notification.md) structure as an input parameter that contains data to describe the event.</span></span> 
  
<span data-ttu-id="ab7d3-152">通讯簿提供程序，根据**OnNotify**调用紧跟更改对注册对象或更高版本时出现。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-152">Depending on the address book provider, the call to **OnNotify** can occur immediately following the change to the registered object or at a later time.</span></span> <span data-ttu-id="ab7d3-153">支持多个线程的执行系统，在调用**OnNotify**可以发生任何线程上。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-153">On systems that support multiple threads of execution, the call to **OnNotify** can occur on any thread.</span></span> <span data-ttu-id="ab7d3-154">客户端可以请求对这些通知通过调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数来创建 advise 接收器对象传递给**Advise**发生在特定线程。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-154">Clients can request that these notifications occur on a particular thread by calling the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function to create the advise sink object that is passed to **Advise**.</span></span> 
  
<span data-ttu-id="ab7d3-155">因为通讯簿提供程序可以释放 advise 接收器对象中传递的客户端在任何时候**Advise**成功完成呼叫，并在[IAddrBook::Unadvise](iaddrbook-unadvise.md)前调用取消通知后，应释放客户端当**Advise**返回其 advise 接收器对象。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-155">Because an address book provider can release the advise sink object passed in by clients at any time after the successful completion of the **Advise** call and before an [IAddrBook::Unadvise](iaddrbook-unadvise.md) call to cancel the notification, clients should release their advise sink objects when **Advise** returns.</span></span> 
  
<span data-ttu-id="ab7d3-156">有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="ab7d3-156">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab7d3-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab7d3-157">See also</span></span>



[<span data-ttu-id="ab7d3-158">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="ab7d3-158">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="ab7d3-159">IAddrBook::Unadvise</span><span class="sxs-lookup"><span data-stu-id="ab7d3-159">IAddrBook::Unadvise</span></span>](iaddrbook-unadvise.md)
  
[<span data-ttu-id="ab7d3-160">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="ab7d3-160">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="ab7d3-161">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ab7d3-161">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="ab7d3-162">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ab7d3-162">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

