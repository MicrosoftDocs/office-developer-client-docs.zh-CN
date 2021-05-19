---
title: IMAPITableQueryRows
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.QueryRows
api_type:
- COM
ms.assetid: f26384f1-467e-4343-92b3-0425da9d2123
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 26d6ffe66a5e7749c9d8c4e5210e9f72de808932
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416291"
---
# <a name="imapitablequeryrows"></a><span data-ttu-id="704b1-103">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="704b1-103">IMAPITable::QueryRows</span></span>

  
  
<span data-ttu-id="704b1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="704b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="704b1-105">从表中的一行或多行，从当前光标位置开始。</span><span class="sxs-lookup"><span data-stu-id="704b1-105">Returns one or more rows from a table, beginning at the current cursor position.</span></span>
  
```cpp
HRESULT QueryRows(
LONG lRowCount,
ULONG ulFlags,
LPSRowSet FAR * lppRows
);
```

## <a name="parameters"></a><span data-ttu-id="704b1-106">参数</span><span class="sxs-lookup"><span data-stu-id="704b1-106">Parameters</span></span>

 <span data-ttu-id="704b1-107">_lRowCount_</span><span class="sxs-lookup"><span data-stu-id="704b1-107">_lRowCount_</span></span>
  
> <span data-ttu-id="704b1-108">[in]要返回的最大行数。</span><span class="sxs-lookup"><span data-stu-id="704b1-108">[in] Maximum number of rows to be returned.</span></span>
    
 <span data-ttu-id="704b1-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="704b1-109">_ulFlags_</span></span>
  
> <span data-ttu-id="704b1-110">[in]控制行返回方法的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="704b1-110">[in] Bitmask of flags that control how rows are returned.</span></span> <span data-ttu-id="704b1-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="704b1-111">The following flag can be set:</span></span>
    
<span data-ttu-id="704b1-112">TBL_NOADVANCE</span><span class="sxs-lookup"><span data-stu-id="704b1-112">TBL_NOADVANCE</span></span> 
  
> <span data-ttu-id="704b1-113">防止游标由于行检索而前进。</span><span class="sxs-lookup"><span data-stu-id="704b1-113">Prevents the cursor from advancing as a result of the row retrieval.</span></span> <span data-ttu-id="704b1-114">如果TBL_NOADVANCE，光标指向返回的第一行。</span><span class="sxs-lookup"><span data-stu-id="704b1-114">If the TBL_NOADVANCE flag is set, the cursor points to the first row returned.</span></span> <span data-ttu-id="704b1-115">如果未TBL_NOADVANCE，则光标指向返回的最后一行后行。</span><span class="sxs-lookup"><span data-stu-id="704b1-115">If the TBL_NOADVANCE flag is not set, the cursor points to the row following the last row returned.</span></span>
    
 <span data-ttu-id="704b1-116">_lppRows_</span><span class="sxs-lookup"><span data-stu-id="704b1-116">_lppRows_</span></span>
  
> <span data-ttu-id="704b1-117">[out]指向指向保留表格 [行的 SRowSet](srowset.md) 结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="704b1-117">[out] Pointer to a pointer to an [SRowSet](srowset.md) structure holding the table rows.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="704b1-118">返回值</span><span class="sxs-lookup"><span data-stu-id="704b1-118">Return value</span></span>

<span data-ttu-id="704b1-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="704b1-119">S_OK</span></span> 
  
> <span data-ttu-id="704b1-120">已成功返回行。</span><span class="sxs-lookup"><span data-stu-id="704b1-120">The rows were successfully returned.</span></span>
    
<span data-ttu-id="704b1-121">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="704b1-121">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="704b1-122">正在进行另一个操作，以防止行检索操作启动。</span><span class="sxs-lookup"><span data-stu-id="704b1-122">Another operation is in progress that prevents the row retrieval operation from starting.</span></span> <span data-ttu-id="704b1-123">应允许完成或停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="704b1-123">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="704b1-124">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="704b1-124">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="704b1-125">_IRowCount_ 参数设置为零。</span><span class="sxs-lookup"><span data-stu-id="704b1-125">The  _IRowCount_ parameter is set to zero.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="704b1-126">备注</span><span class="sxs-lookup"><span data-stu-id="704b1-126">Remarks</span></span>

