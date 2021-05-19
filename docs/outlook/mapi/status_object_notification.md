---
title: STATUS_OBJECT_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.STATUS_OBJECT_NOTIFICATION
api_type:
- COM
ms.assetid: 2872130d-a36b-46ea-bfd1-4700fe3dd41b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 84b44b4b054a2b2617502a6a463a6d4a89546804
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426266"
---
# <a name="status_object_notification"></a><span data-ttu-id="a457e-103">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="a457e-103">STATUS_OBJECT_NOTIFICATION</span></span>

  
  
<span data-ttu-id="a457e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a457e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a457e-105">描述受更改影响的状态对象。</span><span class="sxs-lookup"><span data-stu-id="a457e-105">Describes a status object that has been affected by a change.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a457e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a457e-106">Header file:</span></span>  <br/> |<span data-ttu-id="a457e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a457e-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  ULONG cValues;
  LPSPropValue lpPropVals;
} STATUS_OBJECT_NOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="a457e-108">Members</span><span class="sxs-lookup"><span data-stu-id="a457e-108">Members</span></span>

 <span data-ttu-id="a457e-109">**cbEntryID**</span><span class="sxs-lookup"><span data-stu-id="a457e-109">**cbEntryID**</span></span>
  
> <span data-ttu-id="a457e-110">**lpEntryID** 成员指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="a457e-110">Count of bytes in the entry identifier pointed to by the **lpEntryID** member.</span></span> 
    
 <span data-ttu-id="a457e-111">**lpEntryID**</span><span class="sxs-lookup"><span data-stu-id="a457e-111">**lpEntryID**</span></span>
  
> <span data-ttu-id="a457e-112">指向已更改状态对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="a457e-112">Pointer to the entry identifier of the changed status object.</span></span>
    
 <span data-ttu-id="a457e-113">**cValues**</span><span class="sxs-lookup"><span data-stu-id="a457e-113">**cValues**</span></span>
  
> <span data-ttu-id="a457e-114">[lpPropVals](spropvalue.md)成员指向的数组中的 **SPropValue** 结构计数。</span><span class="sxs-lookup"><span data-stu-id="a457e-114">Count of [SPropValue](spropvalue.md) structures in the array pointed to by the **lpPropVals** member.</span></span> 
    
 <span data-ttu-id="a457e-115">**lpPropVals**</span><span class="sxs-lookup"><span data-stu-id="a457e-115">**lpPropVals**</span></span>
  
> <span data-ttu-id="a457e-116">指向描述已更改状态对象的属性 **的 SPropValue** 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="a457e-116">Pointer to an array of **SPropValue** structures that describe the properties of the changed status object.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a457e-117">备注</span><span class="sxs-lookup"><span data-stu-id="a457e-117">Remarks</span></span>

<span data-ttu-id="a457e-118">the **STATUS_OBJECT_NOTIFICATION** structure is one of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span><span class="sxs-lookup"><span data-stu-id="a457e-118">The **STATUS_OBJECT_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="a457e-119">the **STATUS_OBJECT_NOTIFICATION** structure is included with a status object notification for an event of type  _fnevStatusObjectModified_.</span><span class="sxs-lookup"><span data-stu-id="a457e-119">The **STATUS_OBJECT_NOTIFICATION** structure is included with a status object notification for an event of type  _fnevStatusObjectModified_.</span></span> <span data-ttu-id="a457e-120">状态对象通知是一个内部 MAPI 通知;客户端和服务提供商无法注册它，服务提供商无法生成它。</span><span class="sxs-lookup"><span data-stu-id="a457e-120">Status object notification is an internal MAPI notification; clients and service providers cannot register for it and service providers cannot generate it.</span></span>
  
<span data-ttu-id="a457e-121">有关通知详细信息，请参阅下表中介绍的主题。</span><span class="sxs-lookup"><span data-stu-id="a457e-121">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="a457e-122">**主题**</span><span class="sxs-lookup"><span data-stu-id="a457e-122">**Topic**</span></span>|<span data-ttu-id="a457e-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="a457e-123">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a457e-124">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="a457e-124">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="a457e-125">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="a457e-125">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="a457e-126">处理通知</span><span class="sxs-lookup"><span data-stu-id="a457e-126">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="a457e-127">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="a457e-127">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="a457e-128">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="a457e-128">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="a457e-129">讨论服务提供商如何使用 **IMAPISupport** 方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="a457e-129">Discussion of how service providers can use the **IMAPISupport** method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a457e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a457e-130">See also</span></span>



[<span data-ttu-id="a457e-131">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="a457e-131">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="a457e-132">SPropValue</span><span class="sxs-lookup"><span data-stu-id="a457e-132">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="a457e-133">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="a457e-133">MAPI Structures</span></span>](mapi-structures.md)

