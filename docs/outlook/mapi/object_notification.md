---
title: OBJECT_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OBJECT_NOTIFICATION
api_type:
- COM
ms.assetid: de3a2297-e0cc-427b-a978-52bade4d9bce
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c637b3b03a22f208123397f7277cf8968f2509a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279884"
---
# <a name="objectnotification"></a><span data-ttu-id="86801-103">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="86801-103">OBJECT_NOTIFICATION</span></span>

  
  
<span data-ttu-id="86801-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="86801-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="86801-105">包含有关已完成更改 (如复制或修改) 的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="86801-105">Contains information about an object that has undergone a change, such as being copied or modified.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="86801-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="86801-106">Header file:</span></span>  <br/> |<span data-ttu-id="86801-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="86801-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _OBJECT_NOTIFICATION
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  ULONG ulObjType;
  ULONG cbParentID;
  LPENTRYID lpParentID;
  ULONG cbOldID;
  LPENTRYID lpOldID;
  ULONG cbOldParentID;
  LPENTRYID lpOldParentID;
  LPSPropTagArray lpPropTagArray;
} OBJECT_NOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="86801-108">Members</span><span class="sxs-lookup"><span data-stu-id="86801-108">Members</span></span>

 <span data-ttu-id="86801-109">**cbEntryID**</span><span class="sxs-lookup"><span data-stu-id="86801-109">**cbEntryID**</span></span>
  
> <span data-ttu-id="86801-110">由**lpEntryID**成员指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="86801-110">Count of bytes in the entry identifier pointed to by the **lpEntryID** member.</span></span> 
    
 <span data-ttu-id="86801-111">**lpEntryID**</span><span class="sxs-lookup"><span data-stu-id="86801-111">**lpEntryID**</span></span>
  
> <span data-ttu-id="86801-112">指向受影响对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="86801-112">Pointer to the entry identifier of the affected object.</span></span>
    
 <span data-ttu-id="86801-113">**ulObjType**</span><span class="sxs-lookup"><span data-stu-id="86801-113">**ulObjType**</span></span>
  
> <span data-ttu-id="86801-114">受影响的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="86801-114">Type of object affected.</span></span> <span data-ttu-id="86801-115">可能的类型如下所示:</span><span class="sxs-lookup"><span data-stu-id="86801-115">Possible types are as follows:</span></span>
    
<span data-ttu-id="86801-116">MAPI_STORE</span><span class="sxs-lookup"><span data-stu-id="86801-116">MAPI_STORE</span></span> 
  
> <span data-ttu-id="86801-117">邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="86801-117">Message store.</span></span> 
    
<span data-ttu-id="86801-118">MAPI_ADDRBOOK</span><span class="sxs-lookup"><span data-stu-id="86801-118">MAPI_ADDRBOOK</span></span> 
  
> <span data-ttu-id="86801-119">通讯簿。</span><span class="sxs-lookup"><span data-stu-id="86801-119">Address book.</span></span> 
    
<span data-ttu-id="86801-120">MAPI_FOLDER</span><span class="sxs-lookup"><span data-stu-id="86801-120">MAPI_FOLDER</span></span> 
  
> <span data-ttu-id="86801-121">文件夹.</span><span class="sxs-lookup"><span data-stu-id="86801-121">Folder.</span></span>
    
<span data-ttu-id="86801-122">MAPI_ABCONT</span><span class="sxs-lookup"><span data-stu-id="86801-122">MAPI_ABCONT</span></span> 
  
> <span data-ttu-id="86801-123">通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="86801-123">Address book container.</span></span>
    
<span data-ttu-id="86801-124">MAPI_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="86801-124">MAPI_MESSAGE</span></span> 
  
> <span data-ttu-id="86801-125">消息。</span><span class="sxs-lookup"><span data-stu-id="86801-125">Message.</span></span>
    
<span data-ttu-id="86801-126">MAPI_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="86801-126">MAPI_MAILUSER</span></span> 
  
> <span data-ttu-id="86801-127">邮件用户。</span><span class="sxs-lookup"><span data-stu-id="86801-127">Messaging user.</span></span>
    
<span data-ttu-id="86801-128">MAPI_ATTACH</span><span class="sxs-lookup"><span data-stu-id="86801-128">MAPI_ATTACH</span></span> 
  