<span data-ttu-id="704b1-127">**IMAPITable：：QueryRows** 方法从表中获取一行或多行数据。</span><span class="sxs-lookup"><span data-stu-id="704b1-127">The **IMAPITable::QueryRows** method gets one or more rows of data from a table.</span></span> <span data-ttu-id="704b1-128">_IRowCount_ 参数的值会影响检索的起始点。</span><span class="sxs-lookup"><span data-stu-id="704b1-128">The value of the  _IRowCount_ parameter affects the starting point for the retrieval.</span></span> <span data-ttu-id="704b1-129">如果  _IRowCount_ 为正数，则从当前位置开始以向前方向读取行。</span><span class="sxs-lookup"><span data-stu-id="704b1-129">If  _IRowCount_ is positive, rows are read in a forward direction, starting at the current position.</span></span> <span data-ttu-id="704b1-130">如果  _IRowCount_ 为负数 **，QueryRows** 会通过向后移动指示的行数来重置起始点。</span><span class="sxs-lookup"><span data-stu-id="704b1-130">If  _IRowCount_ is negative, **QueryRows** resets the starting point by moving backward the indicated number of rows.</span></span> <span data-ttu-id="704b1-131">重置游标后，将按向前顺序读取行。</span><span class="sxs-lookup"><span data-stu-id="704b1-131">After the cursor is reset, rows are read in forward order.</span></span> 
  
<span data-ttu-id="704b1-132">**lppRows** 参数指向 [的 SRowSet](srowset.md)结构中 _cRows_ 成员指示返回的行数。</span><span class="sxs-lookup"><span data-stu-id="704b1-132">The **cRows** member in the [SRowSet](srowset.md) structure pointed to by the  _lppRows_ parameter indicates the number of rows returned.</span></span> <span data-ttu-id="704b1-133">如果返回零行：</span><span class="sxs-lookup"><span data-stu-id="704b1-133">If zero rows are returned:</span></span> 
  
- <span data-ttu-id="704b1-134">光标已位于表的开头，  _并且 IRowCount_ 的值为负数。</span><span class="sxs-lookup"><span data-stu-id="704b1-134">The cursor was already positioned at the beginning of the table and the value of  _IRowCount_ is negative.</span></span> <span data-ttu-id="704b1-135">-Or-</span><span class="sxs-lookup"><span data-stu-id="704b1-135">-Or-</span></span> 
    
- <span data-ttu-id="704b1-136">光标已位于表的末尾，  _并且 IRowCount_ 的值为正。</span><span class="sxs-lookup"><span data-stu-id="704b1-136">The cursor was already positioned at the end of the table and the value of  _IRowCount_ is positive.</span></span> 
    
<span data-ttu-id="704b1-137">每行的列数及其排序相同。</span><span class="sxs-lookup"><span data-stu-id="704b1-137">The number of columns and their ordering is the same for each row.</span></span> <span data-ttu-id="704b1-138">如果行不存在属性或读取属性时出错，该行中属性的 **SPropValue** 结构将包含下列值：</span><span class="sxs-lookup"><span data-stu-id="704b1-138">If a property does not exist for a row or there is an error reading a property, the **SPropValue** structure for the property in the row contains the following values:</span></span> 
  
- <span data-ttu-id="704b1-139">PT_ERROR **ulPropTag** 成员中的属性类型。</span><span class="sxs-lookup"><span data-stu-id="704b1-139">PT_ERROR for the property type in the **ulPropTag** member.</span></span> 
    
