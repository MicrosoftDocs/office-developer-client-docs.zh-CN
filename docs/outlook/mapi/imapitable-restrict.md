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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328845"
---
# <a name="imapitablerestrict"></a><span data-ttu-id="ff8a7-103">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="ff8a7-103">IMAPITable::Restrict</span></span>

  
  
<span data-ttu-id="ff8a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff8a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff8a7-105">将筛选器应用于表, 将行设置为仅将行设置为与指定条件匹配的行。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-105">Applies a filter to a table, reducing the row set to only those rows matching the specified criteria.</span></span>
  
```cpp
HRESULT Restrict(
LPSRestriction lpRestriction,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="ff8a7-106">参数</span><span class="sxs-lookup"><span data-stu-id="ff8a7-106">Parameters</span></span>

 <span data-ttu-id="ff8a7-107">_lpRestriction_</span><span class="sxs-lookup"><span data-stu-id="ff8a7-107">_lpRestriction_</span></span>
  
> <span data-ttu-id="ff8a7-108">实时指向定义筛选条件的[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-108">[in] Pointer to an [SRestriction](srestriction.md) structure defining the conditions of the filter.</span></span> <span data-ttu-id="ff8a7-109">在_lpRestriction_参数中传递 NULL 将删除当前的筛选器。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-109">Passing NULL in the  _lpRestriction_ parameter removes the current filter.</span></span> 
    
 <span data-ttu-id="ff8a7-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ff8a7-110">_ulFlags_</span></span>
  
> <span data-ttu-id="ff8a7-111">实时控制限制操作的时间的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-111">[in] Bitmask of flags that controls the timing of the restriction operation.</span></span> <span data-ttu-id="ff8a7-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ff8a7-112">The following flags can be set:</span></span>
    
<span data-ttu-id="ff8a7-113">TBL_ASYNC</span><span class="sxs-lookup"><span data-stu-id="ff8a7-113">TBL_ASYNC</span></span> 
  
> <span data-ttu-id="ff8a7-114">异步启动操作并在操作完成前返回。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-114">Starts the operation asynchronously and returns before the operation completes.</span></span>
    
<span data-ttu-id="ff8a7-115">TBL_BATCH</span><span class="sxs-lookup"><span data-stu-id="ff8a7-115">TBL_BATCH</span></span> 
  
> <span data-ttu-id="ff8a7-116">推迟对筛选器的求值, 直到表中的数据是必需的。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-116">Defers evaluation of the filter until the data in the table is required.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ff8a7-117">返回值</span><span class="sxs-lookup"><span data-stu-id="ff8a7-117">Return value</span></span>

<span data-ttu-id="ff8a7-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff8a7-118">S_OK</span></span> 
  
> <span data-ttu-id="ff8a7-119">已成功应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-119">The filter was successfully applied.</span></span>
    
<span data-ttu-id="ff8a7-120">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="ff8a7-120">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="ff8a7-121">正在进行另一个操作, 以阻止启动限制操作。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-121">Another operation is in progress that prevents the restriction operation from starting.</span></span> <span data-ttu-id="ff8a7-122">应允许正在进行的操作完成, 或者应已停止。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-122">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="ff8a7-123">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="ff8a7-123">MAPI_E_TOO_COMPLEX</span></span> 
  
> <span data-ttu-id="ff8a7-124">表无法执行此操作, 因为_lpRestriction_参数指向的特定筛选器过于复杂。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-124">The table cannot perform the operation because the particular filter pointed to by the  _lpRestriction_ parameter is too complicated.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ff8a7-125">注解</span><span class="sxs-lookup"><span data-stu-id="ff8a7-125">Remarks</span></span>

<span data-ttu-id="ff8a7-126">**IMAPITable:: Restrict**方法在表上建立限制或筛选器。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-126">The **IMAPITable::Restrict** method establishes a restriction, or filter, on a table.</span></span> <span data-ttu-id="ff8a7-127">如果存在以前的限制, 将丢弃它并应用新的限制。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-127">If there is a previous restriction, it is discarded and the new one applied.</span></span> <span data-ttu-id="ff8a7-128">应用限制对表的基础数据没有影响。它只是通过限制可检索到包含满足限制的数据的行的行来更改视图。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-128">Applying a restriction has no affect on the underlying data of a table; it simply alters the view by limiting the rows that can be retrieved to rows containing data that satisfy the restriction.</span></span> 
  
<span data-ttu-id="ff8a7-129">有几种不同类型的限制, 每种类型都有不同的结构说明。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-129">There are several different types of restrictions, each described with a different structure.</span></span> <span data-ttu-id="ff8a7-130">[SRestriction](srestriction.md)结构包含两个成员: 一个值, 该值指示限制的类型以及适用于该类型的特定结构。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-130">The [SRestriction](srestriction.md) structure contains two members: a value that indicates the type of restriction and the specific structure applicable for that type.</span></span> 
  
<span data-ttu-id="ff8a7-131">从不生成通过对**Restrict**的调用而隐藏的表行的通知。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-131">Notifications for table rows that are hidden from view by calls to **Restrict** are never generated.</span></span> 
  
<span data-ttu-id="ff8a7-132">对多值属性的属性限制的工作方式类似于对单值属性的限制。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-132">A property restriction on a multivalued property works like a restriction on a single-valued property.</span></span> <span data-ttu-id="ff8a7-133">要在属性限制中使用的多值属性必须设置 MVI_FLAG 标志。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-133">A multivalued property to be used in a property restriction must have the MVI_FLAG flag set.</span></span> <span data-ttu-id="ff8a7-134">如果未设置此标志, 则会将其视为一个完全排序的元组。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-134">If it doesn't have this flag set, it is treated as a totally ordered tuple.</span></span> <span data-ttu-id="ff8a7-135">两个多值列的比较将按顺序对列元素进行比较, 报告第一个不相等的列关系。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-135">A comparison of two multivalued columns compares the column elements in order, reporting the relation of the columns at the first inequality.</span></span> <span data-ttu-id="ff8a7-136">仅当列的比较包含相同顺序的相同值时, 才返回相等性。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-136">Equality is returned only if the columns compared contain the same values in the same order.</span></span> <span data-ttu-id="ff8a7-137">如果某一列的值少于其他列的值, 则报告的关系为将 null 值的其他值。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-137">If one column has fewer values than the other, the reported relation is that of a null value to the other value.</span></span>
  
<span data-ttu-id="ff8a7-138">有关限制的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-138">For more information about restrictions, see [About Restrictions](about-restrictions.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff8a7-139">如果创建动态查询以在服务器上搜索数据, 请使用**FindRow**方法, 而不是将**Restrict**方法和**QueryRows**方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-139">If you create dynamic queries to search for data on the server, use the **FindRow** method instead of using the **Restrict** method and the **QueryRows** method together.</span></span> <span data-ttu-id="ff8a7-140">**Restrict**方法创建一个缓存视图, 用于评估在基文件夹中添加或修改的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-140">The **Restrict** method creates a cached view that is used to evaluate all messages added to or modified in the base folder.</span></span> <span data-ttu-id="ff8a7-141">如果客户端应用程序对每个动态查询使用**Restrict**方法, 则将为每个查询创建一个缓存视图。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-141">If a client application uses the **Restrict** method for each dynamic query, a cached view will be created for each query.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="ff8a7-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ff8a7-142">Notes to callers</span></span>

<span data-ttu-id="ff8a7-143">若要在不创建新限制的情况下放弃当前限制, 请在_lpRestriction_中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-143">To discard the current restriction without creating a new one, pass NULL in  _lpRestriction_.</span></span>
  
<span data-ttu-id="ff8a7-144">如果正在进行另一个异步表调用, 从而导致**限制**返回 MAPI_E_BUSY, 则可以调用[IMAPITable:: Abort](imapitable-abort.md)停止呼叫。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-144">If another asynchronous table call is in progress, causing **Restrict** to return MAPI_E_BUSY, you can call [IMAPITable::Abort](imapitable-abort.md) to stop the call.</span></span> 
  
 <span data-ttu-id="ff8a7-145">**限制**同步操作, 除非您设置了其中一个标志。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-145">**Restrict** operates synchronously unless you set one of the flags.</span></span> <span data-ttu-id="ff8a7-146">如果设置了 TBL_BATCH 标志, 则**限制**推迟对限制的评估, 除非您请求数据。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-146">If you set the TBL_BATCH flag, **Restrict** postpones the evaluation of the restriction unless you request the data.</span></span> <span data-ttu-id="ff8a7-147">如果设置了 TBL_ASYNC 标志, 则**限制**在完成操作之前异步操作, 可能会返回。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-147">If the TBL_ASYNC flag is set, **Restrict**operates asynchronously, potentially returning before the completion of the operation.</span></span>
  
<span data-ttu-id="ff8a7-148">表的所有书签都会在进行**限制**调用时被丢弃, 而将 BOOKMARK_CURRENT 的当前光标位置设置为表的开头。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-148">All bookmarks for a table are discarded when a call to **Restrict** is made, and BOOKMARK_CURRENT, the current cursor position, is set to the beginning of the table.</span></span> 
  
<span data-ttu-id="ff8a7-149">如果尝试对不在表的列集中的属性施加属性限制, 则结果是不确定的。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-149">If you attempt to impose a property restriction on a property that is not in the table's column set, the results are undefined.</span></span> <span data-ttu-id="ff8a7-150">只要您不确定某个属性是否在表中受支持, 请将该属性限制与存在的限制组合在一起。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-150">Whenever you are unsure as to whether a property is supported in a table, combine the property restriction with an exists restriction.</span></span> <span data-ttu-id="ff8a7-151">在尝试强制实施属性限制之前, 存在限制会检查是否存在该属性。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-151">The exists restriction checks for the existence of the property before attempting to impose the property restriction.</span></span> 
  
<span data-ttu-id="ff8a7-152">如果由于限制而从表中筛选出的行上不应收到表通知。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-152">Do not expect to receive a table notification on a row that has been filtered from a table due to a restriction.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ff8a7-153">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="ff8a7-153">MFCMAPI reference</span></span>

<span data-ttu-id="ff8a7-154">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-154">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ff8a7-155">**文件**</span><span class="sxs-lookup"><span data-stu-id="ff8a7-155">**File**</span></span>|<span data-ttu-id="ff8a7-156">**函数**</span><span class="sxs-lookup"><span data-stu-id="ff8a7-156">**Function**</span></span>|<span data-ttu-id="ff8a7-157">**备注**</span><span class="sxs-lookup"><span data-stu-id="ff8a7-157">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ff8a7-158">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="ff8a7-158">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="ff8a7-159">CContentsTableListCtrl:: ApplyRestriction</span><span class="sxs-lookup"><span data-stu-id="ff8a7-159">CContentsTableListCtrl::ApplyRestriction</span></span>  <br/> |<span data-ttu-id="ff8a7-160">MFCMAPI 使用**IMAPITable:: Restrict**方法来设置对表的限制。</span><span class="sxs-lookup"><span data-stu-id="ff8a7-160">MFCMAPI uses the **IMAPITable::Restrict** method to set a restriction on a table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ff8a7-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff8a7-161">See also</span></span>



[<span data-ttu-id="ff8a7-162">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="ff8a7-162">IMAPITable::Abort</span></span>](imapitable-abort.md)
  
[<span data-ttu-id="ff8a7-163">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="ff8a7-163">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
  
[<span data-ttu-id="ff8a7-164">IMAPITable::GetRowCount</span><span class="sxs-lookup"><span data-stu-id="ff8a7-164">IMAPITable::GetRowCount</span></span>](imapitable-getrowcount.md)
  
[<span data-ttu-id="ff8a7-165">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="ff8a7-165">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="ff8a7-166">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="ff8a7-166">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="ff8a7-167">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ff8a7-167">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="ff8a7-168">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ff8a7-168">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

