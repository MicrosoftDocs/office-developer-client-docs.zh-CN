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
# <a name="imapitablesetcolumns"></a><span data-ttu-id="92b62-103">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="92b62-103">IMAPITable::SetColumns</span></span>

  
  
<span data-ttu-id="92b62-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="92b62-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="92b62-105">定义在表中显示为列的特定属性和属性的顺序。</span><span class="sxs-lookup"><span data-stu-id="92b62-105">Defines the particular properties and order of properties to appear as columns in the table.</span></span>
  
```cpp
HRESULT SetColumns(
LPSPropTagArray lpPropTagArray,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="92b62-106">参数</span><span class="sxs-lookup"><span data-stu-id="92b62-106">Parameters</span></span>

 <span data-ttu-id="92b62-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="92b62-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="92b62-108">实时指向一个属性标记数组的指针, 这些标记用于标识要作为表中的列包含的属性。</span><span class="sxs-lookup"><span data-stu-id="92b62-108">[in] Pointer to an array of property tags identifying properties to be included as columns in the table.</span></span> <span data-ttu-id="92b62-109">可以将每个标记的属性类型部分设置为有效的类型或**PR_NULL** , 以便为后续添加保留空间。</span><span class="sxs-lookup"><span data-stu-id="92b62-109">The property type portion of each tag can be set to a valid type or to **PR_NULL** to reserve space for subsequent additions.</span></span> <span data-ttu-id="92b62-110">_lpPropTagArray_参数不能设置为 NULL;每个表必须至少有一列。</span><span class="sxs-lookup"><span data-stu-id="92b62-110">The  _lpPropTagArray_ parameter cannot be set to NULL; every table must have at least one column.</span></span> 
    
 <span data-ttu-id="92b62-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="92b62-111">_ulFlags_</span></span>
  
> <span data-ttu-id="92b62-112">实时标志的位掩码, 用于控制对**SetColumns**的异步调用的返回, 例如, 在通知中使用**SetColumns**时。</span><span class="sxs-lookup"><span data-stu-id="92b62-112">[in] Bitmask of flags that controls the return of an asynchronous call to **SetColumns**, for example when **SetColumns** is used in notification.</span></span> <span data-ttu-id="92b62-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="92b62-113">The following flags can be set:</span></span> 
    
<span data-ttu-id="92b62-114">TBL_ASYNC</span><span class="sxs-lookup"><span data-stu-id="92b62-114">TBL_ASYNC</span></span> 
  
> <span data-ttu-id="92b62-115">请求以异步方式执行列设置操作, 从而导致**SetColumns**在操作完全完成之前可能会返回。</span><span class="sxs-lookup"><span data-stu-id="92b62-115">Requests that the column setting operation be performed asynchronously causing **SetColumns** to potentially return before the operation has fully completed.</span></span> 
    
<span data-ttu-id="92b62-116">TBL_BATCH</span><span class="sxs-lookup"><span data-stu-id="92b62-116">TBL_BATCH</span></span> 
  
> <span data-ttu-id="92b62-117">允许表将列设置操作延期, 直到实际需要数据。</span><span class="sxs-lookup"><span data-stu-id="92b62-117">Permits the table to postpone the column setting operation until the data is actually required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="92b62-118">返回值</span><span class="sxs-lookup"><span data-stu-id="92b62-118">Return value</span></span>

<span data-ttu-id="92b62-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="92b62-119">S_OK</span></span> 
  
> <span data-ttu-id="92b62-120">列设置操作成功。</span><span class="sxs-lookup"><span data-stu-id="92b62-120">The column setting operation was successful.</span></span>
    
<span data-ttu-id="92b62-121">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="92b62-121">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="92b62-122">正在进行另一个操作, 以防止启动列设置操作。</span><span class="sxs-lookup"><span data-stu-id="92b62-122">Another operation is in progress that prevents the column setting operation from starting.</span></span> <span data-ttu-id="92b62-123">应允许正在进行的操作完成, 或者应已停止。</span><span class="sxs-lookup"><span data-stu-id="92b62-123">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="92b62-124">说明</span><span class="sxs-lookup"><span data-stu-id="92b62-124">Remarks</span></span>

<span data-ttu-id="92b62-125">表的列集是组成表中各行的列的一组属性。</span><span class="sxs-lookup"><span data-stu-id="92b62-125">The column set of a table is the group of properties that make up the columns for the rows in the table.</span></span> <span data-ttu-id="92b62-126">为每种类型的表设置了默认列。</span><span class="sxs-lookup"><span data-stu-id="92b62-126">There is a default column set for each type of table.</span></span> <span data-ttu-id="92b62-127">默认列集由表实施者自动包括的属性组成。</span><span class="sxs-lookup"><span data-stu-id="92b62-127">The default column set is made up of the properties that the table implementer automatically includes.</span></span> <span data-ttu-id="92b62-128">表用户可以通过调用**IMAPITable:: SetColumns**方法来更改此默认集。</span><span class="sxs-lookup"><span data-stu-id="92b62-128">Table users can alter this default set by calling the **IMAPITable::SetColumns** method.</span></span> <span data-ttu-id="92b62-129">如果表实施者支持将列删除或列的顺序发生更改, 则用户可以请求将其他列添加到默认集。</span><span class="sxs-lookup"><span data-stu-id="92b62-129">They can request that other columns be added to the default set if the table implementer supports them that columns be removed, or that the order of columns be changed.</span></span> <span data-ttu-id="92b62-130">**SetColumns**指定每行返回的列和行中这些列的顺序。</span><span class="sxs-lookup"><span data-stu-id="92b62-130">**SetColumns** specifies the columns that are returned with each row and the order of these columns within the row.</span></span> 
  
<span data-ttu-id="92b62-131">仅在随后调用以检索表的数据之后, **SetColumns**操作的成功才会变得明显。</span><span class="sxs-lookup"><span data-stu-id="92b62-131">The success of the **SetColumns** operation is apparent only after a subsequent call has been made to retrieve the data of the table.</span></span> <span data-ttu-id="92b62-132">然后, 报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="92b62-132">It is then that any errors are reported.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="92b62-133">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="92b62-133">Notes to implementers</span></span>

<span data-ttu-id="92b62-134">某些提供程序允许**SetColumns**调用仅对表视图的可用列中的表列进行排序。</span><span class="sxs-lookup"><span data-stu-id="92b62-134">Some providers allow a **SetColumns** call to order only table columns that are part of the available columns for a table view.</span></span> <span data-ttu-id="92b62-135">其他提供程序允许**SetColumns**调用对表中的所有列进行排序, 包括那些包含不在原始列集中的属性。</span><span class="sxs-lookup"><span data-stu-id="92b62-135">Other providers allow a **SetColumns** call to order all table columns, including those containing properties not in the original column set.</span></span> 
  
<span data-ttu-id="92b62-136">当 TBL_BATCH 设置为异步操作时, 提供程序应返回 PT_ERROR 的属性类型和不受支持的列的属性值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="92b62-136">When TBL_BATCH is set for asynchronous operations, providers should return a property type of PT_ERROR and a property value of NULL for columns that are not supported.</span></span>
  
<span data-ttu-id="92b62-137">您无需响应 TBL_ASYNC 标志, 请求操作为异步操作。</span><span class="sxs-lookup"><span data-stu-id="92b62-137">You do not need to respond to the TBL_ASYNC flag requesting that the operation be asynchronous.</span></span> <span data-ttu-id="92b62-138">如果不支持异步列集定义, 请同步执行该操作。</span><span class="sxs-lookup"><span data-stu-id="92b62-138">If you do not support asynchronous column set definition, perform the operation synchronously.</span></span> <span data-ttu-id="92b62-139">如果您可以支持 TBL_ASYNC 标志, 而另一个异步操作仍在进行中, 则返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="92b62-139">If you can support the TBL_ASYNC flag and another asynchronous operation is still in progress, return MAPI_E_BUSY.</span></span> <span data-ttu-id="92b62-140">否则, 无论是否支持属性标记数组中包含的所有属性, 都将返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="92b62-140">Otherwise, return S_OK regardless of whether or not you support all of the properties included in the property tag array.</span></span> <span data-ttu-id="92b62-141">由于不受支持的属性而产生的错误应从检索数据的**IMAPITable**方法 (如**QueryRows**) 中返回。</span><span class="sxs-lookup"><span data-stu-id="92b62-141">Errors resulting from unsupported properties should be returned from **IMAPITable** methods that retrieve data, such as **QueryRows**.</span></span> 
  
<span data-ttu-id="92b62-142">不会为通过调用**限制**而隐藏的表行生成通知。</span><span class="sxs-lookup"><span data-stu-id="92b62-142">Do not generate notifications for table rows that are hidden from view by calls to **Restrict**.</span></span> 
  
<span data-ttu-id="92b62-143">发送表通知时, [TABLE_NOTIFICATION](table_notification.md)结构的**行**成员中的属性顺序和由最近的**SetColumns**调用指定的顺序必须与通知请求的时间相同。已发送。</span><span class="sxs-lookup"><span data-stu-id="92b62-143">When sending table notifications, the order of the properties in the **row** member of the [TABLE_NOTIFICATION](table_notification.md) structure and the order specified by the most recent **SetColumns** call must be the same as of the time that the notification request was sent.</span></span> 
  
<span data-ttu-id="92b62-144">另一个标志 TBL_BATCH, 允许呼叫者指定表实施者可以延迟评估操作结果, 直到更晚的时间。</span><span class="sxs-lookup"><span data-stu-id="92b62-144">Another flag, TBL_BATCH, allows callers to specify that the table implementer can defer evaluating the results of the operation until a later time.</span></span> <span data-ttu-id="92b62-145">只要有可能, 呼叫者都应设置此标志, 因为批处理操作可提高性能。</span><span class="sxs-lookup"><span data-stu-id="92b62-145">Whenever possible, callers should set this flag because batched operation improves performance.</span></span>
  
<span data-ttu-id="92b62-146">通常, 调用方可以在检索到的行中保留一些列, 以便日后添加值。</span><span class="sxs-lookup"><span data-stu-id="92b62-146">It is often convenient for callers to reserve some columns in the retrieved row set for values to be added later.</span></span> <span data-ttu-id="92b62-147">调用方通过在传递给**SetColumns**的属性标记数组中的所需位置放置**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 来实现此目的。然后, 该表将在使用**QueryRows**检索的所有行中的这些位置上传递 back **PR_NULL** 。</span><span class="sxs-lookup"><span data-stu-id="92b62-147">Callers do this by placing **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) at the desired positions in the property tag array passed to **SetColumns**; the table will then pass back **PR_NULL** at those positions in all rows retrieved with **QueryRows**.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="92b62-148">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="92b62-148">Notes to callers</span></span>

<span data-ttu-id="92b62-149">为_lpPropTagArray_参数生成属性标记数组时, 请按照您希望列在表视图中显示的顺序对标记进行排序。</span><span class="sxs-lookup"><span data-stu-id="92b62-149">When building the property tag array for the  _lpPropTagArray_ parameter, order the tags in the order that you want the columns to appear in the table view.</span></span> 
  
<span data-ttu-id="92b62-150">通过将多值实例标志 (或 MVI_FLAG 常量) 应用于属性标记, 可以指定要包含在列集中的多值属性。</span><span class="sxs-lookup"><span data-stu-id="92b62-150">You can specify multivalued properties to be included in the column set by applying the multivalued instance flag, or MVI_FLAG constant, to the property tag.</span></span> <span data-ttu-id="92b62-151">通过将属性的单值版本的属性标记作为参数传递给 MVI_PROP 宏, 可以设置此标志, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="92b62-151">Set this flag by passing the property tag for the single-valued version of the property as a parameter to the MVI_PROP macro as follows:</span></span>
  
```
MVI_PROP(ulPropTag)

