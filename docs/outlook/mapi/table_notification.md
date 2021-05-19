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
# <a name="table_notification"></a><span data-ttu-id="0f3ab-103">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="0f3ab-103">TABLE_NOTIFICATION</span></span>

<span data-ttu-id="0f3ab-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f3ab-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0f3ab-105">描述表中受某种类型事件（如更改或错误）影响的行。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-105">Describes a row in a table that has been affected by some type of event, such as a change or an error.</span></span> <span data-ttu-id="0f3ab-106">这将导致生成表通知。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-106">This causes a table notification to be generated.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0f3ab-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0f3ab-107">Header file:</span></span>  <br/> |<span data-ttu-id="0f3ab-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0f3ab-108">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="0f3ab-109">Members</span><span class="sxs-lookup"><span data-stu-id="0f3ab-109">Members</span></span>

<span data-ttu-id="0f3ab-110">**ulTableEvent**</span><span class="sxs-lookup"><span data-stu-id="0f3ab-110">**ulTableEvent**</span></span>
  
> <span data-ttu-id="0f3ab-111">用于表示表事件类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-111">Bitmask of flags used to represent the table event type.</span></span> <span data-ttu-id="0f3ab-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="0f3ab-112">The following flags can be set:</span></span>
    
<span data-ttu-id="0f3ab-113">TABLE_CHANGED</span><span class="sxs-lookup"><span data-stu-id="0f3ab-113">TABLE_CHANGED</span></span> 
  
> <span data-ttu-id="0f3ab-114">在高级别上指示有关表的一些内容已更改。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-114">Indicates at a high level that something about the table has changed.</span></span> <span data-ttu-id="0f3ab-115">表的状态与事件之前的状态一样。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-115">The table's state is as it was before the event.</span></span> <span data-ttu-id="0f3ab-116">这意味着所有 PR_INSTANCE_KEY  ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 、书签、当前位置和用户界面选择都仍然有效。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-116">This means that all **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) properties, bookmarks, current positioning, and user interface selections are still valid.</span></span> <span data-ttu-id="0f3ab-117">通过重新读取表来处理此事件。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-117">Handle this event by rereading the table.</span></span> <span data-ttu-id="0f3ab-118">不希望实现富表通知的服务提供商会TABLE_CHANGED事件而不是更详细的事件来指示特定类型的更改。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-118">Service providers that do not want to implement rich table notifications send TABLE_CHANGED events instead of more detailed events to indicate a particular type of change.</span></span> 
    
<span data-ttu-id="0f3ab-119">TABLE_ERROR</span><span class="sxs-lookup"><span data-stu-id="0f3ab-119">TABLE_ERROR</span></span> 
  
