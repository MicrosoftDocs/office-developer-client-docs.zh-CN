---
title: IMAPITableRestrict
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Restrict
api_type:
- COM
ms.assetid: a5bfc190-b58f-44c3-893c-8727df14ee58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cca6bc12fa6f100885b7bf705d79fa24a2e2f91
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414618"
---
# <a name="imapitablerestrict"></a><span data-ttu-id="9518c-103">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="9518c-103">IMAPITable::Restrict</span></span>

  
  
<span data-ttu-id="9518c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9518c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9518c-105">将筛选器应用于表，从而将行设置为仅与指定条件匹配的行。</span><span class="sxs-lookup"><span data-stu-id="9518c-105">Applies a filter to a table, reducing the row set to only those rows matching the specified criteria.</span></span>
  
```cpp
HRESULT Restrict(
LPSRestriction lpRestriction,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="9518c-106">参数</span><span class="sxs-lookup"><span data-stu-id="9518c-106">Parameters</span></span>

 <span data-ttu-id="9518c-107">_lpRestriction_</span><span class="sxs-lookup"><span data-stu-id="9518c-107">_lpRestriction_</span></span>
  
> <span data-ttu-id="9518c-108">[in]指向定义 [筛选器条件的 SRestriction](srestriction.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="9518c-108">[in] Pointer to an [SRestriction](srestriction.md) structure defining the conditions of the filter.</span></span> <span data-ttu-id="9518c-109">在  _lpRestriction_ 参数中传递 NULL 将删除当前筛选器。</span><span class="sxs-lookup"><span data-stu-id="9518c-109">Passing NULL in the  _lpRestriction_ parameter removes the current filter.</span></span> 
    
 <span data-ttu-id="9518c-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9518c-110">_ulFlags_</span></span>
  
> <span data-ttu-id="9518c-111">[in]控制限制操作计时的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="9518c-111">[in] Bitmask of flags that controls the timing of the restriction operation.</span></span> <span data-ttu-id="9518c-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="9518c-112">The following flags can be set:</span></span>
    
<span data-ttu-id="9518c-113">TBL_ASYNC</span><span class="sxs-lookup"><span data-stu-id="9518c-113">TBL_ASYNC</span></span> 
  
> <span data-ttu-id="9518c-114">异步启动操作，在操作完成之前返回。</span><span class="sxs-lookup"><span data-stu-id="9518c-114">Starts the operation asynchronously and returns before the operation completes.</span></span>
    
<span data-ttu-id="9518c-115">TBL_BATCH</span><span class="sxs-lookup"><span data-stu-id="9518c-115">TBL_BATCH</span></span> 
  
> <span data-ttu-id="9518c-116">延迟对筛选器的评估，直到需要表中的数据。</span><span class="sxs-lookup"><span data-stu-id="9518c-116">Defers evaluation of the filter until the data in the table is required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9518c-117">返回值</span><span class="sxs-lookup"><span data-stu-id="9518c-117">Return value</span></span>

<span data-ttu-id="9518c-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="9518c-118">S_OK</span></span> 
  
> <span data-ttu-id="9518c-119">已成功应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="9518c-119">The filter was successfully applied.</span></span>
    
<span data-ttu-id="9518c-120">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="9518c-120">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="9518c-121">正在进行另一个阻止限制操作启动的操作。</span><span class="sxs-lookup"><span data-stu-id="9518c-121">Another operation is in progress that prevents the restriction operation from starting.</span></span> <span data-ttu-id="9518c-122">应允许完成或停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="9518c-122">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="9518c-123">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="9518c-123">MAPI_E_TOO_COMPLEX</span></span> 
  
> <span data-ttu-id="9518c-124">表无法执行该操作，因为  _lpRestriction_ 参数指向的特定筛选器过于复杂。</span><span class="sxs-lookup"><span data-stu-id="9518c-124">The table cannot perform the operation because the particular filter pointed to by the  _lpRestriction_ parameter is too complicated.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="9518c-125">备注</span><span class="sxs-lookup"><span data-stu-id="9518c-125">Remarks</span></span>

<span data-ttu-id="9518c-126">**IMAPITable：：Restrict** 方法在表上建立限制或筛选器。</span><span class="sxs-lookup"><span data-stu-id="9518c-126">The **IMAPITable::Restrict** method establishes a restriction, or filter, on a table.</span></span> <span data-ttu-id="9518c-127">如果存在以前的限制，则放弃它并应用新的限制。</span><span class="sxs-lookup"><span data-stu-id="9518c-127">If there is a previous restriction, it is discarded and the new one applied.</span></span> <span data-ttu-id="9518c-128">应用限制不会影响表的基础数据;它只需通过将可检索的行限制到包含满足限制的数据的行来更改视图。</span><span class="sxs-lookup"><span data-stu-id="9518c-128">Applying a restriction has no affect on the underlying data of a table; it simply alters the view by limiting the rows that can be retrieved to rows containing data that satisfy the restriction.</span></span> 
  
<span data-ttu-id="9518c-129">存在几种不同类型的限制，每种限制都使用不同的结构进行描述。</span><span class="sxs-lookup"><span data-stu-id="9518c-129">There are several different types of restrictions, each described with a different structure.</span></span> <span data-ttu-id="9518c-130">[SRestriction](srestriction.md)结构包含两个成员：一个指示限制类型和适用于该类型的特定结构的值。</span><span class="sxs-lookup"><span data-stu-id="9518c-130">The [SRestriction](srestriction.md) structure contains two members: a value that indicates the type of restriction and the specific structure applicable for that type.</span></span> 
  
<span data-ttu-id="9518c-131">从不生成通过调用 Restrict 从视图中隐藏的 **表** 行的通知。</span><span class="sxs-lookup"><span data-stu-id="9518c-131">Notifications for table rows that are hidden from view by calls to **Restrict** are never generated.</span></span> 
  
<span data-ttu-id="9518c-132">多值属性的属性限制的工作方式与单值属性的限制类似。</span><span class="sxs-lookup"><span data-stu-id="9518c-132">A property restriction on a multivalued property works like a restriction on a single-valued property.</span></span> <span data-ttu-id="9518c-133">要用于属性限制的多值属性必须设置MVI_FLAG标记。</span><span class="sxs-lookup"><span data-stu-id="9518c-133">A multivalued property to be used in a property restriction must have the MVI_FLAG flag set.</span></span> <span data-ttu-id="9518c-134">如果未设置此标志，则被视为完全排序的元组。</span><span class="sxs-lookup"><span data-stu-id="9518c-134">If it doesn't have this flag set, it is treated as a totally ordered tuple.</span></span> <span data-ttu-id="9518c-135">两个多值列的比较按顺序比较列元素，报告第一个不相等的列的关系。</span><span class="sxs-lookup"><span data-stu-id="9518c-135">A comparison of two multivalued columns compares the column elements in order, reporting the relation of the columns at the first inequality.</span></span> <span data-ttu-id="9518c-136">只有当比较的列包含相同顺序的相同值时，才返回等同性。</span><span class="sxs-lookup"><span data-stu-id="9518c-136">Equality is returned only if the columns compared contain the same values in the same order.</span></span> <span data-ttu-id="9518c-137">如果一列的值数少于另一列的值，则报告的关系为空值与另一个值的关系。</span><span class="sxs-lookup"><span data-stu-id="9518c-137">If one column has fewer values than the other, the reported relation is that of a null value to the other value.</span></span>
  
<span data-ttu-id="9518c-138">有关限制的信息，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="9518c-138">For more information about restrictions, see [About Restrictions](about-restrictions.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9518c-139">如果创建动态查询以搜索服务器上数据，请使用 **FindRow** 方法，而不是同时使用 **Restrict** 方法和 **QueryRows** 方法。</span><span class="sxs-lookup"><span data-stu-id="9518c-139">If you create dynamic queries to search for data on the server, use the **FindRow** method instead of using the **Restrict** method and the **QueryRows** method together.</span></span> <span data-ttu-id="9518c-140">**Restrict** 方法创建一个缓存视图，该视图用于评估添加到基文件夹中或修改的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="9518c-140">The **Restrict** method creates a cached view that is used to evaluate all messages added to or modified in the base folder.</span></span> <span data-ttu-id="9518c-141">如果客户端应用程序针对每个动态查询使用 **Restrict** 方法，将针对每个查询创建缓存视图。</span><span class="sxs-lookup"><span data-stu-id="9518c-141">If a client application uses the **Restrict** method for each dynamic query, a cached view will be created for each query.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9518c-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9518c-142">Notes to callers</span></span>

<span data-ttu-id="9518c-143">若要放弃当前限制而不创建新的限制，请传递  _lpRestriction 中的_ NULL。</span><span class="sxs-lookup"><span data-stu-id="9518c-143">To discard the current restriction without creating a new one, pass NULL in  _lpRestriction_.</span></span>
  
<span data-ttu-id="9518c-144">如果正在进行另一个异步表调用，从而导致 **Restrict** 返回MAPI_E_BUSY，您可以调用 [IMAPITable：：Abort](imapitable-abort.md) 以停止调用。</span><span class="sxs-lookup"><span data-stu-id="9518c-144">If another asynchronous table call is in progress, causing **Restrict** to return MAPI_E_BUSY, you can call [IMAPITable::Abort](imapitable-abort.md) to stop the call.</span></span> 
  
 <span data-ttu-id="9518c-145">**除非** 设置了其中一个标志，否则 Restrict 将同步运行。</span><span class="sxs-lookup"><span data-stu-id="9518c-145">**Restrict** operates synchronously unless you set one of the flags.</span></span> <span data-ttu-id="9518c-146">如果设置 TBL_BATCH 标志，除非请求数据， **否则 Restrict** 将推迟计算限制。</span><span class="sxs-lookup"><span data-stu-id="9518c-146">If you set the TBL_BATCH flag, **Restrict** postpones the evaluation of the restriction unless you request the data.</span></span> <span data-ttu-id="9518c-147">如果TBL_ASYNC， **则 Restrict** 将异步运行，在操作完成之前可能会返回。</span><span class="sxs-lookup"><span data-stu-id="9518c-147">If the TBL_ASYNC flag is set, **Restrict** operates asynchronously, potentially returning before the completion of the operation.</span></span>
  
<span data-ttu-id="9518c-148">当调用 **Restrict** 时，将放弃表的所有书签，BOOKMARK_CURRENT当前光标位置设置为表的开头。</span><span class="sxs-lookup"><span data-stu-id="9518c-148">All bookmarks for a table are discarded when a call to **Restrict** is made, and BOOKMARK_CURRENT, the current cursor position, is set to the beginning of the table.</span></span> 
  
<span data-ttu-id="9518c-149">如果您尝试对不在表的列集内的属性施加属性限制，则结果未定义。</span><span class="sxs-lookup"><span data-stu-id="9518c-149">If you attempt to impose a property restriction on a property that is not in the table's column set, the results are undefined.</span></span> <span data-ttu-id="9518c-150">只要不确定某个属性在表中是否受支持，就会将属性限制与存在的限制组合在一起。</span><span class="sxs-lookup"><span data-stu-id="9518c-150">Whenever you are unsure as to whether a property is supported in a table, combine the property restriction with an exists restriction.</span></span> <span data-ttu-id="9518c-151">在试图施加属性限制之前，存在限制会检查属性是否存在。</span><span class="sxs-lookup"><span data-stu-id="9518c-151">The exists restriction checks for the existence of the property before attempting to impose the property restriction.</span></span> 
  
<span data-ttu-id="9518c-152">不要因为限制而收到从表中筛选的行上的表通知。</span><span class="sxs-lookup"><span data-stu-id="9518c-152">Do not expect to receive a table notification on a row that has been filtered from a table due to a restriction.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9518c-153">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="9518c-153">MFCMAPI reference</span></span>

<span data-ttu-id="9518c-154">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9518c-154">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9518c-155">**文件**</span><span class="sxs-lookup"><span data-stu-id="9518c-155">**File**</span></span>|<span data-ttu-id="9518c-156">**函数**</span><span class="sxs-lookup"><span data-stu-id="9518c-156">**Function**</span></span>|<span data-ttu-id="9518c-157">**备注**</span><span class="sxs-lookup"><span data-stu-id="9518c-157">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9518c-158">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="9518c-158">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="9518c-159">CContentsTableListCtrl：：ApplyRestriction</span><span class="sxs-lookup"><span data-stu-id="9518c-159">CContentsTableListCtrl::ApplyRestriction</span></span>  <br/> |<span data-ttu-id="9518c-160">MFCMAPI 使用 **IMAPITable：：Restrict** 方法对表设置限制。</span><span class="sxs-lookup"><span data-stu-id="9518c-160">MFCMAPI uses the **IMAPITable::Restrict** method to set a restriction on a table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9518c-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9518c-161">See also</span></span>



[<span data-ttu-id="9518c-162">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="9518c-162">IMAPITable::Abort</span></span>](imapitable-abort.md)
  
[<span data-ttu-id="9518c-163">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="9518c-163">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
  
[<span data-ttu-id="9518c-164">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="9518c-164">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
  
[<span data-ttu-id="9518c-165">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="9518c-165">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="9518c-166">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="9518c-166">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="9518c-167">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9518c-167">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="9518c-168">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9518c-168">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

