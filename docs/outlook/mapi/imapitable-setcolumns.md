---
title: IMAPITableSetColumns
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SetColumns
api_type:
- COM
ms.assetid: 9a39cf8d-df0f-493c-b272-f15c65b3f15e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b6a27231c8dd2c0796b2dcba268de54fcd93e38d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587906"
---
# <a name="imapitablesetcolumns"></a><span data-ttu-id="e1197-103">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="e1197-103">IMAPITable::SetColumns</span></span>

  
  
<span data-ttu-id="e1197-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e1197-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e1197-105">定义的特定属性和属性的顺序显示为表中的列。</span><span class="sxs-lookup"><span data-stu-id="e1197-105">Defines the particular properties and order of properties to appear as columns in the table.</span></span>
  
```cpp
HRESULT SetColumns(
LPSPropTagArray lpPropTagArray,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="e1197-106">参数</span><span class="sxs-lookup"><span data-stu-id="e1197-106">Parameters</span></span>

 <span data-ttu-id="e1197-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="e1197-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="e1197-108">[in]指向属性标记标识属性必须包含作为表中的列的数组。</span><span class="sxs-lookup"><span data-stu-id="e1197-108">[in] Pointer to an array of property tags identifying properties to be included as columns in the table.</span></span> <span data-ttu-id="e1197-109">每个标记的属性类型部分可以设置为有效的类型或**PR_NULL**为后续增加保留空间。</span><span class="sxs-lookup"><span data-stu-id="e1197-109">The property type portion of each tag can be set to a valid type or to **PR_NULL** to reserve space for subsequent additions.</span></span> <span data-ttu-id="e1197-110">不能_lpPropTagArray_参数设置为 NULL;每个表必须有至少一个列。</span><span class="sxs-lookup"><span data-stu-id="e1197-110">The  _lpPropTagArray_ parameter cannot be set to NULL; every table must have at least one column.</span></span> 
    
 <span data-ttu-id="e1197-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e1197-111">_ulFlags_</span></span>
  
> <span data-ttu-id="e1197-112">[in]位掩码的标志控制的异步调用**SetColumns**，例如，在通知使用**SetColumns**时返回的。</span><span class="sxs-lookup"><span data-stu-id="e1197-112">[in] Bitmask of flags that controls the return of an asynchronous call to **SetColumns**, for example when **SetColumns** is used in notification.</span></span> <span data-ttu-id="e1197-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="e1197-113">The following flags can be set:</span></span> 
    
<span data-ttu-id="e1197-114">TBL_ASYNC</span><span class="sxs-lookup"><span data-stu-id="e1197-114">TBL_ASYNC</span></span> 
  
> <span data-ttu-id="e1197-115">列设置操作是请求执行异步导致**SetColumns**可能返回操作完全完成之前。</span><span class="sxs-lookup"><span data-stu-id="e1197-115">Requests that the column setting operation be performed asynchronously causing **SetColumns** to potentially return before the operation has fully completed.</span></span> 
    
<span data-ttu-id="e1197-116">TBL_BATCH</span><span class="sxs-lookup"><span data-stu-id="e1197-116">TBL_BATCH</span></span> 
  
> <span data-ttu-id="e1197-117">允许该表推迟列设置操作，直到所实际需要的数据。</span><span class="sxs-lookup"><span data-stu-id="e1197-117">Permits the table to postpone the column setting operation until the data is actually required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e1197-118">返回值</span><span class="sxs-lookup"><span data-stu-id="e1197-118">Return value</span></span>

<span data-ttu-id="e1197-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1197-119">S_OK</span></span> 
  
> <span data-ttu-id="e1197-120">列设置操作已成功。</span><span class="sxs-lookup"><span data-stu-id="e1197-120">The column setting operation was successful.</span></span>
    
<span data-ttu-id="e1197-121">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="e1197-121">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="e1197-122">另一个操作正在进行阻止设置启动操作列中。</span><span class="sxs-lookup"><span data-stu-id="e1197-122">Another operation is in progress that prevents the column setting operation from starting.</span></span> <span data-ttu-id="e1197-123">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="e1197-123">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e1197-124">注解</span><span class="sxs-lookup"><span data-stu-id="e1197-124">Remarks</span></span>

<span data-ttu-id="e1197-125">表的列集是组的表中的行的列组成的属性。</span><span class="sxs-lookup"><span data-stu-id="e1197-125">The column set of a table is the group of properties that make up the columns for the rows in the table.</span></span> <span data-ttu-id="e1197-126">没有为每种类型的表的默认列。</span><span class="sxs-lookup"><span data-stu-id="e1197-126">There is a default column set for each type of table.</span></span> <span data-ttu-id="e1197-127">默认列集由属性表实施自动包含组成。</span><span class="sxs-lookup"><span data-stu-id="e1197-127">The default column set is made up of the properties that the table implementer automatically includes.</span></span> <span data-ttu-id="e1197-128">表的用户可以更改通过调用**IMAPITable::SetColumns**方法设置此默认值。</span><span class="sxs-lookup"><span data-stu-id="e1197-128">Table users can alter this default set by calling the **IMAPITable::SetColumns** method.</span></span> <span data-ttu-id="e1197-129">它们可以请求将其他列添加到默认的设置如果表实施支持其列被删除或更改列的顺序。</span><span class="sxs-lookup"><span data-stu-id="e1197-129">They can request that other columns be added to the default set if the table implementer supports them that columns be removed, or that the order of columns be changed.</span></span> <span data-ttu-id="e1197-130">**SetColumns**与每个行的行中的这些列顺序指定返回的列。</span><span class="sxs-lookup"><span data-stu-id="e1197-130">**SetColumns** specifies the columns that are returned with each row and the order of these columns within the row.</span></span> 
  
<span data-ttu-id="e1197-131">**SetColumns**操作成功很明显的仅后所做的后续调用来检索数据的表。</span><span class="sxs-lookup"><span data-stu-id="e1197-131">The success of the **SetColumns** operation is apparent only after a subsequent call has been made to retrieve the data of the table.</span></span> <span data-ttu-id="e1197-132">然后是报告了任何错误。</span><span class="sxs-lookup"><span data-stu-id="e1197-132">It is then that any errors are reported.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e1197-133">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="e1197-133">Notes to implementers</span></span>

<span data-ttu-id="e1197-134">某些提供程序允许**SetColumns**呼叫可仅属于表视图的可用列的表格列进行排序。</span><span class="sxs-lookup"><span data-stu-id="e1197-134">Some providers allow a **SetColumns** call to order only table columns that are part of the available columns for a table view.</span></span> <span data-ttu-id="e1197-135">其他提供程序允许**SetColumns**呼叫进行排序所有的表格列，包括那些包含不在原始的列集的属性。</span><span class="sxs-lookup"><span data-stu-id="e1197-135">Other providers allow a **SetColumns** call to order all table columns, including those containing properties not in the original column set.</span></span> 
  
<span data-ttu-id="e1197-136">当 TBL_BATCH 设置的异步操作时，提供程序应返回 PT_ERROR 属性类型，并且不受支持的列的空值的属性值。</span><span class="sxs-lookup"><span data-stu-id="e1197-136">When TBL_BATCH is set for asynchronous operations, providers should return a property type of PT_ERROR and a property value of NULL for columns that are not supported.</span></span>
  
<span data-ttu-id="e1197-137">不需要响应请求操作将异步 TBL_ASYNC 标志。</span><span class="sxs-lookup"><span data-stu-id="e1197-137">You do not need to respond to the TBL_ASYNC flag requesting that the operation be asynchronous.</span></span> <span data-ttu-id="e1197-138">如果您不支持异步列集定义，同步执行操作。</span><span class="sxs-lookup"><span data-stu-id="e1197-138">If you do not support asynchronous column set definition, perform the operation synchronously.</span></span> <span data-ttu-id="e1197-139">您可以支持 TBL_ASYNC 标志，另一个异步操作仍在进度，返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="e1197-139">If you can support the TBL_ASYNC flag and another asynchronous operation is still in progress, return MAPI_E_BUSY.</span></span> <span data-ttu-id="e1197-140">否则，返回 S_OK 而不考虑支持所有属性标记数组中包括的属性。</span><span class="sxs-lookup"><span data-stu-id="e1197-140">Otherwise, return S_OK regardless of whether or not you support all of the properties included in the property tag array.</span></span> <span data-ttu-id="e1197-141">应从的检索数据，如**QueryRows** **IMAPITable**方法返回错误生成不受支持的属性。</span><span class="sxs-lookup"><span data-stu-id="e1197-141">Errors resulting from unsupported properties should be returned from **IMAPITable** methods that retrieve data, such as **QueryRows**.</span></span> 
  
<span data-ttu-id="e1197-142">不会生成通知处于隐藏状态的表格行从视图通过调用**限制**。</span><span class="sxs-lookup"><span data-stu-id="e1197-142">Do not generate notifications for table rows that are hidden from view by calls to **Restrict**.</span></span> 
  
<span data-ttu-id="e1197-143">时发送表通知、 [TABLE_NOTIFICATION](table_notification.md)结构中的**行**成员中的属性的顺序和顺序指定最近**SetColumns**调用必须相同截止通知请求的时间已发送。</span><span class="sxs-lookup"><span data-stu-id="e1197-143">When sending table notifications, the order of the properties in the **row** member of the [TABLE_NOTIFICATION](table_notification.md) structure and the order specified by the most recent **SetColumns** call must be the same as of the time that the notification request was sent.</span></span> 
  
<span data-ttu-id="e1197-144">另一个标志，TBL_BATCH，允许呼叫者在指定表实施者可以将推迟评估直到以后操作的结果。</span><span class="sxs-lookup"><span data-stu-id="e1197-144">Another flag, TBL_BATCH, allows callers to specify that the table implementer can defer evaluating the results of the operation until a later time.</span></span> <span data-ttu-id="e1197-145">只要有可能，应将设置主叫方此标志，因为批处理的操作可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="e1197-145">Whenever possible, callers should set this flag because batched operation improves performance.</span></span>
  
<span data-ttu-id="e1197-146">通常方便的呼叫者在保留中的值，以后添加检索的行集的某些列。</span><span class="sxs-lookup"><span data-stu-id="e1197-146">It is often convenient for callers to reserve some columns in the retrieved row set for values to be added later.</span></span> <span data-ttu-id="e1197-147">呼叫者在执行此操作在传递给**SetColumns**; 该属性标记数组中所需的位置设置一道**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))表将传递回**PR_NULL**所有行中的这些位置检索与**QueryRows**然后。</span><span class="sxs-lookup"><span data-stu-id="e1197-147">Callers do this by placing **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) at the desired positions in the property tag array passed to **SetColumns**; the table will then pass back **PR_NULL** at those positions in all rows retrieved with **QueryRows**.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="e1197-148">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e1197-148">Notes to callers</span></span>

<span data-ttu-id="e1197-149">构建_lpPropTagArray_参数属性标记数组时, 您想要在表视图中显示的列的顺序排序标记。</span><span class="sxs-lookup"><span data-stu-id="e1197-149">When building the property tag array for the  _lpPropTagArray_ parameter, order the tags in the order that you want the columns to appear in the table view.</span></span> 
  
<span data-ttu-id="e1197-150">您可以指定多值的属性包含设置通过将多值的实例标志或 MVI_FLAG 常量应用于属性标记列中。</span><span class="sxs-lookup"><span data-stu-id="e1197-150">You can specify multivalued properties to be included in the column set by applying the multivalued instance flag, or MVI_FLAG constant, to the property tag.</span></span> <span data-ttu-id="e1197-151">设置此标志属性标记为单值属性的版本作为参数传递给 MVI_PROP 宏，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e1197-151">Set this flag by passing the property tag for the single-valued version of the property as a parameter to the MVI_PROP macro as follows:</span></span>
  
```
MVI_PROP(ulPropTag)

