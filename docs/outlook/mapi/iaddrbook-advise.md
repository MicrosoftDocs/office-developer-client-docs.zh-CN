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
# <a name="iaddrbookadvise"></a><span data-ttu-id="d5b3d-103">IAddrBook::Advise</span><span class="sxs-lookup"><span data-stu-id="d5b3d-103">IAddrBook::Advise</span></span>

  
  
<span data-ttu-id="d5b3d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d5b3d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d5b3d-105">注册客户端或服务提供商, 以接收有关通讯簿中的一个或多个条目的更改通知。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-105">Registers a client or service provider to receive notifications about changes to one or more entries in the address book.</span></span>
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="d5b3d-106">参数</span><span class="sxs-lookup"><span data-stu-id="d5b3d-106">Parameters</span></span>

 <span data-ttu-id="d5b3d-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="d5b3d-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="d5b3d-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="d5b3d-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="d5b3d-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="d5b3d-110">实时指向通讯簿容器、邮件用户或通讯组列表的条目标识符的指针, 在_ulEventMask_参数中所述的类型或类型发生更改时, 将生成通知。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-110">[in] A pointer to the entry identifier of the address book container, messaging user, or distribution list that will generate a notification when a change occurs of the type or types described in the  _ulEventMask_ parameter.</span></span> 
    
 <span data-ttu-id="d5b3d-111">_ulEventMask_</span><span class="sxs-lookup"><span data-stu-id="d5b3d-111">_ulEventMask_</span></span>
  
> <span data-ttu-id="d5b3d-112">实时呼叫者注册接收的一个或多个通知事件。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-112">[in] One or more notification events that the caller is registering to receive.</span></span> <span data-ttu-id="d5b3d-113">每个事件都与特定的通知结构相关联, 其中包含有关所发生更改的信息。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-113">Each event is associated with a particular notification structure that contains information about the change that occurred.</span></span> <span data-ttu-id="d5b3d-114">下表列出了_ulEventMask_及其对应结构的有效值。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-114">The following table lists the valid values for  _ulEventMask_ and their corresponding structures.</span></span> 
    
