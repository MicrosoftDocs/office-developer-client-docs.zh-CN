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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425440"
---
# <a name="error_notification"></a><span data-ttu-id="aa4cb-103">ERROR_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="aa4cb-103">ERROR_NOTIFICATION</span></span>

  
  
<span data-ttu-id="aa4cb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa4cb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa4cb-105">描述与严重错误有关的信息。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-105">Describes information that relate to a critical error.</span></span> <span data-ttu-id="aa4cb-106">这将导致生成错误通知。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-106">This causes an error notification to be generated.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aa4cb-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="aa4cb-107">Header file:</span></span>  <br/> |<span data-ttu-id="aa4cb-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="aa4cb-108">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="aa4cb-109">Members</span><span class="sxs-lookup"><span data-stu-id="aa4cb-109">Members</span></span>

 <span data-ttu-id="aa4cb-110">**cbEntryID**</span><span class="sxs-lookup"><span data-stu-id="aa4cb-110">**cbEntryID**</span></span>
  
> <span data-ttu-id="aa4cb-111">**lpEntryID** 指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-111">Count of bytes in the entry identifier pointed to by **lpEntryID**.</span></span> 
    
 <span data-ttu-id="aa4cb-112">**lpEntryID**</span><span class="sxs-lookup"><span data-stu-id="aa4cb-112">**lpEntryID**</span></span>
  
> <span data-ttu-id="aa4cb-113">指向导致错误的对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-113">Pointer to the entry identifier of the object that causes the error.</span></span>
    
 <span data-ttu-id="aa4cb-114">**scode**</span><span class="sxs-lookup"><span data-stu-id="aa4cb-114">**scode**</span></span>
  
> <span data-ttu-id="aa4cb-115">严重错误的错误值。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-115">Error value for the critical error.</span></span> 
    
 <span data-ttu-id="aa4cb-116">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="aa4cb-116">**ulFlags**</span></span>
  
> <span data-ttu-id="aa4cb-117">用于指定 **lpszError** 成员在 **lpMAPIError** 指向的结构中指向的文本格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-117">Bitmask of flags used to designate the format of the text pointed to by the **lpszError** member in the structure pointed to by **lpMAPIError**.</span></span> <span data-ttu-id="aa4cb-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="aa4cb-118">The following flag can be set:</span></span>
    
<span data-ttu-id="aa4cb-119">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="aa4cb-119">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="aa4cb-120">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-120">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="aa4cb-121">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-121">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="aa4cb-122">**lpMAPIError**</span><span class="sxs-lookup"><span data-stu-id="aa4cb-122">**lpMAPIError**</span></span>
  
> <span data-ttu-id="aa4cb-123">指向描述错误的 [MAPIERROR](mapierror.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-123">Pointer to a [MAPIERROR](mapierror.md) structure describing the error.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="aa4cb-124">备注</span><span class="sxs-lookup"><span data-stu-id="aa4cb-124">Remarks</span></span>

<span data-ttu-id="aa4cb-125">the **ERROR_NOTIFICATION** structure is one of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span><span class="sxs-lookup"><span data-stu-id="aa4cb-125">The **ERROR_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="aa4cb-126">当 **NOTIFICATION** 结构的信息成员包含一个 ERROR_NOTIFICATION **结构时\*\*\*\*，NOTIFICATION** 结构的 **ulEventType** 成员将设置为 _fnevCriticalError_。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-126">When the **info** member of a **NOTIFICATION** structure contains an **ERROR_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to  _fnevCriticalError_.</span></span>
  
<span data-ttu-id="aa4cb-127">**cbEntryID** 成员和 **lpEntryID** 成员的值可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-127">The value of the **cbEntryID** member and the **lpEntryID** member can be NULL.</span></span> 
  
<span data-ttu-id="aa4cb-128">有关通知详细信息，请参阅下表中介绍的主题。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-128">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="aa4cb-129">**主题**</span><span class="sxs-lookup"><span data-stu-id="aa4cb-129">**Topic**</span></span>|<span data-ttu-id="aa4cb-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa4cb-130">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="aa4cb-131">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="aa4cb-131">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="aa4cb-132">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-132">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="aa4cb-133">处理通知</span><span class="sxs-lookup"><span data-stu-id="aa4cb-133">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="aa4cb-134">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-134">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="aa4cb-135">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="aa4cb-135">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="aa4cb-136">讨论服务提供商如何使用 **IMAPISupport** 方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="aa4cb-136">Discussion of how service providers can use the **IMAPISupport** method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="aa4cb-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa4cb-137">See also</span></span>



[<span data-ttu-id="aa4cb-138">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="aa4cb-138">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="aa4cb-139">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="aa4cb-139">NOTIFICATION</span></span>](notification.md)


[<span data-ttu-id="aa4cb-140">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="aa4cb-140">MAPI Structures</span></span>](mapi-structures.md)

