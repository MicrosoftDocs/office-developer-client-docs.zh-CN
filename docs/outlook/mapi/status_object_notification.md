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
ms.openlocfilehash: 71e0a08436c925f0d68d63111722cc01bd73cc5f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778894"
---
# <a name="statusobjectnotification"></a><span data-ttu-id="164b2-103">STATUS_OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="164b2-103">STATUS_OBJECT_NOTIFICATION</span></span>

  
  
<span data-ttu-id="164b2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="164b2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="164b2-105">介绍受更改状态对象。</span><span class="sxs-lookup"><span data-stu-id="164b2-105">Describes a status object that has been affected by a change.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="164b2-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="164b2-106">Header file:</span></span>  <br/> |<span data-ttu-id="164b2-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="164b2-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  ULONG cValues;
  LPSPropValue lpPropVals;
} STATUS_OBJECT_NOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="164b2-108">Members</span><span class="sxs-lookup"><span data-stu-id="164b2-108">Members</span></span>

 <span data-ttu-id="164b2-109">**cbEntryID**</span><span class="sxs-lookup"><span data-stu-id="164b2-109">**cbEntryID**</span></span>
  
> <span data-ttu-id="164b2-110">由**lpEntryID**成员指向中的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="164b2-110">Count of bytes in the entry identifier pointed to by the **lpEntryID** member.</span></span> 
    
 <span data-ttu-id="164b2-111">**lpEntryID**</span><span class="sxs-lookup"><span data-stu-id="164b2-111">**lpEntryID**</span></span>
  
> <span data-ttu-id="164b2-112">更改的状态对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="164b2-112">Pointer to the entry identifier of the changed status object.</span></span>
    
 <span data-ttu-id="164b2-113">**cValues**</span><span class="sxs-lookup"><span data-stu-id="164b2-113">**cValues**</span></span>
  
> <span data-ttu-id="164b2-114">由**lpPropVals**成员指向[SPropValue](spropvalue.md)结构数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="164b2-114">Count of [SPropValue](spropvalue.md) structures in the array pointed to by the **lpPropVals** member.</span></span> 
    
 <span data-ttu-id="164b2-115">**lpPropVals**</span><span class="sxs-lookup"><span data-stu-id="164b2-115">**lpPropVals**</span></span>
  
> <span data-ttu-id="164b2-116">指向介绍已更改的状态对象的属性的**SPropValue**结构的数组。</span><span class="sxs-lookup"><span data-stu-id="164b2-116">Pointer to an array of **SPropValue** structures that describe the properties of the changed status object.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="164b2-117">说明</span><span class="sxs-lookup"><span data-stu-id="164b2-117">Remarks</span></span>

<span data-ttu-id="164b2-118">**STATUS_OBJECT_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。</span><span class="sxs-lookup"><span data-stu-id="164b2-118">The **STATUS_OBJECT_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="164b2-119">包含状态的对象通知事件的类型_fnevStatusObjectModified_ **STATUS_OBJECT_NOTIFICATION**结构。</span><span class="sxs-lookup"><span data-stu-id="164b2-119">The **STATUS_OBJECT_NOTIFICATION** structure is included with a status object notification for an event of type  _fnevStatusObjectModified_.</span></span> <span data-ttu-id="164b2-120">状态对象通知是内部的 MAPI 通知;客户端与服务提供程序无法为其注册和服务提供程序无法生成它。</span><span class="sxs-lookup"><span data-stu-id="164b2-120">Status object notification is an internal MAPI notification; clients and service providers cannot register for it and service providers cannot generate it.</span></span>
  
<span data-ttu-id="164b2-121">有关通知的详细信息，请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="164b2-121">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="164b2-122">**主题**</span><span class="sxs-lookup"><span data-stu-id="164b2-122">**Topic**</span></span>|<span data-ttu-id="164b2-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="164b2-123">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="164b2-124">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="164b2-124">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="164b2-125">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="164b2-125">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="164b2-126">处理通知</span><span class="sxs-lookup"><span data-stu-id="164b2-126">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="164b2-127">讨论了客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="164b2-127">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="164b2-128">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="164b2-128">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="164b2-129">讨论的服务提供程序如何使用**IMAPISupport**方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="164b2-129">Discussion of how service providers can use the **IMAPISupport** method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="164b2-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="164b2-130">See also</span></span>



[<span data-ttu-id="164b2-131">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="164b2-131">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="164b2-132">SPropValue</span><span class="sxs-lookup"><span data-stu-id="164b2-132">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="164b2-133">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="164b2-133">MAPI Structures</span></span>](mapi-structures.md)