|<span data-ttu-id="d5b3d-115">**通知事件**</span><span class="sxs-lookup"><span data-stu-id="d5b3d-115">**Notification event**</span></span>|<span data-ttu-id="d5b3d-116">**对应的结构**</span><span class="sxs-lookup"><span data-stu-id="d5b3d-116">**Corresponding structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d5b3d-117">**fnevCriticalError**</span><span class="sxs-lookup"><span data-stu-id="d5b3d-117">**fnevCriticalError**</span></span> <br/> |[<span data-ttu-id="d5b3d-118">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="d5b3d-118">ERROR_NOTIFICATION</span></span>](error_notification.md) <br/> |
|<span data-ttu-id="d5b3d-119">**fnevObjectCreated**</span><span class="sxs-lookup"><span data-stu-id="d5b3d-119">**fnevObjectCreated**</span></span> <br/> |[<span data-ttu-id="d5b3d-120">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="d5b3d-120">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="d5b3d-121">**fnevObjectDeleted**</span><span class="sxs-lookup"><span data-stu-id="d5b3d-121">**fnevObjectDeleted**</span></span> <br/> |[<span data-ttu-id="d5b3d-122">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="d5b3d-122">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="d5b3d-123">**fnevObjectModified**</span><span class="sxs-lookup"><span data-stu-id="d5b3d-123">**fnevObjectModified**</span></span> <br/> |[<span data-ttu-id="d5b3d-124">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="d5b3d-124">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="d5b3d-125">**fnevObjectCopied**</span><span class="sxs-lookup"><span data-stu-id="d5b3d-125">**fnevObjectCopied**</span></span> <br/> |[<span data-ttu-id="d5b3d-126">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="d5b3d-126">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="d5b3d-127">**fnevObjectMoved**</span><span class="sxs-lookup"><span data-stu-id="d5b3d-127">**fnevObjectMoved**</span></span> <br/> |[<span data-ttu-id="d5b3d-128">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="d5b3d-128">OBJECT_NOTIFICATION</span></span>](object_notification.md) <br/> |
|<span data-ttu-id="d5b3d-129">**fnevTableModified**</span><span class="sxs-lookup"><span data-stu-id="d5b3d-129">**fnevTableModified**</span></span> <br/> |[<span data-ttu-id="d5b3d-130">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="d5b3d-130">TABLE_NOTIFICATION</span></span>](table_notification.md) <br/> |
   
 <span data-ttu-id="d5b3d-131">_lpAdviseSink_</span><span class="sxs-lookup"><span data-stu-id="d5b3d-131">_lpAdviseSink_</span></span>
  
> <span data-ttu-id="d5b3d-132">实时指向在请求通知的事件发生时要调用的通知接收器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-132">[in] A pointer to the advise sink object to be called when the event for which notification has been requested occurs.</span></span>
    
 <span data-ttu-id="d5b3d-133">_lpulConnection_</span><span class="sxs-lookup"><span data-stu-id="d5b3d-133">_lpulConnection_</span></span>
  
> <span data-ttu-id="d5b3d-134">排除指向代表通知注册的非零连接号的指针。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-134">[out] A pointer to a nonzero connection number that represents the notification registration.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d5b3d-135">返回值</span><span class="sxs-lookup"><span data-stu-id="d5b3d-135">Return value</span></span>

<span data-ttu-id="d5b3d-136">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5b3d-136">S_OK</span></span> 
  
> <span data-ttu-id="d5b3d-137">通知注册已成功。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-137">The notification registration was successful.</span></span>
    
<span data-ttu-id="d5b3d-138">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d5b3d-138">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="d5b3d-139">负责_lpEntryID_中传递的条目标识符的通讯簿提供程序无法为相应条目注册通知。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-139">The address book provider responsible for the entry identifier passed in  _lpEntryID_ could not register a notification for the corresponding entry.</span></span> 
    
<span data-ttu-id="d5b3d-140">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d5b3d-140">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="d5b3d-141">通讯簿提供程序不支持通知, 该通讯簿提供程序负责由_lpEntryID_参数中传递的条目标识符标识的对象。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-141">Notification is not supported by the address book provider responsible for the object identified by the entry identifier passed in the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="d5b3d-142">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d5b3d-142">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="d5b3d-143">_lpEntryID_中传递的条目标识符不能由配置文件中的任何通讯簿提供程序处理。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-143">The entry identifier passed in  _lpEntryID_ cannot be handled by any of the address book providers in the profile.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d5b3d-144">说明</span><span class="sxs-lookup"><span data-stu-id="d5b3d-144">Remarks</span></span>

<span data-ttu-id="d5b3d-145">客户端和服务提供程序调用**Advise**方法以在通讯簿条目上注册特定类型或通知类型。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-145">Clients and service providers call the **Advise** method to register for a particular type or types of notification on an address book entry.</span></span> <span data-ttu-id="d5b3d-146">通知的类型由通过_ulEventMask_参数传入的事件掩码指示。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-146">The types of notification are indicated by the event mask passed in with the  _ulEventMask_ parameter.</span></span> 
  
<span data-ttu-id="d5b3d-147">MAPI 将此**通知**调用转发给通讯簿提供程序, 该提供程序负责_lpEntryID_参数中的条目标识符所表示的条目。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-147">MAPI forwards this **Advise** call to the address book provider that is responsible for the entry as indicated by the entry identifier in the  _lpEntryID_ parameter.</span></span> <span data-ttu-id="d5b3d-148">通讯簿提供程序可以处理注册本身, 也可以调用支持方法[IMAPISupport:: 订阅](imapisupport-subscribe.md), 以提示 MAPI 注册呼叫者。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-148">The address book provider either handles the registration itself or calls the support method, [IMAPISupport::Subscribe](imapisupport-subscribe.md), to prompt MAPI to register the caller.</span></span> <span data-ttu-id="d5b3d-149">返回一个非零连接号码以表示成功注册。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-149">A nonzero connection number is returned to represent the successful registration.</span></span>
  
<span data-ttu-id="d5b3d-150">每当通知注册所指示的类型的项发生更改时, 通讯簿提供程序都会为_lpAdviseSink_参数中指定的建议接收器对象调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-150">Whenever a change occurs to the entry of the type indicated by the notification registration, the address book provider calls the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object specified in the  _lpAdviseSink_ parameter.</span></span> <span data-ttu-id="d5b3d-151">**OnNotify**方法包含一个[通知](notification.md)结构作为输入参数, 其中包含用于描述事件的数据。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-151">The **OnNotify** method includes a [NOTIFICATION](notification.md) structure as an input parameter that contains data to describe the event.</span></span> 
  
<span data-ttu-id="d5b3d-152">根据通讯簿提供程序, 对**OnNotify**的调用可以立即发生在对已注册对象的更改之后, 或在以后发生时。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-152">Depending on the address book provider, the call to **OnNotify** can occur immediately following the change to the registered object or at a later time.</span></span> <span data-ttu-id="d5b3d-153">在支持多个执行线程的系统上, 对**OnNotify**的调用可以出现在任何线程上。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-153">On systems that support multiple threads of execution, the call to **OnNotify** can occur on any thread.</span></span> <span data-ttu-id="d5b3d-154">客户端可以通过调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数来创建传递给**advise**的建议接收器对象, 从而请求在特定线程上发生这些通知。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-154">Clients can request that these notifications occur on a particular thread by calling the [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) function to create the advise sink object that is passed to **Advise**.</span></span> 
  
<span data-ttu-id="d5b3d-155">由于通讯簿提供程序可以在成功完成通知呼叫之后随时释放客户端传入的通知接收器对象, 并且在\*\*\*\* [IAddrBook:: Unadvise](iaddrbook-unadvise.md)调用取消通知之前, 客户端应释放**建议**返回时的通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-155">Because an address book provider can release the advise sink object passed in by clients at any time after the successful completion of the **Advise** call and before an [IAddrBook::Unadvise](iaddrbook-unadvise.md) call to cancel the notification, clients should release their advise sink objects when **Advise** returns.</span></span> 
  
<span data-ttu-id="d5b3d-156">有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="d5b3d-156">For more information about the notification process, see [Event Notification in MAPI](event-notification-in-mapi.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d5b3d-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5b3d-157">See also</span></span>



[<span data-ttu-id="d5b3d-158">HrThisThreadAdviseSink</span><span class="sxs-lookup"><span data-stu-id="d5b3d-158">HrThisThreadAdviseSink</span></span>](hrthisthreadadvisesink.md)
  
[<span data-ttu-id="d5b3d-159">IAddrBook::Unadvise</span><span class="sxs-lookup"><span data-stu-id="d5b3d-159">IAddrBook::Unadvise</span></span>](iaddrbook-unadvise.md)
  
[<span data-ttu-id="d5b3d-160">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="d5b3d-160">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="d5b3d-161">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="d5b3d-161">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="d5b3d-162">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d5b3d-162">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

