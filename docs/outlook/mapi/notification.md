---
title: NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.NOTIFICATION
api_type:
- COM
ms.assetid: 01b6e695-a649-4efd-a893-7586b476467e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a3235c2305d61318f482943167e5f307e5da0d70
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432875"
---
# <a name="notification"></a><span data-ttu-id="c7833-103">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c7833-103">NOTIFICATION</span></span>
 
<span data-ttu-id="c7833-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7833-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7833-105">包含有关已发生的事件和受事件影响的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="c7833-105">Contains information about an event that has occurred and the data that has been affected by the event.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c7833-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c7833-106">Header file:</span></span>  <br/> |<span data-ttu-id="c7833-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c7833-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG ulEventType;
  union
  {
    ERROR_NOTIFICATION err;
    NEWMAIL_NOTIFICATION newmail;
    OBJECT_NOTIFICATION obj;
    TABLE_NOTIFICATION tab;
    EXTENDED_NOTIFICATION ext;
    STATUS_OBJECT_NOTIFICATION statobj;
  } info;
} NOTIFICATION, FAR *LPNOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="c7833-108">Members</span><span class="sxs-lookup"><span data-stu-id="c7833-108">Members</span></span>

<span data-ttu-id="c7833-109">**ulEventType**</span><span class="sxs-lookup"><span data-stu-id="c7833-109">**ulEventType**</span></span>
  
