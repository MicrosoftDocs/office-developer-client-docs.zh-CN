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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328867"
---
# <a name="imapitablequeryrows"></a><span data-ttu-id="53afb-103">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="53afb-103">IMAPITable::QueryRows</span></span>

  
  
<span data-ttu-id="53afb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53afb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53afb-105">从当前游标位置开始, 返回表中的一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="53afb-105">Returns one or more rows from a table, beginning at the current cursor position.</span></span>
  
```cpp
HRESULT QueryRows(
LONG lRowCount,
ULONG ulFlags,
LPSRowSet FAR * lppRows
);
```

## <a name="parameters"></a><span data-ttu-id="53afb-106">参数</span><span class="sxs-lookup"><span data-stu-id="53afb-106">Parameters</span></span>

 <span data-ttu-id="53afb-107">_lRowCount_</span><span class="sxs-lookup"><span data-stu-id="53afb-107">_lRowCount_</span></span>
  
> <span data-ttu-id="53afb-108">实时要返回的最大行数。</span><span class="sxs-lookup"><span data-stu-id="53afb-108">[in] Maximum number of rows to be returned.</span></span>
    
 <span data-ttu-id="53afb-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="53afb-109">_ulFlags_</span></span>
  
> <span data-ttu-id="53afb-110">实时控制如何返回行的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="53afb-110">[in] Bitmask of flags that control how rows are returned.</span></span> <span data-ttu-id="53afb-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="53afb-111">The following flag can be set:</span></span>
    
<span data-ttu-id="53afb-112">TBL_NOADVANCE</span><span class="sxs-lookup"><span data-stu-id="53afb-112">TBL_NOADVANCE</span></span> 
  
> <span data-ttu-id="53afb-113">防止因行检索而导致光标不前移。</span><span class="sxs-lookup"><span data-stu-id="53afb-113">Prevents the cursor from advancing as a result of the row retrieval.</span></span> <span data-ttu-id="53afb-114">如果设置了 TBL_NOADVANCE 标志, 则游标指向返回的第一行。</span><span class="sxs-lookup"><span data-stu-id="53afb-114">If the TBL_NOADVANCE flag is set, the cursor points to the first row returned.</span></span> <span data-ttu-id="53afb-115">如果未设置 TBL_NOADVANCE 标志, 则游标指向返回的最后一行后面的行。</span><span class="sxs-lookup"><span data-stu-id="53afb-115">If the TBL_NOADVANCE flag is not set, the cursor points to the row following the last row returned.</span></span>
    
 <span data-ttu-id="53afb-116">_lppRows_</span><span class="sxs-lookup"><span data-stu-id="53afb-116">_lppRows_</span></span>
  
