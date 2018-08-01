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
ms.openlocfilehash: a6659f64f6e8d2e3dc61819b2263efe672cdd15c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775734"
---
# <a name="imapitablequeryrows"></a><span data-ttu-id="5e93b-103">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="5e93b-103">IMAPITable::QueryRows</span></span>

  
  
<span data-ttu-id="5e93b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5e93b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5e93b-105">从表中，开始在当前光标位置返回一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-105">Returns one or more rows from a table, beginning at the current cursor position.</span></span>
  
```cpp
HRESULT QueryRows(
LONG lRowCount,
ULONG ulFlags,
LPSRowSet FAR * lppRows
);
```

## <a name="parameters"></a><span data-ttu-id="5e93b-106">参数</span><span class="sxs-lookup"><span data-stu-id="5e93b-106">Parameters</span></span>

 <span data-ttu-id="5e93b-107">_lRowCount_</span><span class="sxs-lookup"><span data-stu-id="5e93b-107">_lRowCount_</span></span>
  
> <span data-ttu-id="5e93b-108">[in]要返回的行的最大数量。</span><span class="sxs-lookup"><span data-stu-id="5e93b-108">[in] Maximum number of rows to be returned.</span></span>
    
 <span data-ttu-id="5e93b-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5e93b-109">_ulFlags_</span></span>
  
> <span data-ttu-id="5e93b-110">[in]控制如何返回行的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5e93b-110">[in] Bitmask of flags that control how rows are returned.</span></span> <span data-ttu-id="5e93b-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="5e93b-111">The following flag can be set:</span></span>
    
<span data-ttu-id="5e93b-112">TBL_NOADVANCE</span><span class="sxs-lookup"><span data-stu-id="5e93b-112">TBL_NOADVANCE</span></span> 
  
> <span data-ttu-id="5e93b-113">防止由于行检索执行光标。</span><span class="sxs-lookup"><span data-stu-id="5e93b-113">Prevents the cursor from advancing as a result of the row retrieval.</span></span> <span data-ttu-id="5e93b-114">如果设置 TBL_NOADVANCE 标志，则返回的第一行的指针指向。</span><span class="sxs-lookup"><span data-stu-id="5e93b-114">If the TBL_NOADVANCE flag is set, the cursor points to the first row returned.</span></span> <span data-ttu-id="5e93b-115">如果未设置 TBL_NOADVANCE 标志，光标指向关注返回的最后一行的行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-115">If the TBL_NOADVANCE flag is not set, the cursor points to the row following the last row returned.</span></span>
    
 <span data-ttu-id="5e93b-116">_lppRows_</span><span class="sxs-lookup"><span data-stu-id="5e93b-116">_lppRows_</span></span>
  
> <span data-ttu-id="5e93b-117">[输出]为存放的表格行[SRowSet](srowset.md)结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5e93b-117">[out] Pointer to a pointer to an [SRowSet](srowset.md) structure holding the table rows.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5e93b-118">返回值</span><span class="sxs-lookup"><span data-stu-id="5e93b-118">Return value</span></span>

<span data-ttu-id="5e93b-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e93b-119">S_OK</span></span> 
  
> <span data-ttu-id="5e93b-120">已成功返回行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-120">The rows were successfully returned.</span></span>
    
<span data-ttu-id="5e93b-121">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="5e93b-121">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="5e93b-122">正在阻止从起始行检索操作是另一个操作。</span><span class="sxs-lookup"><span data-stu-id="5e93b-122">Another operation is in progress that prevents the row retrieval operation from starting.</span></span> <span data-ttu-id="5e93b-123">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="5e93b-123">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="5e93b-124">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="5e93b-124">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="5e93b-125">_IRowCount_参数设置为零。</span><span class="sxs-lookup"><span data-stu-id="5e93b-125">The  _IRowCount_ parameter is set to zero.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="5e93b-126">说明</span><span class="sxs-lookup"><span data-stu-id="5e93b-126">Remarks</span></span>

<span data-ttu-id="5e93b-127">**IMAPITable::QueryRows**方法获取表中的一个或多个数据行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-127">The **IMAPITable::QueryRows** method gets one or more rows of data from a table.</span></span> <span data-ttu-id="5e93b-128">_IRowCount_参数的值会影响检索的起始点。</span><span class="sxs-lookup"><span data-stu-id="5e93b-128">The value of the  _IRowCount_ parameter affects the starting point for the retrieval.</span></span> <span data-ttu-id="5e93b-129">如果_IRowCount_为正数，则读取行时向前，当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="5e93b-129">If  _IRowCount_ is positive, rows are read in a forward direction, starting at the current position.</span></span> <span data-ttu-id="5e93b-130">如果_IRowCount_为负数， **QueryRows**通过向后移动指定的行数重置的起始点。</span><span class="sxs-lookup"><span data-stu-id="5e93b-130">If  _IRowCount_ is negative, **QueryRows** resets the starting point by moving backward the indicated number of rows.</span></span> <span data-ttu-id="5e93b-131">光标重置之后，将向顺序读取行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-131">After the cursor is reset, rows are read in forward order.</span></span> 
  
