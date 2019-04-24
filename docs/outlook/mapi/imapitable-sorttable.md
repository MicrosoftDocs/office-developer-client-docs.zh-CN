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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328852"
---
# <a name="imapitablesorttable"></a><span data-ttu-id="05264-103">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="05264-103">IMAPITable::SortTable</span></span>

<span data-ttu-id="05264-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="05264-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="05264-105">**IMAPITable:: SortTable**方法根据排序条件对表的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="05264-105">The **IMAPITable::SortTable** method orders the rows of the table, depending on sort criteria.</span></span> 
  
```cpp
HRESULT SortTable(
LPSSortOrderSet lpSortCriteria,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="05264-106">参数</span><span class="sxs-lookup"><span data-stu-id="05264-106">Parameters</span></span>

<span data-ttu-id="05264-107">_lpSortCriteria_</span><span class="sxs-lookup"><span data-stu-id="05264-107">_lpSortCriteria_</span></span>
  
> <span data-ttu-id="05264-108">实时指向包含要应用的排序条件的[SSortOrderSet](ssortorderset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="05264-108">[in] Pointer to an [SSortOrderSet](ssortorderset.md) structure that contains the sort criteria to apply.</span></span> <span data-ttu-id="05264-109">传递包含零列的**SSortOrderSet**结构表示不必按任何特定的顺序对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="05264-109">Passing an **SSortOrderSet** structure that contains zero columns indicates that the table does not have to be sorted in any particular order.</span></span> 
    
<span data-ttu-id="05264-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="05264-110">_ulFlags_</span></span>
  
> <span data-ttu-id="05264-111">实时控制**IMAPITable:: SortTable**操作的计时的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="05264-111">[in] Bitmask of flags that controls the timing of the **IMAPITable::SortTable** operation.</span></span> <span data-ttu-id="05264-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="05264-112">The following flags can be set:</span></span> 
    
<span data-ttu-id="05264-113">TBL_ASYNC</span><span class="sxs-lookup"><span data-stu-id="05264-113">TBL_ASYNC</span></span> 
  
> <span data-ttu-id="05264-114">异步启动操作并在操作完成前返回。</span><span class="sxs-lookup"><span data-stu-id="05264-114">Starts the operation asynchronously and returns before the operation is complete.</span></span>
    
<span data-ttu-id="05264-115">TBL_BATCH</span><span class="sxs-lookup"><span data-stu-id="05264-115">TBL_BATCH</span></span> 
  
> <span data-ttu-id="05264-116">将完成排序, 直到表中的数据是必需的。</span><span class="sxs-lookup"><span data-stu-id="05264-116">Defers the completion of the sort until the data in the table is required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="05264-117">返回值</span><span class="sxs-lookup"><span data-stu-id="05264-117">Return value</span></span>

<span data-ttu-id="05264-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="05264-118">S_OK</span></span> 
  
> <span data-ttu-id="05264-119">排序操作成功完成。</span><span class="sxs-lookup"><span data-stu-id="05264-119">The sort operation was successful.</span></span>
    
<span data-ttu-id="05264-120">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="05264-120">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="05264-121">正在进行另一个操作, 阻止排序操作启动。</span><span class="sxs-lookup"><span data-stu-id="05264-121">Another operation is in progress that prevents the sort operation from starting.</span></span> <span data-ttu-id="05264-122">应允许正在进行的操作完成, 或者应已停止。</span><span class="sxs-lookup"><span data-stu-id="05264-122">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="05264-123">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="05264-123">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="05264-124">该表不支持请求的排序类型。</span><span class="sxs-lookup"><span data-stu-id="05264-124">The table does not support the type of sorting requested.</span></span>
    
<span data-ttu-id="05264-125">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="05264-125">MAPI_E_TOO_COMPLEX</span></span> 
  
> <span data-ttu-id="05264-126">由于_lpSortCriteria_参数指向的特定排序条件过于复杂, 因此表无法执行该操作。</span><span class="sxs-lookup"><span data-stu-id="05264-126">The table cannot perform the operation because the particular sort criteria pointed to by the  _lpSortCriteria_ parameter is too complex.</span></span> <span data-ttu-id="05264-127">在下列情况下, **SortTable**可以返回 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="05264-127">**SortTable** can return MAPI_E_TOO_COMPLEX under the following conditions.</span></span> 
    
   - <span data-ttu-id="05264-128">对实现无法排序的属性列请求排序操作。</span><span class="sxs-lookup"><span data-stu-id="05264-128">A sort operation is requested for a property column that the implementation cannot sort.</span></span>
    
   - <span data-ttu-id="05264-129">该实现不支持在**SSortOrderSet**结构的**ulOrder**成员中请求的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="05264-129">The implementation does not support the sort order requested in the **ulOrder** member of the **SSortOrderSet** structure.</span></span> 
    
   - <span data-ttu-id="05264-130">要排序的列数 (在**SSortOrderSet**中的**cSorts**成员中指定) 大于实现可以处理的数量。</span><span class="sxs-lookup"><span data-stu-id="05264-130">The number of columns to be sorted, as specified in the **cSorts** member in **SSortOrderSet**, is larger than the implementation can handle.</span></span>
    
   - <span data-ttu-id="05264-131">根据**SSortOrderSet**中的属性标记来请求排序操作, 该操作基于不在可用或活动集内的属性, 且实现不支持对不可用的集合中的属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="05264-131">A sort operation is requested, as indicated by a property tag in **SSortOrderSet**, based on a property that is not in the available or active set and the implementation does not support sorting on properties not in the available set.</span></span>
    
   - <span data-ttu-id="05264-132">一个属性按排序顺序集多次指定 (由同一属性标记的多个实例指示), 并且实现无法执行此类排序操作。</span><span class="sxs-lookup"><span data-stu-id="05264-132">One property is specified multiple times in a sort order set, as indicated by multiple instances of the same property tag, and the implementation cannot perform such a sort operation.</span></span>
    
   - <span data-ttu-id="05264-133">基于多值属性列的排序操作是使用 MVI_FLAG 请求的, 而实现不支持对多值属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="05264-133">A sort operation based on multivalued property columns is requested using MVI_FLAG and the implementation does not support sorting on multivalued properties.</span></span> 
    
   - <span data-ttu-id="05264-134">**SSortOrderSet**中的属性的属性标记指定实现不支持的属性或类型。</span><span class="sxs-lookup"><span data-stu-id="05264-134">A property tag for a property in **SSortOrderSet** specifies a property or type that the implementation does not support.</span></span> 
    
   - <span data-ttu-id="05264-135">除从**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性前进到表的过程之外的排序操作仅为支持此类型排序的附件表指定。</span><span class="sxs-lookup"><span data-stu-id="05264-135">A sort operation other than one that proceeds through the table from the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property forward is specified only for an attachment table that supports this type of sorting.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="05264-136">注解</span><span class="sxs-lookup"><span data-stu-id="05264-136">Remarks</span></span>

<span data-ttu-id="05264-137">**IMAPITable:: SortTable**方法对表格视图中的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="05264-137">The **IMAPITable::SortTable** method orders the rows in a table view.</span></span> <span data-ttu-id="05264-138">有些表支持对各种排序键列进行标准和分类排序, 而其他表在支持方面更受限制。</span><span class="sxs-lookup"><span data-stu-id="05264-138">Whereas some tables support both standard and categorized sorting on various sort key columns, other tables are more limited in their support.</span></span> <span data-ttu-id="05264-139">通讯簿提供程序通常不支持表排序。</span><span class="sxs-lookup"><span data-stu-id="05264-139">Address book providers ordinarily do not support table sorting.</span></span> <span data-ttu-id="05264-140">邮件存储提供程序通常支持对其保存在完整的表 (不受限制的表) 进行排序时结果的排序顺序的范围进行排序。</span><span class="sxs-lookup"><span data-stu-id="05264-140">Message store providers usually support sorting to the extent that they keep the sort order of folders that results when a full table (a table without restrictions) is sorted.</span></span> 
  
<span data-ttu-id="05264-141">某些表格允许对任何表格列进行排序。</span><span class="sxs-lookup"><span data-stu-id="05264-141">Some tables allow sorting to be done on any table column.</span></span> <span data-ttu-id="05264-142">其他表不执行;未包含在表视图中的列不受**SortTable**调用的影响。</span><span class="sxs-lookup"><span data-stu-id="05264-142">Other tables do not; columns not included in the table view are unaffected by a **SortTable** call.</span></span> <span data-ttu-id="05264-143">某些表要求仅使用表的当前列集中的列生成排序键。</span><span class="sxs-lookup"><span data-stu-id="05264-143">Some tables require that sort keys be built only with columns in the table's current column set.</span></span> 
  
<span data-ttu-id="05264-144">如果表无法完成排序操作, 则表可以从**SortTable**中返回 MAPI_E_NO_SUPPORT 或 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="05264-144">A table can return either MAPI_E_NO_SUPPORT or MAPI_E_TOO_COMPLEX from **SortTable** when it cannot complete a sort operation.</span></span> <span data-ttu-id="05264-145">此外, 不能保证存储提供程序遵循为层次结构表指定的排序顺序集。</span><span class="sxs-lookup"><span data-stu-id="05264-145">Moreover, store providers are not guaranteed to honor the sort order set specified for hierarchy tables.</span></span> 
  
<span data-ttu-id="05264-146">如果_lpSortCriteria_参数所指向的[SSortOrderSet](ssortorderset.md)结构中的列数为零, 则该表将返回当前列集。</span><span class="sxs-lookup"><span data-stu-id="05264-146">When there are zero columns in the [SSortOrderSet](ssortorderset.md) structure pointed to by the  _lpSortCriteria_ parameter, the table returns the current column set.</span></span> <span data-ttu-id="05264-147">可以通过调用表的[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)方法来检索当前排序顺序。</span><span class="sxs-lookup"><span data-stu-id="05264-147">The current sort order can be retrieved by calling the table's [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
<span data-ttu-id="05264-148">表的所有书签都会失效, 应在调用**SortTable**时删除该书签, 并将指示当前光标位置的 BOOKMARK_CURRENT 书签设置为表的开头。</span><span class="sxs-lookup"><span data-stu-id="05264-148">All bookmarks for a table are invalidated and should be deleted when a call to **SortTable** is made, and the BOOKMARK_CURRENT bookmark that indicates the current cursor position, should be set to the beginning of the table.</span></span> 
  
<span data-ttu-id="05264-149">如果要对包含多值属性的列进行排序, 而不设置 MVI_FLAG 标志, 则该列的值将被视为完全排序的元组。</span><span class="sxs-lookup"><span data-stu-id="05264-149">If you are sorting on a column that contains a multivalued property without the MVI_FLAG flag set, the column's values are treated as a completely ordered tuple.</span></span> <span data-ttu-id="05264-150">两个多值列的比较将按顺序对列元素进行比较, 在第一个不相等处报告列的关系, 并在进行比较的列包含相同顺序的相同值时, 仅返回相等性。</span><span class="sxs-lookup"><span data-stu-id="05264-150">A comparison of two multivalued columns compares the column elements in order, reporting the relation of the columns at the first inequality, and returns equality only if the columns being compared contain the same values in the same order.</span></span> <span data-ttu-id="05264-151">如果某一列的值少于其他列的值, 则报告的关系为将 null 值的其他值。</span><span class="sxs-lookup"><span data-stu-id="05264-151">If one column has fewer values than the other, the reported relation is that of a null value to the other value.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="05264-152">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="05264-152">Notes to callers</span></span>

<span data-ttu-id="05264-153">**SortTable**将同步运行, 除非您设置其中一个标志。</span><span class="sxs-lookup"><span data-stu-id="05264-153">**SortTable** operates synchronously unless you set one of the flags.</span></span> <span data-ttu-id="05264-154">如果设置了 TBL_BATCH 标志, 则**SortTable**将推迟排序操作, 除非您请求数据。</span><span class="sxs-lookup"><span data-stu-id="05264-154">If you set the TBL_BATCH flag, **SortTable** postpones the sort operation unless you request the data.</span></span> <span data-ttu-id="05264-155">如果设置了 TBL_ASYNC 标志, 则**SortTable**以异步方式运行, 在操作完成之前可能会返回。</span><span class="sxs-lookup"><span data-stu-id="05264-155">If the TBL_ASYNC flag is set, **SortTable** operates asynchronously, potentially returning before the completion of the operation.</span></span> 
  
<span data-ttu-id="05264-156">如果必须立即执行排序, 请调用[IMAPITable:: Abort](imapitable-abort.md)方法以停止正在进行的异步操作。</span><span class="sxs-lookup"><span data-stu-id="05264-156">Call the [IMAPITable::Abort](imapitable-abort.md) method to stop an asynchronous operation in progress if your sort must be done immediately.</span></span> <span data-ttu-id="05264-157">如果**SortTable**无法继续, 因为对表进行了一个或多个异步操作, 则它将返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="05264-157">If **SortTable** cannot continue because one or more asynchronous operations on the table are in progress, it returns MAPI_E_BUSY.</span></span> 
  
<span data-ttu-id="05264-158">为了获得最佳性能, 请调用**SetColumns**以自定义表的列\*\*\*\* 集, 并在调用**SortTable**以执行排序之前限制表中的行数。</span><span class="sxs-lookup"><span data-stu-id="05264-158">For best performance, call **SetColumns** to customize the table's column set and **Restrict** to limit the number of rows in the table before you call **SortTable** to perform the sort.</span></span> 
  
<span data-ttu-id="05264-159">只要**SortTable**发生故障, 在故障之前生效的排序顺序仍有效。</span><span class="sxs-lookup"><span data-stu-id="05264-159">Whenever **SortTable** fails, the sort order that was in effect before the failure is still in effect.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="05264-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05264-160">See also</span></span>

- [<span data-ttu-id="05264-161">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="05264-161">IMAPITable::Abort</span></span>](imapitable-abort.md)
- [<span data-ttu-id="05264-162">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="05264-162">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
- [<span data-ttu-id="05264-163">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="05264-163">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
- [<span data-ttu-id="05264-164">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="05264-164">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
- [<span data-ttu-id="05264-165">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="05264-165">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
- [<span data-ttu-id="05264-166">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="05264-166">SSortOrderSet</span></span>](ssortorderset.md)
- [<span data-ttu-id="05264-167">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="05264-167">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

