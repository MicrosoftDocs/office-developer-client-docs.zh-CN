---
title: IMAPITableGetCollapseState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.GetCollapseState
api_type:
- COM
ms.assetid: fd4ea496-4c83-49cd-854e-f373cc1ed2af
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2c1246c46e9723cd3f6d92f0a44fc1419eef4a2e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775698"
---
# <a name="imapitablegetcollapsestate"></a><span data-ttu-id="dd59d-103">IMAPITable::GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="dd59d-103">IMAPITable::GetCollapseState</span></span>

  
  
<span data-ttu-id="dd59d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dd59d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dd59d-105">返回的数据所需重新生成当前折叠或展开分类表的状态。</span><span class="sxs-lookup"><span data-stu-id="dd59d-105">Returns the data that is needed to rebuild the current collapsed or expanded state of a categorized table.</span></span>
  
```cpp
HRESULT GetCollapseState(
ULONG ulFlags,
ULONG cbInstanceKey,
LPBYTE lpbInstanceKey,
ULONG FAR * lpcbCollapseState,
LPBYTE FAR * lppbCollapseState
);
```

## <a name="parameters"></a><span data-ttu-id="dd59d-106">参数</span><span class="sxs-lookup"><span data-stu-id="dd59d-106">Parameters</span></span>

 <span data-ttu-id="dd59d-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="dd59d-107">_ulFlags_</span></span>
  
> <span data-ttu-id="dd59d-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="dd59d-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="dd59d-109">_cbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="dd59d-109">_cbInstanceKey_</span></span>
  
> <span data-ttu-id="dd59d-110">[in]_LpbInstanceKey_参数指向的实例项中的字节数。</span><span class="sxs-lookup"><span data-stu-id="dd59d-110">[in] The count of bytes in the instance key pointed to by the  _lpbInstanceKey_ parameter.</span></span> 
    
 <span data-ttu-id="dd59d-111">_lpbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="dd59d-111">_lpbInstanceKey_</span></span>
  
> <span data-ttu-id="dd59d-112">[in]应重新生成一个指向当前折叠或展开状态的行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="dd59d-112">[in] A pointer to the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property of the row at which the current collapsed or expanded state should be rebuilt.</span></span> <span data-ttu-id="dd59d-113">_LpbInstanceKey_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="dd59d-113">The  _lpbInstanceKey_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="dd59d-114">_lpcbCollapseState_</span><span class="sxs-lookup"><span data-stu-id="dd59d-114">_lpcbCollapseState_</span></span>
  
> <span data-ttu-id="dd59d-115">[输出]一个指向结构_lppbCollapseState_参数指向的计数。</span><span class="sxs-lookup"><span data-stu-id="dd59d-115">[out] A pointer to the count of structures pointed to by the  _lppbCollapseState_ parameter.</span></span> 
    
 <span data-ttu-id="dd59d-116">_lppbCollapseState_</span><span class="sxs-lookup"><span data-stu-id="dd59d-116">_lppbCollapseState_</span></span>
  
> <span data-ttu-id="dd59d-117">[输出]指向包含介绍当前表视图的数据结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="dd59d-117">[out] A pointer to a pointer to structures that contain data that describes the current table view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="dd59d-118">返回值</span><span class="sxs-lookup"><span data-stu-id="dd59d-118">Return value</span></span>

<span data-ttu-id="dd59d-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd59d-119">S_OK</span></span> 
  
> <span data-ttu-id="dd59d-120">已成功保存分类的表的状态。</span><span class="sxs-lookup"><span data-stu-id="dd59d-120">The state for the categorized table was successfully saved.</span></span>
    
<span data-ttu-id="dd59d-121">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="dd59d-121">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="dd59d-122">正在进行中，可以防止启动操作是另一个操作。</span><span class="sxs-lookup"><span data-stu-id="dd59d-122">Another operation is in progress that prevents the operation from starting.</span></span> <span data-ttu-id="dd59d-123">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="dd59d-123">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="dd59d-124">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="dd59d-124">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="dd59d-125">表不支持分类和展开和折叠视图。</span><span class="sxs-lookup"><span data-stu-id="dd59d-125">The table does not support categorization and expanded and collapsed views.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dd59d-126">说明</span><span class="sxs-lookup"><span data-stu-id="dd59d-126">Remarks</span></span>

<span data-ttu-id="dd59d-127">**IMAPITable::GetCollapseState**方法处理所[IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)方法更改用户的分类表视图。</span><span class="sxs-lookup"><span data-stu-id="dd59d-127">The **IMAPITable::GetCollapseState** method works with the [IMAPITable::SetCollapseState](imapitable-setcollapsestate.md) method to change the user's view of a categorized table.</span></span> <span data-ttu-id="dd59d-128">**GetCollapseState**保存数据所需的**SetCollapseState**用于重新生成适当类别分类的表的视图。</span><span class="sxs-lookup"><span data-stu-id="dd59d-128">**GetCollapseState** saves the data that is needed for **SetCollapseState** to use to rebuild the appropriate views of the categories of a categorized table.</span></span> <span data-ttu-id="dd59d-129">服务提供商确定要保存的数据。</span><span class="sxs-lookup"><span data-stu-id="dd59d-129">Service providers determine the data to be saved.</span></span> <span data-ttu-id="dd59d-130">但是，大多数服务提供商实现**GetCollapseState**保存下列：</span><span class="sxs-lookup"><span data-stu-id="dd59d-130">However, most service providers implementing **GetCollapseState** save the following:</span></span> 
  
- <span data-ttu-id="dd59d-131">排序关键字 （标准的列和类别列）。</span><span class="sxs-lookup"><span data-stu-id="dd59d-131">The sort keys (standard columns and category columns).</span></span>
    
- <span data-ttu-id="dd59d-132">有关实例键所表示的行的信息。</span><span class="sxs-lookup"><span data-stu-id="dd59d-132">Information about the row that the instance key represents.</span></span>
    
- <span data-ttu-id="dd59d-133">若要还原的表的折叠和展开类别的信息。</span><span class="sxs-lookup"><span data-stu-id="dd59d-133">Information to restore the collapsed and expanded categories of the table.</span></span>
    
<span data-ttu-id="dd59d-134">有关分类表的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="dd59d-134">For more information about categorized tables, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="dd59d-135">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="dd59d-135">Notes to implementers</span></span>

<span data-ttu-id="dd59d-136">_LppbCollapseState_参数中存储的表的所有节点的当前状态。</span><span class="sxs-lookup"><span data-stu-id="dd59d-136">Store the current state of all nodes of a table in the  _lppbCollapseState_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="dd59d-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="dd59d-137">Notes to callers</span></span>

<span data-ttu-id="dd59d-138">调用**SetCollapseState**之前，始终调用**GetCollapseState** 。</span><span class="sxs-lookup"><span data-stu-id="dd59d-138">Always call **GetCollapseState** before you call **SetCollapseState**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dd59d-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd59d-139">See also</span></span>



[<span data-ttu-id="dd59d-140">IMAPITable::SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="dd59d-140">IMAPITable::SetCollapseState</span></span>](imapitable-setcollapsestate.md)
  
[<span data-ttu-id="dd59d-141">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="dd59d-141">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

