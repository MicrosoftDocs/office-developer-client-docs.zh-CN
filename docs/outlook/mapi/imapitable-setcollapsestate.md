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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 51c239897e5e225a0765f78404526e2836371f30
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567900"
---
# <a name="imapitablesetcollapsestate"></a><span data-ttu-id="7cb4b-103">IMAPITable::SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="7cb4b-103">IMAPITable::SetCollapseState</span></span>

  
  
<span data-ttu-id="7cb4b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7cb4b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7cb4b-105">重建使用以前[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)方法调用已保存的数据分类表的当前展开还是折叠状态。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-105">Rebuilds the current expanded or collapsed state of a categorized table using data that was saved by a prior call to the [IMAPITable::GetCollapseState](imapitable-getcollapsestate.md) method.</span></span> 
  
```cpp
HRESULT SetCollapseState(
ULONG ulFlags,
ULONG cbCollapseState,
LPBYTE pbCollapseState,
BOOKMARK FAR * lpbkLocation
);
```

## <a name="parameters"></a><span data-ttu-id="7cb4b-106">参数</span><span class="sxs-lookup"><span data-stu-id="7cb4b-106">Parameters</span></span>

 <span data-ttu-id="7cb4b-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7cb4b-107">_ulFlags_</span></span>
  
> <span data-ttu-id="7cb4b-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="7cb4b-109">_cbCollapseState_</span><span class="sxs-lookup"><span data-stu-id="7cb4b-109">_cbCollapseState_</span></span>
  
> <span data-ttu-id="7cb4b-110">[in]由_pbCollapseState_参数指向的结构中的字节数。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-110">[in] Count of bytes in the structure pointed to by the  _pbCollapseState_ parameter.</span></span> 
    
 <span data-ttu-id="7cb4b-111">_pbCollapseState_</span><span class="sxs-lookup"><span data-stu-id="7cb4b-111">_pbCollapseState_</span></span>
  
> <span data-ttu-id="7cb4b-112">[in]指针指向包含重建表视图所需的数据的结构。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-112">[in] Pointer to the structures containing the data needed to rebuild the table view.</span></span>
    
 <span data-ttu-id="7cb4b-113">_lpbkLocation_</span><span class="sxs-lookup"><span data-stu-id="7cb4b-113">_lpbkLocation_</span></span>
  
> <span data-ttu-id="7cb4b-114">[输出]确定应频率重建折叠或展开状态表中的行的书签的指针。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-114">[out] Pointer to a bookmark identifying the row in the table at which the collapsed or expanded state should be rebuilt.</span></span> <span data-ttu-id="7cb4b-115">该书签和[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)调用_lpbInstanceKey_参数中传递的实例密钥标识同一行。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-115">This bookmark and the instance key passed in the  _lpbInstanceKey_ parameter in the call to [IMAPITable::GetCollapseState](imapitable-getcollapsestate.md) identify the same row.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7cb4b-116">返回值</span><span class="sxs-lookup"><span data-stu-id="7cb4b-116">Return value</span></span>

<span data-ttu-id="7cb4b-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cb4b-117">S_OK</span></span> 
  
> <span data-ttu-id="7cb4b-118">已成功重建分类的表的状态。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-118">The state of the categorized table was successfully rebuilt.</span></span>
    
<span data-ttu-id="7cb4b-119">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="7cb4b-119">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="7cb4b-120">正在进行中，可以防止启动操作是另一个操作。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-120">Another operation is in progress that prevents the operation from starting.</span></span> <span data-ttu-id="7cb4b-121">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-121">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="7cb4b-122">MAPI_E_UNABLE_TO_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="7cb4b-122">MAPI_E_UNABLE_TO_COMPLETE</span></span> 
  
> <span data-ttu-id="7cb4b-123">表无法完成重建折叠或展开视图。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-123">The table could not finish rebuilding the collapsed or expanded view.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7cb4b-124">注解</span><span class="sxs-lookup"><span data-stu-id="7cb4b-124">Remarks</span></span>

