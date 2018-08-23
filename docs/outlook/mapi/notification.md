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
ms.openlocfilehash: 0d427adde72c24d4ca879c7bd883af09c4ecad53
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579968"
---
# <a name="notification"></a><span data-ttu-id="afe7e-103">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="afe7e-103">NOTIFICATION</span></span>
 
<span data-ttu-id="afe7e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="afe7e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="afe7e-105">包含有关发生的事件和受事件的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="afe7e-105">Contains information about an event that has occurred and the data that has been affected by the event.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="afe7e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="afe7e-106">Header file:</span></span>  <br/> |<span data-ttu-id="afe7e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="afe7e-107">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="afe7e-108">Members</span><span class="sxs-lookup"><span data-stu-id="afe7e-108">Members</span></span>

<span data-ttu-id="afe7e-109">**ulEventType**</span><span class="sxs-lookup"><span data-stu-id="afe7e-109">**ulEventType**</span></span>
  
> <span data-ttu-id="afe7e-110">通知事件发生的类型。</span><span class="sxs-lookup"><span data-stu-id="afe7e-110">Type of notification event that occurred.</span></span> <span data-ttu-id="afe7e-111">**UlEventType**成员的值对应于**info**联合中包含的结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-111">The value of the **ulEventType** member corresponds to the structure that is included in the **info** union.</span></span> <span data-ttu-id="afe7e-112">**UlEventType**成员可以设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="afe7e-112">The **ulEventType** member can be set to one of the following values:</span></span> 
    
 <span data-ttu-id="afe7e-113">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="afe7e-113">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="afe7e-114">全局发生的错误，如会话正在关闭。</span><span class="sxs-lookup"><span data-stu-id="afe7e-114">A global error has occurred, such as a session shut down in progress.</span></span> <span data-ttu-id="afe7e-115">**Info**成员包含[ERROR_NOTIFICATION](error_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-115">The **info** member contains an [ERROR_NOTIFICATION](error_notification.md) structure.</span></span> 
    
 <span data-ttu-id="afe7e-116">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="afe7e-116">_fnevExtended_</span></span>
  
> <span data-ttu-id="afe7e-117">特定服务提供程序定义的内部事件发生。</span><span class="sxs-lookup"><span data-stu-id="afe7e-117">An internal event defined by a particular service provider has occurred.</span></span> <span data-ttu-id="afe7e-118">**Info**成员包含[EXTENDED_NOTIFICATION](extended_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-118">The **info** member contains an [EXTENDED_NOTIFICATION](extended_notification.md) structure.</span></span> 
    
 <span data-ttu-id="afe7e-119">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="afe7e-119">_fnevNewMail_</span></span>
  
> <span data-ttu-id="afe7e-120">已将消息发送到相应的接收文件夹的邮件类和正在等待处理。</span><span class="sxs-lookup"><span data-stu-id="afe7e-120">A message has been delivered to the appropriate receive folder for the message class and is waiting to be processed.</span></span> <span data-ttu-id="afe7e-121">**Info**成员包含[NEWMAIL_NOTIFICATION](newmail_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-121">The **info** member contains an [NEWMAIL_NOTIFICATION](newmail_notification.md) structure.</span></span> 
    
 <span data-ttu-id="afe7e-122">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="afe7e-122">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="afe7e-123">已复制的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="afe7e-123">A MAPI object has been copied.</span></span> <span data-ttu-id="afe7e-124">**Info**成员包含[OBJECT_NOTIFICATION](object_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-124">The **info** member contains an [OBJECT_NOTIFICATION](object_notification.md) structure.</span></span> 
    
 <span data-ttu-id="afe7e-125">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="afe7e-125">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="afe7e-126">已创建一个 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="afe7e-126">A MAPI object has been created.</span></span> <span data-ttu-id="afe7e-127">**Info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-127">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="afe7e-128">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="afe7e-128">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="afe7e-129">MAPI 对象已被删除。</span><span class="sxs-lookup"><span data-stu-id="afe7e-129">A MAPI object has been deleted.</span></span> <span data-ttu-id="afe7e-130">**Info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-130">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="afe7e-131">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="afe7e-131">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="afe7e-132">MAPI 对象已更改。</span><span class="sxs-lookup"><span data-stu-id="afe7e-132">A MAPI object has changed.</span></span> <span data-ttu-id="afe7e-133">**Info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-133">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="afe7e-134">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="afe7e-134">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="afe7e-135">消息存储或地址簿对象已移动。</span><span class="sxs-lookup"><span data-stu-id="afe7e-135">A message store or address book object has been moved.</span></span> <span data-ttu-id="afe7e-136">**Info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-136">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="afe7e-137">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="afe7e-137">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="afe7e-138">完成搜索操作并且可结果。</span><span class="sxs-lookup"><span data-stu-id="afe7e-138">A search operation has finished and the results are available.</span></span> <span data-ttu-id="afe7e-139">**Info**成员包含**OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-139">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="afe7e-140">_fnevTableModified_</span><span class="sxs-lookup"><span data-stu-id="afe7e-140">_fnevTableModified_</span></span>
  
> <span data-ttu-id="afe7e-141">已更改表中的信息。</span><span class="sxs-lookup"><span data-stu-id="afe7e-141">Information in a table has changed.</span></span> <span data-ttu-id="afe7e-142">**Info**成员包含[TABLE_NOTIFICATION](table_notification.md)结构。</span><span class="sxs-lookup"><span data-stu-id="afe7e-142">The **info** member contains an [TABLE_NOTIFICATION](table_notification.md) structure.</span></span> 
    
<span data-ttu-id="afe7e-143">**信息**</span><span class="sxs-lookup"><span data-stu-id="afe7e-143">**info**</span></span>
  
> <span data-ttu-id="afe7e-144">描述受影响的数据的特定类型的事件通知结构的联合。</span><span class="sxs-lookup"><span data-stu-id="afe7e-144">Union of notification structures describing the affected data for a particular type of event.</span></span> <span data-ttu-id="afe7e-145">**Info**成员中包含的结构取决于**ulEventType**成员的值。</span><span class="sxs-lookup"><span data-stu-id="afe7e-145">The structure included in the **info** member depends on the value of the **ulEventType** member.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="afe7e-146">注解</span><span class="sxs-lookup"><span data-stu-id="afe7e-146">Remarks</span></span>

<span data-ttu-id="afe7e-147">一个或多个**通知**结构与每个呼叫的注册的 advise 接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法传递作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="afe7e-147">One or more **NOTIFICATION** structures are passed as input parameters with every call to a registered advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="afe7e-148">**通知**结构包含有关的特定事件的发生和描述受影响的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="afe7e-148">The **NOTIFICATION** structures contain information about the particular events that have occurred and describe the affected objects.</span></span> 
  
<span data-ttu-id="afe7e-149">客户端或接收通知的服务提供商可以使用结构处理该事件之前，它们必须检查的事件类型， **ulEventType**成员中所述。</span><span class="sxs-lookup"><span data-stu-id="afe7e-149">Before clients or service providers receiving a notification can use the structure to process the event, they must check the event type as indicated in the **ulEventType** member.</span></span> <span data-ttu-id="afe7e-150">例如，此处检查到达新消息和在检测这种类型的事件时显示的代码示例将输出的邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="afe7e-150">For example, the code sample that is shown here checks for the arrival of a new message and upon detecting an event of this kind, prints out the message class of the message.</span></span> 
  
```cpp
if (pNotif -> ulEventType == fnevNewMail)
{
printf("%s\n", pNotif -> newmail.lpszMessageClass)
}

```

<span data-ttu-id="afe7e-151">有关通知的详细信息，请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="afe7e-151">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="afe7e-152">**主题**</span><span class="sxs-lookup"><span data-stu-id="afe7e-152">**Topic**</span></span>|<span data-ttu-id="afe7e-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="afe7e-153">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="afe7e-154">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="afe7e-154">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="afe7e-155">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="afe7e-155">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="afe7e-156">处理通知</span><span class="sxs-lookup"><span data-stu-id="afe7e-156">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="afe7e-157">讨论了客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="afe7e-157">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="afe7e-158">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="afe7e-158">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="afe7e-159">讨论的服务提供程序如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="afe7e-159">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="afe7e-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afe7e-160">See also</span></span>


- [<span data-ttu-id="afe7e-161">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="afe7e-161">ERROR_NOTIFICATION</span></span>](error_notification.md)  
- [<span data-ttu-id="afe7e-162">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="afe7e-162">EXTENDED_NOTIFICATION</span></span>](extended_notification.md)  
- [<span data-ttu-id="afe7e-163">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="afe7e-163">NEWMAIL_NOTIFICATION</span></span>](newmail_notification.md)  
- [<span data-ttu-id="afe7e-164">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="afe7e-164">OBJECT_NOTIFICATION</span></span>](object_notification.md)  
- [<span data-ttu-id="afe7e-165">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="afe7e-165">STATUS_OBJECT_NOTIFICATION</span></span>](status_object_notification.md)  
- [<span data-ttu-id="afe7e-166">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="afe7e-166">TABLE_NOTIFICATION</span></span>](table_notification.md)
- [<span data-ttu-id="afe7e-167">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="afe7e-167">MAPI Structures</span></span>](mapi-structures.md)

