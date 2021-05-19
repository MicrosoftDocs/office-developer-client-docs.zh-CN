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
# <a name="notification"></a><span data-ttu-id="25c43-103">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="25c43-103">NOTIFICATION</span></span>
 
<span data-ttu-id="25c43-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="25c43-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="25c43-105">包含有关已发生事件以及受事件影响的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="25c43-105">Contains information about an event that has occurred and the data that has been affected by the event.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="25c43-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="25c43-106">Header file:</span></span>  <br/> |<span data-ttu-id="25c43-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="25c43-107">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="25c43-108">Members</span><span class="sxs-lookup"><span data-stu-id="25c43-108">Members</span></span>

<span data-ttu-id="25c43-109">**ulEventType**</span><span class="sxs-lookup"><span data-stu-id="25c43-109">**ulEventType**</span></span>
  
> <span data-ttu-id="25c43-110">发生的通知事件的类型。</span><span class="sxs-lookup"><span data-stu-id="25c43-110">Type of notification event that occurred.</span></span> <span data-ttu-id="25c43-111">**ulEventType** 成员的值对应于信息联合 **中包含的结构。**</span><span class="sxs-lookup"><span data-stu-id="25c43-111">The value of the **ulEventType** member corresponds to the structure that is included in the **info** union.</span></span> <span data-ttu-id="25c43-112">**ulEventType** 成员可以设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="25c43-112">The **ulEventType** member can be set to one of the following values:</span></span> 
    
 <span data-ttu-id="25c43-113">_fnevCriticalError_</span><span class="sxs-lookup"><span data-stu-id="25c43-113">_fnevCriticalError_</span></span>
  
> <span data-ttu-id="25c43-114">发生全局错误，例如会话正在关闭。</span><span class="sxs-lookup"><span data-stu-id="25c43-114">A global error has occurred, such as a session shut down in progress.</span></span> <span data-ttu-id="25c43-115">信息 **成员**[包含ERROR_NOTIFICATION结构](error_notification.md)。</span><span class="sxs-lookup"><span data-stu-id="25c43-115">The **info** member contains an [ERROR_NOTIFICATION](error_notification.md) structure.</span></span> 
    
 <span data-ttu-id="25c43-116">_fnevExtended_</span><span class="sxs-lookup"><span data-stu-id="25c43-116">_fnevExtended_</span></span>
  
> <span data-ttu-id="25c43-117">发生了由特定服务提供商定义的内部事件。</span><span class="sxs-lookup"><span data-stu-id="25c43-117">An internal event defined by a particular service provider has occurred.</span></span> <span data-ttu-id="25c43-118">信息 **成员**[包含EXTENDED_NOTIFICATION结构](extended_notification.md)。</span><span class="sxs-lookup"><span data-stu-id="25c43-118">The **info** member contains an [EXTENDED_NOTIFICATION](extended_notification.md) structure.</span></span> 
    
 <span data-ttu-id="25c43-119">_fnevNewMail_</span><span class="sxs-lookup"><span data-stu-id="25c43-119">_fnevNewMail_</span></span>
  
> <span data-ttu-id="25c43-120">邮件已传递到邮件类相应的接收文件夹，正在等待处理。</span><span class="sxs-lookup"><span data-stu-id="25c43-120">A message has been delivered to the appropriate receive folder for the message class and is waiting to be processed.</span></span> <span data-ttu-id="25c43-121">信息 **成员**[包含NEWMAIL_NOTIFICATION结构](newmail_notification.md)。</span><span class="sxs-lookup"><span data-stu-id="25c43-121">The **info** member contains an [NEWMAIL_NOTIFICATION](newmail_notification.md) structure.</span></span> 
    
 <span data-ttu-id="25c43-122">_fnevObjectCopied_</span><span class="sxs-lookup"><span data-stu-id="25c43-122">_fnevObjectCopied_</span></span>
  