> <span data-ttu-id="53afb-117">排除指向包含表行的[SRowSet](srowset.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="53afb-117">[out] Pointer to a pointer to an [SRowSet](srowset.md) structure holding the table rows.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="53afb-118">返回值</span><span class="sxs-lookup"><span data-stu-id="53afb-118">Return value</span></span>

<span data-ttu-id="53afb-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="53afb-119">S_OK</span></span> 
  
> <span data-ttu-id="53afb-120">已成功返回行。</span><span class="sxs-lookup"><span data-stu-id="53afb-120">The rows were successfully returned.</span></span>
    
<span data-ttu-id="53afb-121">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="53afb-121">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="53afb-122">正在进行另一个操作, 以阻止行检索操作启动。</span><span class="sxs-lookup"><span data-stu-id="53afb-122">Another operation is in progress that prevents the row retrieval operation from starting.</span></span> <span data-ttu-id="53afb-123">应允许正在进行的操作完成, 或者应已停止。</span><span class="sxs-lookup"><span data-stu-id="53afb-123">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="53afb-124">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="53afb-124">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="53afb-125">将_IRowCount_参数设置为零。</span><span class="sxs-lookup"><span data-stu-id="53afb-125">The  _IRowCount_ parameter is set to zero.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="53afb-126">注解</span><span class="sxs-lookup"><span data-stu-id="53afb-126">Remarks</span></span>

<span data-ttu-id="53afb-127">**IMAPITable:: QueryRows**方法从表中获取一个或多个数据行。</span><span class="sxs-lookup"><span data-stu-id="53afb-127">The **IMAPITable::QueryRows** method gets one or more rows of data from a table.</span></span> <span data-ttu-id="53afb-128">_IRowCount_参数的值影响检索的起始点。</span><span class="sxs-lookup"><span data-stu-id="53afb-128">The value of the  _IRowCount_ parameter affects the starting point for the retrieval.</span></span> <span data-ttu-id="53afb-129">如果_IRowCount_为正数, 则从当前位置开始沿正向方向读取行。</span><span class="sxs-lookup"><span data-stu-id="53afb-129">If  _IRowCount_ is positive, rows are read in a forward direction, starting at the current position.</span></span> <span data-ttu-id="53afb-130">如果_IRowCount_为负值, **QueryRows**将通过向后移动指定的行数来重置起始点。</span><span class="sxs-lookup"><span data-stu-id="53afb-130">If  _IRowCount_ is negative, **QueryRows** resets the starting point by moving backward the indicated number of rows.</span></span> <span data-ttu-id="53afb-131">重置游标后, 将按正向顺序读取行。</span><span class="sxs-lookup"><span data-stu-id="53afb-131">After the cursor is reset, rows are read in forward order.</span></span> 
  
<span data-ttu-id="53afb-132">由_lppRows_参数指向的[SRowSet](srowset.md)结构中的**cRows**成员指示返回的行数。</span><span class="sxs-lookup"><span data-stu-id="53afb-132">The **cRows** member in the [SRowSet](srowset.md) structure pointed to by the  _lppRows_ parameter indicates the number of rows returned.</span></span> <span data-ttu-id="53afb-133">如果返回零行:</span><span class="sxs-lookup"><span data-stu-id="53afb-133">If zero rows are returned:</span></span> 
  
- <span data-ttu-id="53afb-134">游标已经定位在表的开头, _IRowCount_的值为负值。</span><span class="sxs-lookup"><span data-stu-id="53afb-134">The cursor was already positioned at the beginning of the table and the value of  _IRowCount_ is negative.</span></span> <span data-ttu-id="53afb-135">和</span><span class="sxs-lookup"><span data-stu-id="53afb-135">-Or-</span></span> 
    
- <span data-ttu-id="53afb-136">游标已经定位在表的末尾, _IRowCount_的值是正数。</span><span class="sxs-lookup"><span data-stu-id="53afb-136">The cursor was already positioned at the end of the table and the value of  _IRowCount_ is positive.</span></span> 
    
<span data-ttu-id="53afb-137">列数及其排序对于每一行都是相同的。</span><span class="sxs-lookup"><span data-stu-id="53afb-137">The number of columns and their ordering is the same for each row.</span></span> <span data-ttu-id="53afb-138">如果某一行的属性不存在, 或者在读取属性时出现错误, 则该行中的该属性的**SPropValue**结构包含以下值:</span><span class="sxs-lookup"><span data-stu-id="53afb-138">If a property does not exist for a row or there is an error reading a property, the **SPropValue** structure for the property in the row contains the following values:</span></span> 
  
- <span data-ttu-id="53afb-139">**ulPropTag**成员中的属性类型的 PT_ERROR。</span><span class="sxs-lookup"><span data-stu-id="53afb-139">PT_ERROR for the property type in the **ulPropTag** member.</span></span> 
    
- <span data-ttu-id="53afb-140">MAPI_E_NOT_FOUND 为**Value**成员。</span><span class="sxs-lookup"><span data-stu-id="53afb-140">MAPI_E_NOT_FOUND for the **Value** member.</span></span> 
    
<span data-ttu-id="53afb-141">为_lppRows_参数所指向的行集中的[SPropValue](spropvalue.md)结构使用的内存必须为每个行单独分配和释放。</span><span class="sxs-lookup"><span data-stu-id="53afb-141">Memory used for the [SPropValue](spropvalue.md) structures in the row set pointed to by the  _lppRows_ parameter must be separately allocated and freed for each row.</span></span> <span data-ttu-id="53afb-142">使用[MAPIFreeBuffer](mapifreebuffer.md)释放属性值结构并释放行集。</span><span class="sxs-lookup"><span data-stu-id="53afb-142">Use [MAPIFreeBuffer](mapifreebuffer.md) to free the property value structures and to free the row set.</span></span> <span data-ttu-id="53afb-143">但是, 当对**QueryRows**的调用返回0时, 指示表的开头或结尾, 只有**SRowSet**结构本身需要释放。</span><span class="sxs-lookup"><span data-stu-id="53afb-143">When a call to **QueryRows** returns zero, however, indicating the beginning or end of the table, only the **SRowSet** structure itself needs to be freed.</span></span> <span data-ttu-id="53afb-144">有关如何在**SRowSet**结构中分配和释放内存的详细信息, 请参阅[管理内存中的 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="53afb-144">For more information about how to allocate and free memory in an **SRowSet** structure, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span>
  
<span data-ttu-id="53afb-145">返回的行以及返回的顺序取决于是否对[IMAPITable:: Restrict](imapitable-restrict.md)和[imapitable:: SortTable](imapitable-sorttable.md)进行了成功的调用。</span><span class="sxs-lookup"><span data-stu-id="53afb-145">The rows that are returned and the order in which they are returned depend on whether or not successful calls have been made to [IMAPITable::Restrict](imapitable-restrict.md) and [IMAPITable::SortTable](imapitable-sorttable.md).</span></span> <span data-ttu-id="53afb-146">**限制**筛选视图中的行, 从而导致**QueryRows**仅返回与限制中指定的条件匹配的行。</span><span class="sxs-lookup"><span data-stu-id="53afb-146">**Restrict** filters rows from the view, causing **QueryRows** to return only the rows that match the criteria specified in the restriction.</span></span> <span data-ttu-id="53afb-147">**SortTable**建立标准的或已分类的排序顺序, 从而影响**QueryRows**返回的行序列。</span><span class="sxs-lookup"><span data-stu-id="53afb-147">**SortTable** establishes a standard or categorized sort order, affecting the sequence of rows returned by **QueryRows**.</span></span> <span data-ttu-id="53afb-148">返回的行的顺序与传递给**SortTable**的[SSortOrderSet](ssortorderset.md)结构中指定的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="53afb-148">The returned rows are in the order specified in the [SSortOrderSet](ssortorderset.md) structure passed to **SortTable**.</span></span>
  
<span data-ttu-id="53afb-149">为每个行返回的列及其返回的顺序取决于是否对[IMAPITable:: SetColumns](imapitable-setcolumns.md)成功进行了调用。</span><span class="sxs-lookup"><span data-stu-id="53afb-149">The columns returned for each row and the order in which they are returned depend on whether or not a successful call has been made to [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span> <span data-ttu-id="53afb-150">**SetColumns**建立列集, 指定要包含在表的列中的属性以及应包含的顺序。</span><span class="sxs-lookup"><span data-stu-id="53afb-150">**SetColumns** establishes a column set, specifying the properties to be included in columns in the table and the order in which they should be included.</span></span> <span data-ttu-id="53afb-151">如果进行了**SetColumns**调用, 则每行中的特定列和这些列的顺序与调用中指定的列集相匹配。</span><span class="sxs-lookup"><span data-stu-id="53afb-151">If a **SetColumns** call has been made, the particular columns in each row and the order of those columns match the column set specified in the call.</span></span> <span data-ttu-id="53afb-152">如果未进行任何**SetColumns**调用, 则该表将返回其默认列集。</span><span class="sxs-lookup"><span data-stu-id="53afb-152">If no **SetColumns** call has been made, the table returns its default column set.</span></span> 
  
<span data-ttu-id="53afb-153">如果未进行这些调用, 则**QueryRows**将返回表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="53afb-153">If none of these calls has been made, **QueryRows** returns all of the rows in the table.</span></span> <span data-ttu-id="53afb-154">每行都包含默认的默认列集。</span><span class="sxs-lookup"><span data-stu-id="53afb-154">Each row contains the default column set in default order.</span></span> 
  
<span data-ttu-id="53afb-155">当在对[IMAPITable:: SetColumns](imapitable-setcolumns.md)的调用中建立的列集包含设置为 PR_NULL 的列时, _lppRows_中返回的行集内的[SPropValue](spropvalue.md)数组将包含空槽。</span><span class="sxs-lookup"><span data-stu-id="53afb-155">When the column set established in a call to [IMAPITable::SetColumns](imapitable-setcolumns.md) includes columns set to PR_NULL, the [SPropValue](spropvalue.md) array within the row set returned in  _lppRows_ will contain empty slots.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="53afb-156">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="53afb-156">Notes to implementers</span></span>

<span data-ttu-id="53afb-157">您可以允许呼叫者请求在列集中包含不受支持的列。</span><span class="sxs-lookup"><span data-stu-id="53afb-157">You can allow a caller to request an unsupported column to be included in the column set.</span></span> <span data-ttu-id="53afb-158">发生这种情况时, 请将 PT_ERROR 置于属性标记的属性类型部分, 并在属性值中为不受支持的列键入 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="53afb-158">When this occurs, place PT_ERROR in the property type portion of the property tag and MAPI_E_NOT_FOUND in the property value for the unsupported column.</span></span> 
  
<span data-ttu-id="53afb-159">将行数视为请求而不是要求。</span><span class="sxs-lookup"><span data-stu-id="53afb-159">Treat the row count as a request rather than a requirement.</span></span> <span data-ttu-id="53afb-160">如果在查询的方向上没有行, 则可以从零行返回到请求的数量。</span><span class="sxs-lookup"><span data-stu-id="53afb-160">You can return anywhere from zero rows, if there are no rows in the direction of the query, to the number requested.</span></span> 
  
<span data-ttu-id="53afb-161">仅返回在分类表视图中请求行时用户将看到的行, 从而允许调用方对数据范围做出有效假设并避免额外的工作。</span><span class="sxs-lookup"><span data-stu-id="53afb-161">Return only the rows that the user will see when rows are requested from a categorized table view, allowing the caller to make valid assumptions about the scope of the data and avoid extra work.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="53afb-162">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="53afb-162">Notes to callers</span></span>

<span data-ttu-id="53afb-163">通常情况下, 您最终会拥有在_lRowCount_参数中指定的多个行。</span><span class="sxs-lookup"><span data-stu-id="53afb-163">Usually you will end up with as many rows as you have specified in the  _lRowCount_ parameter.</span></span> <span data-ttu-id="53afb-164">但是, 当内存或实现限制出现问题, 或者操作在提前到达表的开头或结尾时, **QueryRows**将返回的行数少于请求的行数。</span><span class="sxs-lookup"><span data-stu-id="53afb-164">However, when memory or implementation limits are an issue or when the operation reaches the beginning or end of the table prematurely, **QueryRows** will return less rows than requested.</span></span> 
  
<span data-ttu-id="53afb-165">如果**QueryRows**返回 MAPI_E_BUSY, 则调用[IMAPITable:: WaitForCompletion](imapitable-waitforcompletion.md)方法, 并在异步操作完成时重试对**QueryRows**的调用。</span><span class="sxs-lookup"><span data-stu-id="53afb-165">If **QueryRows** returns MAPI_E_BUSY, call the [IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md) method and retry the call to **QueryRows** when the asynchronous operation is complete.</span></span> 
  
<span data-ttu-id="53afb-166">调用**QueryRows**时, 请注意, 异步通知的计时可能会导致从**QueryRows**返回的行集不能准确表示基础数据。</span><span class="sxs-lookup"><span data-stu-id="53afb-166">When calling **QueryRows**, be aware that the timing of asynchronous notifications can potentially cause the row set that you get back from **QueryRows** not to accurately represent the underlying data.</span></span> <span data-ttu-id="53afb-167">例如, 在删除邮件之后但在收到相应通知之前, 对文件夹的内容表的**QueryRows**调用将导致删除的行在行集中返回。</span><span class="sxs-lookup"><span data-stu-id="53afb-167">For example, a call to **QueryRows** to a folder's contents table following the deletion of a message but prior to the receipt of the corresponding notification will cause the deleted row to be returned in the row set.</span></span> <span data-ttu-id="53afb-168">始终等待通知在更新用户的数据视图之前到达。</span><span class="sxs-lookup"><span data-stu-id="53afb-168">Always wait for a notification to arrive before updating the user's view of the data.</span></span> 
  
<span data-ttu-id="53afb-169">有关检索表中的行的详细信息, 请参阅[从表行检索数据](retrieving-data-from-table-rows.md)。</span><span class="sxs-lookup"><span data-stu-id="53afb-169">For more information about retrieving rows from tables, see [Retrieving Data from Table Rows](retrieving-data-from-table-rows.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="53afb-170">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="53afb-170">MFCMAPI reference</span></span>

<span data-ttu-id="53afb-171">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="53afb-171">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="53afb-172">**文件**</span><span class="sxs-lookup"><span data-stu-id="53afb-172">**File**</span></span>|<span data-ttu-id="53afb-173">**函数**</span><span class="sxs-lookup"><span data-stu-id="53afb-173">**Function**</span></span>|<span data-ttu-id="53afb-174">**备注**</span><span class="sxs-lookup"><span data-stu-id="53afb-174">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="53afb-175">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="53afb-175">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="53afb-176">DwThreadFuncLoadTable</span><span class="sxs-lookup"><span data-stu-id="53afb-176">DwThreadFuncLoadTable</span></span>  <br/> |<span data-ttu-id="53afb-177">MFCMAPI 使用**IMAPITable:: QueryRows**方法检索要加载到视图中的表中的行。</span><span class="sxs-lookup"><span data-stu-id="53afb-177">MFCMAPI uses the **IMAPITable::QueryRows** method to retrieve rows in the table to load into the view.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="53afb-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53afb-178">See also</span></span>



[<span data-ttu-id="53afb-179">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="53afb-179">ADRENTRY</span></span>](adrentry.md)
  
[<span data-ttu-id="53afb-180">FreeProws</span><span class="sxs-lookup"><span data-stu-id="53afb-180">FreeProws</span></span>](freeprows.md)
  
[<span data-ttu-id="53afb-181">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="53afb-181">HrQueryAllRows</span></span>](hrqueryallrows.md)
  
[<span data-ttu-id="53afb-182">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="53afb-182">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="53afb-183">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="53afb-183">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="53afb-184">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="53afb-184">IMAPITable::WaitForCompletion</span></span>](imapitable-waitforcompletion.md)
  
[<span data-ttu-id="53afb-185">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="53afb-185">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="53afb-186">SRow</span><span class="sxs-lookup"><span data-stu-id="53afb-186">SRow</span></span>](srow.md)
  
[<span data-ttu-id="53afb-187">SRowSet</span><span class="sxs-lookup"><span data-stu-id="53afb-187">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="53afb-188">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="53afb-188">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="53afb-189">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="53afb-189">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