<span data-ttu-id="5e93b-132">_LppRows_参数指向的[SRowSet](srowset.md)结构中作为**cRows**成员指示返回的行数。</span><span class="sxs-lookup"><span data-stu-id="5e93b-132">The **cRows** member in the [SRowSet](srowset.md) structure pointed to by the  _lppRows_ parameter indicates the number of rows returned.</span></span> <span data-ttu-id="5e93b-133">如果返回零行：</span><span class="sxs-lookup"><span data-stu-id="5e93b-133">If zero rows are returned:</span></span> 
  
- <span data-ttu-id="5e93b-134">光标已被置于表的开始和_IRowCount_的值为负数。</span><span class="sxs-lookup"><span data-stu-id="5e93b-134">The cursor was already positioned at the beginning of the table and the value of  _IRowCount_ is negative.</span></span> <span data-ttu-id="5e93b-135">-或者-</span><span class="sxs-lookup"><span data-stu-id="5e93b-135">-Or-</span></span> 
    
- <span data-ttu-id="5e93b-136">光标已位于表末尾和_IRowCount_的值为正数。</span><span class="sxs-lookup"><span data-stu-id="5e93b-136">The cursor was already positioned at the end of the table and the value of  _IRowCount_ is positive.</span></span> 
    
<span data-ttu-id="5e93b-137">列数和它们的顺序是相同的每个行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-137">The number of columns and their ordering is the same for each row.</span></span> <span data-ttu-id="5e93b-138">如果属性不存在的行或读取属性时出错，行中的属性的**SPropValue**结构包含以下值：</span><span class="sxs-lookup"><span data-stu-id="5e93b-138">If a property does not exist for a row or there is an error reading a property, the **SPropValue** structure for the property in the row contains the following values:</span></span> 
  
- <span data-ttu-id="5e93b-139">属性类型**ulPropTag**成员中 PT_ERROR。</span><span class="sxs-lookup"><span data-stu-id="5e93b-139">PT_ERROR for the property type in the **ulPropTag** member.</span></span> 
    
- <span data-ttu-id="5e93b-140">**值**成员的 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="5e93b-140">MAPI_E_NOT_FOUND for the **Value** member.</span></span> 
    
<span data-ttu-id="5e93b-141">用于_lppRows_参数指向在行集中的[SPropValue](spropvalue.md)结构内存必须单独分配和释放对于每个行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-141">Memory used for the [SPropValue](spropvalue.md) structures in the row set pointed to by the  _lppRows_ parameter must be separately allocated and freed for each row.</span></span> <span data-ttu-id="5e93b-142">使用[MAPIFreeBuffer](mapifreebuffer.md)以释放属性值结构并释放行设置。</span><span class="sxs-lookup"><span data-stu-id="5e93b-142">Use [MAPIFreeBuffer](mapifreebuffer.md) to free the property value structures and to free the row set.</span></span> <span data-ttu-id="5e93b-143">时对**QueryRows**的调用返回零，但是，指示的开头或结尾的表中，仅本身**SRowSet**结构需要释放。</span><span class="sxs-lookup"><span data-stu-id="5e93b-143">When a call to **QueryRows** returns zero, however, indicating the beginning or end of the table, only the **SRowSet** structure itself needs to be freed.</span></span> <span data-ttu-id="5e93b-144">有关如何分配和释放内存**SRowSet**结构中的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="5e93b-144">For more information about how to allocate and free memory in an **SRowSet** structure, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span>
  
<span data-ttu-id="5e93b-145">返回的行和所返回的顺序取决于成功的呼叫进行了[IMAPITable::Restrict](imapitable-restrict.md)和[IMAPITable::SortTable](imapitable-sorttable.md)。</span><span class="sxs-lookup"><span data-stu-id="5e93b-145">The rows that are returned and the order in which they are returned depend on whether or not successful calls have been made to [IMAPITable::Restrict](imapitable-restrict.md) and [IMAPITable::SortTable](imapitable-sorttable.md).</span></span> <span data-ttu-id="5e93b-146">**限制**筛选器行从视图中，导致**QueryRows**返回符合条件限制中指定的行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-146">**Restrict** filters rows from the view, causing **QueryRows** to return only the rows that match the criteria specified in the restriction.</span></span> <span data-ttu-id="5e93b-147">**SortTable**建立一种标准，或者分类影响**QueryRows**所返回的行的顺序排序次序。</span><span class="sxs-lookup"><span data-stu-id="5e93b-147">**SortTable** establishes a standard or categorized sort order, affecting the sequence of rows returned by **QueryRows**.</span></span> <span data-ttu-id="5e93b-148">在传递给**SortTable** [SSortOrderSet](ssortorderset.md)结构中指定的顺序是返回的行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-148">The returned rows are in the order specified in the [SSortOrderSet](ssortorderset.md) structure passed to **SortTable**.</span></span>
  