```

<span data-ttu-id="e1197-152">MVI_PROP 宏将设置该属性，将转换的多值标记为标记 MVI_FLAG。</span><span class="sxs-lookup"><span data-stu-id="e1197-152">The MVI_PROP macro will set MVI_FLAG for the property, turning the tag into a multivalued tag.</span></span> <span data-ttu-id="e1197-153">如果您错误地尝试调用 MVI_PROP 对单值属性，MAPI 将忽略呼叫并保持不变的属性标记。</span><span class="sxs-lookup"><span data-stu-id="e1197-153">If you erroneously try to call MVI_PROP on a single-valued property, MAPI will ignore the call and leave the property tag unchanged.</span></span> 
  
<span data-ttu-id="e1197-154">您可以包括属性设置为**PR_NULL**属性标记数组中保留空间列设置中的标记。</span><span class="sxs-lookup"><span data-stu-id="e1197-154">You can include property tags set to **PR_NULL** in the property tag array to reserve space in the column set.</span></span> <span data-ttu-id="e1197-155">保留空间允许您添加到列设置而无需分配新的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="e1197-155">Reserving space allows you to add to a column set without having to allocate a new property tag array.</span></span> 
  
<span data-ttu-id="e1197-156">**SetColumns**您调用使表的列的顺序发生的更改以及一个或多个列表示一个多值的属性时，可能要增加的表中的行数。</span><span class="sxs-lookup"><span data-stu-id="e1197-156">When your call to **SetColumns** causes a change to the order of a table's columns and one or more of these columns represent a multivalued property, it is possible for the number of rows in the table to increase.</span></span> <span data-ttu-id="e1197-157">如果发生这种情况，将放弃所有表的书签。</span><span class="sxs-lookup"><span data-stu-id="e1197-157">If this occurs, all of the bookmarks for the table are discarded.</span></span> <span data-ttu-id="e1197-158">详细了解如何多值的列会影响表，请参阅[使用多值列](working-with-multivalued-columns.md)。</span><span class="sxs-lookup"><span data-stu-id="e1197-158">For more information about how multivalued columns affect tables, see [Working with Multivalued Columns](working-with-multivalued-columns.md).</span></span>
  
<span data-ttu-id="e1197-159">设置列是默认情况下同步操作。</span><span class="sxs-lookup"><span data-stu-id="e1197-159">Setting columns is by default a synchronous operation.</span></span> <span data-ttu-id="e1197-160">但是，您可以允许表，直到数据所需通过设置 TBL_BATCH 标志如次推迟操作。</span><span class="sxs-lookup"><span data-stu-id="e1197-160">However, you can allow the table to postpone the operation until such time as the data is needed by setting the TBL_BATCH flag.</span></span> <span data-ttu-id="e1197-161">将该标志设置可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="e1197-161">Setting this flag can improve performance.</span></span> <span data-ttu-id="e1197-162">另一个标志，TBL_ASYNC，使操作异步，允许**SetColumns**返回才能完成此操作。</span><span class="sxs-lookup"><span data-stu-id="e1197-162">Another flag, TBL_ASYNC, makes the operation asynchronous, allowing **SetColumns** to return before the operation is complete.</span></span> <span data-ttu-id="e1197-163">若要确定完成发生时，请调用[IMAPITable::GetStatus](imapitable-getstatus.md)。</span><span class="sxs-lookup"><span data-stu-id="e1197-163">To determine when completion occurs, call [IMAPITable::GetStatus](imapitable-getstatus.md).</span></span>
  
<span data-ttu-id="e1197-164">如果对**SetColumns**的调用返回 MAPI_E_BUSY，表示另一个操作阻止了您的操作启动，则可以呼叫[IMAPITable::Abort](imapitable-abort.md)停止正在进行的操作。</span><span class="sxs-lookup"><span data-stu-id="e1197-164">If a call to **SetColumns** returns MAPI_E_BUSY, indicating that another operation is preventing your operation from starting, you can call [IMAPITable::Abort](imapitable-abort.md) to stop the operation in progress.</span></span> 
  
<span data-ttu-id="e1197-165">您可以调用[HrAddColumnsEx](hraddcolumnsex.md)更改一列。</span><span class="sxs-lookup"><span data-stu-id="e1197-165">You can also call [HrAddColumnsEx](hraddcolumnsex.md) to change a column set.</span></span> <span data-ttu-id="e1197-166">**HrAddColumnsEx**和**IMAPITable::SetColumns**之间的区别是**HrAddColumnsEx**是较低灵活;它只能添加列。</span><span class="sxs-lookup"><span data-stu-id="e1197-166">The difference between **HrAddColumnsEx** and **IMAPITable::SetColumns** is that **HrAddColumnsEx** is less flexible; it can only add columns.</span></span> <span data-ttu-id="e1197-167">额外的列的位于列集; 的开头以下这些列将显示所有的现有列。</span><span class="sxs-lookup"><span data-stu-id="e1197-167">The additional columns are placed at the beginning of the column set; all existing columns appear following these columns.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e1197-168">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="e1197-168">MFCMAPI reference</span></span>

<span data-ttu-id="e1197-169">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e1197-169">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e1197-170">**文件**</span><span class="sxs-lookup"><span data-stu-id="e1197-170">**File**</span></span>|<span data-ttu-id="e1197-171">**函数**</span><span class="sxs-lookup"><span data-stu-id="e1197-171">**Function**</span></span>|<span data-ttu-id="e1197-172">**Comment**</span><span class="sxs-lookup"><span data-stu-id="e1197-172">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1197-173">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="e1197-173">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="e1197-174">CContentsTableListCtrl::DoSetColumns</span><span class="sxs-lookup"><span data-stu-id="e1197-174">CContentsTableListCtrl::DoSetColumns</span></span>  <br/> |<span data-ttu-id="e1197-175">MFCMAPI 使用**IMAPITable::SetColumns**方法设置所需的表的列。</span><span class="sxs-lookup"><span data-stu-id="e1197-175">MFCMAPI uses the **IMAPITable::SetColumns** method to set the desired columns for the table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e1197-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1197-176">See also</span></span>



[<span data-ttu-id="e1197-177">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="e1197-177">HrQueryAllRows</span></span>](hrqueryallrows.md)
  
[<span data-ttu-id="e1197-178">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="e1197-178">IMAPITable::Abort</span></span>](imapitable-abort.md)
  
[<span data-ttu-id="e1197-179">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="e1197-179">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
  
[<span data-ttu-id="e1197-180">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="e1197-180">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="e1197-181">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="e1197-181">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="e1197-182">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="e1197-182">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
  
[<span data-ttu-id="e1197-183">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="e1197-183">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="e1197-184">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="e1197-184">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="e1197-185">SPropValue</span><span class="sxs-lookup"><span data-stu-id="e1197-185">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="e1197-186">SRowSet</span><span class="sxs-lookup"><span data-stu-id="e1197-186">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="e1197-187">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e1197-187">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="e1197-188">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e1197-188">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="e1197-189">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e1197-189">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

