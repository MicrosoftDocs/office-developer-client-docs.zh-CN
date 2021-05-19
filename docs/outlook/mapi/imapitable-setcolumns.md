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
ms.openlocfilehash: 897330feb216dbc3ab143378977c77141cf488f0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416347"
---
# <a name="imapitablesetcolumns"></a><span data-ttu-id="c7bc4-103">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="c7bc4-103">IMAPITable::SetColumns</span></span>

  
  
<span data-ttu-id="c7bc4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7bc4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7bc4-105">定义要作为表格中的列显示的属性的特定属性和顺序。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-105">Defines the particular properties and order of properties to appear as columns in the table.</span></span>
  
```cpp
HRESULT SetColumns(
LPSPropTagArray lpPropTagArray,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="c7bc4-106">参数</span><span class="sxs-lookup"><span data-stu-id="c7bc4-106">Parameters</span></span>

 <span data-ttu-id="c7bc4-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="c7bc4-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="c7bc4-108">[in]指向属性标记数组的指针，用于标识要作为表中的列包含的属性。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-108">[in] Pointer to an array of property tags identifying properties to be included as columns in the table.</span></span> <span data-ttu-id="c7bc4-109">每个标记的属性类型部分可以设置为有效类型，也可以设置为PR_NULL保留空间以用于后续添加。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-109">The property type portion of each tag can be set to a valid type or to **PR_NULL** to reserve space for subsequent additions.</span></span> <span data-ttu-id="c7bc4-110">_lpPropTagArray_ 参数不能设置为 NULL;每个表都必须至少有一列。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-110">The  _lpPropTagArray_ parameter cannot be set to NULL; every table must have at least one column.</span></span> 
    
 <span data-ttu-id="c7bc4-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c7bc4-111">_ulFlags_</span></span>
  
> <span data-ttu-id="c7bc4-112">[in]控制对 **SetColumns** 的异步调用返回的标志的位掩码，例如，在通知中使用 **SetColumns** 时。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-112">[in] Bitmask of flags that controls the return of an asynchronous call to **SetColumns**, for example when **SetColumns** is used in notification.</span></span> <span data-ttu-id="c7bc4-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="c7bc4-113">The following flags can be set:</span></span> 
    
<span data-ttu-id="c7bc4-114">TBL_ASYNC</span><span class="sxs-lookup"><span data-stu-id="c7bc4-114">TBL_ASYNC</span></span> 
  
> <span data-ttu-id="c7bc4-115">请求异步执行列设置操作，导致 **SetColumns** 在操作完全完成之前可能返回。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-115">Requests that the column setting operation be performed asynchronously causing **SetColumns** to potentially return before the operation has fully completed.</span></span> 
    
<span data-ttu-id="c7bc4-116">TBL_BATCH</span><span class="sxs-lookup"><span data-stu-id="c7bc4-116">TBL_BATCH</span></span> 
  
> <span data-ttu-id="c7bc4-117">允许表推迟列设置操作，直到实际需要数据。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-117">Permits the table to postpone the column setting operation until the data is actually required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c7bc4-118">返回值</span><span class="sxs-lookup"><span data-stu-id="c7bc4-118">Return value</span></span>

<span data-ttu-id="c7bc4-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7bc4-119">S_OK</span></span> 
  
> <span data-ttu-id="c7bc4-120">列设置操作成功。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-120">The column setting operation was successful.</span></span>
    
<span data-ttu-id="c7bc4-121">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="c7bc4-121">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="c7bc4-122">另一个操作正在进行中，该操作阻止列设置操作启动。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-122">Another operation is in progress that prevents the column setting operation from starting.</span></span> <span data-ttu-id="c7bc4-123">应允许完成或停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-123">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c7bc4-124">备注</span><span class="sxs-lookup"><span data-stu-id="c7bc4-124">Remarks</span></span>

<span data-ttu-id="c7bc4-125">表格的列集是组成表格中行的列的属性组。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-125">The column set of a table is the group of properties that make up the columns for the rows in the table.</span></span> <span data-ttu-id="c7bc4-126">每种类型的表都有一个默认列集。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-126">There is a default column set for each type of table.</span></span> <span data-ttu-id="c7bc4-127">默认列集由表实现程序自动包含的属性所决定。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-127">The default column set is made up of the properties that the table implementer automatically includes.</span></span> <span data-ttu-id="c7bc4-128">表用户可以通过调用 **IMAPITable：：SetColumns** 方法来更改此默认设置。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-128">Table users can alter this default set by calling the **IMAPITable::SetColumns** method.</span></span> <span data-ttu-id="c7bc4-129">如果表实现程序支持删除其他列，或者更改列的顺序，则它们可以请求将其他列添加到默认集。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-129">They can request that other columns be added to the default set if the table implementer supports them that columns be removed, or that the order of columns be changed.</span></span> <span data-ttu-id="c7bc4-130">**SetColumns** 指定每行返回的列以及这些列在行中的顺序。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-130">**SetColumns** specifies the columns that are returned with each row and the order of these columns within the row.</span></span> 
  
<span data-ttu-id="c7bc4-131">只有在执行后续调用以检索表数据后 **，SetColumns** 操作才明显成功。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-131">The success of the **SetColumns** operation is apparent only after a subsequent call has been made to retrieve the data of the table.</span></span> <span data-ttu-id="c7bc4-132">然后报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-132">It is then that any errors are reported.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="c7bc4-133">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="c7bc4-133">Notes to implementers</span></span>

<span data-ttu-id="c7bc4-134">某些提供程序允许 **SetColumns** 调用仅对表视图的可用列的表列进行排序。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-134">Some providers allow a **SetColumns** call to order only table columns that are part of the available columns for a table view.</span></span> <span data-ttu-id="c7bc4-135">其他提供程序允许 **SetColumns** 调用来排序所有表列，包括那些包含原始列集外的属性的列。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-135">Other providers allow a **SetColumns** call to order all table columns, including those containing properties not in the original column set.</span></span> 
  
<span data-ttu-id="c7bc4-136">当TBL_BATCH异步操作时，提供程序应返回属性类型的值PT_ERROR不支持的列的属性值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-136">When TBL_BATCH is set for asynchronous operations, providers should return a property type of PT_ERROR and a property value of NULL for columns that are not supported.</span></span>
  
<span data-ttu-id="c7bc4-137">你无需响应请求TBL_ASYNC异步的异步标记。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-137">You do not need to respond to the TBL_ASYNC flag requesting that the operation be asynchronous.</span></span> <span data-ttu-id="c7bc4-138">如果不支持异步列集定义，请同步执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-138">If you do not support asynchronous column set definition, perform the operation synchronously.</span></span> <span data-ttu-id="c7bc4-139">如果可以支持该TBL_ASYNC，并且另一个异步操作仍在进行中，请返回MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-139">If you can support the TBL_ASYNC flag and another asynchronous operation is still in progress, return MAPI_E_BUSY.</span></span> <span data-ttu-id="c7bc4-140">否则，S_OK返回值，而不管是否支持属性标记数组中包含的所有属性。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-140">Otherwise, return S_OK regardless of whether or not you support all of the properties included in the property tag array.</span></span> <span data-ttu-id="c7bc4-141">由不受支持的属性导致的错误应从检索数据的 **IMAPITable** 方法返回，如 **QueryRows**。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-141">Errors resulting from unsupported properties should be returned from **IMAPITable** methods that retrieve data, such as **QueryRows**.</span></span> 
  
<span data-ttu-id="c7bc4-142">不要为通过调用 Restrict 从视图中隐藏的表行 **生成通知**。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-142">Do not generate notifications for table rows that are hidden from view by calls to **Restrict**.</span></span> 
  
<span data-ttu-id="c7bc4-143">发送表通知时 [，TABLE_NOTIFICATION](table_notification.md)结构的行成员中的属性顺序和最近的 **SetColumns** 调用指定的顺序必须与发送通知请求的时间相同。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-143">When sending table notifications, the order of the properties in the **row** member of the [TABLE_NOTIFICATION](table_notification.md) structure and the order specified by the most recent **SetColumns** call must be the same as of the time that the notification request was sent.</span></span> 
  
<span data-ttu-id="c7bc4-144">另一个标志（TBL_BATCH）允许调用方指定表实施者可以将计算操作结果延迟到稍后时间。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-144">Another flag, TBL_BATCH, allows callers to specify that the table implementer can defer evaluating the results of the operation until a later time.</span></span> <span data-ttu-id="c7bc4-145">如果可能，调用方应设置此标志，因为批处理操作可提高性能。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-145">Whenever possible, callers should set this flag because batched operation improves performance.</span></span>
  
<span data-ttu-id="c7bc4-146">调用方通常可以方便地在检索到的行集内保留一些列，以用于稍后添加的值。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-146">It is often convenient for callers to reserve some columns in the retrieved row set for values to be added later.</span></span> <span data-ttu-id="c7bc4-147">调用方通过将 [PidTagNull PR_NULL (PidTagNull](pidtagnull-canonical-property.md)) 传递到 **SetColumns** 的属性标记数组中的所需位置来达到此目的。 然后，该表将 **传递PR_NULL** **QueryRows** 检索到的所有行中这些位置的位置。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-147">Callers do this by placing **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) at the desired positions in the property tag array passed to **SetColumns**; the table will then pass back **PR_NULL** at those positions in all rows retrieved with **QueryRows**.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="c7bc4-148">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c7bc4-148">Notes to callers</span></span>

<span data-ttu-id="c7bc4-149">为  _lpPropTagArray_ 参数构建属性标记数组时，按希望列在表视图中显示的顺序对标记进行排序。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-149">When building the property tag array for the  _lpPropTagArray_ parameter, order the tags in the order that you want the columns to appear in the table view.</span></span> 
  
<span data-ttu-id="c7bc4-150">通过向属性标记应用多值实例标志或MVI_FLAG，可以指定列集中包含的多值属性。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-150">You can specify multivalued properties to be included in the column set by applying the multivalued instance flag, or MVI_FLAG constant, to the property tag.</span></span> <span data-ttu-id="c7bc4-151">通过将单值版本的属性的属性标记作为参数传递给 MVI_PROP宏，以设置此标志，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c7bc4-151">Set this flag by passing the property tag for the single-valued version of the property as a parameter to the MVI_PROP macro as follows:</span></span>
  
```
MVI_PROP(ulPropTag)

