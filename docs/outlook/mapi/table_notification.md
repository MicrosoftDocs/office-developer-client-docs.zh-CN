---
title: TABLE_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.TABLE_NOTIFICATION
api_type:
- COM
ms.assetid: 48e478c4-6e9a-40ab-a7bb-e6219b743b08
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6c35220529fb88b470c563a0b004bfcf7e63ef76
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415955"
---
# <a name="tablenotification"></a><span data-ttu-id="77bcb-103">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="77bcb-103">TABLE_NOTIFICATION</span></span>

<span data-ttu-id="77bcb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="77bcb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="77bcb-105">描述已受某种类型的事件 (如更改或错误) 影响的表中的行。</span><span class="sxs-lookup"><span data-stu-id="77bcb-105">Describes a row in a table that has been affected by some type of event, such as a change or an error.</span></span> <span data-ttu-id="77bcb-106">这将导致生成表通知。</span><span class="sxs-lookup"><span data-stu-id="77bcb-106">This causes a table notification to be generated.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="77bcb-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="77bcb-107">Header file:</span></span>  <br/> |<span data-ttu-id="77bcb-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="77bcb-108">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _TABLE_NOTIFICATION
{
  ULONG ulTableEvent;
  HRESULT hResult;
  SPropValue propIndex;
  SPropValue propPrior;
  SRow row;
} TABLE_NOTIFICATION;

