---
title: IMAPITableSetCollapseState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SetCollapseState
api_type:
- COM
ms.assetid: 31325e8f-1cf9-49b2-8118-953996b0037f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7351457dc5b72cfc4a7ef9f91e9d33a80ca98c39
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328831"
---
# <a name="imapitablesetcollapsestate"></a><span data-ttu-id="d79fd-103">IMAPITable::SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="d79fd-103">IMAPITable::SetCollapseState</span></span>

  
  
<span data-ttu-id="d79fd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d79fd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d79fd-105">使用以前对[IMAPITable:: GetCollapseState](imapitable-getcollapsestate.md)方法所保存的数据, 重新生成已分类表的当前展开或折叠状态。</span><span class="sxs-lookup"><span data-stu-id="d79fd-105">Rebuilds the current expanded or collapsed state of a categorized table using data that was saved by a prior call to the [IMAPITable::GetCollapseState](imapitable-getcollapsestate.md) method.</span></span> 
  
```cpp
HRESULT SetCollapseState(
ULONG ulFlags,
ULONG cbCollapseState,
LPBYTE pbCollapseState,
BOOKMARK FAR * lpbkLocation
);
```

## <a name="parameters"></a><span data-ttu-id="d79fd-106">参数</span><span class="sxs-lookup"><span data-stu-id="d79fd-106">Parameters</span></span>

 <span data-ttu-id="d79fd-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d79fd-107">_ulFlags_</span></span>
  
> <span data-ttu-id="d79fd-108">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="d79fd-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="d79fd-109">_cbCollapseState_</span><span class="sxs-lookup"><span data-stu-id="d79fd-109">_cbCollapseState_</span></span>
  
> <span data-ttu-id="d79fd-110">实时由_pbCollapseState_参数指向的结构中的字节数。</span><span class="sxs-lookup"><span data-stu-id="d79fd-110">[in] Count of bytes in the structure pointed to by the  _pbCollapseState_ parameter.</span></span> 
    
 <span data-ttu-id="d79fd-111">_pbCollapseState_</span><span class="sxs-lookup"><span data-stu-id="d79fd-111">_pbCollapseState_</span></span>
  
> <span data-ttu-id="d79fd-112">实时指向结构的指针, 这些结构包含重建表视图所需的数据。</span><span class="sxs-lookup"><span data-stu-id="d79fd-112">[in] Pointer to the structures containing the data needed to rebuild the table view.</span></span>
    
 <span data-ttu-id="d79fd-113">_lpbkLocation_</span><span class="sxs-lookup"><span data-stu-id="d79fd-113">_lpbkLocation_</span></span>
  
> <span data-ttu-id="d79fd-114">排除指向一个书签的指针, 该书签标识应在表中重新生成折叠或展开状态的行。</span><span class="sxs-lookup"><span data-stu-id="d79fd-114">[out] Pointer to a bookmark identifying the row in the table at which the collapsed or expanded state should be rebuilt.</span></span> <span data-ttu-id="d79fd-115">在对[IMAPITable:: GetCollapseState](imapitable-getcollapsestate.md)的调用中, 此书签和在_lpbInstanceKey_参数中传递的实例键可标识同一行。</span><span class="sxs-lookup"><span data-stu-id="d79fd-115">This bookmark and the instance key passed in the  _lpbInstanceKey_ parameter in the call to [IMAPITable::GetCollapseState](imapitable-getcollapsestate.md) identify the same row.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d79fd-116">返回值</span><span class="sxs-lookup"><span data-stu-id="d79fd-116">Return value</span></span>

<span data-ttu-id="d79fd-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="d79fd-117">S_OK</span></span> 
  
> <span data-ttu-id="d79fd-118">已成功重建已分类表的状态。</span><span class="sxs-lookup"><span data-stu-id="d79fd-118">The state of the categorized table was successfully rebuilt.</span></span>
    
<span data-ttu-id="d79fd-119">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="d79fd-119">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="d79fd-120">正在进行另一个操作, 以阻止操作启动。</span><span class="sxs-lookup"><span data-stu-id="d79fd-120">Another operation is in progress that prevents the operation from starting.</span></span> <span data-ttu-id="d79fd-121">应允许正在进行的操作完成, 或者应已停止。</span><span class="sxs-lookup"><span data-stu-id="d79fd-121">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="d79fd-122">MAPI_E_UNABLE_TO_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="d79fd-122">MAPI_E_UNABLE_TO_COMPLETE</span></span> 
  
> <span data-ttu-id="d79fd-123">表无法完成已折叠或展开的视图的重建。</span><span class="sxs-lookup"><span data-stu-id="d79fd-123">The table could not finish rebuilding the collapsed or expanded view.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d79fd-124">注解</span><span class="sxs-lookup"><span data-stu-id="d79fd-124">Remarks</span></span>