```

<span data-ttu-id="c7bc4-152">The MVI_PROP macro will set MVI_FLAG for the property， turning the tag into a multivalued tag.</span><span class="sxs-lookup"><span data-stu-id="c7bc4-152">The MVI_PROP macro will set MVI_FLAG for the property, turning the tag into a multivalued tag.</span></span> <span data-ttu-id="c7bc4-153">如果错误地尝试对单值MVI_PROP调用属性，MAPI 将忽略该调用，并保留属性标记不变。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-153">If you erroneously try to call MVI_PROP on a single-valued property, MAPI will ignore the call and leave the property tag unchanged.</span></span> 
  
<span data-ttu-id="c7bc4-154">可以在属性标记数组中添加 **PR_NULL** 属性标记，以在列集内保留空间。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-154">You can include property tags set to **PR_NULL** in the property tag array to reserve space in the column set.</span></span> <span data-ttu-id="c7bc4-155">保留空间允许您添加到列集，而无需分配新的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-155">Reserving space allows you to add to a column set without having to allocate a new property tag array.</span></span> 
  
<span data-ttu-id="c7bc4-156">如果对 **SetColumns** 的调用导致表的列顺序发生变化，并且其中一个或多个列代表多值属性，则表格中的行数可能会增加。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-156">When your call to **SetColumns** causes a change to the order of a table's columns and one or more of these columns represent a multivalued property, it is possible for the number of rows in the table to increase.</span></span> <span data-ttu-id="c7bc4-157">如果发生这种情况，将放弃表格的所有书签。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-157">If this occurs, all of the bookmarks for the table are discarded.</span></span> <span data-ttu-id="c7bc4-158">有关多值列如何影响表的信息，请参阅使用 [多值列](working-with-multivalued-columns.md)。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-158">For more information about how multivalued columns affect tables, see [Working with Multivalued Columns](working-with-multivalued-columns.md).</span></span>
  
<span data-ttu-id="c7bc4-159">默认情况下，设置列是同步操作。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-159">Setting columns is by default a synchronous operation.</span></span> <span data-ttu-id="c7bc4-160">但是，可以通过设置数据标记来允许表将操作推迟到需要TBL_BATCH的时间。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-160">However, you can allow the table to postpone the operation until such time as the data is needed by setting the TBL_BATCH flag.</span></span> <span data-ttu-id="c7bc4-161">设置此标志可提高性能。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-161">Setting this flag can improve performance.</span></span> <span data-ttu-id="c7bc4-162">另一个TBL_ASYNC标记使操作异步，从而允许 **SetColumns** 在操作完成之前返回。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-162">Another flag, TBL_ASYNC, makes the operation asynchronous, allowing **SetColumns** to return before the operation is complete.</span></span> <span data-ttu-id="c7bc4-163">若要确定完成时间，请调用 [IMAPITable：：GetStatus](imapitable-getstatus.md)。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-163">To determine when completion occurs, call [IMAPITable::GetStatus](imapitable-getstatus.md).</span></span>
  
<span data-ttu-id="c7bc4-164">如果对 **SetColumns** 的调用返回 MAPI_E_BUSY，指示另一个操作阻止了操作启动，您可以调用 [IMAPITable：：Abort](imapitable-abort.md) 以停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-164">If a call to **SetColumns** returns MAPI_E_BUSY, indicating that another operation is preventing your operation from starting, you can call [IMAPITable::Abort](imapitable-abort.md) to stop the operation in progress.</span></span> 
  
<span data-ttu-id="c7bc4-165">还可以调用 [HrAddColumnsEx](hraddcolumnsex.md) 更改列集。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-165">You can also call [HrAddColumnsEx](hraddcolumnsex.md) to change a column set.</span></span> <span data-ttu-id="c7bc4-166">**HrAddColumnsEx** 和 **IMAPITable：：SetColumns** 之间的区别在于 **HrAddColumnsEx** 灵活性较低;它只能添加列。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-166">The difference between **HrAddColumnsEx** and **IMAPITable::SetColumns** is that **HrAddColumnsEx** is less flexible; it can only add columns.</span></span> <span data-ttu-id="c7bc4-167">其他列放置在列集的开头;所有现有列都显示在这些列之后。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-167">The additional columns are placed at the beginning of the column set; all existing columns appear following these columns.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c7bc4-168">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c7bc4-168">MFCMAPI reference</span></span>

<span data-ttu-id="c7bc4-169">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-169">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c7bc4-170">**文件**</span><span class="sxs-lookup"><span data-stu-id="c7bc4-170">**File**</span></span>|<span data-ttu-id="c7bc4-171">**函数**</span><span class="sxs-lookup"><span data-stu-id="c7bc4-171">**Function**</span></span>|<span data-ttu-id="c7bc4-172">**备注**</span><span class="sxs-lookup"><span data-stu-id="c7bc4-172">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7bc4-173">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="c7bc4-173">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="c7bc4-174">CContentsTableListCtrl：:D oSetColumns</span><span class="sxs-lookup"><span data-stu-id="c7bc4-174">CContentsTableListCtrl::DoSetColumns</span></span>  <br/> |<span data-ttu-id="c7bc4-175">MFCMAPI 使用 **IMAPITable：：SetColumns** 方法设置表的所需列。</span><span class="sxs-lookup"><span data-stu-id="c7bc4-175">MFCMAPI uses the **IMAPITable::SetColumns** method to set the desired columns for the table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c7bc4-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7bc4-176">See also</span></span>



[<span data-ttu-id="c7bc4-177">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="c7bc4-177">HrQueryAllRows</span></span>](hrqueryallrows.md)
  
[<span data-ttu-id="c7bc4-178">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="c7bc4-178">IMAPITable::Abort</span></span>](imapitable-abort.md)
  
[<span data-ttu-id="c7bc4-179">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="c7bc4-179">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
  
[<span data-ttu-id="c7bc4-180">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="c7bc4-180">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="c7bc4-181">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="c7bc4-181">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="c7bc4-182">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="c7bc4-182">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
  
[<span data-ttu-id="c7bc4-183">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="c7bc4-183">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="c7bc4-184">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="c7bc4-184">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="c7bc4-185">SPropValue</span><span class="sxs-lookup"><span data-stu-id="c7bc4-185">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="c7bc4-186">SRowSet</span><span class="sxs-lookup"><span data-stu-id="c7bc4-186">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="c7bc4-187">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c7bc4-187">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="c7bc4-188">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c7bc4-188">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="c7bc4-189">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c7bc4-189">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