> <span data-ttu-id="25c43-123">已复制 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="25c43-123">A MAPI object has been copied.</span></span> <span data-ttu-id="25c43-124">**信息** 成员 [包含OBJECT_NOTIFICATION结构](object_notification.md)。</span><span class="sxs-lookup"><span data-stu-id="25c43-124">The **info** member contains an [OBJECT_NOTIFICATION](object_notification.md) structure.</span></span> 
    
 <span data-ttu-id="25c43-125">_fnevObjectCreated_</span><span class="sxs-lookup"><span data-stu-id="25c43-125">_fnevObjectCreated_</span></span>
  
> <span data-ttu-id="25c43-126">已创建 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="25c43-126">A MAPI object has been created.</span></span> <span data-ttu-id="25c43-127">**信息** 成员 **包含OBJECT_NOTIFICATION结构**。</span><span class="sxs-lookup"><span data-stu-id="25c43-127">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="25c43-128">_fnevObjectDeleted_</span><span class="sxs-lookup"><span data-stu-id="25c43-128">_fnevObjectDeleted_</span></span>
  
> <span data-ttu-id="25c43-129">已删除 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="25c43-129">A MAPI object has been deleted.</span></span> <span data-ttu-id="25c43-130">**信息** 成员 **包含OBJECT_NOTIFICATION结构**。</span><span class="sxs-lookup"><span data-stu-id="25c43-130">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="25c43-131">_fnevObjectModified_</span><span class="sxs-lookup"><span data-stu-id="25c43-131">_fnevObjectModified_</span></span>
  
> <span data-ttu-id="25c43-132">MAPI 对象已更改。</span><span class="sxs-lookup"><span data-stu-id="25c43-132">A MAPI object has changed.</span></span> <span data-ttu-id="25c43-133">**信息** 成员 **包含OBJECT_NOTIFICATION结构**。</span><span class="sxs-lookup"><span data-stu-id="25c43-133">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="25c43-134">_fnevObjectMoved_</span><span class="sxs-lookup"><span data-stu-id="25c43-134">_fnevObjectMoved_</span></span>
  
> <span data-ttu-id="25c43-135">已移动邮件存储或通讯簿对象。</span><span class="sxs-lookup"><span data-stu-id="25c43-135">A message store or address book object has been moved.</span></span> <span data-ttu-id="25c43-136">**信息** 成员 **包含OBJECT_NOTIFICATION结构**。</span><span class="sxs-lookup"><span data-stu-id="25c43-136">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="25c43-137">_fnevSearchComplete_</span><span class="sxs-lookup"><span data-stu-id="25c43-137">_fnevSearchComplete_</span></span>
  
> <span data-ttu-id="25c43-138">搜索操作已完成且结果可用。</span><span class="sxs-lookup"><span data-stu-id="25c43-138">A search operation has finished and the results are available.</span></span> <span data-ttu-id="25c43-139">**信息** 成员 **包含OBJECT_NOTIFICATION结构**。</span><span class="sxs-lookup"><span data-stu-id="25c43-139">The **info** member contains an **OBJECT_NOTIFICATION** structure.</span></span> 
    
 <span data-ttu-id="25c43-140">_fnevTableModified_</span><span class="sxs-lookup"><span data-stu-id="25c43-140">_fnevTableModified_</span></span>
  
> <span data-ttu-id="25c43-141">表中的信息已更改。</span><span class="sxs-lookup"><span data-stu-id="25c43-141">Information in a table has changed.</span></span> <span data-ttu-id="25c43-142">信息 **成员**[包含TABLE_NOTIFICATION结构](table_notification.md)。</span><span class="sxs-lookup"><span data-stu-id="25c43-142">The **info** member contains an [TABLE_NOTIFICATION](table_notification.md) structure.</span></span> 
    
<span data-ttu-id="25c43-143">**info**</span><span class="sxs-lookup"><span data-stu-id="25c43-143">**info**</span></span>
  
