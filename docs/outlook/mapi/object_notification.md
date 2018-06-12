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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 1593152786a3345827089e5f6702454896944b1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776545"
---
# <a name="objectnotification"></a><span data-ttu-id="82951-103">OBJECT_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="82951-103">OBJECT_NOTIFICATION</span></span>

  
  
<span data-ttu-id="82951-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="82951-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="82951-105">包含有关对象已进行更改，如正在复制或修改的信息。</span><span class="sxs-lookup"><span data-stu-id="82951-105">Contains information about an object that has undergone a change, such as being copied or modified.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="82951-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="82951-106">Header file:</span></span>  <br/> |<span data-ttu-id="82951-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="82951-107">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="82951-108">成员</span><span class="sxs-lookup"><span data-stu-id="82951-108">Members</span></span>

 <span data-ttu-id="82951-109">**cbEntryID**</span><span class="sxs-lookup"><span data-stu-id="82951-109">**cbEntryID**</span></span>
  
> <span data-ttu-id="82951-110">由**lpEntryID**成员指向中的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="82951-110">Count of bytes in the entry identifier pointed to by the **lpEntryID** member.</span></span> 
    
 <span data-ttu-id="82951-111">**lpEntryID**</span><span class="sxs-lookup"><span data-stu-id="82951-111">**lpEntryID**</span></span>
  
> <span data-ttu-id="82951-112">受影响的对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="82951-112">Pointer to the entry identifier of the affected object.</span></span>
    
 <span data-ttu-id="82951-113">**ulObjType**</span><span class="sxs-lookup"><span data-stu-id="82951-113">**ulObjType**</span></span>
  
> <span data-ttu-id="82951-114">受影响的对象类型。</span><span class="sxs-lookup"><span data-stu-id="82951-114">Type of object affected.</span></span> <span data-ttu-id="82951-115">可能的类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="82951-115">Possible types are as follows:</span></span>
    
<span data-ttu-id="82951-116">MAPI_STORE</span><span class="sxs-lookup"><span data-stu-id="82951-116">MAPI_STORE</span></span> 
  
> <span data-ttu-id="82951-117">邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="82951-117">Message store.</span></span> 
    
<span data-ttu-id="82951-118">MAPI_ADDRBOOK</span><span class="sxs-lookup"><span data-stu-id="82951-118">MAPI_ADDRBOOK</span></span> 
  
> <span data-ttu-id="82951-119">通讯簿。</span><span class="sxs-lookup"><span data-stu-id="82951-119">Address book.</span></span> 
    
<span data-ttu-id="82951-120">MAPI_FOLDER</span><span class="sxs-lookup"><span data-stu-id="82951-120">MAPI_FOLDER</span></span> 
  
> <span data-ttu-id="82951-121">文件夹。</span><span class="sxs-lookup"><span data-stu-id="82951-121">Folder.</span></span>
    
<span data-ttu-id="82951-122">MAPI_ABCONT</span><span class="sxs-lookup"><span data-stu-id="82951-122">MAPI_ABCONT</span></span> 
  
> <span data-ttu-id="82951-123">通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="82951-123">Address book container.</span></span>
    
<span data-ttu-id="82951-124">MAPI_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="82951-124">MAPI_MESSAGE</span></span> 
  
> <span data-ttu-id="82951-125">消息。</span><span class="sxs-lookup"><span data-stu-id="82951-125">Message.</span></span>
    
<span data-ttu-id="82951-126">MAPI_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="82951-126">MAPI_MAILUSER</span></span> 
  
> <span data-ttu-id="82951-127">邮件用户。</span><span class="sxs-lookup"><span data-stu-id="82951-127">Messaging user.</span></span>
    
<span data-ttu-id="82951-128">MAPI_ATTACH</span><span class="sxs-lookup"><span data-stu-id="82951-128">MAPI_ATTACH</span></span> 
  
> <span data-ttu-id="82951-129">附件。</span><span class="sxs-lookup"><span data-stu-id="82951-129">Attachment.</span></span>
    
<span data-ttu-id="82951-130">MAPI_DISTLIST</span><span class="sxs-lookup"><span data-stu-id="82951-130">MAPI_DISTLIST</span></span> 
  
