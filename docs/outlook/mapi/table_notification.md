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
ms.openlocfilehash: 7f32145e0947411c48e1e6c3a941c9913a08709c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565842"
---
# <a name="tablenotification"></a><span data-ttu-id="c3d67-103">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c3d67-103">TABLE_NOTIFICATION</span></span>

<span data-ttu-id="c3d67-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c3d67-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c3d67-105">介绍受某些类型的事件，如错误或更改表中的行。</span><span class="sxs-lookup"><span data-stu-id="c3d67-105">Describes a row in a table that has been affected by some type of event, such as a change or an error.</span></span> <span data-ttu-id="c3d67-106">这会导致表通知要生成。</span><span class="sxs-lookup"><span data-stu-id="c3d67-106">This causes a table notification to be generated.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c3d67-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="c3d67-107">Header file:</span></span>  <br/> |<span data-ttu-id="c3d67-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c3d67-108">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="c3d67-109">Members</span><span class="sxs-lookup"><span data-stu-id="c3d67-109">Members</span></span>

<span data-ttu-id="c3d67-110">**ulTableEvent**</span><span class="sxs-lookup"><span data-stu-id="c3d67-110">**ulTableEvent**</span></span>
  
> <span data-ttu-id="c3d67-111">用于表示表事件类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="c3d67-111">Bitmask of flags used to represent the table event type.</span></span> <span data-ttu-id="c3d67-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="c3d67-112">The following flags can be set:</span></span>
    
<span data-ttu-id="c3d67-113">TABLE_CHANGED</span><span class="sxs-lookup"><span data-stu-id="c3d67-113">TABLE_CHANGED</span></span> 
  
> <span data-ttu-id="c3d67-114">指示在高级别已更改内容的表。</span><span class="sxs-lookup"><span data-stu-id="c3d67-114">Indicates at a high level that something about the table has changed.</span></span> <span data-ttu-id="c3d67-115">表的状态是前的事件。</span><span class="sxs-lookup"><span data-stu-id="c3d67-115">The table's state is as it was before the event.</span></span> <span data-ttu-id="c3d67-116">这意味着所有**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性、 书签、 当前定位和用户界面选择都仍然有效。</span><span class="sxs-lookup"><span data-stu-id="c3d67-116">This means that all **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) properties, bookmarks, current positioning, and user interface selections are still valid.</span></span> <span data-ttu-id="c3d67-117">通过重新读取表处理此事件。</span><span class="sxs-lookup"><span data-stu-id="c3d67-117">Handle this event by rereading the table.</span></span> <span data-ttu-id="c3d67-118">要实现富表通知的服务提供商发送 TABLE_CHANGED 事件，而不是更详细的事件，以指示特定类型的更改。</span><span class="sxs-lookup"><span data-stu-id="c3d67-118">Service providers that do not want to implement rich table notifications send TABLE_CHANGED events instead of more detailed events to indicate a particular type of change.</span></span> 
    
<span data-ttu-id="c3d67-119">TABLE_ERROR</span><span class="sxs-lookup"><span data-stu-id="c3d67-119">TABLE_ERROR</span></span> 
  