> <span data-ttu-id="25c43-144">描述特定类型事件受影响的数据的通知结构联合。</span><span class="sxs-lookup"><span data-stu-id="25c43-144">Union of notification structures describing the affected data for a particular type of event.</span></span> <span data-ttu-id="25c43-145">信息 **成员中包含的结构** 取决于 **ulEventType** 成员的值。</span><span class="sxs-lookup"><span data-stu-id="25c43-145">The structure included in the **info** member depends on the value of the **ulEventType** member.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="25c43-146">备注</span><span class="sxs-lookup"><span data-stu-id="25c43-146">Remarks</span></span>

<span data-ttu-id="25c43-147">每次调用注册的通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法时，一个或多个 **NOTIFICATION** 结构都作为输入参数传递。</span><span class="sxs-lookup"><span data-stu-id="25c43-147">One or more **NOTIFICATION** structures are passed as input parameters with every call to a registered advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="25c43-148">**NOTIFICATION** 结构包含有关已发生特定事件的信息，并描述了受影响的对象。</span><span class="sxs-lookup"><span data-stu-id="25c43-148">The **NOTIFICATION** structures contain information about the particular events that have occurred and describe the affected objects.</span></span> 
  
<span data-ttu-id="25c43-149">在接收通知的客户端或服务提供商可以使用结构处理事件之前，他们必须检查 **ulEventType** 成员中指示的事件类型。</span><span class="sxs-lookup"><span data-stu-id="25c43-149">Before clients or service providers receiving a notification can use the structure to process the event, they must check the event type as indicated in the **ulEventType** member.</span></span> <span data-ttu-id="25c43-150">例如，此处显示的代码示例将检查新邮件的到达时间，在检测到此类事件时，将输出邮件的邮件类别。</span><span class="sxs-lookup"><span data-stu-id="25c43-150">For example, the code sample that is shown here checks for the arrival of a new message and upon detecting an event of this kind, prints out the message class of the message.</span></span> 
  
```cpp
if (pNotif -> ulEventType == fnevNewMail)
{
printf("%s\n", pNotif -> newmail.lpszMessageClass)
}

```

<span data-ttu-id="25c43-151">有关通知详细信息，请参阅下表中介绍的主题。</span><span class="sxs-lookup"><span data-stu-id="25c43-151">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="25c43-152">**主题**</span><span class="sxs-lookup"><span data-stu-id="25c43-152">**Topic**</span></span>|<span data-ttu-id="25c43-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="25c43-153">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="25c43-154">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="25c43-154">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="25c43-155">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="25c43-155">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="25c43-156">处理通知</span><span class="sxs-lookup"><span data-stu-id="25c43-156">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="25c43-157">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="25c43-157">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="25c43-158">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="25c43-158">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="25c43-159">讨论服务提供商如何使用 [IMAPISupport](imapisupportiunknown.md) 方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="25c43-159">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="25c43-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25c43-160">See also</span></span>


- [<span data-ttu-id="25c43-161">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="25c43-161">ERROR_NOTIFICATION</span></span>](error_notification.md)  
- [<span data-ttu-id="25c43-162">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="25c43-162">EXTENDED_NOTIFICATION</span></span>](extended_notification.md)  
- [<span data-ttu-id="25c43-163">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="25c43-163">NEWMAIL_NOTIFICATION</span></span>](newmail_notification.md)  
- [<span data-ttu-id="25c43-164">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="25c43-164">OBJECT_NOTIFICATION</span></span>](object_notification.md)  
- [<span data-ttu-id="25c43-165">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="25c43-165">STATUS_OBJECT_NOTIFICATION</span></span>](status_object_notification.md)  
- [<span data-ttu-id="25c43-166">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="25c43-166">TABLE_NOTIFICATION</span></span>](table_notification.md)
- [<span data-ttu-id="25c43-167">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="25c43-167">MAPI Structures</span></span>](mapi-structures.md)