<span data-ttu-id="d79fd-125">**IMAPITable:: SetCollapseState**方法将重新建立表格视图的展开或折叠状态。</span><span class="sxs-lookup"><span data-stu-id="d79fd-125">The **IMAPITable::SetCollapseState** method reestablishes the expanded or collapsed state of the table view.</span></span> <span data-ttu-id="d79fd-126">**SetCollapseState**和**GetCollapseState**协同工作, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d79fd-126">**SetCollapseState** and **GetCollapseState** work together as follows:</span></span> 
  
1. <span data-ttu-id="d79fd-127">当分类表的状态即将发生更改时, 将调用[IMAPITable:: GetCollapseState](imapitable-getcollapsestate.md) , 以保存与更改前的状态相关的所有数据。</span><span class="sxs-lookup"><span data-stu-id="d79fd-127">When the state of a categorized table is about to change, [IMAPITable::GetCollapseState](imapitable-getcollapsestate.md) is called to save all of the data pertaining to the state prior to the change.</span></span> 
    
2. <span data-ttu-id="d79fd-128">若要将表的视图还原到其保存状态, 请调用**SetCollapseState** 。</span><span class="sxs-lookup"><span data-stu-id="d79fd-128">To restore the view of the table to its saved state, **SetCollapseState** is called.</span></span> <span data-ttu-id="d79fd-129">由**GetCollapseState**保存的数据被传递给**SetCollapseState**。</span><span class="sxs-lookup"><span data-stu-id="d79fd-129">The data saved by **GetCollapseState** is passed to **SetCollapseState**.</span></span> <span data-ttu-id="d79fd-130">**SetCollapseState**可以使用该数据还原状态。</span><span class="sxs-lookup"><span data-stu-id="d79fd-130">**SetCollapseState** is able to use that data to restore the state.</span></span> 
    
3. <span data-ttu-id="d79fd-131">**SetCollapseState**作为输出参数返回一个书签, 该书签将一个标识为作为输入传递给**GetCollapseState**的实例键的同一行。</span><span class="sxs-lookup"><span data-stu-id="d79fd-131">**SetCollapseState** returns as an output parameter a bookmark that identifies the same row as the instance key passed as input to **GetCollapseState**.</span></span>
    
<span data-ttu-id="d79fd-132">有关分类表的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="d79fd-132">For more information about categorized tables, see [Sorting and Categorization](sorting-and-categorization.md).</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="d79fd-133">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="d79fd-133">Notes to implementers</span></span>

<span data-ttu-id="d79fd-134">您负责验证排序顺序和限制是否与在**GetCollapseState**调用时完全相同的。</span><span class="sxs-lookup"><span data-stu-id="d79fd-134">You are responsible for verifying that the sort order and restrictions are exactly the same as they were at the time of the **GetCollapseState** call.</span></span> <span data-ttu-id="d79fd-135">如果进行了更改, 则不应调用**SetCollapseState** , 因为结果可能是不可预知的。</span><span class="sxs-lookup"><span data-stu-id="d79fd-135">If a change has been made, **SetCollapseState** should not be called because the results can be unpredictable.</span></span> <span data-ttu-id="d79fd-136">例如, 在调用**SetCollapseState**之前, 客户端调用**GetCollapseState** , 然后**SortTable**更改排序关键字时, 可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d79fd-136">This can happen if, for example, a client calls **GetCollapseState** and then **SortTable** to change the sort key before calling **SetCollapseState**.</span></span> <span data-ttu-id="d79fd-137">为安全起见, 请先检查保存的数据是否仍然有效, 然后再继续进行还原。</span><span class="sxs-lookup"><span data-stu-id="d79fd-137">To be safe, check that the saved data is still valid before proceeding with the restoration.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d79fd-138">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d79fd-138">Notes to callers</span></span>

<span data-ttu-id="d79fd-139">若要调用**SetCollapseState**, 必须先调用**GetCollapseState**。</span><span class="sxs-lookup"><span data-stu-id="d79fd-139">To call **SetCollapseState**, you must have previously called **GetCollapseState**.</span></span> <span data-ttu-id="d79fd-140">对于这两种方法, 建立类别的排序顺序应相同。</span><span class="sxs-lookup"><span data-stu-id="d79fd-140">The sort order establishing the categories should be the same for both methods.</span></span> <span data-ttu-id="d79fd-141">如果排序顺序不同, 则**SetCollapseState**操作的结果是不可预知的。</span><span class="sxs-lookup"><span data-stu-id="d79fd-141">If the sort orders differ, the results of the **SetCollapseState** operation are unpredictable.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d79fd-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d79fd-142">See also</span></span>



[<span data-ttu-id="d79fd-143">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="d79fd-143">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="d79fd-144">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="d79fd-144">IMAPITable::FreeBookmark</span></span>](imapitable-freebookmark.md)
  
[<span data-ttu-id="d79fd-145">IMAPITable::GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="d79fd-145">IMAPITable::GetCollapseState</span></span>](imapitable-getcollapsestate.md)
  
[<span data-ttu-id="d79fd-146">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d79fd-146">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