> <span data-ttu-id="0f3ab-120">通常在处理异步操作期间发生错误。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-120">An error has occurred, usually during the processing of an asynchronous operation.</span></span> <span data-ttu-id="0f3ab-121">处理以下方法时出错可能会生成此事件：</span><span class="sxs-lookup"><span data-stu-id="0f3ab-121">Errors during the processing of the following methods can generate this event:</span></span> 
    
   - [<span data-ttu-id="0f3ab-122">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="0f3ab-122">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
    
   - [<span data-ttu-id="0f3ab-123">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="0f3ab-123">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
    
   - [<span data-ttu-id="0f3ab-124">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="0f3ab-124">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
    
   <span data-ttu-id="0f3ab-125">收到TABLE_ERROR事件后，客户端无法依赖于表内容的准确性。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-125">After receiving a TABLE_ERROR event, a client cannot rely on the accuracy of the table contents.</span></span> <span data-ttu-id="0f3ab-126">此外，有关其他更改的挂起通知可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-126">Also, pending notifications about other changes might be lost.</span></span> <span data-ttu-id="0f3ab-127">[IMAPITable：：GetLastError](imapitable-getlasterror.md)方法可能不会提供有关该错误的任何附加信息，因为它是在上一个时间点生成的，不一定是上一个方法调用生成的。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-127">The [IMAPITable::GetLastError](imapitable-getlasterror.md) method might not provide any additional information about the error because it was generated at some previous point, not necessarily from the last method call.</span></span> 
    
<span data-ttu-id="0f3ab-128">TABLE_RELOAD</span><span class="sxs-lookup"><span data-stu-id="0f3ab-128">TABLE_RELOAD</span></span> 
  
> <span data-ttu-id="0f3ab-129">应重新加载表中的数据。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-129">The data in the table should be reloaded.</span></span> <span data-ttu-id="0f3ab-130">例如，TABLE_RELOAD在数据库中存储基础数据并替换数据库时，服务提供商会发送数据。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-130">Service providers send TABLE_RELOAD when, for example, the underlying data is stored in a database and the database is replaced.</span></span> <span data-ttu-id="0f3ab-131">通过假定表没有任何信息仍然有效，然后重新读取表来处理此事件。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-131">Handle this event by assuming that nothing about the table is still valid and by rereading the table.</span></span> <span data-ttu-id="0f3ab-132">所有书签、实例键、状态和位置信息均无效。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-132">All bookmarks, instance keys, status and positioning information are invalid.</span></span>
    
<span data-ttu-id="0f3ab-133">TABLE_RESTRICT_DONE</span><span class="sxs-lookup"><span data-stu-id="0f3ab-133">TABLE_RESTRICT_DONE</span></span> 
  
> <span data-ttu-id="0f3ab-134">使用 **IMAPITable：：Restrict** 方法调用启动的限制操作已完成。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-134">A restriction operation initiated with an **IMAPITable::Restrict** method call has completed.</span></span> 
    
<span data-ttu-id="0f3ab-135">TABLE_ROW_ADDED</span><span class="sxs-lookup"><span data-stu-id="0f3ab-135">TABLE_ROW_ADDED</span></span> 
  
> <span data-ttu-id="0f3ab-136">新行已添加到表中并保存相应的对象。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-136">A new row has been added to the table and the corresponding object saved.</span></span> <span data-ttu-id="0f3ab-137">TABLE_ROW_ADDED [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法调用后，将生成事件。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-137">TABLE_ROW_ADDED events are generated after a call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
    
<span data-ttu-id="0f3ab-138">TABLE_ROW_DELETED</span><span class="sxs-lookup"><span data-stu-id="0f3ab-138">TABLE_ROW_DELETED</span></span> 
  
> <span data-ttu-id="0f3ab-139">已从表格中删除一行。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-139">A row has been removed from the table.</span></span> <span data-ttu-id="0f3ab-140">**propPrior** 成员设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-140">The **propPrior** member is set to NULL.</span></span> 
    
<span data-ttu-id="0f3ab-141">TABLE_ROW_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0f3ab-141">TABLE_ROW_MODIFIED</span></span> 
  
> <span data-ttu-id="0f3ab-142">行已更改。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-142">A row has been changed.</span></span> <span data-ttu-id="0f3ab-143">行 **成员** 包含行受影响的属性。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-143">The **row** member contains the affected properties for the row.</span></span> <span data-ttu-id="0f3ab-144">多个TABLE_ROW_MODIFIED事件按它们在表视图中的显示顺序发送。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-144">Multiple TABLE_ROW_MODIFIED events are sent in the order that they appear in the table view.</span></span> 
    
  <span data-ttu-id="0f3ab-145">TABLE_ROW_MODIFIED对相应对象的更改后，通过调用 **IMAPIProp：：SaveChanges** 方法发送事件。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-145">TABLE_ROW_MODIFIED events are sent after changes to the corresponding object have been committed with a call to the **IMAPIProp::SaveChanges** method.</span></span> <span data-ttu-id="0f3ab-146">如果修改的行现在是表格中的第一行，**则 propPrior** 成员中的属性标记值PR_NULL ( [PidTagNull](pidtagnull-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-146">If the modified row is now the first row in the table, the value of the property tag in the **propPrior** member is **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)).</span></span>
    
<span data-ttu-id="0f3ab-147">TABLE_SETCOL_DONE</span><span class="sxs-lookup"><span data-stu-id="0f3ab-147">TABLE_SETCOL_DONE</span></span> 
  
> <span data-ttu-id="0f3ab-148">使用 **IMAPITable：：SetColumns** 方法调用启动的列设置操作已完成。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-148">A column setting operation initiated with an **IMAPITable::SetColumns** method call has completed.</span></span> 
    
<span data-ttu-id="0f3ab-149">TABLE_SORT_DONE</span><span class="sxs-lookup"><span data-stu-id="0f3ab-149">TABLE_SORT_DONE</span></span> 
  
> <span data-ttu-id="0f3ab-150">已完成使用 **IMAPITable：：SortTable** 方法调用启动的表排序操作。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-150">A table sorting operation initiated with an **IMAPITable::SortTable** method call has completed.</span></span> 
    
<span data-ttu-id="0f3ab-151">**hResult**</span><span class="sxs-lookup"><span data-stu-id="0f3ab-151">**hResult**</span></span>
  
> <span data-ttu-id="0f3ab-152">如果 **ulTableEvent** 成员设置为活动状态，则已发生错误的 HRESULT TABLE_ERROR。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-152">HRESULT value for the error that has occurred, if the **ulTableEvent** member is set to TABLE_ERROR.</span></span> 
    
<span data-ttu-id="0f3ab-153">**propIndex**</span><span class="sxs-lookup"><span data-stu-id="0f3ab-153">**propIndex**</span></span>
  
> <span data-ttu-id="0f3ab-154">受影响行的 PR_INSTANCE_KEY **属性的** [SPropValue](spropvalue.md)结构。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-154">[SPropValue](spropvalue.md) structure for the **PR_INSTANCE_KEY** property of the affected row.</span></span> 
    
<span data-ttu-id="0f3ab-155">**propPrior**</span><span class="sxs-lookup"><span data-stu-id="0f3ab-155">**propPrior**</span></span>
  
> <span data-ttu-id="0f3ab-156">受影响行之前PR_INSTANCE_KEY属性的 **SPropValue** 结构。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-156">**SPropValue** structure for the **PR_INSTANCE_KEY** property of the row before the affected one.</span></span> <span data-ttu-id="0f3ab-157">如果受影响的行是表格中的第一行 **，propPrior** 必须设置为 **PR_NULL而不是零** 。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-157">If the affected row is the first row in the table, **propPrior** must be set to **PR_NULL** and not zero.</span></span> <span data-ttu-id="0f3ab-158">零不是有效的属性标记。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-158">Zero is not a valid property tag.</span></span> 
    
<span data-ttu-id="0f3ab-159">**row**</span><span class="sxs-lookup"><span data-stu-id="0f3ab-159">**row**</span></span>
  
> <span data-ttu-id="0f3ab-160">描述受影响行的[SRow](srow.md)结构。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-160">[SRow](srow.md) structure describing the affected row.</span></span> <span data-ttu-id="0f3ab-161">此结构用于所有表通知事件。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-161">This structure is filled for all table notification events.</span></span> <span data-ttu-id="0f3ab-162">对于不传递行数据的表通知事件 **，SRow** 结构的 **cValues** 成员设置为零 **，lpProps** 成员设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-162">For table notification events that do not pass row data, the **cValues** member of the **SRow** structure is set to zero and the **lpProps** member is set to NULL.</span></span> <span data-ttu-id="0f3ab-163">因为此 **SRow** 结构是只读的;客户端必须创建一个副本，以进行修改。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-163">Because this **SRow** structure is read-only; clients must make a copy of it if they want to make modifications.</span></span> <span data-ttu-id="0f3ab-164">[ScDupPropset](scduppropset.md)函数可用于创建副本。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-164">The [ScDupPropset](scduppropset.md) function can be used to make the copy.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="0f3ab-165">备注</span><span class="sxs-lookup"><span data-stu-id="0f3ab-165">Remarks</span></span>

<span data-ttu-id="0f3ab-166">**TABLE \_ NOTIFICATION** 结构是 NOTIFICATION 结构的信息成员中包含的结构联合 [的成员](notification.md)之一。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-166">The **TABLE\_NOTIFICATION** structure is one of the members of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure.</span></span> <span data-ttu-id="0f3ab-167">当 **结构的** **ulEventType** 成员设置为 _fnevTableModified_ 时，信息成员包括 TABLE NOTIFICATION 结构。 **\_**</span><span class="sxs-lookup"><span data-stu-id="0f3ab-167">The **info** member includes a **TABLE\_NOTIFICATION** structure when the **ulEventType** member of the structure is set to  _fnevTableModified_.</span></span>
  
<span data-ttu-id="0f3ab-168">行成员中列的顺序和类型反映生成通知时生效的顺序和类型。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-168">The order and type of columns in the row member reflect the order and type that was in effect at the time that the notification was generated.</span></span> <span data-ttu-id="0f3ab-169">生成通知时的顺序和类型不一定与通知送达时相同。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-169">The order and type at the time that the notification was generated is not necessarily the same as when the notification was delivered.</span></span> 
  
<span data-ttu-id="0f3ab-170">有关通知详细信息，请参阅下表中介绍的主题。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-170">For more information about notification, see the topics described in the following table.</span></span>
  
|<span data-ttu-id="0f3ab-171">**主题**</span><span class="sxs-lookup"><span data-stu-id="0f3ab-171">**Topic**</span></span>|<span data-ttu-id="0f3ab-172">**说明**</span><span class="sxs-lookup"><span data-stu-id="0f3ab-172">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0f3ab-173">MAPI 中的事件通知</span><span class="sxs-lookup"><span data-stu-id="0f3ab-173">Event Notification in MAPI</span></span>](event-notification-in-mapi.md) <br/> |<span data-ttu-id="0f3ab-174">通知和通知事件的一般概述。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-174">General overview of notification and notification events.</span></span>  <br/> |
|[<span data-ttu-id="0f3ab-175">处理通知</span><span class="sxs-lookup"><span data-stu-id="0f3ab-175">Handling Notifications</span></span>](handling-notifications.md) <br/> |<span data-ttu-id="0f3ab-176">讨论客户端应如何处理通知。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-176">Discussion of how clients should handle notifications.</span></span>  <br/> |
|[<span data-ttu-id="0f3ab-177">支持事件通知</span><span class="sxs-lookup"><span data-stu-id="0f3ab-177">Supporting Event Notification</span></span>](supporting-event-notification.md) <br/> |<span data-ttu-id="0f3ab-178">讨论服务提供商如何使用 **IMAPISupport** 方法生成通知。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-178">Discussion of how service providers can use the **IMAPISupport** method to generate notifications.</span></span>  <br/> |
   
<span data-ttu-id="0f3ab-179">由于表通知是异步的，因此客户端可以在通过其他方式了解添加内容后收到添加行的通知。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-179">Because table notifications are asynchronous, clients can receive notification of an added row after learning about the addition through another means.</span></span> <span data-ttu-id="0f3ab-180">当 **IMAPITable：：Sort** **、IMAPITable：：Restrict** 或 **IMAPITable：：SetColumns** 方法出错时，或者当基础进程尝试使用新的或修改的行更新表时，可能会收到 TABLE_ERROR 事件。</span><span class="sxs-lookup"><span data-stu-id="0f3ab-180">It is possible to receive a TABLE_ERROR event when there is an error in an **IMAPITable::Sort**, **IMAPITable::Restrict**, or **IMAPITable::SetColumns** method or when an underlying process attempts to update a table with, for example, new or modified rows.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0f3ab-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f3ab-181">See also</span></span>

- [<span data-ttu-id="0f3ab-182">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="0f3ab-182">NOTIFICATION</span></span>](notification.md) 
- [<span data-ttu-id="0f3ab-183">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="0f3ab-183">ScDupPropset</span></span>](scduppropset.md)
- [<span data-ttu-id="0f3ab-184">SRow</span><span class="sxs-lookup"><span data-stu-id="0f3ab-184">SRow</span></span>](srow.md)
- [<span data-ttu-id="0f3ab-185">SPropValue</span><span class="sxs-lookup"><span data-stu-id="0f3ab-185">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="0f3ab-186">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="0f3ab-186">MAPI Structures</span></span>](mapi-structures.md)

