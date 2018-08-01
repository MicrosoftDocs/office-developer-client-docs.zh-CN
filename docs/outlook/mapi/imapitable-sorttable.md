---
title: IMAPITableSortTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SortTable
api_type:
- COM
ms.assetid: ff5f78ac-06cf-46fb-93da-5f4a3a5d1b22
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 46a87a6eb5c80244c04ae6257cd4441b8797ba36
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775726"
---
# <a name="imapitablesorttable"></a><span data-ttu-id="379d9-103">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="379d9-103">IMAPITable::SortTable</span></span>

<span data-ttu-id="379d9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="379d9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="379d9-105">**IMAPITable::SortTable**方法对行进行排序的表中，具体取决于排序条件。</span><span class="sxs-lookup"><span data-stu-id="379d9-105">The **IMAPITable::SortTable** method orders the rows of the table, depending on sort criteria.</span></span> 
  
```cpp
HRESULT SortTable(
LPSSortOrderSet lpSortCriteria,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="379d9-106">参数</span><span class="sxs-lookup"><span data-stu-id="379d9-106">Parameters</span></span>

<span data-ttu-id="379d9-107">_lpSortCriteria_</span><span class="sxs-lookup"><span data-stu-id="379d9-107">_lpSortCriteria_</span></span>
  
> <span data-ttu-id="379d9-108">[in]指向[SSortOrderSet](ssortorderset.md)结构，其中包含要应用的排序条件。</span><span class="sxs-lookup"><span data-stu-id="379d9-108">[in] Pointer to an [SSortOrderSet](ssortorderset.md) structure that contains the sort criteria to apply.</span></span> <span data-ttu-id="379d9-109">传递**SSortOrderSet**结构，其中包含零个列指示表不需要任何特定顺序排序。</span><span class="sxs-lookup"><span data-stu-id="379d9-109">Passing an **SSortOrderSet** structure that contains zero columns indicates that the table does not have to be sorted in any particular order.</span></span> 
    
<span data-ttu-id="379d9-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="379d9-110">_ulFlags_</span></span>
  
> <span data-ttu-id="379d9-111">[in]位掩码的标志，控制**IMAPITable::SortTable**操作的时间。</span><span class="sxs-lookup"><span data-stu-id="379d9-111">[in] Bitmask of flags that controls the timing of the **IMAPITable::SortTable** operation.</span></span> <span data-ttu-id="379d9-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="379d9-112">The following flags can be set:</span></span> 
    
<span data-ttu-id="379d9-113">TBL_ASYNC</span><span class="sxs-lookup"><span data-stu-id="379d9-113">TBL_ASYNC</span></span> 
  
> <span data-ttu-id="379d9-114">异步启动操作并返回才能完成此操作。</span><span class="sxs-lookup"><span data-stu-id="379d9-114">Starts the operation asynchronously and returns before the operation is complete.</span></span>
    
<span data-ttu-id="379d9-115">TBL_BATCH</span><span class="sxs-lookup"><span data-stu-id="379d9-115">TBL_BATCH</span></span> 
  
> <span data-ttu-id="379d9-116">延迟排序完成，直到表中的数据，则需要。</span><span class="sxs-lookup"><span data-stu-id="379d9-116">Defers the completion of the sort until the data in the table is required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="379d9-117">返回值</span><span class="sxs-lookup"><span data-stu-id="379d9-117">Return value</span></span>

<span data-ttu-id="379d9-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="379d9-118">S_OK</span></span> 
  
> <span data-ttu-id="379d9-119">排序操作已成功。</span><span class="sxs-lookup"><span data-stu-id="379d9-119">The sort operation was successful.</span></span>
    
<span data-ttu-id="379d9-120">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="379d9-120">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="379d9-121">正在进行中，可以防止启动排序操作是另一个操作。</span><span class="sxs-lookup"><span data-stu-id="379d9-121">Another operation is in progress that prevents the sort operation from starting.</span></span> <span data-ttu-id="379d9-122">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="379d9-122">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="379d9-123">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="379d9-123">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="379d9-124">表不支持的排序请求的类型。</span><span class="sxs-lookup"><span data-stu-id="379d9-124">The table does not support the type of sorting requested.</span></span>
    
<span data-ttu-id="379d9-125">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="379d9-125">MAPI_E_TOO_COMPLEX</span></span> 
  
> <span data-ttu-id="379d9-126">表无法执行操作，因为太复杂_lpSortCriteria_参数指向的特定的排序条件。</span><span class="sxs-lookup"><span data-stu-id="379d9-126">The table cannot perform the operation because the particular sort criteria pointed to by the  _lpSortCriteria_ parameter is too complex.</span></span> <span data-ttu-id="379d9-127">**SortTable**可以在下列情况下返回 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="379d9-127">**SortTable** can return MAPI_E_TOO_COMPLEX under the following conditions.</span></span> 
    
   - <span data-ttu-id="379d9-128">排序操作被请求属性列实现不能进行排序。</span><span class="sxs-lookup"><span data-stu-id="379d9-128">A sort operation is requested for a property column that the implementation cannot sort.</span></span>
    
   - <span data-ttu-id="379d9-129">实现不支持在**SSortOrderSet**结构的**ulOrder**成员中请求的排序次序。</span><span class="sxs-lookup"><span data-stu-id="379d9-129">The implementation does not support the sort order requested in the **ulOrder** member of the **SSortOrderSet** structure.</span></span> 
    
   - <span data-ttu-id="379d9-130">要进行排序的列数中**SSortOrderSet** **cSorts**成员指定，大于所实现可处理。</span><span class="sxs-lookup"><span data-stu-id="379d9-130">The number of columns to be sorted, as specified in the **cSorts** member in **SSortOrderSet**, is larger than the implementation can handle.</span></span>
    
   - <span data-ttu-id="379d9-131">请求排序操作，由**SSortOrderSet**，基于不在可用的或活动集中属性中的属性标记和实现不支持排序不在可用集合的属性。</span><span class="sxs-lookup"><span data-stu-id="379d9-131">A sort operation is requested, as indicated by a property tag in **SSortOrderSet**, based on a property that is not in the available or active set and the implementation does not support sorting on properties not in the available set.</span></span>
    
   - <span data-ttu-id="379d9-132">一个属性是多次集合中指定排序顺序，由多个实例的相同属性标记，并实现无法执行排序操作。</span><span class="sxs-lookup"><span data-stu-id="379d9-132">One property is specified multiple times in a sort order set, as indicated by multiple instances of the same property tag, and the implementation cannot perform such a sort operation.</span></span>
    
   - <span data-ttu-id="379d9-133">基于多值的属性列排序操作请求使用 MVI_FLAG 并实现不支持多值属性排序。</span><span class="sxs-lookup"><span data-stu-id="379d9-133">A sort operation based on multivalued property columns is requested using MVI_FLAG and the implementation does not support sorting on multivalued properties.</span></span> 
    
   - <span data-ttu-id="379d9-134">属性标记中**SSortOrderSet**为属性指定的属性或实现不支持的类型。</span><span class="sxs-lookup"><span data-stu-id="379d9-134">A property tag for a property in **SSortOrderSet** specifies a property or type that the implementation does not support.</span></span> 
    
   - <span data-ttu-id="379d9-135">仅支持这种类型的排序附件表指定排序操作以外从头到尾转接**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性中的表。</span><span class="sxs-lookup"><span data-stu-id="379d9-135">A sort operation other than one that proceeds through the table from the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property forward is specified only for an attachment table that supports this type of sorting.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="379d9-136">说明</span><span class="sxs-lookup"><span data-stu-id="379d9-136">Remarks</span></span>

<span data-ttu-id="379d9-137">**IMAPITable::SortTable**方法在表视图中对行进行排序。</span><span class="sxs-lookup"><span data-stu-id="379d9-137">The **IMAPITable::SortTable** method orders the rows in a table view.</span></span> <span data-ttu-id="379d9-138">某些表格中支持标准和分类键列的排序各种上排序，而其他表在支持更多限制。</span><span class="sxs-lookup"><span data-stu-id="379d9-138">Whereas some tables support both standard and categorized sorting on various sort key columns, other tables are more limited in their support.</span></span> <span data-ttu-id="379d9-139">通讯簿提供程序通常不支持表排序。</span><span class="sxs-lookup"><span data-stu-id="379d9-139">Address book providers ordinarily do not support table sorting.</span></span> <span data-ttu-id="379d9-140">消息存储提供程序通常支持的范围内它们保留文件夹的完整表格 （无限制） 进行排序时结果的排序顺序排序。</span><span class="sxs-lookup"><span data-stu-id="379d9-140">Message store providers usually support sorting to the extent that they keep the sort order of folders that results when a full table (a table without restrictions) is sorted.</span></span> 
  
<span data-ttu-id="379d9-141">某些表格中允许要完成的任何表格列进行排序。</span><span class="sxs-lookup"><span data-stu-id="379d9-141">Some tables allow sorting to be done on any table column.</span></span> <span data-ttu-id="379d9-142">其他表不;不包含在表视图中的列不受**SortTable**呼叫。</span><span class="sxs-lookup"><span data-stu-id="379d9-142">Other tables do not; columns not included in the table view are unaffected by a **SortTable** call.</span></span> <span data-ttu-id="379d9-143">某些表格中需要排序关键字构建仅与表的当前列组中的列。</span><span class="sxs-lookup"><span data-stu-id="379d9-143">Some tables require that sort keys be built only with columns in the table's current column set.</span></span> 
  
<span data-ttu-id="379d9-144">表可以返回 MAPI_E_NO_SUPPORT 或 MAPI_E_TOO_COMPLEX 从**SortTable**它不能完成排序操作时。</span><span class="sxs-lookup"><span data-stu-id="379d9-144">A table can return either MAPI_E_NO_SUPPORT or MAPI_E_TOO_COMPLEX from **SortTable** when it cannot complete a sort operation.</span></span> <span data-ttu-id="379d9-145">此外，存储提供程序不能保证服从设置指定的层次结构表的排序次序。</span><span class="sxs-lookup"><span data-stu-id="379d9-145">Moreover, store providers are not guaranteed to honor the sort order set specified for hierarchy tables.</span></span> 
  
<span data-ttu-id="379d9-146">当_lpSortCriteria_参数指向[SSortOrderSet](ssortorderset.md)结构中存在零列时，表返回当前的列集。</span><span class="sxs-lookup"><span data-stu-id="379d9-146">When there are zero columns in the [SSortOrderSet](ssortorderset.md) structure pointed to by the  _lpSortCriteria_ parameter, the table returns the current column set.</span></span> <span data-ttu-id="379d9-147">可以通过调用表的[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法来检索当前的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="379d9-147">The current sort order can be retrieved by calling the table's [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
<span data-ttu-id="379d9-148">表的所有书签将无效，并应删除时调用**SortTable**不进行，并且 BOOKMARK_CURRENT 书签，该值指示当前光标位置，应设置为表的开头。</span><span class="sxs-lookup"><span data-stu-id="379d9-148">All bookmarks for a table are invalidated and should be deleted when a call to **SortTable** is made, and the BOOKMARK_CURRENT bookmark that indicates the current cursor position, should be set to the beginning of the table.</span></span> 
  
<span data-ttu-id="379d9-149">如果在包含一个多值的属性没有设置 MVI_FLAG 标志的列上排序，列的值将被视为完全有序元组。</span><span class="sxs-lookup"><span data-stu-id="379d9-149">If you are sorting on a column that contains a multivalued property without the MVI_FLAG flag set, the column's values are treated as a completely ordered tuple.</span></span> <span data-ttu-id="379d9-150">两个多值列的比较比较中报告的第一个不相等中的列的关系的顺序的列元素，并返回相等，才进行比较的列包含相同的顺序相同的值。</span><span class="sxs-lookup"><span data-stu-id="379d9-150">A comparison of two multivalued columns compares the column elements in order, reporting the relation of the columns at the first inequality, and returns equality only if the columns being compared contain the same values in the same order.</span></span> <span data-ttu-id="379d9-151">如果一个列具有比其他值少，报告的关系是 null 值为其他值。</span><span class="sxs-lookup"><span data-stu-id="379d9-151">If one column has fewer values than the other, the reported relation is that of a null value to the other value.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="379d9-152">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="379d9-152">Notes to callers</span></span>

<span data-ttu-id="379d9-153">除非将其中一个标志设置**SortTable**进行同步操作。</span><span class="sxs-lookup"><span data-stu-id="379d9-153">**SortTable** operates synchronously unless you set one of the flags.</span></span> <span data-ttu-id="379d9-154">如果设置 TBL_BATCH 标志， **SortTable**推迟排序操作，除非您请求的数据。</span><span class="sxs-lookup"><span data-stu-id="379d9-154">If you set the TBL_BATCH flag, **SortTable** postpones the sort operation unless you request the data.</span></span> <span data-ttu-id="379d9-155">如果设置了 TBL_ASYNC 标志， **SortTable**操作以异步方式，可能返回之前完成操作。</span><span class="sxs-lookup"><span data-stu-id="379d9-155">If the TBL_ASYNC flag is set, **SortTable** operates asynchronously, potentially returning before the completion of the operation.</span></span> 
  
<span data-ttu-id="379d9-156">调用[IMAPITable::Abort](imapitable-abort.md)方法以停止正在进行的异步操作，如果立即必须进行排序。</span><span class="sxs-lookup"><span data-stu-id="379d9-156">Call the [IMAPITable::Abort](imapitable-abort.md) method to stop an asynchronous operation in progress if your sort must be done immediately.</span></span> <span data-ttu-id="379d9-157">如果**SortTable**无法继续，因为一个或多个表的异步操作正在进行，则将返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="379d9-157">If **SortTable** cannot continue because one or more asynchronous operations on the table are in progress, it returns MAPI_E_BUSY.</span></span> 
  
<span data-ttu-id="379d9-158">为了获得最佳性能，调用**SetColumns**自定义表的列组并**限制**以限制的表中的行数之前调用**SortTable**执行排序。</span><span class="sxs-lookup"><span data-stu-id="379d9-158">For best performance, call **SetColumns** to customize the table's column set and **Restrict** to limit the number of rows in the table before you call **SortTable** to perform the sort.</span></span> 
  
<span data-ttu-id="379d9-159">只要**SortTable**失败，已起作用之前失败的排序顺序所做的更改。</span><span class="sxs-lookup"><span data-stu-id="379d9-159">Whenever **SortTable** fails, the sort order that was in effect before the failure is still in effect.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="379d9-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="379d9-160">See also</span></span>

- [<span data-ttu-id="379d9-161">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="379d9-161">IMAPITable::Abort</span></span>](imapitable-abort.md)
- [<span data-ttu-id="379d9-162">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="379d9-162">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
- [<span data-ttu-id="379d9-163">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="379d9-163">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
- [<span data-ttu-id="379d9-164">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="379d9-164">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
- [<span data-ttu-id="379d9-165">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="379d9-165">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
- [<span data-ttu-id="379d9-166">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="379d9-166">SSortOrderSet</span></span>](ssortorderset.md)
- [<span data-ttu-id="379d9-167">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="379d9-167">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