```

<span data-ttu-id="92b62-152">MVI_PROP 宏将设置属性的 MVI_FLAG, 并将标记转换为多值标记。</span><span class="sxs-lookup"><span data-stu-id="92b62-152">The MVI_PROP macro will set MVI_FLAG for the property, turning the tag into a multivalued tag.</span></span> <span data-ttu-id="92b62-153">如果您错误地尝试在单值属性上调用 MVI_PROP, MAPI 将忽略该调用并保持属性标记不变。</span><span class="sxs-lookup"><span data-stu-id="92b62-153">If you erroneously try to call MVI_PROP on a single-valued property, MAPI will ignore the call and leave the property tag unchanged.</span></span> 
  
<span data-ttu-id="92b62-154">您可以包含设置为**PR_NULL**的属性标记数组中的属性标记, 以在列集中保留空间。</span><span class="sxs-lookup"><span data-stu-id="92b62-154">You can include property tags set to **PR_NULL** in the property tag array to reserve space in the column set.</span></span> <span data-ttu-id="92b62-155">通过保留空间, 可以将添加到列集, 而无需分配新的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="92b62-155">Reserving space allows you to add to a column set without having to allocate a new property tag array.</span></span> 
  
<span data-ttu-id="92b62-156">当您对**SetColumns**的调用导致对表的列的顺序的更改, 并且其中的一个或多个列表示多值属性时, 表中的行数可能会增加。</span><span class="sxs-lookup"><span data-stu-id="92b62-156">When your call to **SetColumns** causes a change to the order of a table's columns and one or more of these columns represent a multivalued property, it is possible for the number of rows in the table to increase.</span></span> <span data-ttu-id="92b62-157">如果出现这种情况, 将丢弃表的所有书签。</span><span class="sxs-lookup"><span data-stu-id="92b62-157">If this occurs, all of the bookmarks for the table are discarded.</span></span> <span data-ttu-id="92b62-158">有关多值列对表的影响的详细信息, 请参阅[使用多值列](working-with-multivalued-columns.md)。</span><span class="sxs-lookup"><span data-stu-id="92b62-158">For more information about how multivalued columns affect tables, see [Working with Multivalued Columns](working-with-multivalued-columns.md).</span></span>
  
<span data-ttu-id="92b62-159">默认情况下, 设置列是同步操作。</span><span class="sxs-lookup"><span data-stu-id="92b62-159">Setting columns is by default a synchronous operation.</span></span> <span data-ttu-id="92b62-160">但是, 可以通过设置 TBL_BATCH 标志, 允许表延迟操作, 直到需要数据时才使用。</span><span class="sxs-lookup"><span data-stu-id="92b62-160">However, you can allow the table to postpone the operation until such time as the data is needed by setting the TBL_BATCH flag.</span></span> <span data-ttu-id="92b62-161">设置此标志可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="92b62-161">Setting this flag can improve performance.</span></span> <span data-ttu-id="92b62-162">另一个标志 TBL_ASYNC, 使操作成为异步操作, 允许**SetColumns**在操作完成前返回。</span><span class="sxs-lookup"><span data-stu-id="92b62-162">Another flag, TBL_ASYNC, makes the operation asynchronous, allowing **SetColumns** to return before the operation is complete.</span></span> <span data-ttu-id="92b62-163">若要确定完成发生的时间, 请调用[IMAPITable:: GetStatus](imapitable-getstatus.md)。</span><span class="sxs-lookup"><span data-stu-id="92b62-163">To determine when completion occurs, call [IMAPITable::GetStatus](imapitable-getstatus.md).</span></span>
  
<span data-ttu-id="92b62-164">如果对**SetColumns**的调用返回 MAPI_E_BUSY, 表明另一个操作正在阻止您的操作启动, 则可以调用[IMAPITable:: Abort](imapitable-abort.md)停止正在进行的操作。</span><span class="sxs-lookup"><span data-stu-id="92b62-164">If a call to **SetColumns** returns MAPI_E_BUSY, indicating that another operation is preventing your operation from starting, you can call [IMAPITable::Abort](imapitable-abort.md) to stop the operation in progress.</span></span> 
  
<span data-ttu-id="92b62-165">您还可以调用[HrAddColumnsEx](hraddcolumnsex.md)更改列集。</span><span class="sxs-lookup"><span data-stu-id="92b62-165">You can also call [HrAddColumnsEx](hraddcolumnsex.md) to change a column set.</span></span> <span data-ttu-id="92b62-166">**HrAddColumnsEx**和**IMAPITable:: SetColumns**之间的差异在于, **HrAddColumnsEx**的灵活性较低;它只能添加列。</span><span class="sxs-lookup"><span data-stu-id="92b62-166">The difference between **HrAddColumnsEx** and **IMAPITable::SetColumns** is that **HrAddColumnsEx** is less flexible; it can only add columns.</span></span> <span data-ttu-id="92b62-167">其他列位于列集的开头;所有现有列都显示在这些列之后。</span><span class="sxs-lookup"><span data-stu-id="92b62-167">The additional columns are placed at the beginning of the column set; all existing columns appear following these columns.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="92b62-168">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="92b62-168">MFCMAPI reference</span></span>

<span data-ttu-id="92b62-169">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="92b62-169">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="92b62-170">**文件**</span><span class="sxs-lookup"><span data-stu-id="92b62-170">**File**</span></span>|<span data-ttu-id="92b62-171">**函数**</span><span class="sxs-lookup"><span data-stu-id="92b62-171">**Function**</span></span>|<span data-ttu-id="92b62-172">**备注**</span><span class="sxs-lookup"><span data-stu-id="92b62-172">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92b62-173">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="92b62-173">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="92b62-174">CContentsTableListCtrl::D osetcolumns</span><span class="sxs-lookup"><span data-stu-id="92b62-174">CContentsTableListCtrl::DoSetColumns</span></span>  <br/> |<span data-ttu-id="92b62-175">MFCMAPI 使用**IMAPITable:: SetColumns**方法为表设置所需的列。</span><span class="sxs-lookup"><span data-stu-id="92b62-175">MFCMAPI uses the **IMAPITable::SetColumns** method to set the desired columns for the table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="92b62-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92b62-176">See also</span></span>



[<span data-ttu-id="92b62-177">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="92b62-177">HrQueryAllRows</span></span>](hrqueryallrows.md)
  
[<span data-ttu-id="92b62-178">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="92b62-178">IMAPITable::Abort</span></span>](imapitable-abort.md)
  
[<span data-ttu-id="92b62-179">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="92b62-179">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
  
[<span data-ttu-id="92b62-180">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="92b62-180">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="92b62-181">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="92b62-181">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="92b62-182">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="92b62-182">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
  
[<span data-ttu-id="92b62-183">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="92b62-183">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="92b62-184">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="92b62-184">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="92b62-185">SPropValue</span><span class="sxs-lookup"><span data-stu-id="92b62-185">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="92b62-186">SRowSet</span><span class="sxs-lookup"><span data-stu-id="92b62-186">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="92b62-187">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="92b62-187">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="92b62-188">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="92b62-188">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="92b62-189">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="92b62-189">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

