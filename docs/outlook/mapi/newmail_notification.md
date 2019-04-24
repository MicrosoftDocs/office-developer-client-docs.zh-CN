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
ms.openlocfilehash: 25af1c1b05618d4f36a43721e71be6ff5c7c597f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326241"
---
# <a name="newmailnotification"></a><span data-ttu-id="107b7-103">NEWMAIL_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="107b7-103">NEWMAIL_NOTIFICATION</span></span>

  
  
<span data-ttu-id="107b7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="107b7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="107b7-105">介绍与新邮件到达相关的信息。</span><span class="sxs-lookup"><span data-stu-id="107b7-105">Describes information that relate to the arrival of a new message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="107b7-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="107b7-106">Header file:</span></span>  <br/> |<span data-ttu-id="107b7-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="107b7-107">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="107b7-108">Members</span><span class="sxs-lookup"><span data-stu-id="107b7-108">Members</span></span>

 <span data-ttu-id="107b7-109">**cbEntryID**</span><span class="sxs-lookup"><span data-stu-id="107b7-109">**cbEntryID**</span></span>
  
> <span data-ttu-id="107b7-110">由**lpEntryID**成员指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="107b7-110">Count of bytes in the entry identifier pointed to by the **lpEntryID** member.</span></span> 
    
 <span data-ttu-id="107b7-111">**lpEntryID**</span><span class="sxs-lookup"><span data-stu-id="107b7-111">**lpEntryID**</span></span>
  
> <span data-ttu-id="107b7-112">指向新到达的邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="107b7-112">Pointer to the entry identifier of the newly arrived message.</span></span>
    
 <span data-ttu-id="107b7-113">**cbParentID**</span><span class="sxs-lookup"><span data-stu-id="107b7-113">**cbParentID**</span></span>
  
> <span data-ttu-id="107b7-114">由**lpParentID**成员指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="107b7-114">Count of bytes in the entry identifier pointed to by the **lpParentID** member.</span></span> 
    
 <span data-ttu-id="107b7-115">**lpParentID**</span><span class="sxs-lookup"><span data-stu-id="107b7-115">**lpParentID**</span></span>
  
> <span data-ttu-id="107b7-116">指向接收文件夹的新到达邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="107b7-116">Pointer to the entry identifier of the receive folder for the newly arrived message.</span></span>
    
 <span data-ttu-id="107b7-117">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="107b7-117">**ulFlags**</span></span>
  
> <span data-ttu-id="107b7-118">标志的位掩码, 用于描述邮件中包含的字符串属性的格式。</span><span class="sxs-lookup"><span data-stu-id="107b7-118">Bitmask of flags used to describe the format of the string properties included with the message.</span></span> <span data-ttu-id="107b7-119">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="107b7-119">The following flag can be set:</span></span>
    
<span data-ttu-id="107b7-120">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="107b7-120">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="107b7-121">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="107b7-121">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="107b7-122">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="107b7-122">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="107b7-123">**lpszMessageClass**</span><span class="sxs-lookup"><span data-stu-id="107b7-123">**lpszMessageClass**</span></span>
  
> <span data-ttu-id="107b7-124">指向新到达的邮件的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="107b7-124">Pointer to the message class of the newly arrived message.</span></span> 
    
 <span data-ttu-id="107b7-125">**ulMessageFlags**</span><span class="sxs-lookup"><span data-stu-id="107b7-125">**ulMessageFlags**</span></span>
  
> <span data-ttu-id="107b7-126">描述新到达的邮件的当前状态的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="107b7-126">Bitmask of flags that describes the current state of the newly arrived message.</span></span> <span data-ttu-id="107b7-127">**ulMessageFlags**成员是邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性的副本。</span><span class="sxs-lookup"><span data-stu-id="107b7-127">The **ulMessageFlags** member is a copy of the message's **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="107b7-128">注解</span><span class="sxs-lookup"><span data-stu-id="107b7-128">Remarks</span></span>

<span data-ttu-id="107b7-129">**NEWMAIL_NOTIFICATION**结构是[通知](notification.md)结构的**info**成员中包含的结构联合的成员之一。</span><span class="sxs-lookup"><span data-stu-id="107b7-129">The **NEWMAIL_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="107b7-130">当**通知**结构的**info**成员包含**NEWMAIL_NOTIFICATION**结构时,**通知**结构的**ulEventType**成员将设置为_fnevNewMail。_</span><span class="sxs-lookup"><span data-stu-id="107b7-130">When the **info** member of a **NOTIFICATION** structure contains a **NEWMAIL_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to  _fnevNewMail._</span></span>
  
<span data-ttu-id="107b7-131">MAPI 使用**NEWMAIL_NOTIFICATION**结构作为**通知**结构的成员, 其中包含有关通知接收器通知事件的信息。</span><span class="sxs-lookup"><span data-stu-id="107b7-131">MAPI uses the **NEWMAIL_NOTIFICATION** structure only as a member of the **NOTIFICATION** structure, which holds information about a notification event for the advise sink.</span></span> 
  
<span data-ttu-id="107b7-132">有关通知的详细信息, 请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="107b7-132">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="107b7-133">**主题**</span><span class="sxs-lookup"><span data-stu-id="107b7-133">**Topic**</span></span>|<span data-ttu-id="107b7-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="107b7-134">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="107b7-135">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="107b7-135">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="107b7-136">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="107b7-136">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="107b7-137">处理通知</span><span class="sxs-lookup"><span data-stu-id="107b7-137">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="107b7-138">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="107b7-138">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="107b7-139">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="107b7-139">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="107b7-140">讨论了如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="107b7-140">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="107b7-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="107b7-141">See also</span></span>



[<span data-ttu-id="107b7-142">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="107b7-142">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="107b7-143">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="107b7-143">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)


[<span data-ttu-id="107b7-144">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="107b7-144">MAPI Structures</span></span>](mapi-structures.md)