<span data-ttu-id="5e93b-149">对于每个行返回列和所返回的顺序取决于成功调用对进行了[IMAPITable::SetColumns](imapitable-setcolumns.md)。</span><span class="sxs-lookup"><span data-stu-id="5e93b-149">The columns returned for each row and the order in which they are returned depend on whether or not a successful call has been made to [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span> <span data-ttu-id="5e93b-150">**SetColumns**建立一列中，指定要包括在表和在其中他们应包含的顺序中的列的属性。</span><span class="sxs-lookup"><span data-stu-id="5e93b-150">**SetColumns** establishes a column set, specifying the properties to be included in columns in the table and the order in which they should be included.</span></span> <span data-ttu-id="5e93b-151">如果已**SetColumns**呼叫，每一行和这些列的顺序中的特定列将匹配设置调用中指定的列。</span><span class="sxs-lookup"><span data-stu-id="5e93b-151">If a **SetColumns** call has been made, the particular columns in each row and the order of those columns match the column set specified in the call.</span></span> <span data-ttu-id="5e93b-152">如果已没有**SetColumns**呼叫，表返回其默认列集。</span><span class="sxs-lookup"><span data-stu-id="5e93b-152">If no **SetColumns** call has been made, the table returns its default column set.</span></span> 
  
<span data-ttu-id="5e93b-153">如果已尽可能无这些呼叫， **QueryRows**将返回的所有行表中。</span><span class="sxs-lookup"><span data-stu-id="5e93b-153">If none of these calls has been made, **QueryRows** returns all of the rows in the table.</span></span> <span data-ttu-id="5e93b-154">每个行包含默认列中默认顺序设置。</span><span class="sxs-lookup"><span data-stu-id="5e93b-154">Each row contains the default column set in default order.</span></span> 
  
<span data-ttu-id="5e93b-155">当建立[IMAPITable::SetColumns](imapitable-setcolumns.md)将调用的列集包括设为 PR_NULL 列时，在行集中返回_lppRows_ [SPropValue](spropvalue.md)数组将包含空插槽。</span><span class="sxs-lookup"><span data-stu-id="5e93b-155">When the column set established in a call to [IMAPITable::SetColumns](imapitable-setcolumns.md) includes columns set to PR_NULL, the [SPropValue](spropvalue.md) array within the row set returned in  _lppRows_ will contain empty slots.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="5e93b-156">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="5e93b-156">Notes to implementers</span></span>

<span data-ttu-id="5e93b-157">您可以允许呼叫者可以请求列设置中包含不受支持的列。</span><span class="sxs-lookup"><span data-stu-id="5e93b-157">You can allow a caller to request an unsupported column to be included in the column set.</span></span> <span data-ttu-id="5e93b-158">当发生这种情况时，PT_ERROR 置于属性类型的部分属性标记和 MAPI_E_NOT_FOUND 中不受支持的列的属性值。</span><span class="sxs-lookup"><span data-stu-id="5e93b-158">When this occurs, place PT_ERROR in the property type portion of the property tag and MAPI_E_NOT_FOUND in the property value for the unsupported column.</span></span> 
  
<span data-ttu-id="5e93b-159">视为请求，而不是必需的行数。</span><span class="sxs-lookup"><span data-stu-id="5e93b-159">Treat the row count as a request rather than a requirement.</span></span> <span data-ttu-id="5e93b-160">您可以任意位置从返回零行中是否存在任何行查询，到请求的数目的方向。</span><span class="sxs-lookup"><span data-stu-id="5e93b-160">You can return anywhere from zero rows, if there are no rows in the direction of the query, to the number requested.</span></span> 
  
<span data-ttu-id="5e93b-161">返回只有该用户将看到行分类的表视图，从请求时允许呼叫者有关数据的范围进行有效假设，避免额外的工作的行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-161">Return only the rows that the user will see when rows are requested from a categorized table view, allowing the caller to make valid assumptions about the scope of the data and avoid extra work.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5e93b-162">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5e93b-162">Notes to callers</span></span>

<span data-ttu-id="5e93b-163">通常您将结尾任意具有_lRowCount_参数中指定数量的行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-163">Usually you will end up with as many rows as you have specified in the  _lRowCount_ parameter.</span></span> <span data-ttu-id="5e93b-164">但是，当内存或实现的限制是问题或操作提前达到的开始或表末尾， **QueryRows**将返回较少比所请求的行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-164">However, when memory or implementation limits are an issue or when the operation reaches the beginning or end of the table prematurely, **QueryRows** will return less rows than requested.</span></span> 
  
<span data-ttu-id="5e93b-165">如果**QueryRows**返回 MAPI_E_BUSY，调用[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md)方法，并异步操作完成后重试**QueryRows**调用。</span><span class="sxs-lookup"><span data-stu-id="5e93b-165">If **QueryRows** returns MAPI_E_BUSY, call the [IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md) method and retry the call to **QueryRows** when the asynchronous operation is complete.</span></span> 
  
<span data-ttu-id="5e93b-166">当调用**QueryRows**，请注意，所需的异步通知的时间可能会导致，您可以返回从**QueryRows**不准确地表示基础数据行集。</span><span class="sxs-lookup"><span data-stu-id="5e93b-166">When calling **QueryRows**, be aware that the timing of asynchronous notifications can potentially cause the row set that you get back from **QueryRows** not to accurately represent the underlying data.</span></span> <span data-ttu-id="5e93b-167">例如，调用**QueryRows**到某个文件夹的内容表以下删除一条消息，但之前收到的相应通知会导致要返回的行中的已删除的行设置。</span><span class="sxs-lookup"><span data-stu-id="5e93b-167">For example, a call to **QueryRows** to a folder's contents table following the deletion of a message but prior to the receipt of the corresponding notification will cause the deleted row to be returned in the row set.</span></span> <span data-ttu-id="5e93b-168">总是等待通知来更新用户的数据视图之前完成。</span><span class="sxs-lookup"><span data-stu-id="5e93b-168">Always wait for a notification to arrive before updating the user's view of the data.</span></span> 
  
<span data-ttu-id="5e93b-169">有关从表中检索行的详细信息，请参阅[从表格行检索数据](retrieving-data-from-table-rows.md)。</span><span class="sxs-lookup"><span data-stu-id="5e93b-169">For more information about retrieving rows from tables, see [Retrieving Data from Table Rows](retrieving-data-from-table-rows.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="5e93b-170">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="5e93b-170">MFCMAPI reference</span></span>

<span data-ttu-id="5e93b-171">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5e93b-171">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="5e93b-172">**文件**</span><span class="sxs-lookup"><span data-stu-id="5e93b-172">**File**</span></span>|<span data-ttu-id="5e93b-173">**函数**</span><span class="sxs-lookup"><span data-stu-id="5e93b-173">**Function**</span></span>|<span data-ttu-id="5e93b-174">**Comment**</span><span class="sxs-lookup"><span data-stu-id="5e93b-174">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e93b-175">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="5e93b-175">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="5e93b-176">DwThreadFuncLoadTable</span><span class="sxs-lookup"><span data-stu-id="5e93b-176">DwThreadFuncLoadTable</span></span>  <br/> |<span data-ttu-id="5e93b-177">MFCMAPI 使用**IMAPITable::QueryRows**方法检索要加载到视图的表中的行。</span><span class="sxs-lookup"><span data-stu-id="5e93b-177">MFCMAPI uses the **IMAPITable::QueryRows** method to retrieve rows in the table to load into the view.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5e93b-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e93b-178">See also</span></span>



[<span data-ttu-id="5e93b-179">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="5e93b-179">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="5e93b-180">FreeProws</span><span class="sxs-lookup"><span data-stu-id="5e93b-180">FreeProws</span></span>](freeprows.md)
  
[<span data-ttu-id="5e93b-181">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="5e93b-181">HrQueryAllRows</span></span>](hrqueryallrows.md)
  
[<span data-ttu-id="5e93b-182">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="5e93b-182">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="5e93b-183">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="5e93b-183">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="5e93b-184">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="5e93b-184">IMAPITable::WaitForCompletion</span></span>](imapitable-waitforcompletion.md)
  
[<span data-ttu-id="5e93b-185">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="5e93b-185">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="5e93b-186">SRow</span><span class="sxs-lookup"><span data-stu-id="5e93b-186">SRow</span></span>](srow.md)
  
[<span data-ttu-id="5e93b-187">SRowSet</span><span class="sxs-lookup"><span data-stu-id="5e93b-187">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="5e93b-188">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5e93b-188">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="5e93b-189">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="5e93b-189">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