```

## <a name="members"></a><span data-ttu-id="77bcb-109">Members</span><span class="sxs-lookup"><span data-stu-id="77bcb-109">Members</span></span>

<span data-ttu-id="77bcb-110">**ulTableEvent**</span><span class="sxs-lookup"><span data-stu-id="77bcb-110">**ulTableEvent**</span></span>
  
> <span data-ttu-id="77bcb-111">用于表示表事件类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="77bcb-111">Bitmask of flags used to represent the table event type.</span></span> <span data-ttu-id="77bcb-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="77bcb-112">The following flags can be set:</span></span>
    
<span data-ttu-id="77bcb-113">TABLE_CHANGED</span><span class="sxs-lookup"><span data-stu-id="77bcb-113">TABLE_CHANGED</span></span> 
  
> <span data-ttu-id="77bcb-114">指示在较高级别上, 关于表的某项已更改。</span><span class="sxs-lookup"><span data-stu-id="77bcb-114">Indicates at a high level that something about the table has changed.</span></span> <span data-ttu-id="77bcb-115">表的状态与事件之前的状态相同。</span><span class="sxs-lookup"><span data-stu-id="77bcb-115">The table's state is as it was before the event.</span></span> <span data-ttu-id="77bcb-116">这意味着所有**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性、书签、当前定位和用户界面选择仍然有效。</span><span class="sxs-lookup"><span data-stu-id="77bcb-116">This means that all **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) properties, bookmarks, current positioning, and user interface selections are still valid.</span></span> <span data-ttu-id="77bcb-117">通过并表格处理此事件。</span><span class="sxs-lookup"><span data-stu-id="77bcb-117">Handle this event by rereading the table.</span></span> <span data-ttu-id="77bcb-118">不希望实现丰富表通知的服务提供程序发送 TABLE_CHANGED 事件, 而不是更详细的事件来指示特定类型的更改。</span><span class="sxs-lookup"><span data-stu-id="77bcb-118">Service providers that do not want to implement rich table notifications send TABLE_CHANGED events instead of more detailed events to indicate a particular type of change.</span></span> 
    
<span data-ttu-id="77bcb-119">TABLE_ERROR</span><span class="sxs-lookup"><span data-stu-id="77bcb-119">TABLE_ERROR</span></span> 
  
> <span data-ttu-id="77bcb-120">发生错误, 通常是在处理异步操作的过程中。</span><span class="sxs-lookup"><span data-stu-id="77bcb-120">An error has occurred, usually during the processing of an asynchronous operation.</span></span> <span data-ttu-id="77bcb-121">处理以下方法时出现的错误可能会生成此事件:</span><span class="sxs-lookup"><span data-stu-id="77bcb-121">Errors during the processing of the following methods can generate this event:</span></span> 
    
   - [<span data-ttu-id="77bcb-122">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="77bcb-122">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
    
   - [<span data-ttu-id="77bcb-123">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="77bcb-123">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
    
   - [<span data-ttu-id="77bcb-124">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="77bcb-124">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
    
   <span data-ttu-id="77bcb-125">在接收到 TABLE_ERROR 事件之后, 客户端将无法依赖表内容的准确性。</span><span class="sxs-lookup"><span data-stu-id="77bcb-125">After receiving a TABLE_ERROR event, a client cannot rely on the accuracy of the table contents.</span></span> <span data-ttu-id="77bcb-126">此外, 有关其他更改的挂起通知可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="77bcb-126">Also, pending notifications about other changes might be lost.</span></span> <span data-ttu-id="77bcb-127">[IMAPITable:: GetLastError](imapitable-getlasterror.md)方法可能不提供有关错误的任何其他信息, 因为它是在之前的某个点生成的, 而不一定是从最后的方法调用生成的。</span><span class="sxs-lookup"><span data-stu-id="77bcb-127">The [IMAPITable::GetLastError](imapitable-getlasterror.md) method might not provide any additional information about the error because it was generated at some previous point, not necessarily from the last method call.</span></span> 
    
<span data-ttu-id="77bcb-128">TABLE_RELOAD</span><span class="sxs-lookup"><span data-stu-id="77bcb-128">TABLE_RELOAD</span></span> 
  
> <span data-ttu-id="77bcb-129">应重新加载表中的数据。</span><span class="sxs-lookup"><span data-stu-id="77bcb-129">The data in the table should be reloaded.</span></span> <span data-ttu-id="77bcb-130">服务提供程序发送 TABLE_RELOAD, 例如, 基础数据存储在数据库中, 而数据库被替换。</span><span class="sxs-lookup"><span data-stu-id="77bcb-130">Service providers send TABLE_RELOAD when, for example, the underlying data is stored in a database and the database is replaced.</span></span> <span data-ttu-id="77bcb-131">通过假定表中的任何内容仍然有效并并表来处理此事件。</span><span class="sxs-lookup"><span data-stu-id="77bcb-131">Handle this event by assuming that nothing about the table is still valid and by rereading the table.</span></span> <span data-ttu-id="77bcb-132">所有书签、实例键、状态和定位信息都无效。</span><span class="sxs-lookup"><span data-stu-id="77bcb-132">All bookmarks, instance keys, status and positioning information are invalid.</span></span>
    
<span data-ttu-id="77bcb-133">TABLE_RESTRICT_DONE</span><span class="sxs-lookup"><span data-stu-id="77bcb-133">TABLE_RESTRICT_DONE</span></span> 
  
> <span data-ttu-id="77bcb-134">已完成使用**IMAPITable:: Restrict**方法调用启动的限制操作。</span><span class="sxs-lookup"><span data-stu-id="77bcb-134">A restriction operation initiated with an **IMAPITable::Restrict** method call has completed.</span></span> 
    
<span data-ttu-id="77bcb-135">TABLE_ROW_ADDED</span><span class="sxs-lookup"><span data-stu-id="77bcb-135">TABLE_ROW_ADDED</span></span> 
  
> <span data-ttu-id="77bcb-136">已将新的行添加到表中, 并保存了对应的对象。</span><span class="sxs-lookup"><span data-stu-id="77bcb-136">A new row has been added to the table and the corresponding object saved.</span></span> <span data-ttu-id="77bcb-137">TABLE_ROW_ADDED 事件是在调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法之后生成的。</span><span class="sxs-lookup"><span data-stu-id="77bcb-137">TABLE_ROW_ADDED events are generated after a call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
    
<span data-ttu-id="77bcb-138">TABLE_ROW_DELETED</span><span class="sxs-lookup"><span data-stu-id="77bcb-138">TABLE_ROW_DELETED</span></span> 
  
> <span data-ttu-id="77bcb-139">已从表中删除了行。</span><span class="sxs-lookup"><span data-stu-id="77bcb-139">A row has been removed from the table.</span></span> <span data-ttu-id="77bcb-140">**propPrior**成员设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="77bcb-140">The **propPrior** member is set to NULL.</span></span> 
    
<span data-ttu-id="77bcb-141">TABLE_ROW_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="77bcb-141">TABLE_ROW_MODIFIED</span></span> 
  
> <span data-ttu-id="77bcb-142">行已更改。</span><span class="sxs-lookup"><span data-stu-id="77bcb-142">A row has been changed.</span></span> <span data-ttu-id="77bcb-143">**行**成员包含受影响的行属性。</span><span class="sxs-lookup"><span data-stu-id="77bcb-143">The **row** member contains the affected properties for the row.</span></span> <span data-ttu-id="77bcb-144">多个 TABLE_ROW_MODIFIED 事件按其在表视图中的显示顺序发送。</span><span class="sxs-lookup"><span data-stu-id="77bcb-144">Multiple TABLE_ROW_MODIFIED events are sent in the order that they appear in the table view.</span></span> 
    
  <span data-ttu-id="77bcb-145">在使用对**IMAPIProp:: SaveChanges**方法的调用提交对相应对象的更改之后, 将发送 TABLE_ROW_MODIFIED 事件。</span><span class="sxs-lookup"><span data-stu-id="77bcb-145">TABLE_ROW_MODIFIED events are sent after changes to the corresponding object have been committed with a call to the **IMAPIProp::SaveChanges** method.</span></span> <span data-ttu-id="77bcb-146">如果已修改的行现在是表中的第一行, 则**propPrior**成员中的属性标记的值是**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="77bcb-146">If the modified row is now the first row in the table, the value of the property tag in the **propPrior** member is **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)).</span></span>
    
<span data-ttu-id="77bcb-147">TABLE_SETCOL_DONE</span><span class="sxs-lookup"><span data-stu-id="77bcb-147">TABLE_SETCOL_DONE</span></span> 
  
> <span data-ttu-id="77bcb-148">已完成使用**IMAPITable:: SetColumns**方法调用启动的列设置操作。</span><span class="sxs-lookup"><span data-stu-id="77bcb-148">A column setting operation initiated with an **IMAPITable::SetColumns** method call has completed.</span></span> 
    
<span data-ttu-id="77bcb-149">TABLE_SORT_DONE</span><span class="sxs-lookup"><span data-stu-id="77bcb-149">TABLE_SORT_DONE</span></span> 
  
> <span data-ttu-id="77bcb-150">已完成使用**IMAPITable:: SortTable**方法调用启动的表排序操作。</span><span class="sxs-lookup"><span data-stu-id="77bcb-150">A table sorting operation initiated with an **IMAPITable::SortTable** method call has completed.</span></span> 
    
<span data-ttu-id="77bcb-151">**hResult**</span><span class="sxs-lookup"><span data-stu-id="77bcb-151">**hResult**</span></span>
  
> <span data-ttu-id="77bcb-152">如果将**ulTableEvent**成员设置为 TABLE_ERROR, 则为已发生的错误的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="77bcb-152">HRESULT value for the error that has occurred, if the **ulTableEvent** member is set to TABLE_ERROR.</span></span> 
    
<span data-ttu-id="77bcb-153">**propIndex**</span><span class="sxs-lookup"><span data-stu-id="77bcb-153">**propIndex**</span></span>
  
> <span data-ttu-id="77bcb-154">受影响的行的**PR_INSTANCE_KEY**属性的[SPropValue](spropvalue.md)结构。</span><span class="sxs-lookup"><span data-stu-id="77bcb-154">[SPropValue](spropvalue.md) structure for the **PR_INSTANCE_KEY** property of the affected row.</span></span> 
    
<span data-ttu-id="77bcb-155">**propPrior**</span><span class="sxs-lookup"><span data-stu-id="77bcb-155">**propPrior**</span></span>
  
> <span data-ttu-id="77bcb-156">受影响的行前面的**PR_INSTANCE_KEY**属性的**SPropValue**结构。</span><span class="sxs-lookup"><span data-stu-id="77bcb-156">**SPropValue** structure for the **PR_INSTANCE_KEY** property of the row before the affected one.</span></span> <span data-ttu-id="77bcb-157">如果受影响的行是表中的第一行, 则**propPrior**必须设置为**PR_NULL** , 而不是零。</span><span class="sxs-lookup"><span data-stu-id="77bcb-157">If the affected row is the first row in the table, **propPrior** must be set to **PR_NULL** and not zero.</span></span> <span data-ttu-id="77bcb-158">零不是有效的属性标记。</span><span class="sxs-lookup"><span data-stu-id="77bcb-158">Zero is not a valid property tag.</span></span> 
    
<span data-ttu-id="77bcb-159">**行**</span><span class="sxs-lookup"><span data-stu-id="77bcb-159">**row**</span></span>
  
> <span data-ttu-id="77bcb-160">描述受影响的行的[SRow](srow.md)结构。</span><span class="sxs-lookup"><span data-stu-id="77bcb-160">[SRow](srow.md) structure describing the affected row.</span></span> <span data-ttu-id="77bcb-161">此结构是为所有表通知事件而填充的。</span><span class="sxs-lookup"><span data-stu-id="77bcb-161">This structure is filled for all table notification events.</span></span> <span data-ttu-id="77bcb-162">对于不传递行数据的表通知事件, **SRow**结构的**cValues**成员设置为零, **lpProps**成员设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="77bcb-162">For table notification events that do not pass row data, the **cValues** member of the **SRow** structure is set to zero and the **lpProps** member is set to NULL.</span></span> <span data-ttu-id="77bcb-163">由于此**SRow**结构是只读的;如果客户端要进行修改, 则必须为其创建副本。</span><span class="sxs-lookup"><span data-stu-id="77bcb-163">Because this **SRow** structure is read-only; clients must make a copy of it if they want to make modifications.</span></span> <span data-ttu-id="77bcb-164">[ScDupPropset](scduppropset.md)函数可用于制作副本。</span><span class="sxs-lookup"><span data-stu-id="77bcb-164">The [ScDupPropset](scduppropset.md) function can be used to make the copy.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="77bcb-165">说明</span><span class="sxs-lookup"><span data-stu-id="77bcb-165">Remarks</span></span>

<span data-ttu-id="77bcb-166">**表\_通知**结构是[通知](notification.md)结构的**info**成员中包含的结构联合的成员之一。</span><span class="sxs-lookup"><span data-stu-id="77bcb-166">The **TABLE\_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="77bcb-167">当结构的**ulEventType**成员设置为_fnevTableModified_时, **info**成员包含一个**表\_通知**结构。</span><span class="sxs-lookup"><span data-stu-id="77bcb-167">The **info** member includes a **TABLE\_NOTIFICATION** structure when the **ulEventType** member of the structure is set to  _fnevTableModified_.</span></span>
  
<span data-ttu-id="77bcb-168">行成员中的列的顺序和类型反映生成通知时有效的顺序和类型。</span><span class="sxs-lookup"><span data-stu-id="77bcb-168">The order and type of columns in the row member reflect the order and type that was in effect at the time that the notification was generated.</span></span> <span data-ttu-id="77bcb-169">通知生成时的顺序和类型不一定与传递通知的时间相同。</span><span class="sxs-lookup"><span data-stu-id="77bcb-169">The order and type at the time that the notification was generated is not necessarily the same as when the notification was delivered.</span></span> 
  
<span data-ttu-id="77bcb-170">有关通知的详细信息, 请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="77bcb-170">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="77bcb-171">**主题**</span><span class="sxs-lookup"><span data-stu-id="77bcb-171">**Topic**</span></span>|<span data-ttu-id="77bcb-172">**说明**</span><span class="sxs-lookup"><span data-stu-id="77bcb-172">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="77bcb-173">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="77bcb-173">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="77bcb-174">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="77bcb-174">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="77bcb-175">处理通知</span><span class="sxs-lookup"><span data-stu-id="77bcb-175">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="77bcb-176">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="77bcb-176">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="77bcb-177">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="77bcb-177">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="77bcb-178">讨论了如何使用**IMAPISupport**方法生成通知的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="77bcb-178">Discussion of how service providers can use the **IMAPISupport** method to generate notifications.</span></span>  <br/> |
   
<span data-ttu-id="77bcb-179">由于表通知是异步的, 因此, 客户端可以在了解通过另一种方法添加的信息后接收已添加的行的通知。</span><span class="sxs-lookup"><span data-stu-id="77bcb-179">Because table notifications are asynchronous, clients can receive notification of an added row after learning about the addition through another means.</span></span> <span data-ttu-id="77bcb-180">如果**IMAPITable:: Sort**、 **IMAPITable:: Restrict**或**IMAPITable:: SetColumns**方法中出现错误, 或者基础进程尝试更新表 (例如 new 或 TABLE_ERROR), 则可能会收到一个 "" 事件。修改的行。</span><span class="sxs-lookup"><span data-stu-id="77bcb-180">It is possible to receive a TABLE_ERROR event when there is an error in an **IMAPITable::Sort**, **IMAPITable::Restrict**, or **IMAPITable::SetColumns** method or when an underlying process attempts to update a table with, for example, new or modified rows.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="77bcb-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77bcb-181">See also</span></span>

- [<span data-ttu-id="77bcb-182">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="77bcb-182">NOTIFICATION</span></span>](notification.md) 
- [<span data-ttu-id="77bcb-183">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="77bcb-183">ScDupPropset</span></span>](scduppropset.md)
- [<span data-ttu-id="77bcb-184">SRow</span><span class="sxs-lookup"><span data-stu-id="77bcb-184">SRow</span></span>](srow.md)
- [<span data-ttu-id="77bcb-185">SPropValue</span><span class="sxs-lookup"><span data-stu-id="77bcb-185">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="77bcb-186">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="77bcb-186">MAPI Structures</span></span>](mapi-structures.md)

