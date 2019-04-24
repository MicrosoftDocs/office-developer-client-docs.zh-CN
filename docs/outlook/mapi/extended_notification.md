---
title: EXTENDED_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.EXTENDED_NOTIFICATION
api_type:
- COM
ms.assetid: f01fce7b-a038-4002-8bad-0e6a51ae9d05
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8b49d0b80102f6295f3f717fb123a6581854d5a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341116"
---
# <a name="extendednotification"></a><span data-ttu-id="aa451-103">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="aa451-103">EXTENDED_NOTIFICATION</span></span>

  
  
<span data-ttu-id="aa451-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa451-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa451-105">介绍与特定于服务提供程序的事件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="aa451-105">Describes information that relates to an event that is service provider-specific.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aa451-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="aa451-106">Header file:</span></span>  <br/> |<span data-ttu-id="aa451-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="aa451-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _EXTENDED_NOTIFICATION
{
  ULONG ulEvent;
  ULONG cb;
  LPBYTE pbEventParameters;
} EXTENDED_NOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="aa451-108">Members</span><span class="sxs-lookup"><span data-stu-id="aa451-108">Members</span></span>

 <span data-ttu-id="aa451-109">**ulEvent**</span><span class="sxs-lookup"><span data-stu-id="aa451-109">**ulEvent**</span></span>
  
> <span data-ttu-id="aa451-110">由提供程序定义的扩展事件代码。</span><span class="sxs-lookup"><span data-stu-id="aa451-110">Extended event code that is defined by the provider.</span></span>
    
 <span data-ttu-id="aa451-111">**cb**</span><span class="sxs-lookup"><span data-stu-id="aa451-111">**cb**</span></span>
  
> <span data-ttu-id="aa451-112">由**pbEventParameters**指向的事件特定参数中的字节数。</span><span class="sxs-lookup"><span data-stu-id="aa451-112">Count of bytes in the event-specific parameters pointed to by **pbEventParameters**.</span></span> 
    
 <span data-ttu-id="aa451-113">**pbEventParameters**</span><span class="sxs-lookup"><span data-stu-id="aa451-113">**pbEventParameters**</span></span>
  
> <span data-ttu-id="aa451-114">指向事件特定参数的指针。</span><span class="sxs-lookup"><span data-stu-id="aa451-114">Pointer to event-specific parameters.</span></span> <span data-ttu-id="aa451-115">使用的参数类型取决于**ulEvent**成员的值;这些参数由发出事件的提供程序记录。</span><span class="sxs-lookup"><span data-stu-id="aa451-115">The type of parameters that are used depends on the value of the **ulEvent** member; these parameters are documented by the provider that issued the event.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="aa451-116">注解</span><span class="sxs-lookup"><span data-stu-id="aa451-116">Remarks</span></span>

<span data-ttu-id="aa451-117">**EXTENDED_NOTIFICATION**结构是[通知](notification.md)结构的**info**成员中包含的结构联合的成员之一。</span><span class="sxs-lookup"><span data-stu-id="aa451-117">The **EXTENDED_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="aa451-118">当**通知**结构的**info**成员包含**EXTENDED_NOTIFICATION**结构时,**通知**结构的**ulEventType**成员将设置为_fnevExtended_。</span><span class="sxs-lookup"><span data-stu-id="aa451-118">When the **info** member of a **NOTIFICATION** structure contains an **EXTENDED_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to  _fnevExtended_.</span></span>
  
<span data-ttu-id="aa451-119">扩展事件由服务提供程序定义, 以表示不能由任何其他预定义事件覆盖的更改类型。</span><span class="sxs-lookup"><span data-stu-id="aa451-119">The extended event is defined by a service provider to represent a type of change that cannot be covered by any of the other predefined events.</span></span> <span data-ttu-id="aa451-120">只有在注册服务提供程序之前知道的客户端支持扩展事件才能为该事件注册。</span><span class="sxs-lookup"><span data-stu-id="aa451-120">Only clients that know before they register that a service provider supports an extended event can register for that event.</span></span> <span data-ttu-id="aa451-121">如果服务提供程序支持一个扩展事件, 则客户端不能确定没有高级知识的情况。</span><span class="sxs-lookup"><span data-stu-id="aa451-121">It is not possible for clients to determine without advanced knowledge if a service provider supports an extended event.</span></span> <span data-ttu-id="aa451-122">如果服务提供程序支持一个扩展事件, 它将显示如何在收到此类事件时对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="aa451-122">If a service provider supports an extended event, it shows how to handle such an event when it is received.</span></span>
  
<span data-ttu-id="aa451-123">当客户端注销时, 会话将发送一个扩展通知。</span><span class="sxs-lookup"><span data-stu-id="aa451-123">An extended notification is sent by the session when a client logs off.</span></span> <span data-ttu-id="aa451-124">通过调用[IMAPISession:: 建议](imapisession-advise.md)将_lpEntryID_参数设置为 NULL 并将_cbEntryID_参数设置为零, 注册此通知。</span><span class="sxs-lookup"><span data-stu-id="aa451-124">Register for this notification by calling [IMAPISession::Advise](imapisession-advise.md) with the  _lpEntryID_ parameter set to NULL and the  _cbEntryID_ parameter set to zero.</span></span> 
  
<span data-ttu-id="aa451-125">有关通知的详细信息, 请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="aa451-125">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="aa451-126">**主题**</span><span class="sxs-lookup"><span data-stu-id="aa451-126">**Topic**</span></span>|<span data-ttu-id="aa451-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa451-127">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="aa451-128">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="aa451-128">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="aa451-129">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="aa451-129">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="aa451-130">处理通知</span><span class="sxs-lookup"><span data-stu-id="aa451-130">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="aa451-131">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="aa451-131">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="aa451-132">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="aa451-132">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="aa451-133">讨论了如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="aa451-133">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) methods to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="aa451-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa451-134">See also</span></span>



[<span data-ttu-id="aa451-135">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="aa451-135">NOTIFICATION</span></span>](notification.md)


[<span data-ttu-id="aa451-136">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="aa451-136">MAPI Structures</span></span>](mapi-structures.md)

