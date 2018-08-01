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
ms.openlocfilehash: 5e23d9b829a941e3add8b8d8e137c73052b08aa6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19774904"
---
# <a name="extendednotification"></a><span data-ttu-id="02f11-103">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="02f11-103">EXTENDED_NOTIFICATION</span></span>

  
  
<span data-ttu-id="02f11-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="02f11-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="02f11-105">介绍与服务提供程序特定的事件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="02f11-105">Describes information that relates to an event that is service provider-specific.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="02f11-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="02f11-106">Header file:</span></span>  <br/> |<span data-ttu-id="02f11-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="02f11-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _EXTENDED_NOTIFICATION
{
  ULONG ulEvent;
  ULONG cb;
  LPBYTE pbEventParameters;
} EXTENDED_NOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="02f11-108">Members</span><span class="sxs-lookup"><span data-stu-id="02f11-108">Members</span></span>

 <span data-ttu-id="02f11-109">**ulEvent**</span><span class="sxs-lookup"><span data-stu-id="02f11-109">**ulEvent**</span></span>
  
> <span data-ttu-id="02f11-110">定义服务提供商的扩展的事件代码。</span><span class="sxs-lookup"><span data-stu-id="02f11-110">Extended event code that is defined by the provider.</span></span>
    
 <span data-ttu-id="02f11-111">**cb**</span><span class="sxs-lookup"><span data-stu-id="02f11-111">**cb**</span></span>
  
> <span data-ttu-id="02f11-112">由**pbEventParameters**指向特定于事件的参数中的字节数。</span><span class="sxs-lookup"><span data-stu-id="02f11-112">Count of bytes in the event-specific parameters pointed to by **pbEventParameters**.</span></span> 
    
 <span data-ttu-id="02f11-113">**pbEventParameters**</span><span class="sxs-lookup"><span data-stu-id="02f11-113">**pbEventParameters**</span></span>
  
> <span data-ttu-id="02f11-114">指向特定于事件的参数。</span><span class="sxs-lookup"><span data-stu-id="02f11-114">Pointer to event-specific parameters.</span></span> <span data-ttu-id="02f11-115">使用的参数的类型取决于**ulEvent**成员; 的值这些参数由的提供程序发出事件记录。</span><span class="sxs-lookup"><span data-stu-id="02f11-115">The type of parameters that are used depends on the value of the **ulEvent** member; these parameters are documented by the provider that issued the event.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="02f11-116">说明</span><span class="sxs-lookup"><span data-stu-id="02f11-116">Remarks</span></span>

<span data-ttu-id="02f11-117">**EXTENDED_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。</span><span class="sxs-lookup"><span data-stu-id="02f11-117">The **EXTENDED_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="02f11-118">如果**通知**结构的**信息**成员包含**EXTENDED_NOTIFICATION**结构，**通知**结构的**ulEventType**成员设置为_fnevExtended_。</span><span class="sxs-lookup"><span data-stu-id="02f11-118">When the **info** member of a **NOTIFICATION** structure contains an **EXTENDED_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to  _fnevExtended_.</span></span>
  
<span data-ttu-id="02f11-119">由表示的更改不能包含的任何其他预定义事件类型的服务提供程序定义扩展的事件。</span><span class="sxs-lookup"><span data-stu-id="02f11-119">The extended event is defined by a service provider to represent a type of change that cannot be covered by any of the other predefined events.</span></span> <span data-ttu-id="02f11-120">只有知道他们注册服务提供商支持扩展的事件之前的客户端可以注册的事件。</span><span class="sxs-lookup"><span data-stu-id="02f11-120">Only clients that know before they register that a service provider supports an extended event can register for that event.</span></span> <span data-ttu-id="02f11-121">不能为客户端确定高级不知情的情况下，如果服务提供商支持的扩展的事件。</span><span class="sxs-lookup"><span data-stu-id="02f11-121">It is not possible for clients to determine without advanced knowledge if a service provider supports an extended event.</span></span> <span data-ttu-id="02f11-122">如果服务提供商支持的扩展的事件，它演示如何处理接收时的事件。</span><span class="sxs-lookup"><span data-stu-id="02f11-122">If a service provider supports an extended event, it shows how to handle such an event when it is received.</span></span>
  
<span data-ttu-id="02f11-123">由客户端注销的会话发送一扩展的通知。</span><span class="sxs-lookup"><span data-stu-id="02f11-123">An extended notification is sent by the session when a client logs off.</span></span> <span data-ttu-id="02f11-124">通过调用不带_lpEntryID_参数设置为 NULL 和_cbEntryID_参数设置为零[IMAPISession::Advise](imapisession-advise.md)注册此通知。</span><span class="sxs-lookup"><span data-stu-id="02f11-124">Register for this notification by calling [IMAPISession::Advise](imapisession-advise.md) with the  _lpEntryID_ parameter set to NULL and the  _cbEntryID_ parameter set to zero.</span></span> 
  
<span data-ttu-id="02f11-125">有关通知的详细信息，请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="02f11-125">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="02f11-126">**主题**</span><span class="sxs-lookup"><span data-stu-id="02f11-126">**Topic**</span></span>|<span data-ttu-id="02f11-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="02f11-127">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="02f11-128">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="02f11-128">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="02f11-129">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="02f11-129">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="02f11-130">处理通知</span><span class="sxs-lookup"><span data-stu-id="02f11-130">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="02f11-131">讨论了客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="02f11-131">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="02f11-132">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="02f11-132">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="02f11-133">讨论的服务提供程序如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="02f11-133">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) methods to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="02f11-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02f11-134">See also</span></span>



[<span data-ttu-id="02f11-135">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="02f11-135">NOTIFICATION</span></span>](notification.md)


[<span data-ttu-id="02f11-136">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="02f11-136">MAPI Structures</span></span>](mapi-structures.md)