<span data-ttu-id="7cb4b-125">**IMAPITable::SetCollapseState**方法重建表视图展开或折叠状态。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-125">The **IMAPITable::SetCollapseState** method reestablishes the expanded or collapsed state of the table view.</span></span> <span data-ttu-id="7cb4b-126">**SetCollapseState**和**GetCollapseState**协同工作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7cb4b-126">**SetCollapseState** and **GetCollapseState** work together as follows:</span></span> 
  
1. <span data-ttu-id="7cb4b-127">分类表的状态为将要更改，当[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)称为保存所有到更改之前的状态相关的数据。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-127">When the state of a categorized table is about to change, [IMAPITable::GetCollapseState](imapitable-getcollapsestate.md) is called to save all of the data pertaining to the state prior to the change.</span></span> 
    
2. <span data-ttu-id="7cb4b-128">若要向其保存的状态还原表的视图，请调用**SetCollapseState** 。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-128">To restore the view of the table to its saved state, **SetCollapseState** is called.</span></span> <span data-ttu-id="7cb4b-129">由**GetCollapseState**保存数据传递到**SetCollapseState**。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-129">The data saved by **GetCollapseState** is passed to **SetCollapseState**.</span></span> <span data-ttu-id="7cb4b-130">**SetCollapseState**是能够使用该数据还原状态。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-130">**SetCollapseState** is able to use that data to restore the state.</span></span> 
    
3. <span data-ttu-id="7cb4b-131">**SetCollapseState**输出参数的形式返回标识作为输入传递给**GetCollapseState**实例键所在的行的书签。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-131">**SetCollapseState** returns as an output parameter a bookmark that identifies the same row as the instance key passed as input to **GetCollapseState**.</span></span>
    
<span data-ttu-id="7cb4b-132">有关分类表的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-132">For more information about categorized tables, see [Sorting and Categorization](sorting-and-categorization.md).</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="7cb4b-133">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="7cb4b-133">Notes to implementers</span></span>

<span data-ttu-id="7cb4b-134">您负责验证的排序顺序和限制完全相同时**GetCollapseState**呼叫的时间。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-134">You are responsible for verifying that the sort order and restrictions are exactly the same as they were at the time of the **GetCollapseState** call.</span></span> <span data-ttu-id="7cb4b-135">如果已进行更改，应不会由于结果不可预知调用**SetCollapseState** 。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-135">If a change has been made, **SetCollapseState** should not be called because the results can be unpredictable.</span></span> <span data-ttu-id="7cb4b-136">如果，例如，在客户端调用**GetCollapseState** ，然后选择**SortTable**调用**SetCollapseState**之前更改排序关键字，则可以发生此错误。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-136">This can happen if, for example, a client calls **GetCollapseState** and then **SortTable** to change the sort key before calling **SetCollapseState**.</span></span> <span data-ttu-id="7cb4b-137">为安全起见，检查仍然有效，然后再继续完成还原操作保存的数据。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-137">To be safe, check that the saved data is still valid before proceeding with the restoration.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="7cb4b-138">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7cb4b-138">Notes to callers</span></span>

<span data-ttu-id="7cb4b-139">若要调用**SetCollapseState**，您必须以前称为**GetCollapseState**。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-139">To call **SetCollapseState**, you must have previously called **GetCollapseState**.</span></span> <span data-ttu-id="7cb4b-140">建立类别的排序次序应为这两种方法相同。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-140">The sort order establishing the categories should be the same for both methods.</span></span> <span data-ttu-id="7cb4b-141">如果排序次序不同， **SetCollapseState**操作的结果将无法预料。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-141">If the sort orders differ, the results of the **SetCollapseState** operation are unpredictable.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7cb4b-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cb4b-142">See also</span></span>



[<span data-ttu-id="7cb4b-143">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="7cb4b-143">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="7cb4b-144">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="7cb4b-144">IMAPITable::FreeBookmark</span></span>](imapitable-freebookmark.md)
  
[<span data-ttu-id="7cb4b-145">IMAPITable::GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="7cb4b-145">IMAPITable::GetCollapseState</span></span>](imapitable-getcollapsestate.md)
  
[<span data-ttu-id="7cb4b-146">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7cb4b-146">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