> <span data-ttu-id="86801-129">附着.</span><span class="sxs-lookup"><span data-stu-id="86801-129">Attachment.</span></span>
    
<span data-ttu-id="86801-130">MAPI_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="86801-130">MAPI_DISTLIST</span></span> 
  
> <span data-ttu-id="86801-131">通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="86801-131">Distribution list.</span></span>
    
<span data-ttu-id="86801-132">MAPI_PROFSECT</span><span class="sxs-lookup"><span data-stu-id="86801-132">MAPI_PROFSECT</span></span> 
  
> <span data-ttu-id="86801-133">Profile 部分。</span><span class="sxs-lookup"><span data-stu-id="86801-133">Profile section.</span></span>
    
<span data-ttu-id="86801-134">MAPI_STATUS</span><span class="sxs-lookup"><span data-stu-id="86801-134">MAPI_STATUS</span></span> 
  
> <span data-ttu-id="86801-135">Status 对象。</span><span class="sxs-lookup"><span data-stu-id="86801-135">Status object.</span></span>
    
<span data-ttu-id="86801-136">MAPI_SESSION</span><span class="sxs-lookup"><span data-stu-id="86801-136">MAPI_SESSION</span></span> 
  
> <span data-ttu-id="86801-137">Session 对象。</span><span class="sxs-lookup"><span data-stu-id="86801-137">Session object.</span></span>
    
 <span data-ttu-id="86801-138">**cbParentID**</span><span class="sxs-lookup"><span data-stu-id="86801-138">**cbParentID**</span></span>
  
> <span data-ttu-id="86801-139">由**lpParentID**成员指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="86801-139">Count of bytes in the entry identifier pointed to by the **lpParentID** member.</span></span> 
    
 <span data-ttu-id="86801-140">**lpParentID**</span><span class="sxs-lookup"><span data-stu-id="86801-140">**lpParentID**</span></span>
  
> <span data-ttu-id="86801-141">指向受影响对象的父级的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="86801-141">Pointer to the entry identifier of the parent of the affected object.</span></span>
    
 <span data-ttu-id="86801-142">**cbOldID**</span><span class="sxs-lookup"><span data-stu-id="86801-142">**cbOldID**</span></span>
  
> <span data-ttu-id="86801-143">由**lpOldID**成员指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="86801-143">Count of bytes in the entry identifier pointed to by the **lpOldID** member.</span></span> 
    
 <span data-ttu-id="86801-144">**lpOldID**</span><span class="sxs-lookup"><span data-stu-id="86801-144">**lpOldID**</span></span>
  
> <span data-ttu-id="86801-145">指向原始对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="86801-145">Pointer to the entry identifier of the original object.</span></span> <span data-ttu-id="86801-146">如果事件不需要原始对象, 则此指针可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="86801-146">This pointer can be NULL if the event does not require an original object.</span></span>
    
 <span data-ttu-id="86801-147">**cbOldParentID**</span><span class="sxs-lookup"><span data-stu-id="86801-147">**cbOldParentID**</span></span>
  
> <span data-ttu-id="86801-148">由**lpOldParentID**成员指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="86801-148">Count of bytes in the entry identifier pointed to by the **lpOldParentID** member.</span></span> 
    
 <span data-ttu-id="86801-149">**lpOldParentID**</span><span class="sxs-lookup"><span data-stu-id="86801-149">**lpOldParentID**</span></span>
  
> <span data-ttu-id="86801-150">指向原始对象的父对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="86801-150">Pointer to the entry identifier of the parent of the original object.</span></span> <span data-ttu-id="86801-151">如果事件不需要原始对象, 则此指针可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="86801-151">This pointer can be NULL if the event does not require an original object.</span></span>
    
 <span data-ttu-id="86801-152">**lpPropTagArray**</span><span class="sxs-lookup"><span data-stu-id="86801-152">**lpPropTagArray**</span></span>
  
> <span data-ttu-id="86801-153">指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含用于标识受事件影响的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="86801-153">Pointer to an [SPropTagArray](sproptagarray.md) structure that contains the property tags identifying properties affected by the event.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="86801-154">注解</span><span class="sxs-lookup"><span data-stu-id="86801-154">Remarks</span></span>

