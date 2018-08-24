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
ms.openlocfilehash: de9b5e377840b1fbfa3b6dd73fd952c0c72efeb7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580640"
---
# <a name="extendednotification"></a><span data-ttu-id="29cca-103">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="29cca-103">EXTENDED_NOTIFICATION</span></span>

  
  
<span data-ttu-id="29cca-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29cca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29cca-105">介绍与服务提供程序特定的事件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="29cca-105">Describes information that relates to an event that is service provider-specific.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="29cca-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="29cca-106">Header file:</span></span>  <br/> |<span data-ttu-id="29cca-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="29cca-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _EXTENDED_NOTIFICATION
{
  ULONG ulEvent;
  ULONG cb;
  LPBYTE pbEventParameters;
} EXTENDED_NOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="29cca-108">Members</span><span class="sxs-lookup"><span data-stu-id="29cca-108">Members</span></span>

 <span data-ttu-id="29cca-109">**ulEvent**</span><span class="sxs-lookup"><span data-stu-id="29cca-109">**ulEvent**</span></span>
  
> <span data-ttu-id="29cca-110">定义服务提供商的扩展的事件代码。</span><span class="sxs-lookup"><span data-stu-id="29cca-110">Extended event code that is defined by the provider.</span></span>
    
 <span data-ttu-id="29cca-111">**cb**</span><span class="sxs-lookup"><span data-stu-id="29cca-111">**cb**</span></span>
  
> <span data-ttu-id="29cca-112">由**pbEventParameters**指向特定于事件的参数中的字节数。</span><span class="sxs-lookup"><span data-stu-id="29cca-112">Count of bytes in the event-specific parameters pointed to by **pbEventParameters**.</span></span> 
    
 <span data-ttu-id="29cca-113">**pbEventParameters**</span><span class="sxs-lookup"><span data-stu-id="29cca-113">**pbEventParameters**</span></span>
  
> <span data-ttu-id="29cca-114">指向特定于事件的参数。</span><span class="sxs-lookup"><span data-stu-id="29cca-114">Pointer to event-specific parameters.</span></span> <span data-ttu-id="29cca-115">使用的参数的类型取决于**ulEvent**成员; 的值这些参数由的提供程序发出事件记录。</span><span class="sxs-lookup"><span data-stu-id="29cca-115">The type of parameters that are used depends on the value of the **ulEvent** member; these parameters are documented by the provider that issued the event.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="29cca-116">注解</span><span class="sxs-lookup"><span data-stu-id="29cca-116">Remarks</span></span>

<span data-ttu-id="29cca-117">**EXTENDED_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。</span><span class="sxs-lookup"><span data-stu-id="29cca-117">The **EXTENDED_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="29cca-118">如果**通知**结构的**信息**成员包含**EXTENDED_NOTIFICATION**结构，**通知**结构的**ulEventType**成员设置为_fnevExtended_。</span><span class="sxs-lookup"><span data-stu-id="29cca-118">When the **info** member of a **NOTIFICATION** structure contains an **EXTENDED_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to  _fnevExtended_.</span></span>
  
<span data-ttu-id="29cca-119">由表示的更改不能包含的任何其他预定义事件类型的服务提供程序定义扩展的事件。</span><span class="sxs-lookup"><span data-stu-id="29cca-119">The extended event is defined by a service provider to represent a type of change that cannot be covered by any of the other predefined events.</span></span> <span data-ttu-id="29cca-120">只有知道他们注册服务提供商支持扩展的事件之前的客户端可以注册的事件。</span><span class="sxs-lookup"><span data-stu-id="29cca-120">Only clients that know before they register that a service provider supports an extended event can register for that event.</span></span> <span data-ttu-id="29cca-121">不能为客户端确定高级不知情的情况下，如果服务提供商支持的扩展的事件。</span><span class="sxs-lookup"><span data-stu-id="29cca-121">It is not possible for clients to determine without advanced knowledge if a service provider supports an extended event.</span></span> <span data-ttu-id="29cca-122">如果服务提供商支持的扩展的事件，它演示如何处理接收时的事件。</span><span class="sxs-lookup"><span data-stu-id="29cca-122">If a service provider supports an extended event, it shows how to handle such an event when it is received.</span></span>
  
<span data-ttu-id="29cca-123">由客户端注销的会话发送一扩展的通知。</span><span class="sxs-lookup"><span data-stu-id="29cca-123">An extended notification is sent by the session when a client logs off.</span></span> <span data-ttu-id="29cca-124">通过调用不带_lpEntryID_参数设置为 NULL 和_cbEntryID_参数设置为零[IMAPISession::Advise](imapisession-advise.md)注册此通知。</span><span class="sxs-lookup"><span data-stu-id="29cca-124">Register for this notification by calling [IMAPISession::Advise](imapisession-advise.md) with the  _lpEntryID_ parameter set to NULL and the  _cbEntryID_ parameter set to zero.</span></span> 
  
<span data-ttu-id="29cca-125">有关通知的详细信息，请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="29cca-125">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="29cca-126">**主题**</span><span class="sxs-lookup"><span data-stu-id="29cca-126">**Topic**</span></span>|<span data-ttu-id="29cca-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="29cca-127">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="29cca-128">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="29cca-128">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="29cca-129">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="29cca-129">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="29cca-130">处理通知</span><span class="sxs-lookup"><span data-stu-id="29cca-130">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="29cca-131">讨论了客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="29cca-131">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="29cca-132">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="29cca-132">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="29cca-133">讨论的服务提供程序如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="29cca-133">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) methods to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="29cca-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29cca-134">See also</span></span>



[<span data-ttu-id="29cca-135">通知</span><span class="sxs-lookup"><span data-stu-id="29cca-135">NOTIFICATION</span></span>](notification.md)


[<span data-ttu-id="29cca-136">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="29cca-136">MAPI Structures</span></span>](mapi-structures.md)