> <span data-ttu-id="c7833-110">发生的通知事件的类型。</span><span class="sxs-lookup"><span data-stu-id="c7833-110">Type of notification event that occurred.</span></span> <span data-ttu-id="c7833-111">**ulEventType**成员的值对应于**info**联合中包含的结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-111">The value of the **ulEventType** member corresponds to the structure that is included in the **info** union.</span></span> <span data-ttu-id="c7833-112">**ulEventType**成员可设置为以下值之一:</span><span class="sxs-lookup"><span data-stu-id="c7833-112">The **ulEventType** member can be set to one of the following values:</span></span> 
    
 <span data-ttu-id="c7833-113">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="c7833-113">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="c7833-114">发生全局错误, 如正在进行中的会话关闭。</span><span class="sxs-lookup"><span data-stu-id="c7833-114">A global error has occurred, such as a session shut down in progress.</span></span> <span data-ttu-id="c7833-115">**info**成员包含[ERROR_NOTIFICATION](error_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-115">The **info** member contains an [ERROR_NOTIFICATION](error_notification.md) structure.</span></span> 
    
 <span data-ttu-id="c7833-116">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="c7833-116">_fnevExtended_</span></span>
  
> <span data-ttu-id="c7833-117">特定服务提供程序定义的内部事件已发生。</span><span class="sxs-lookup"><span data-stu-id="c7833-117">An internal event defined by a particular service provider has occurred.</span></span> <span data-ttu-id="c7833-118">**info**成员包含[EXTENDED_NOTIFICATION](extended_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-118">The **info** member contains an [EXTENDED_NOTIFICATION](extended_notification.md) structure.</span></span> 
    
 <span data-ttu-id="c7833-119">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="c7833-119">_fnevNewMail_</span></span>
  
> <span data-ttu-id="c7833-120">邮件已传递到邮件类的相应接收文件夹, 并且正在等待处理。</span><span class="sxs-lookup"><span data-stu-id="c7833-120">A message has been delivered to the appropriate receive folder for the message class and is waiting to be processed.</span></span> <span data-ttu-id="c7833-121">**info**成员包含[NEWMAIL_NOTIFICATION](newmail_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-121">The **info** member contains an [NEWMAIL_NOTIFICATION](newmail_notification.md) structure.</span></span> 
    
 <span data-ttu-id="c7833-122">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="c7833-122">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="c7833-123">MAPI 对象已复制。</span><span class="sxs-lookup"><span data-stu-id="c7833-123">A MAPI object has been copied.</span></span> <span data-ttu-id="c7833-124">**info**成员包含[OBJECT_NOTIFICATION](object_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-124">The **info** member contains an [OBJECT_NOTIFICATION](object_notification.md) structure.</span></span> 
    
 <span data-ttu-id="c7833-125">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="c7833-125">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="c7833-126">已创建 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="c7833-126">A MAPI object has been created.</span></span> <span data-ttu-id="c7833-127">**info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-127">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="c7833-128">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="c7833-128">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="c7833-129">MAPI 对象已被删除。</span><span class="sxs-lookup"><span data-stu-id="c7833-129">A MAPI object has been deleted.</span></span> <span data-ttu-id="c7833-130">**info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-130">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="c7833-131">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="c7833-131">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="c7833-132">MAPI 对象已更改。</span><span class="sxs-lookup"><span data-stu-id="c7833-132">A MAPI object has changed.</span></span> <span data-ttu-id="c7833-133">**info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-133">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="c7833-134">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="c7833-134">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="c7833-135">已移动邮件存储或通讯簿对象。</span><span class="sxs-lookup"><span data-stu-id="c7833-135">A message store or address book object has been moved.</span></span> <span data-ttu-id="c7833-136">**info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-136">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="c7833-137">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="c7833-137">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="c7833-138">搜索操作已完成, 结果可用。</span><span class="sxs-lookup"><span data-stu-id="c7833-138">A search operation has finished and the results are available.</span></span> <span data-ttu-id="c7833-139">**info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-139">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="c7833-140">_fnevTableModified_</span><span class="sxs-lookup"><span data-stu-id="c7833-140">_fnevTableModified_</span></span>
  
> <span data-ttu-id="c7833-141">表中的信息已更改。</span><span class="sxs-lookup"><span data-stu-id="c7833-141">Information in a table has changed.</span></span> <span data-ttu-id="c7833-142">**info**成员包含[TABLE_NOTIFICATION](table_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="c7833-142">The **info** member contains an [TABLE_NOTIFICATION](table_notification.md) structure.</span></span> 
    
<span data-ttu-id="c7833-143">**info**</span><span class="sxs-lookup"><span data-stu-id="c7833-143">**info**</span></span>
  
> <span data-ttu-id="c7833-144">通知结构的联合, 用于描述特定类型事件的受影响数据。</span><span class="sxs-lookup"><span data-stu-id="c7833-144">Union of notification structures describing the affected data for a particular type of event.</span></span> <span data-ttu-id="c7833-145">**info**成员中包含的结构取决于**ulEventType**成员的值。</span><span class="sxs-lookup"><span data-stu-id="c7833-145">The structure included in the **info** member depends on the value of the **ulEventType** member.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c7833-146">说明</span><span class="sxs-lookup"><span data-stu-id="c7833-146">Remarks</span></span>

<span data-ttu-id="c7833-147">每次调用已注册的通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法时, 都会将一个或多个**通知**结构作为输入参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="c7833-147">One or more **NOTIFICATION** structures are passed as input parameters with every call to a registered advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="c7833-148">**通知**结构包含有关已发生的特定事件的信息, 并描述受影响的对象。</span><span class="sxs-lookup"><span data-stu-id="c7833-148">The **NOTIFICATION** structures contain information about the particular events that have occurred and describe the affected objects.</span></span> 
  
<span data-ttu-id="c7833-149">在接收通知的客户端或服务提供程序可以使用结构处理事件之前, 必须按照**ulEventType**成员中的指示检查事件类型。</span><span class="sxs-lookup"><span data-stu-id="c7833-149">Before clients or service providers receiving a notification can use the structure to process the event, they must check the event type as indicated in the **ulEventType** member.</span></span> <span data-ttu-id="c7833-150">例如, 此处显示的代码示例检查新邮件的到达, 并在检测到此类事件时, 输出邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="c7833-150">For example, the code sample that is shown here checks for the arrival of a new message and upon detecting an event of this kind, prints out the message class of the message.</span></span> 
  
```cpp
if (pNotif -> ulEventType == fnevNewMail)
{
printf("%s\n", pNotif -> newmail.lpszMessageClass)
}

```

<span data-ttu-id="c7833-151">有关通知的详细信息, 请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="c7833-151">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="c7833-152">**主题**</span><span class="sxs-lookup"><span data-stu-id="c7833-152">**Topic**</span></span>|<span data-ttu-id="c7833-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="c7833-153">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c7833-154">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="c7833-154">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="c7833-155">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="c7833-155">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="c7833-156">处理通知</span><span class="sxs-lookup"><span data-stu-id="c7833-156">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="c7833-157">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="c7833-157">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="c7833-158">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="c7833-158">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="c7833-159">讨论了如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="c7833-159">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c7833-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7833-160">See also</span></span>


- [<span data-ttu-id="c7833-161">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c7833-161">ERROR_NOTIFICATION</span></span>](error_notification.md)  
- [<span data-ttu-id="c7833-162">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c7833-162">EXTENDED_NOTIFICATION</span></span>](extended_notification.md)  
- [<span data-ttu-id="c7833-163">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c7833-163">NEWMAIL_NOTIFICATION</span></span>](newmail_notification.md)  
- [<span data-ttu-id="c7833-164">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c7833-164">OBJECT_NOTIFICATION</span></span>](object_notification.md)  
- [<span data-ttu-id="c7833-165">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c7833-165">STATUS_OBJECT_NOTIFICATION</span></span>](status_object_notification.md)  
- [<span data-ttu-id="c7833-166">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c7833-166">TABLE_NOTIFICATION</span></span>](table_notification.md)
- [<span data-ttu-id="c7833-167">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c7833-167">MAPI Structures</span></span>](mapi-structures.md)