> <span data-ttu-id="c3d67-120">出错，通常在异步操作的处理。</span><span class="sxs-lookup"><span data-stu-id="c3d67-120">An error has occurred, usually during the processing of an asynchronous operation.</span></span> <span data-ttu-id="c3d67-121">错误处理过程中的以下方法可以生成此事件：</span><span class="sxs-lookup"><span data-stu-id="c3d67-121">Errors during the processing of the following methods can generate this event:</span></span> 
    
   - [<span data-ttu-id="c3d67-122">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="c3d67-122">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
    
   - [<span data-ttu-id="c3d67-123">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="c3d67-123">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
    
   - [<span data-ttu-id="c3d67-124">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="c3d67-124">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
    
   <span data-ttu-id="c3d67-125">接收 TABLE_ERROR 事件之后, 客户端不能依赖目录的准确性。</span><span class="sxs-lookup"><span data-stu-id="c3d67-125">After receiving a TABLE_ERROR event, a client cannot rely on the accuracy of the table contents.</span></span> <span data-ttu-id="c3d67-126">此外，待处理的有关其他更改的通知可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="c3d67-126">Also, pending notifications about other changes might be lost.</span></span> <span data-ttu-id="c3d67-127">[IMAPITable::GetLastError](imapitable-getlasterror.md)方法可能提供有关错误的任何其他信息，因为它已生成以前点，不一定是从最后一个方法调用。</span><span class="sxs-lookup"><span data-stu-id="c3d67-127">The [IMAPITable::GetLastError](imapitable-getlasterror.md) method might not provide any additional information about the error because it was generated at some previous point, not necessarily from the last method call.</span></span> 
    
<span data-ttu-id="c3d67-128">TABLE_RELOAD</span><span class="sxs-lookup"><span data-stu-id="c3d67-128">TABLE_RELOAD</span></span> 
  
> <span data-ttu-id="c3d67-129">应重新加载表中的数据。</span><span class="sxs-lookup"><span data-stu-id="c3d67-129">The data in the table should be reloaded.</span></span> <span data-ttu-id="c3d67-130">服务提供商发送 TABLE_RELOAD 时，例如，基础数据存储在数据库和数据库已替换为。</span><span class="sxs-lookup"><span data-stu-id="c3d67-130">Service providers send TABLE_RELOAD when, for example, the underlying data is stored in a database and the database is replaced.</span></span> <span data-ttu-id="c3d67-131">假定 nothing 有关表是仍然有效和重新读取表处理此事件。</span><span class="sxs-lookup"><span data-stu-id="c3d67-131">Handle this event by assuming that nothing about the table is still valid and by rereading the table.</span></span> <span data-ttu-id="c3d67-132">所有书签、 实例项、 状态和位置信息都是无效。</span><span class="sxs-lookup"><span data-stu-id="c3d67-132">All bookmarks, instance keys, status and positioning information are invalid.</span></span>
    
<span data-ttu-id="c3d67-133">TABLE_RESTRICT_DONE</span><span class="sxs-lookup"><span data-stu-id="c3d67-133">TABLE_RESTRICT_DONE</span></span> 
  
> <span data-ttu-id="c3d67-134">启动**IMAPITable::Restrict**方法调用的限制操作已完成。</span><span class="sxs-lookup"><span data-stu-id="c3d67-134">A restriction operation initiated with an **IMAPITable::Restrict** method call has completed.</span></span> 
    
<span data-ttu-id="c3d67-135">TABLE_ROW_ADDED</span><span class="sxs-lookup"><span data-stu-id="c3d67-135">TABLE_ROW_ADDED</span></span> 
  
> <span data-ttu-id="c3d67-136">新行已添加到表并保存相应对象。</span><span class="sxs-lookup"><span data-stu-id="c3d67-136">A new row has been added to the table and the corresponding object saved.</span></span> <span data-ttu-id="c3d67-137">调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法后会生成 TABLE_ROW_ADDED 事件。</span><span class="sxs-lookup"><span data-stu-id="c3d67-137">TABLE_ROW_ADDED events are generated after a call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
    
<span data-ttu-id="c3d67-138">TABLE_ROW_DELETED</span><span class="sxs-lookup"><span data-stu-id="c3d67-138">TABLE_ROW_DELETED</span></span> 
  
> <span data-ttu-id="c3d67-139">从表中已被删除行。</span><span class="sxs-lookup"><span data-stu-id="c3d67-139">A row has been removed from the table.</span></span> <span data-ttu-id="c3d67-140">**PropPrior**成员设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c3d67-140">The **propPrior** member is set to NULL.</span></span> 
    
<span data-ttu-id="c3d67-141">TABLE_ROW_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c3d67-141">TABLE_ROW_MODIFIED</span></span> 
  
> <span data-ttu-id="c3d67-142">已更改的行。</span><span class="sxs-lookup"><span data-stu-id="c3d67-142">A row has been changed.</span></span> <span data-ttu-id="c3d67-143">**行**成员包含行受影响的属性。</span><span class="sxs-lookup"><span data-stu-id="c3d67-143">The **row** member contains the affected properties for the row.</span></span> <span data-ttu-id="c3d67-144">多个 TABLE_ROW_MODIFIED 事件发送它们在表视图中显示的顺序。</span><span class="sxs-lookup"><span data-stu-id="c3d67-144">Multiple TABLE_ROW_MODIFIED events are sent in the order that they appear in the table view.</span></span> 
    
  <span data-ttu-id="c3d67-145">TABLE_ROW_MODIFIED 事件发送后已经与调用**IMAPIProp::SaveChanges**方法提交到相应的对象的更改。</span><span class="sxs-lookup"><span data-stu-id="c3d67-145">TABLE_ROW_MODIFIED events are sent after changes to the corresponding object have been committed with a call to the **IMAPIProp::SaveChanges** method.</span></span> <span data-ttu-id="c3d67-146">如果已修改的行现在是表中的第一行， **propPrior**成员中的属性标记的值为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="c3d67-146">If the modified row is now the first row in the table, the value of the property tag in the **propPrior** member is **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)).</span></span>
    
<span data-ttu-id="c3d67-147">TABLE_SETCOL_DONE</span><span class="sxs-lookup"><span data-stu-id="c3d67-147">TABLE_SETCOL_DONE</span></span> 
  
> <span data-ttu-id="c3d67-148">启动**IMAPITable::SetColumns**方法调用列设置操作已完成。</span><span class="sxs-lookup"><span data-stu-id="c3d67-148">A column setting operation initiated with an **IMAPITable::SetColumns** method call has completed.</span></span> 
    
<span data-ttu-id="c3d67-149">TABLE_SORT_DONE</span><span class="sxs-lookup"><span data-stu-id="c3d67-149">TABLE_SORT_DONE</span></span> 
  
> <span data-ttu-id="c3d67-150">已完成，表的排序操作启动**IMAPITable::SortTable**方法调用。</span><span class="sxs-lookup"><span data-stu-id="c3d67-150">A table sorting operation initiated with an **IMAPITable::SortTable** method call has completed.</span></span> 
    
<span data-ttu-id="c3d67-151">**hResult**</span><span class="sxs-lookup"><span data-stu-id="c3d67-151">**hResult**</span></span>
  
> <span data-ttu-id="c3d67-152">如果设置为 TABLE_ERROR **ulTableEvent**成员已发生的错误的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="c3d67-152">HRESULT value for the error that has occurred, if the **ulTableEvent** member is set to TABLE_ERROR.</span></span> 
    
<span data-ttu-id="c3d67-153">**propIndex**</span><span class="sxs-lookup"><span data-stu-id="c3d67-153">**propIndex**</span></span>
  
> <span data-ttu-id="c3d67-154">受影响的行的**PR_INSTANCE_KEY**属性的[SPropValue](spropvalue.md)结构。</span><span class="sxs-lookup"><span data-stu-id="c3d67-154">[SPropValue](spropvalue.md) structure for the **PR_INSTANCE_KEY** property of the affected row.</span></span> 
    
<span data-ttu-id="c3d67-155">**propPrior**</span><span class="sxs-lookup"><span data-stu-id="c3d67-155">**propPrior**</span></span>
  
> <span data-ttu-id="c3d67-156">受影响的一个之前的行的**PR_INSTANCE_KEY**属性**SPropValue**结构。</span><span class="sxs-lookup"><span data-stu-id="c3d67-156">**SPropValue** structure for the **PR_INSTANCE_KEY** property of the row before the affected one.</span></span> <span data-ttu-id="c3d67-157">如果受影响的行，表中的第一行**propPrior**必须设置为**PR_NULL**和不为零。</span><span class="sxs-lookup"><span data-stu-id="c3d67-157">If the affected row is the first row in the table, **propPrior** must be set to **PR_NULL** and not zero.</span></span> <span data-ttu-id="c3d67-158">零不是有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="c3d67-158">Zero is not a valid property tag.</span></span> 
    
<span data-ttu-id="c3d67-159">**row**</span><span class="sxs-lookup"><span data-stu-id="c3d67-159">**row**</span></span>
  
> <span data-ttu-id="c3d67-160">[SRow](srow.md)结构，描述受影响的行。</span><span class="sxs-lookup"><span data-stu-id="c3d67-160">[SRow](srow.md) structure describing the affected row.</span></span> <span data-ttu-id="c3d67-161">为所有表通知事件填充该结构。</span><span class="sxs-lookup"><span data-stu-id="c3d67-161">This structure is filled for all table notification events.</span></span> <span data-ttu-id="c3d67-162">对于不传递行数据的表通知事件， **SRow**结构的**cValues**成员设置为零， **lpProps**成员设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c3d67-162">For table notification events that do not pass row data, the **cValues** member of the **SRow** structure is set to zero and the **lpProps** member is set to NULL.</span></span> <span data-ttu-id="c3d67-163">因为此**SRow**结构是只读的。如果他们想要进行修改，客户端必须创建它的一个副本。</span><span class="sxs-lookup"><span data-stu-id="c3d67-163">Because this **SRow** structure is read-only; clients must make a copy of it if they want to make modifications.</span></span> <span data-ttu-id="c3d67-164">[ScDupPropset](scduppropset.md)函数可用于创建副本。</span><span class="sxs-lookup"><span data-stu-id="c3d67-164">The [ScDupPropset](scduppropset.md) function can be used to make the copy.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c3d67-165">注解</span><span class="sxs-lookup"><span data-stu-id="c3d67-165">Remarks</span></span>

<span data-ttu-id="c3d67-166">**表\_通知**结构是结构[通知](notification.md)结构的**信息**成员中包含的联合的成员之一。</span><span class="sxs-lookup"><span data-stu-id="c3d67-166">The **TABLE\_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="c3d67-167">**Info**成员包括**表\_通知**结构结构中的**ulEventType**成员设置为_fnevTableModified_时。</span><span class="sxs-lookup"><span data-stu-id="c3d67-167">The **info** member includes a **TABLE\_NOTIFICATION** structure when the **ulEventType** member of the structure is set to  _fnevTableModified_.</span></span>
  
<span data-ttu-id="c3d67-168">顺序和行成员中的列类型反映的顺序和生效时所处的生成通知的类型。</span><span class="sxs-lookup"><span data-stu-id="c3d67-168">The order and type of columns in the row member reflect the order and type that was in effect at the time that the notification was generated.</span></span> <span data-ttu-id="c3d67-169">顺序和时生成通知的类型不一定相同时通知已送达。</span><span class="sxs-lookup"><span data-stu-id="c3d67-169">The order and type at the time that the notification was generated is not necessarily the same as when the notification was delivered.</span></span> 
  
<span data-ttu-id="c3d67-170">有关通知的详细信息，请参阅下表中所述的主题。</span><span class="sxs-lookup"><span data-stu-id="c3d67-170">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="c3d67-171">**主题**</span><span class="sxs-lookup"><span data-stu-id="c3d67-171">**Topic**</span></span>|<span data-ttu-id="c3d67-172">**说明**</span><span class="sxs-lookup"><span data-stu-id="c3d67-172">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c3d67-173">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="c3d67-173">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="c3d67-174">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="c3d67-174">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="c3d67-175">处理通知</span><span class="sxs-lookup"><span data-stu-id="c3d67-175">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="c3d67-176">讨论了客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="c3d67-176">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="c3d67-177">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="c3d67-177">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="c3d67-178">讨论的服务提供程序如何使用**IMAPISupport**方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="c3d67-178">Discussion of how service providers can use the **IMAPISupport** method to generate notifications.</span></span>  <br/> |
   
<span data-ttu-id="c3d67-179">表通知是异步的因为客户端可以接收有关通过其他方式添加学习之后添加一行的通知。</span><span class="sxs-lookup"><span data-stu-id="c3d67-179">Because table notifications are asynchronous, clients can receive notification of an added row after learning about the addition through another means.</span></span> <span data-ttu-id="c3d67-180">可以接收 TABLE_ERROR 事件在**IMAPITable::Sort**、 **IMAPITable::Restrict**或**IMAPITable::SetColumns**方法时出现错误或进程时基础尝试更新一个表格，例如，新时或修改后的行。</span><span class="sxs-lookup"><span data-stu-id="c3d67-180">It is possible to receive a TABLE_ERROR event when there is an error in an **IMAPITable::Sort**, **IMAPITable::Restrict**, or **IMAPITable::SetColumns** method or when an underlying process attempts to update a table with, for example, new or modified rows.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c3d67-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3d67-181">See also</span></span>

- [<span data-ttu-id="c3d67-182">通知</span><span class="sxs-lookup"><span data-stu-id="c3d67-182">NOTIFICATION</span></span>](notification.md) 
- [<span data-ttu-id="c3d67-183">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="c3d67-183">ScDupPropset</span></span>](scduppropset.md)
- [<span data-ttu-id="c3d67-184">SRow</span><span class="sxs-lookup"><span data-stu-id="c3d67-184">SRow</span></span>](srow.md)
- [<span data-ttu-id="c3d67-185">SPropValue</span><span class="sxs-lookup"><span data-stu-id="c3d67-185">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="c3d67-186">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c3d67-186">MAPI Structures</span></span>](mapi-structures.md)

