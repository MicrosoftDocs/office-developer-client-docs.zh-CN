---
title: ERROR_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ERROR_NOTIFICATION
api_type:
- COM
ms.assetid: 6c5bb383-f8e2-4d79-bcf2-aa86c130e8b1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f8d4fb6b8cd7ad0ebf1e7660a0f3c0602274fa10
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335733"
---
# <a name="errornotification"></a><span data-ttu-id="dbf4a-103">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="dbf4a-103">ERROR_NOTIFICATION</span></span>

  
  
<span data-ttu-id="dbf4a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dbf4a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dbf4a-105">介绍与严重错误相关的信息。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-105">Describes information that relate to a critical error.</span></span> <span data-ttu-id="dbf4a-106">这将导致生成错误通知。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-106">This causes an error notification to be generated.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dbf4a-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="dbf4a-107">Header file:</span></span>  <br/> |<span data-ttu-id="dbf4a-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="dbf4a-108">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _ERROR_NOTIFICATION
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  SCODE scode;
  ULONG ulFlags;
  LPMAPIERROR lpMAPIError;
} ERROR_NOTIFICATION;
```

## <a name="members"></a><span data-ttu-id="dbf4a-109">Members</span><span class="sxs-lookup"><span data-stu-id="dbf4a-109">Members</span></span>

 <span data-ttu-id="dbf4a-110">**cbEntryID**</span><span class="sxs-lookup"><span data-stu-id="dbf4a-110">**cbEntryID**</span></span>
  
> <span data-ttu-id="dbf4a-111">由**lpEntryID**指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-111">Count of bytes in the entry identifier pointed to by **lpEntryID**.</span></span> 
    
 <span data-ttu-id="dbf4a-112">**lpEntryID**</span><span class="sxs-lookup"><span data-stu-id="dbf4a-112">**lpEntryID**</span></span>
  
> <span data-ttu-id="dbf4a-113">指向导致错误的对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-113">Pointer to the entry identifier of the object that causes the error.</span></span>
    
 <span data-ttu-id="dbf4a-114">**scode**</span><span class="sxs-lookup"><span data-stu-id="dbf4a-114">**scode**</span></span>
  
> <span data-ttu-id="dbf4a-115">严重错误的错误值。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-115">Error value for the critical error.</span></span> 
    
 <span data-ttu-id="dbf4a-116">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="dbf4a-116">**ulFlags**</span></span>
  
> <span data-ttu-id="dbf4a-117">标志的位掩码, 用于指定由**lpMAPIError**指向的结构中的**lpszError**成员所指向的文本的格式。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-117">Bitmask of flags used to designate the format of the text pointed to by the **lpszError** member in the structure pointed to by **lpMAPIError**.</span></span> <span data-ttu-id="dbf4a-118">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="dbf4a-118">The following flag can be set:</span></span>
    
<span data-ttu-id="dbf4a-119">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="dbf4a-119">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="dbf4a-120">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-120">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="dbf4a-121">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-121">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="dbf4a-122">**lpMAPIError**</span><span class="sxs-lookup"><span data-stu-id="dbf4a-122">**lpMAPIError**</span></span>
  
> <span data-ttu-id="dbf4a-123">指向描述错误的[MAPIERROR](mapierror.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-123">Pointer to a [MAPIERROR](mapierror.md) structure describing the error.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="dbf4a-124">注解</span><span class="sxs-lookup"><span data-stu-id="dbf4a-124">Remarks</span></span>

<span data-ttu-id="dbf4a-125">**ERROR_NOTIFICATION**结构是[通知](notification.md)结构的**info**成员中包含的结构联合的成员之一。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-125">The **ERROR_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="dbf4a-126">当**通知**结构的**info**成员包含**ERROR_NOTIFICATION**结构时,**通知**结构的**ulEventType**成员将设置为_fnevCriticalError_。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-126">When the **info** member of a **NOTIFICATION** structure contains an **ERROR_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to  _fnevCriticalError_.</span></span>
  
<span data-ttu-id="dbf4a-127">**cbEntryID**成员和**lpEntryID**成员的值可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-127">The value of the **cbEntryID** member and the **lpEntryID** member can be NULL.</span></span> 
  
<span data-ttu-id="dbf4a-128">有关通知的详细信息, 请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-128">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="dbf4a-129">**主题**</span><span class="sxs-lookup"><span data-stu-id="dbf4a-129">**Topic**</span></span>|<span data-ttu-id="dbf4a-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="dbf4a-130">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="dbf4a-131">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="dbf4a-131">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="dbf4a-132">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-132">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="dbf4a-133">处理通知</span><span class="sxs-lookup"><span data-stu-id="dbf4a-133">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="dbf4a-134">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-134">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="dbf4a-135">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="dbf4a-135">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="dbf4a-136">讨论了如何使用**IMAPISupport**方法生成通知的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="dbf4a-136">Discussion of how service providers can use the **IMAPISupport** method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="dbf4a-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbf4a-137">See also</span></span>



[<span data-ttu-id="dbf4a-138">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="dbf4a-138">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="dbf4a-139">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="dbf4a-139">NOTIFICATION</span></span>](notification.md)


[<span data-ttu-id="dbf4a-140">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="dbf4a-140">MAPI Structures</span></span>](mapi-structures.md)