> <span data-ttu-id="82951-131">通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="82951-131">Distribution list.</span></span>
    
<span data-ttu-id="82951-132">MAPI_PROFSECT</span><span class="sxs-lookup"><span data-stu-id="82951-132">MAPI_PROFSECT</span></span> 
  
> <span data-ttu-id="82951-133">配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="82951-133">Profile section.</span></span>
    
<span data-ttu-id="82951-134">MAPI_STATUS</span><span class="sxs-lookup"><span data-stu-id="82951-134">MAPI_STATUS</span></span> 
  
> <span data-ttu-id="82951-135">状态对象。</span><span class="sxs-lookup"><span data-stu-id="82951-135">Status object.</span></span>
    
<span data-ttu-id="82951-136">MAPI_SESSION</span><span class="sxs-lookup"><span data-stu-id="82951-136">MAPI_SESSION</span></span> 
  
> <span data-ttu-id="82951-137">会话对象。</span><span class="sxs-lookup"><span data-stu-id="82951-137">Session object.</span></span>
    
 <span data-ttu-id="82951-138">**cbParentID**</span><span class="sxs-lookup"><span data-stu-id="82951-138">**cbParentID**</span></span>
  
> <span data-ttu-id="82951-139">由**lpParentID**成员指向中的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="82951-139">Count of bytes in the entry identifier pointed to by the **lpParentID** member.</span></span> 
    
 <span data-ttu-id="82951-140">**lpParentID**</span><span class="sxs-lookup"><span data-stu-id="82951-140">**lpParentID**</span></span>
  
> <span data-ttu-id="82951-141">受影响的对象的父对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="82951-141">Pointer to the entry identifier of the parent of the affected object.</span></span>
    
 <span data-ttu-id="82951-142">**cbOldID**</span><span class="sxs-lookup"><span data-stu-id="82951-142">**cbOldID**</span></span>
  
> <span data-ttu-id="82951-143">由**lpOldID**成员指向中的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="82951-143">Count of bytes in the entry identifier pointed to by the **lpOldID** member.</span></span> 
    
 <span data-ttu-id="82951-144">**lpOldID**</span><span class="sxs-lookup"><span data-stu-id="82951-144">**lpOldID**</span></span>
  
> <span data-ttu-id="82951-145">指向原始对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="82951-145">Pointer to the entry identifier of the original object.</span></span> <span data-ttu-id="82951-146">如果事件不需要原始对象，该指针可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="82951-146">This pointer can be NULL if the event does not require an original object.</span></span>
    
 <span data-ttu-id="82951-147">**cbOldParentID**</span><span class="sxs-lookup"><span data-stu-id="82951-147">**cbOldParentID**</span></span>
  
> <span data-ttu-id="82951-148">由**lpOldParentID**成员指向中的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="82951-148">Count of bytes in the entry identifier pointed to by the **lpOldParentID** member.</span></span> 
    
 <span data-ttu-id="82951-149">**lpOldParentID**</span><span class="sxs-lookup"><span data-stu-id="82951-149">**lpOldParentID**</span></span>
  
> <span data-ttu-id="82951-150">指向原始对象的父对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="82951-150">Pointer to the entry identifier of the parent of the original object.</span></span> <span data-ttu-id="82951-151">如果事件不需要原始对象，该指针可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="82951-151">This pointer can be NULL if the event does not require an original object.</span></span>
    
 <span data-ttu-id="82951-152">**lpPropTagArray**</span><span class="sxs-lookup"><span data-stu-id="82951-152">**lpPropTagArray**</span></span>
  
