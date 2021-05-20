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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f16ba9164d55fdb7bd688d4068f99dc4407e5413
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432364"
---
# <a name="imapitablesorttable"></a><span data-ttu-id="e1374-103">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="e1374-103">IMAPITable::SortTable</span></span>

<span data-ttu-id="e1374-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e1374-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e1374-105">**IMAPITable：：SortTable** 方法根据排序条件对表的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="e1374-105">The **IMAPITable::SortTable** method orders the rows of the table, depending on sort criteria.</span></span> 
  
```cpp
HRESULT SortTable(
LPSSortOrderSet lpSortCriteria,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="e1374-106">参数</span><span class="sxs-lookup"><span data-stu-id="e1374-106">Parameters</span></span>

<span data-ttu-id="e1374-107">_lpSortCriteria_</span><span class="sxs-lookup"><span data-stu-id="e1374-107">_lpSortCriteria_</span></span>
  
> <span data-ttu-id="e1374-108">[in]指向包含要 [应用排序条件的 SSortOrderSet](ssortorderset.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="e1374-108">[in] Pointer to an [SSortOrderSet](ssortorderset.md) structure that contains the sort criteria to apply.</span></span> <span data-ttu-id="e1374-109">传递包含 **零列的 SSortOrderSet** 结构指示无需按任何特定顺序对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="e1374-109">Passing an **SSortOrderSet** structure that contains zero columns indicates that the table does not have to be sorted in any particular order.</span></span> 
    
<span data-ttu-id="e1374-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e1374-110">_ulFlags_</span></span>
  
> <span data-ttu-id="e1374-111">[in]控制 **IMAPITable：：SortTable 操作计时的标志的位** 掩码。</span><span class="sxs-lookup"><span data-stu-id="e1374-111">[in] Bitmask of flags that controls the timing of the **IMAPITable::SortTable** operation.</span></span> <span data-ttu-id="e1374-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="e1374-112">The following flags can be set:</span></span> 
    
<span data-ttu-id="e1374-113">TBL_ASYNC</span><span class="sxs-lookup"><span data-stu-id="e1374-113">TBL_ASYNC</span></span> 
  
> <span data-ttu-id="e1374-114">异步启动操作，在操作完成之前返回。</span><span class="sxs-lookup"><span data-stu-id="e1374-114">Starts the operation asynchronously and returns before the operation is complete.</span></span>
    
<span data-ttu-id="e1374-115">TBL_BATCH</span><span class="sxs-lookup"><span data-stu-id="e1374-115">TBL_BATCH</span></span> 
  
> <span data-ttu-id="e1374-116">延迟排序的完成，直到需要表中的数据。</span><span class="sxs-lookup"><span data-stu-id="e1374-116">Defers the completion of the sort until the data in the table is required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e1374-117">返回值</span><span class="sxs-lookup"><span data-stu-id="e1374-117">Return value</span></span>

<span data-ttu-id="e1374-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1374-118">S_OK</span></span> 
  
> <span data-ttu-id="e1374-119">排序操作成功。</span><span class="sxs-lookup"><span data-stu-id="e1374-119">The sort operation was successful.</span></span>
    
<span data-ttu-id="e1374-120">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="e1374-120">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="e1374-121">正在进行另一个阻止排序操作启动的操作。</span><span class="sxs-lookup"><span data-stu-id="e1374-121">Another operation is in progress that prevents the sort operation from starting.</span></span> <span data-ttu-id="e1374-122">应允许完成或停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="e1374-122">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="e1374-123">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="e1374-123">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="e1374-124">该表不支持所请求的排序类型。</span><span class="sxs-lookup"><span data-stu-id="e1374-124">The table does not support the type of sorting requested.</span></span>
    
<span data-ttu-id="e1374-125">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="e1374-125">MAPI_E_TOO_COMPLEX</span></span> 
  
> <span data-ttu-id="e1374-126">表无法执行该操作，因为  _lpSortCriteria_ 参数指向的特定排序条件过于复杂。</span><span class="sxs-lookup"><span data-stu-id="e1374-126">The table cannot perform the operation because the particular sort criteria pointed to by the  _lpSortCriteria_ parameter is too complex.</span></span> <span data-ttu-id="e1374-127">**SortTable** 可以在MAPI_E_TOO_COMPLEX返回值。</span><span class="sxs-lookup"><span data-stu-id="e1374-127">**SortTable** can return MAPI_E_TOO_COMPLEX under the following conditions.</span></span> 
    
   - <span data-ttu-id="e1374-128">为实现无法排序的属性列请求排序操作。</span><span class="sxs-lookup"><span data-stu-id="e1374-128">A sort operation is requested for a property column that the implementation cannot sort.</span></span>
    
   - <span data-ttu-id="e1374-129">实现不支持 **SSortOrderSet** 结构的 **ulOrder** 成员中请求的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="e1374-129">The implementation does not support the sort order requested in the **ulOrder** member of the **SSortOrderSet** structure.</span></span> 
    
   - <span data-ttu-id="e1374-130">**SSortOrderSet** 中的 **cSorts** 成员中指定的要排序的列数大于实现可以处理的数量。</span><span class="sxs-lookup"><span data-stu-id="e1374-130">The number of columns to be sorted, as specified in the **cSorts** member in **SSortOrderSet**, is larger than the implementation can handle.</span></span>
    
   - <span data-ttu-id="e1374-131">请求排序操作，如 **SSortOrderSet** 中的属性标记所指示，它基于不在可用集或活动集内的属性，并且实现不支持对不在可用集内的属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="e1374-131">A sort operation is requested, as indicated by a property tag in **SSortOrderSet**, based on a property that is not in the available or active set and the implementation does not support sorting on properties not in the available set.</span></span>
    
   - <span data-ttu-id="e1374-132">一个属性按排序顺序集多次指定，如同一属性标记的多个实例所指示，并且实现无法执行此类排序操作。</span><span class="sxs-lookup"><span data-stu-id="e1374-132">One property is specified multiple times in a sort order set, as indicated by multiple instances of the same property tag, and the implementation cannot perform such a sort operation.</span></span>
    
   - <span data-ttu-id="e1374-133">基于多值属性列的排序操作是使用 MVI_FLAG 并且实现不支持对多值属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="e1374-133">A sort operation based on multivalued property columns is requested using MVI_FLAG and the implementation does not support sorting on multivalued properties.</span></span> 
    
   - <span data-ttu-id="e1374-134">**SSortOrderSet** 中属性的属性标记指定实现不支持的属性或类型。</span><span class="sxs-lookup"><span data-stu-id="e1374-134">A property tag for a property in **SSortOrderSet** specifies a property or type that the implementation does not support.</span></span> 
    
   - <span data-ttu-id="e1374-135">除了从 **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性向前浏览表的排序操作外，只为支持这种类型的排序的附件表指定排序操作。</span><span class="sxs-lookup"><span data-stu-id="e1374-135">A sort operation other than one that proceeds through the table from the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property forward is specified only for an attachment table that supports this type of sorting.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e1374-136">备注</span><span class="sxs-lookup"><span data-stu-id="e1374-136">Remarks</span></span>

<span data-ttu-id="e1374-137">**IMAPITable：：SortTable** 方法对表视图中的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="e1374-137">The **IMAPITable::SortTable** method orders the rows in a table view.</span></span> <span data-ttu-id="e1374-138">有些表支持对各种排序键列的标准排序和分类排序，而其他表的支持则更加有限。</span><span class="sxs-lookup"><span data-stu-id="e1374-138">Whereas some tables support both standard and categorized sorting on various sort key columns, other tables are more limited in their support.</span></span> <span data-ttu-id="e1374-139">通讯簿提供程序通常不支持表排序。</span><span class="sxs-lookup"><span data-stu-id="e1374-139">Address book providers ordinarily do not support table sorting.</span></span> <span data-ttu-id="e1374-140">邮件存储提供程序通常支持按以下程度进行排序：当完整表在表中排序时，它们保持 (排序时) 排序。</span><span class="sxs-lookup"><span data-stu-id="e1374-140">Message store providers usually support sorting to the extent that they keep the sort order of folders that results when a full table (a table without restrictions) is sorted.</span></span> 
  
<span data-ttu-id="e1374-141">某些表允许对任意表列进行排序。</span><span class="sxs-lookup"><span data-stu-id="e1374-141">Some tables allow sorting to be done on any table column.</span></span> <span data-ttu-id="e1374-142">其他表不能;表视图中未包含的列不受 **SortTable** 调用的影响。</span><span class="sxs-lookup"><span data-stu-id="e1374-142">Other tables do not; columns not included in the table view are unaffected by a **SortTable** call.</span></span> <span data-ttu-id="e1374-143">某些表要求仅对表的当前列集的列构建排序键。</span><span class="sxs-lookup"><span data-stu-id="e1374-143">Some tables require that sort keys be built only with columns in the table's current column set.</span></span> 
  
<span data-ttu-id="e1374-144">当表无法完成排序MAPI_E_NO_SUPPORT，MAPI_E_TOO_COMPLEX **返回 SortTable** 中的一个或多个值。</span><span class="sxs-lookup"><span data-stu-id="e1374-144">A table can return either MAPI_E_NO_SUPPORT or MAPI_E_TOO_COMPLEX from **SortTable** when it cannot complete a sort operation.</span></span> <span data-ttu-id="e1374-145">此外，不保证存储提供程序遵守为层次结构表指定的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="e1374-145">Moreover, store providers are not guaranteed to honor the sort order set specified for hierarchy tables.</span></span> 
  
<span data-ttu-id="e1374-146">当 _lpSortCriteria_ 参数指向 [的 SSortOrderSet](ssortorderset.md)结构中有零列时，表将返回当前列集。</span><span class="sxs-lookup"><span data-stu-id="e1374-146">When there are zero columns in the [SSortOrderSet](ssortorderset.md) structure pointed to by the  _lpSortCriteria_ parameter, the table returns the current column set.</span></span> <span data-ttu-id="e1374-147">可以通过调用表的 [IMAPITable：：QuerySortOrder](imapitable-querysortorder.md) 方法检索当前的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="e1374-147">The current sort order can be retrieved by calling the table's [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
<span data-ttu-id="e1374-148">表格的所有书签都失效，应在调用 **SortTable** 时删除，并且指示当前光标位置的 BOOKMARK_CURRENT 书签应设置为表格的开头。</span><span class="sxs-lookup"><span data-stu-id="e1374-148">All bookmarks for a table are invalidated and should be deleted when a call to **SortTable** is made, and the BOOKMARK_CURRENT bookmark that indicates the current cursor position, should be set to the beginning of the table.</span></span> 
  
<span data-ttu-id="e1374-149">如果要对包含多值属性的列进行排序，而未设置 MVI_FLAG 标志，则列的值将被视为完全有序的元组。</span><span class="sxs-lookup"><span data-stu-id="e1374-149">If you are sorting on a column that contains a multivalued property without the MVI_FLAG flag set, the column's values are treated as a completely ordered tuple.</span></span> <span data-ttu-id="e1374-150">两个多值列的比较将按顺序比较列元素，报告第一个不相等的列的关系，并且仅在进行比较的列包含相同值时返回相等值。</span><span class="sxs-lookup"><span data-stu-id="e1374-150">A comparison of two multivalued columns compares the column elements in order, reporting the relation of the columns at the first inequality, and returns equality only if the columns being compared contain the same values in the same order.</span></span> <span data-ttu-id="e1374-151">如果一列的值数少于另一列的值，则报告的关系为空值与另一个值的关系。</span><span class="sxs-lookup"><span data-stu-id="e1374-151">If one column has fewer values than the other, the reported relation is that of a null value to the other value.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="e1374-152">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e1374-152">Notes to callers</span></span>

<span data-ttu-id="e1374-153">**SortTable** 将同步运行，除非您设置了其中一个标志。</span><span class="sxs-lookup"><span data-stu-id="e1374-153">**SortTable** operates synchronously unless you set one of the flags.</span></span> <span data-ttu-id="e1374-154">如果设置了该 **TBL_BATCH，SortTable** 将推迟排序操作，除非您请求数据。</span><span class="sxs-lookup"><span data-stu-id="e1374-154">If you set the TBL_BATCH flag, **SortTable** postpones the sort operation unless you request the data.</span></span> <span data-ttu-id="e1374-155">如果 **TBL_ASYNC，SortTable** 将异步运行，并且可能会在完成操作之前返回。</span><span class="sxs-lookup"><span data-stu-id="e1374-155">If the TBL_ASYNC flag is set, **SortTable** operates asynchronously, potentially returning before the completion of the operation.</span></span> 
  
<span data-ttu-id="e1374-156">如果必须立即排序，请调用 [IMAPITable：：Abort](imapitable-abort.md) 方法来停止进行中的异步操作。</span><span class="sxs-lookup"><span data-stu-id="e1374-156">Call the [IMAPITable::Abort](imapitable-abort.md) method to stop an asynchronous operation in progress if your sort must be done immediately.</span></span> <span data-ttu-id="e1374-157">如果 **SortTable** 由于表上的一个或多个异步操作正在进行而无法继续，它将返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="e1374-157">If **SortTable** cannot continue because one or more asynchronous operations on the table are in progress, it returns MAPI_E_BUSY.</span></span> 
  
<span data-ttu-id="e1374-158">为获得最佳性能，在调用 **SortTable** 执行排序之前，请调用 **SetColumns** 自定义表的列集和 **Restrict** 以限制表中的行数。</span><span class="sxs-lookup"><span data-stu-id="e1374-158">For best performance, call **SetColumns** to customize the table's column set and **Restrict** to limit the number of rows in the table before you call **SortTable** to perform the sort.</span></span> 
  
<span data-ttu-id="e1374-159">每当 **SortTable** 失败时，在失败之前生效的排序顺序仍然有效。</span><span class="sxs-lookup"><span data-stu-id="e1374-159">Whenever **SortTable** fails, the sort order that was in effect before the failure is still in effect.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e1374-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1374-160">See also</span></span>

- [<span data-ttu-id="e1374-161">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="e1374-161">IMAPITable::Abort</span></span>](imapitable-abort.md)
- [<span data-ttu-id="e1374-162">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="e1374-162">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
- [<span data-ttu-id="e1374-163">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="e1374-163">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
- [<span data-ttu-id="e1374-164">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="e1374-164">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
- [<span data-ttu-id="e1374-165">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="e1374-165">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
- [<span data-ttu-id="e1374-166">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="e1374-166">SSortOrderSet</span></span>](ssortorderset.md)
- [<span data-ttu-id="e1374-167">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e1374-167">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

