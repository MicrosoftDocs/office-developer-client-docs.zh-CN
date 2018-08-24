---
title: NEWMAIL_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.NEWMAIL_NOTIFICATION
api_type:
- COM
ms.assetid: 49913050-900a-4b05-84c4-c596a93ce68b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 779585f73a7032ae0259b30ebfc16868c733c7fc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569510"
---
# <a name="newmailnotification"></a><span data-ttu-id="aab05-103">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="aab05-103">NEWMAIL_NOTIFICATION</span></span>

  
  
<span data-ttu-id="aab05-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aab05-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aab05-105">介绍与新消息的到达相关的信息。</span><span class="sxs-lookup"><span data-stu-id="aab05-105">Describes information that relate to the arrival of a new message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aab05-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="aab05-106">Header file:</span></span>  <br/> |<span data-ttu-id="aab05-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="aab05-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _NEWMAIL_NOTIFICATION
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  ULONG cbParentID;
  LPENTRYID lpParentID;
  ULONG ulFlags;
  LPSTR lpszMessageClass;
  ULONG ulMessageFlags;
} NEWMAIL_NOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="aab05-108">Members</span><span class="sxs-lookup"><span data-stu-id="aab05-108">Members</span></span>

 <span data-ttu-id="aab05-109">**cbEntryID**</span><span class="sxs-lookup"><span data-stu-id="aab05-109">**cbEntryID**</span></span>
  
> <span data-ttu-id="aab05-110">由**lpEntryID**成员指向中的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="aab05-110">Count of bytes in the entry identifier pointed to by the **lpEntryID** member.</span></span> 
    
 <span data-ttu-id="aab05-111">**lpEntryID**</span><span class="sxs-lookup"><span data-stu-id="aab05-111">**lpEntryID**</span></span>
  
> <span data-ttu-id="aab05-112">为新到达消息的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="aab05-112">Pointer to the entry identifier of the newly arrived message.</span></span>
    
 <span data-ttu-id="aab05-113">**cbParentID**</span><span class="sxs-lookup"><span data-stu-id="aab05-113">**cbParentID**</span></span>
  
> <span data-ttu-id="aab05-114">由**lpParentID**成员指向中的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="aab05-114">Count of bytes in the entry identifier pointed to by the **lpParentID** member.</span></span> 
    
 <span data-ttu-id="aab05-115">**lpParentID**</span><span class="sxs-lookup"><span data-stu-id="aab05-115">**lpParentID**</span></span>
  
> <span data-ttu-id="aab05-116">为新到达消息的接收文件夹的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="aab05-116">Pointer to the entry identifier of the receive folder for the newly arrived message.</span></span>
    
 <span data-ttu-id="aab05-117">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="aab05-117">**ulFlags**</span></span>
  
> <span data-ttu-id="aab05-118">用于描述消息中包含的字符串属性的格式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="aab05-118">Bitmask of flags used to describe the format of the string properties included with the message.</span></span> <span data-ttu-id="aab05-119">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="aab05-119">The following flag can be set:</span></span>
    
<span data-ttu-id="aab05-120">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="aab05-120">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="aab05-121">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="aab05-121">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="aab05-122">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="aab05-122">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="aab05-123">**lpszMessageClass**</span><span class="sxs-lookup"><span data-stu-id="aab05-123">**lpszMessageClass**</span></span>
  
> <span data-ttu-id="aab05-124">向新到达消息的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="aab05-124">Pointer to the message class of the newly arrived message.</span></span> 
    
 <span data-ttu-id="aab05-125">**ulMessageFlags**</span><span class="sxs-lookup"><span data-stu-id="aab05-125">**ulMessageFlags**</span></span>
  
> <span data-ttu-id="aab05-126">位掩码的标志，描述新到达消息的当前状态。</span><span class="sxs-lookup"><span data-stu-id="aab05-126">Bitmask of flags that describes the current state of the newly arrived message.</span></span> <span data-ttu-id="aab05-127">**UlMessageFlags**成员是**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 消息的副本。</span><span class="sxs-lookup"><span data-stu-id="aab05-127">The **ulMessageFlags** member is a copy of the message's **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="aab05-128">注解</span><span class="sxs-lookup"><span data-stu-id="aab05-128">Remarks</span></span>

<span data-ttu-id="aab05-129">**NEWMAIL_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。</span><span class="sxs-lookup"><span data-stu-id="aab05-129">The **NEWMAIL_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="aab05-130">**通知**结构的**ulEventType**成员时**通知**结构的**信息**成员包含**NEWMAIL_NOTIFICATION**结构，设置为_fnevNewMail。_</span><span class="sxs-lookup"><span data-stu-id="aab05-130">When the **info** member of a **NOTIFICATION** structure contains a **NEWMAIL_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to  _fnevNewMail._</span></span>
  
<span data-ttu-id="aab05-131">MAPI 仅将**NEWMAIL_NOTIFICATION**结构用作**通知**结构，其中包含有关通知事件的通知接收器的信息中的成员。</span><span class="sxs-lookup"><span data-stu-id="aab05-131">MAPI uses the **NEWMAIL_NOTIFICATION** structure only as a member of the **NOTIFICATION** structure, which holds information about a notification event for the advise sink.</span></span> 
  
<span data-ttu-id="aab05-132">有关通知的详细信息，请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="aab05-132">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="aab05-133">**主题**</span><span class="sxs-lookup"><span data-stu-id="aab05-133">**Topic**</span></span>|<span data-ttu-id="aab05-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="aab05-134">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="aab05-135">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="aab05-135">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="aab05-136">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="aab05-136">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="aab05-137">处理通知</span><span class="sxs-lookup"><span data-stu-id="aab05-137">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="aab05-138">讨论了客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="aab05-138">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="aab05-139">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="aab05-139">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="aab05-140">讨论的服务提供程序如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="aab05-140">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="aab05-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aab05-141">See also</span></span>



[<span data-ttu-id="aab05-142">通知</span><span class="sxs-lookup"><span data-stu-id="aab05-142">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="aab05-143">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="aab05-143">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)


[<span data-ttu-id="aab05-144">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="aab05-144">MAPI Structures</span></span>](mapi-structures.md)