- <span data-ttu-id="704b1-140">MAPI_E_NOT_FOUND Value **成员** 。</span><span class="sxs-lookup"><span data-stu-id="704b1-140">MAPI_E_NOT_FOUND for the **Value** member.</span></span> 
    
<span data-ttu-id="704b1-141">_lppRows_ 参数指向的行集内用于 [SPropValue](spropvalue.md)结构的内存必须单独分配，并针对每一行释放。</span><span class="sxs-lookup"><span data-stu-id="704b1-141">Memory used for the [SPropValue](spropvalue.md) structures in the row set pointed to by the  _lppRows_ parameter must be separately allocated and freed for each row.</span></span> <span data-ttu-id="704b1-142">使用 [MAPIFreeBuffer](mapifreebuffer.md) 释放属性值结构并释放行集。</span><span class="sxs-lookup"><span data-stu-id="704b1-142">Use [MAPIFreeBuffer](mapifreebuffer.md) to free the property value structures and to free the row set.</span></span> <span data-ttu-id="704b1-143">但是，当 **对 QueryRows** 的调用返回零时，指示表的开头或结尾，则仅 **需要释放 SRowSet** 结构本身。</span><span class="sxs-lookup"><span data-stu-id="704b1-143">When a call to **QueryRows** returns zero, however, indicating the beginning or end of the table, only the **SRowSet** structure itself needs to be freed.</span></span> <span data-ttu-id="704b1-144">若要详细了解如何在 **SRowSet** 结构中分配和释放内存，请参阅 [管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="704b1-144">For more information about how to allocate and free memory in an **SRowSet** structure, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span>
  
<span data-ttu-id="704b1-145">返回的行及其返回顺序取决于是否已成功调用 [IMAPITable：：Restrict](imapitable-restrict.md) 和 [IMAPITable：：SortTable](imapitable-sorttable.md)。</span><span class="sxs-lookup"><span data-stu-id="704b1-145">The rows that are returned and the order in which they are returned depend on whether or not successful calls have been made to [IMAPITable::Restrict](imapitable-restrict.md) and [IMAPITable::SortTable](imapitable-sorttable.md).</span></span> <span data-ttu-id="704b1-146">**限制** 视图中的筛选行，从而导致 **QueryRows** 仅返回与限制中指定的条件匹配的行。</span><span class="sxs-lookup"><span data-stu-id="704b1-146">**Restrict** filters rows from the view, causing **QueryRows** to return only the rows that match the criteria specified in the restriction.</span></span> <span data-ttu-id="704b1-147">**SortTable** 建立标准或分类的排序顺序，影响 **QueryRows** 返回的行的顺序。</span><span class="sxs-lookup"><span data-stu-id="704b1-147">**SortTable** establishes a standard or categorized sort order, affecting the sequence of rows returned by **QueryRows**.</span></span> <span data-ttu-id="704b1-148">返回的行按照传递给 SortTable [的 SSortOrderSet](ssortorderset.md) 结构中 **指定的顺序排列**。</span><span class="sxs-lookup"><span data-stu-id="704b1-148">The returned rows are in the order specified in the [SSortOrderSet](ssortorderset.md) structure passed to **SortTable**.</span></span>
  
<span data-ttu-id="704b1-149">每行返回的列及其返回顺序取决于是否已对 [IMAPITable：：SetColumns](imapitable-setcolumns.md)成功调用。</span><span class="sxs-lookup"><span data-stu-id="704b1-149">The columns returned for each row and the order in which they are returned depend on whether or not a successful call has been made to [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span> <span data-ttu-id="704b1-150">**SetColumns** 建立一个列集，指定要包含在表中的列中的属性以及这些属性的包含顺序。</span><span class="sxs-lookup"><span data-stu-id="704b1-150">**SetColumns** establishes a column set, specifying the properties to be included in columns in the table and the order in which they should be included.</span></span> <span data-ttu-id="704b1-151">如果 **已进行 SetColumns** 调用，则每行中的特定列以及这些列的顺序与调用中指定的列集匹配。</span><span class="sxs-lookup"><span data-stu-id="704b1-151">If a **SetColumns** call has been made, the particular columns in each row and the order of those columns match the column set specified in the call.</span></span> <span data-ttu-id="704b1-152">如果未进行 **SetColumns** 调用，则表将返回其默认列集。</span><span class="sxs-lookup"><span data-stu-id="704b1-152">If no **SetColumns** call has been made, the table returns its default column set.</span></span> 
  
<span data-ttu-id="704b1-153">如果未进行这些调用 **，QueryRows** 将返回表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="704b1-153">If none of these calls has been made, **QueryRows** returns all of the rows in the table.</span></span> <span data-ttu-id="704b1-154">每行包含默认顺序的默认列集。</span><span class="sxs-lookup"><span data-stu-id="704b1-154">Each row contains the default column set in default order.</span></span> 
  
<span data-ttu-id="704b1-155">当 [在 IMAPITable：：SetColumns](imapitable-setcolumns.md)的调用中建立的列集包含设置为 PR_NULL 的列时 _，lppRows_ 中返回的行集内的 [SPropValue](spropvalue.md)数组将包含空插槽。</span><span class="sxs-lookup"><span data-stu-id="704b1-155">When the column set established in a call to [IMAPITable::SetColumns](imapitable-setcolumns.md) includes columns set to PR_NULL, the [SPropValue](spropvalue.md) array within the row set returned in  _lppRows_ will contain empty slots.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="704b1-156">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="704b1-156">Notes to implementers</span></span>

<span data-ttu-id="704b1-157">您可以允许调用方请求将不受支持列包含在列集内。</span><span class="sxs-lookup"><span data-stu-id="704b1-157">You can allow a caller to request an unsupported column to be included in the column set.</span></span> <span data-ttu-id="704b1-158">当发生这种情况时，PT_ERROR属性标记的属性类型部分，MAPI_E_NOT_FOUND不受支持的列的属性值中。</span><span class="sxs-lookup"><span data-stu-id="704b1-158">When this occurs, place PT_ERROR in the property type portion of the property tag and MAPI_E_NOT_FOUND in the property value for the unsupported column.</span></span> 
  
<span data-ttu-id="704b1-159">将行计数视为请求而不是要求。</span><span class="sxs-lookup"><span data-stu-id="704b1-159">Treat the row count as a request rather than a requirement.</span></span> <span data-ttu-id="704b1-160">如果查询方向没有行，可以从零行到请求的行数返回任意位置。</span><span class="sxs-lookup"><span data-stu-id="704b1-160">You can return anywhere from zero rows, if there are no rows in the direction of the query, to the number requested.</span></span> 
  
<span data-ttu-id="704b1-161">仅返回在从分类表视图中请求行时用户将看到的行，从而允许调用方对数据范围做出有效的假设，并避免额外工作。</span><span class="sxs-lookup"><span data-stu-id="704b1-161">Return only the rows that the user will see when rows are requested from a categorized table view, allowing the caller to make valid assumptions about the scope of the data and avoid extra work.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="704b1-162">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="704b1-162">Notes to callers</span></span>

<span data-ttu-id="704b1-163">通常，您最终将具有在  _lRowCount_ 参数中指定的行数。</span><span class="sxs-lookup"><span data-stu-id="704b1-163">Usually you will end up with as many rows as you have specified in the  _lRowCount_ parameter.</span></span> <span data-ttu-id="704b1-164">但是，当内存或实现限制成为问题时，或者当操作提前到达表的开头或结尾时 **，QueryRows** 返回的行数将少于请求的行数。</span><span class="sxs-lookup"><span data-stu-id="704b1-164">However, when memory or implementation limits are an issue or when the operation reaches the beginning or end of the table prematurely, **QueryRows** will return less rows than requested.</span></span> 
  
<span data-ttu-id="704b1-165">如果 **QueryRows** 返回 MAPI_E_BUSY，请调用 [IMAPITable：：WaitForCompletion](imapitable-waitforcompletion.md) 方法，在异步操作完成时重试 **对 QueryRows** 的调用。</span><span class="sxs-lookup"><span data-stu-id="704b1-165">If **QueryRows** returns MAPI_E_BUSY, call the [IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md) method and retry the call to **QueryRows** when the asynchronous operation is complete.</span></span> 
  
<span data-ttu-id="704b1-166">调用 **QueryRows** 时，请注意异步通知的计时可能会导致从 **QueryRows** 返回的行集无法准确表示基础数据。</span><span class="sxs-lookup"><span data-stu-id="704b1-166">When calling **QueryRows**, be aware that the timing of asynchronous notifications can potentially cause the row set that you get back from **QueryRows** not to accurately represent the underlying data.</span></span> <span data-ttu-id="704b1-167">例如，在删除邮件之后但在收到相应通知之前，对文件夹内容表的 **QueryRows** 调用将导致在行集内返回已删除的行。</span><span class="sxs-lookup"><span data-stu-id="704b1-167">For example, a call to **QueryRows** to a folder's contents table following the deletion of a message but prior to the receipt of the corresponding notification will cause the deleted row to be returned in the row set.</span></span> <span data-ttu-id="704b1-168">在更新用户的数据视图之前，请始终等待通知到达。</span><span class="sxs-lookup"><span data-stu-id="704b1-168">Always wait for a notification to arrive before updating the user's view of the data.</span></span> 
  
<span data-ttu-id="704b1-169">有关从表中检索行的信息，请参阅 [从表行检索数据](retrieving-data-from-table-rows.md)。</span><span class="sxs-lookup"><span data-stu-id="704b1-169">For more information about retrieving rows from tables, see [Retrieving Data from Table Rows](retrieving-data-from-table-rows.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="704b1-170">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="704b1-170">MFCMAPI reference</span></span>

<span data-ttu-id="704b1-171">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="704b1-171">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="704b1-172">**文件**</span><span class="sxs-lookup"><span data-stu-id="704b1-172">**File**</span></span>|<span data-ttu-id="704b1-173">**函数**</span><span class="sxs-lookup"><span data-stu-id="704b1-173">**Function**</span></span>|<span data-ttu-id="704b1-174">**备注**</span><span class="sxs-lookup"><span data-stu-id="704b1-174">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="704b1-175">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="704b1-175">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="704b1-176">DwThreadFuncLoadTable</span><span class="sxs-lookup"><span data-stu-id="704b1-176">DwThreadFuncLoadTable</span></span>  <br/> |<span data-ttu-id="704b1-177">MFCMAPI 使用 **IMAPITable：：QueryRows** 方法检索表中要加载到视图中的行。</span><span class="sxs-lookup"><span data-stu-id="704b1-177">MFCMAPI uses the **IMAPITable::QueryRows** method to retrieve rows in the table to load into the view.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="704b1-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="704b1-178">See also</span></span>



[<span data-ttu-id="704b1-179">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="704b1-179">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="704b1-180">FreeProws</span><span class="sxs-lookup"><span data-stu-id="704b1-180">FreeProws</span></span>](freeprows.md)
  
[<span data-ttu-id="704b1-181">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="704b1-181">HrQueryAllRows</span></span>](hrqueryallrows.md)
  
[<span data-ttu-id="704b1-182">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="704b1-182">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="704b1-183">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="704b1-183">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="704b1-184">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="704b1-184">IMAPITable::WaitForCompletion</span></span>](imapitable-waitforcompletion.md)
  
[<span data-ttu-id="704b1-185">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="704b1-185">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="704b1-186">SRow</span><span class="sxs-lookup"><span data-stu-id="704b1-186">SRow</span></span>](srow.md)
  
[<span data-ttu-id="704b1-187">SRowSet</span><span class="sxs-lookup"><span data-stu-id="704b1-187">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="704b1-188">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="704b1-188">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="704b1-189">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="704b1-189">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