<span data-ttu-id="86801-155">**OBJECT_NOTIFICATION**结构是[通知](notification.md)结构的**info**成员中包含的结构联合的成员之一。</span><span class="sxs-lookup"><span data-stu-id="86801-155">The **OBJECT_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="86801-156">当**通知**结构的**info**成员包含**OBJECT_NOTIFICATION**结构时,**通知**结构的**ulEventType**成员将设置为以下事件类型之一:</span><span class="sxs-lookup"><span data-stu-id="86801-156">When the **info** member of a **NOTIFICATION** structure contains an **OBJECT_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to one of the following types of events:</span></span> 
  
- <span data-ttu-id="86801-157">fnevObjectCreated</span><span class="sxs-lookup"><span data-stu-id="86801-157">fnevObjectCreated</span></span>
    
- <span data-ttu-id="86801-158">fnevObjectModified</span><span class="sxs-lookup"><span data-stu-id="86801-158">fnevObjectModified</span></span>
    
- <span data-ttu-id="86801-159">fnevObjectDeleted</span><span class="sxs-lookup"><span data-stu-id="86801-159">fnevObjectDeleted</span></span>
    
- <span data-ttu-id="86801-160">fnevObjectMoved</span><span class="sxs-lookup"><span data-stu-id="86801-160">fnevObjectMoved</span></span>
    
- <span data-ttu-id="86801-161">fnevObjectCopied</span><span class="sxs-lookup"><span data-stu-id="86801-161">fnevObjectCopied</span></span>
    
- <span data-ttu-id="86801-162">fnevSearchComplete</span><span class="sxs-lookup"><span data-stu-id="86801-162">fnevSearchComplete</span></span>
    
<span data-ttu-id="86801-163">由 fnevSearchComplete 事件类型表示的搜索完成事件指示一个搜索文件夹的域的初始搜索已完成。</span><span class="sxs-lookup"><span data-stu-id="86801-163">The search complete event, represented by the fnevSearchComplete event type, indicates that the initial search of the domain for one search folder has completed.</span></span>
  
<span data-ttu-id="86801-164">以下包含有关原始对象的信息的成员仅在 move 事件和 copy 事件中使用。</span><span class="sxs-lookup"><span data-stu-id="86801-164">The following members that contain information about the original object are used only in move and copy events.</span></span> 
  
- <span data-ttu-id="86801-165">**cbOldID**</span><span class="sxs-lookup"><span data-stu-id="86801-165">**cbOldID**</span></span>
    
- <span data-ttu-id="86801-166">**lpOldID**</span><span class="sxs-lookup"><span data-stu-id="86801-166">**lpOldID**</span></span>
    
- <span data-ttu-id="86801-167">**cbOldParentID**</span><span class="sxs-lookup"><span data-stu-id="86801-167">**cbOldParentID**</span></span>
    
- <span data-ttu-id="86801-168">**lpOldParentID**</span><span class="sxs-lookup"><span data-stu-id="86801-168">**lpOldParentID**</span></span>
    
<span data-ttu-id="86801-169">这些成员不适用于其他类型的事件。</span><span class="sxs-lookup"><span data-stu-id="86801-169">These members do not apply to the other types of events.</span></span>
  
<span data-ttu-id="86801-170">有关通知的详细信息, 请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="86801-170">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="86801-171">**主题**</span><span class="sxs-lookup"><span data-stu-id="86801-171">**Topic**</span></span>|<span data-ttu-id="86801-172">**说明**</span><span class="sxs-lookup"><span data-stu-id="86801-172">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="86801-173">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="86801-173">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="86801-174">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="86801-174">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="86801-175">处理通知</span><span class="sxs-lookup"><span data-stu-id="86801-175">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="86801-176">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="86801-176">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="86801-177">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="86801-177">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="86801-178">讨论了如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="86801-178">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="86801-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86801-179">See also</span></span>



[<span data-ttu-id="86801-180">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="86801-180">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="86801-181">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="86801-181">SPropTagArray</span></span>](sproptagarray.md)


[<span data-ttu-id="86801-182">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="86801-182">MAPI Structures</span></span>](mapi-structures.md)

