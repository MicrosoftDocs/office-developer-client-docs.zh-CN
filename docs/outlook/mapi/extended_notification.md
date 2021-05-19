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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415717"
---
# <a name="extended_notification"></a><span data-ttu-id="5696f-103">EXTENDED_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="5696f-103">EXTENDED_NOTIFICATION</span></span>

  
  
<span data-ttu-id="5696f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5696f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5696f-105">描述与特定于服务提供商的事件相关的信息。</span><span class="sxs-lookup"><span data-stu-id="5696f-105">Describes information that relates to an event that is service provider-specific.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5696f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="5696f-106">Header file:</span></span>  <br/> |<span data-ttu-id="5696f-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5696f-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _EXTENDED_NOTIFICATION
{
  ULONG ulEvent;
  ULONG cb;
  LPBYTE pbEventParameters;
} EXTENDED_NOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="5696f-108">Members</span><span class="sxs-lookup"><span data-stu-id="5696f-108">Members</span></span>

 <span data-ttu-id="5696f-109">**ulEvent**</span><span class="sxs-lookup"><span data-stu-id="5696f-109">**ulEvent**</span></span>
  
> <span data-ttu-id="5696f-110">提供程序定义的扩展事件代码。</span><span class="sxs-lookup"><span data-stu-id="5696f-110">Extended event code that is defined by the provider.</span></span>
    
 <span data-ttu-id="5696f-111">**cb**</span><span class="sxs-lookup"><span data-stu-id="5696f-111">**cb**</span></span>
  
> <span data-ttu-id="5696f-112">**pbEventParameters** 指向的事件特定参数中的字节数。</span><span class="sxs-lookup"><span data-stu-id="5696f-112">Count of bytes in the event-specific parameters pointed to by **pbEventParameters**.</span></span> 
    
 <span data-ttu-id="5696f-113">**pbEventParameters**</span><span class="sxs-lookup"><span data-stu-id="5696f-113">**pbEventParameters**</span></span>
  
> <span data-ttu-id="5696f-114">指向特定于事件的参数的指针。</span><span class="sxs-lookup"><span data-stu-id="5696f-114">Pointer to event-specific parameters.</span></span> <span data-ttu-id="5696f-115">使用的参数类型取决于 **ulEvent 成员** 的值;这些参数由发出事件的提供程序记录。</span><span class="sxs-lookup"><span data-stu-id="5696f-115">The type of parameters that are used depends on the value of the **ulEvent** member; these parameters are documented by the provider that issued the event.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="5696f-116">备注</span><span class="sxs-lookup"><span data-stu-id="5696f-116">Remarks</span></span>

<span data-ttu-id="5696f-117">the **EXTENDED_NOTIFICATION** structure is one of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span><span class="sxs-lookup"><span data-stu-id="5696f-117">The **EXTENDED_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="5696f-118">当 **NOTIFICATION** 结构的信息成员包含一个 EXTENDED_NOTIFICATION **结构时\*\*\*\*，NOTIFICATION** 结构的 **ulEventType** 成员将设置为 _fnevExtended_。</span><span class="sxs-lookup"><span data-stu-id="5696f-118">When the **info** member of a **NOTIFICATION** structure contains an **EXTENDED_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to  _fnevExtended_.</span></span>
  
<span data-ttu-id="5696f-119">扩展事件由服务提供商定义，以表示任何其他预定义事件无法覆盖的一种更改类型。</span><span class="sxs-lookup"><span data-stu-id="5696f-119">The extended event is defined by a service provider to represent a type of change that cannot be covered by any of the other predefined events.</span></span> <span data-ttu-id="5696f-120">只有先知道服务提供程序支持扩展事件的客户端才能注册该事件。</span><span class="sxs-lookup"><span data-stu-id="5696f-120">Only clients that know before they register that a service provider supports an extended event can register for that event.</span></span> <span data-ttu-id="5696f-121">客户端无法在没有高级知识的情况下确定服务提供商是否支持扩展事件。</span><span class="sxs-lookup"><span data-stu-id="5696f-121">It is not possible for clients to determine without advanced knowledge if a service provider supports an extended event.</span></span> <span data-ttu-id="5696f-122">如果服务提供商支持扩展事件，则说明当收到该事件时如何处理该事件。</span><span class="sxs-lookup"><span data-stu-id="5696f-122">If a service provider supports an extended event, it shows how to handle such an event when it is received.</span></span>
  
<span data-ttu-id="5696f-123">客户端注销时，会话将发送扩展通知。</span><span class="sxs-lookup"><span data-stu-id="5696f-123">An extended notification is sent by the session when a client logs off.</span></span> <span data-ttu-id="5696f-124">通过调用 [IMAPISession：：Advise](imapisession-advise.md) 注册此通知，  _同时将 lpEntryID_ 参数设置为  _NULL，cbEntryID_ 参数设置为零。</span><span class="sxs-lookup"><span data-stu-id="5696f-124">Register for this notification by calling [IMAPISession::Advise](imapisession-advise.md) with the  _lpEntryID_ parameter set to NULL and the  _cbEntryID_ parameter set to zero.</span></span> 
  
<span data-ttu-id="5696f-125">有关通知详细信息，请参阅下表中介绍的主题。</span><span class="sxs-lookup"><span data-stu-id="5696f-125">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="5696f-126">**主题**</span><span class="sxs-lookup"><span data-stu-id="5696f-126">**Topic**</span></span>|<span data-ttu-id="5696f-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="5696f-127">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5696f-128">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="5696f-128">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="5696f-129">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="5696f-129">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="5696f-130">处理通知</span><span class="sxs-lookup"><span data-stu-id="5696f-130">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="5696f-131">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="5696f-131">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="5696f-132">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="5696f-132">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="5696f-133">讨论服务提供商如何使用 [IMAPISupport](imapisupportiunknown.md) 方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="5696f-133">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) methods to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5696f-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5696f-134">See also</span></span>



[<span data-ttu-id="5696f-135">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="5696f-135">NOTIFICATION</span></span>](notification.md)


[<span data-ttu-id="5696f-136">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="5696f-136">MAPI Structures</span></span>](mapi-structures.md)