> <span data-ttu-id="82951-153">指向包含属性标记标识受影响的事件属性[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="82951-153">Pointer to an [SPropTagArray](sproptagarray.md) structure that contains the property tags identifying properties affected by the event.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="82951-154">备注</span><span class="sxs-lookup"><span data-stu-id="82951-154">Remarks</span></span>

<span data-ttu-id="82951-155">**OBJECT_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。</span><span class="sxs-lookup"><span data-stu-id="82951-155">The **OBJECT_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="82951-156">如果**通知**结构的**信息**成员包含**OBJECT_NOTIFICATION**结构，**通知**结构的**ulEventType**成员设置为以下类型的事件之一：</span><span class="sxs-lookup"><span data-stu-id="82951-156">When the **info** member of a **NOTIFICATION** structure contains an **OBJECT_NOTIFICATION** structure, the **ulEventType** member of the **NOTIFICATION** structure is set to one of the following types of events:</span></span> 
  
- <span data-ttu-id="82951-157">fnevObjectCreated</span><span class="sxs-lookup"><span data-stu-id="82951-157">fnevObjectCreated</span></span>
    
- <span data-ttu-id="82951-158">fnevObjectModified</span><span class="sxs-lookup"><span data-stu-id="82951-158">fnevObjectModified</span></span>
    
- <span data-ttu-id="82951-159">fnevObjectDeleted</span><span class="sxs-lookup"><span data-stu-id="82951-159">fnevObjectDeleted</span></span>
    
- <span data-ttu-id="82951-160">fnevObjectMoved</span><span class="sxs-lookup"><span data-stu-id="82951-160">fnevObjectMoved</span></span>
    
- <span data-ttu-id="82951-161">fnevObjectCopied</span><span class="sxs-lookup"><span data-stu-id="82951-161">fnevObjectCopied</span></span>
    
- <span data-ttu-id="82951-162">fnevSearchComplete</span><span class="sxs-lookup"><span data-stu-id="82951-162">fnevSearchComplete</span></span>
    
<span data-ttu-id="82951-163">搜索完整事件，由 fnevSearchComplete 事件类型，表示一个搜索文件夹的域的初始搜索已完成。</span><span class="sxs-lookup"><span data-stu-id="82951-163">The search complete event, represented by the fnevSearchComplete event type, indicates that the initial search of the domain for one search folder has completed.</span></span>
  
<span data-ttu-id="82951-164">仅在移动和复制事件中使用包含有关原始对象的以下成员。</span><span class="sxs-lookup"><span data-stu-id="82951-164">The following members that contain information about the original object are used only in move and copy events.</span></span> 
  
- <span data-ttu-id="82951-165">**cbOldID**</span><span class="sxs-lookup"><span data-stu-id="82951-165">**cbOldID**</span></span>
    
- <span data-ttu-id="82951-166">**lpOldID**</span><span class="sxs-lookup"><span data-stu-id="82951-166">**lpOldID**</span></span>
    
- <span data-ttu-id="82951-167">**cbOldParentID**</span><span class="sxs-lookup"><span data-stu-id="82951-167">**cbOldParentID**</span></span>
    
- <span data-ttu-id="82951-168">**lpOldParentID**</span><span class="sxs-lookup"><span data-stu-id="82951-168">**lpOldParentID**</span></span>
    
<span data-ttu-id="82951-169">这些成员不适用于其他类型的事件。</span><span class="sxs-lookup"><span data-stu-id="82951-169">These members do not apply to the other types of events.</span></span>
  
<span data-ttu-id="82951-170">有关通知的详细信息，请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="82951-170">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="82951-171">**主题**</span><span class="sxs-lookup"><span data-stu-id="82951-171">**Topic**</span></span>|<span data-ttu-id="82951-172">**说明**</span><span class="sxs-lookup"><span data-stu-id="82951-172">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="82951-173">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="82951-173">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="82951-174">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="82951-174">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="82951-175">处理通知</span><span class="sxs-lookup"><span data-stu-id="82951-175">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="82951-176">讨论了客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="82951-176">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="82951-177">支持的事件通知</span><span class="sxs-lookup"><span data-stu-id="82951-177">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="82951-178">讨论的服务提供程序如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="82951-178">Discussion of how service providers can use the [IMAPISupport](imapisupportiunknown.md) method to generate notifications.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="82951-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82951-179">See also</span></span>



[<span data-ttu-id="82951-180">通知</span><span class="sxs-lookup"><span data-stu-id="82951-180">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="82951-181">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="82951-181">SPropTagArray</span></span>](sproptagarray.md)


[<span data-ttu-id="82951-182">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="82951-182">MAPI Structures</span></span>](mapi-structures.md)

