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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 97575a65cd6825e07d6f11c813beec539f99f53a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436074"
---
# <a name="imapitablegetcollapsestate"></a><span data-ttu-id="22e0d-103">IMAPITable::GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="22e0d-103">IMAPITable::GetCollapseState</span></span>

  
  
<span data-ttu-id="22e0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="22e0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="22e0d-105">返回重建分类表的当前折叠或展开状态所需的数据。</span><span class="sxs-lookup"><span data-stu-id="22e0d-105">Returns the data that is needed to rebuild the current collapsed or expanded state of a categorized table.</span></span>
  
```cpp
HRESULT GetCollapseState(
ULONG ulFlags,
ULONG cbInstanceKey,
LPBYTE lpbInstanceKey,
ULONG FAR * lpcbCollapseState,
LPBYTE FAR * lppbCollapseState
);
```

## <a name="parameters"></a><span data-ttu-id="22e0d-106">参数</span><span class="sxs-lookup"><span data-stu-id="22e0d-106">Parameters</span></span>

 <span data-ttu-id="22e0d-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="22e0d-107">_ulFlags_</span></span>
  
> <span data-ttu-id="22e0d-108">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="22e0d-108">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="22e0d-109">_cbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="22e0d-109">_cbInstanceKey_</span></span>
  
> <span data-ttu-id="22e0d-110">[in]  _lpbInstanceKey_ 参数指向的实例键中的字节数。</span><span class="sxs-lookup"><span data-stu-id="22e0d-110">[in] The count of bytes in the instance key pointed to by the  _lpbInstanceKey_ parameter.</span></span> 
    
 <span data-ttu-id="22e0d-111">_lpbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="22e0d-111">_lpbInstanceKey_</span></span>
  
> <span data-ttu-id="22e0d-112">[in]指向当前 **折叠** 或展开PR_INSTANCE_KEY (的行的 [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性的指针。</span><span class="sxs-lookup"><span data-stu-id="22e0d-112">[in] A pointer to the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property of the row at which the current collapsed or expanded state should be rebuilt.</span></span> <span data-ttu-id="22e0d-113">_lpbInstanceKey_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="22e0d-113">The  _lpbInstanceKey_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="22e0d-114">_lpcbCollapseState_</span><span class="sxs-lookup"><span data-stu-id="22e0d-114">_lpcbCollapseState_</span></span>
  
> <span data-ttu-id="22e0d-115">[out]指向  _lppbCollapseState_ 参数指向的结构计数的指针。</span><span class="sxs-lookup"><span data-stu-id="22e0d-115">[out] A pointer to the count of structures pointed to by the  _lppbCollapseState_ parameter.</span></span> 
    
 <span data-ttu-id="22e0d-116">_lppbCollapseState_</span><span class="sxs-lookup"><span data-stu-id="22e0d-116">_lppbCollapseState_</span></span>
  
> <span data-ttu-id="22e0d-117">[out]指向包含描述当前表视图的数据的结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="22e0d-117">[out] A pointer to a pointer to structures that contain data that describes the current table view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="22e0d-118">返回值</span><span class="sxs-lookup"><span data-stu-id="22e0d-118">Return value</span></span>

<span data-ttu-id="22e0d-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="22e0d-119">S_OK</span></span> 
  
> <span data-ttu-id="22e0d-120">已成功保存分类表的状态。</span><span class="sxs-lookup"><span data-stu-id="22e0d-120">The state for the categorized table was successfully saved.</span></span>
    
<span data-ttu-id="22e0d-121">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="22e0d-121">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="22e0d-122">正在进行另一个阻止操作启动的操作。</span><span class="sxs-lookup"><span data-stu-id="22e0d-122">Another operation is in progress that prevents the operation from starting.</span></span> <span data-ttu-id="22e0d-123">应允许完成或停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="22e0d-123">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="22e0d-124">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="22e0d-124">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="22e0d-125">该表不支持分类以及展开和折叠的视图。</span><span class="sxs-lookup"><span data-stu-id="22e0d-125">The table does not support categorization and expanded and collapsed views.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="22e0d-126">备注</span><span class="sxs-lookup"><span data-stu-id="22e0d-126">Remarks</span></span>

<span data-ttu-id="22e0d-127">**IMAPITable：：GetCollapseState** 方法与 [IMAPITable：：SetCollapseState](imapitable-setcollapsestate.md)方法一起更改已分类表的用户视图。</span><span class="sxs-lookup"><span data-stu-id="22e0d-127">The **IMAPITable::GetCollapseState** method works with the [IMAPITable::SetCollapseState](imapitable-setcollapsestate.md) method to change the user's view of a categorized table.</span></span> <span data-ttu-id="22e0d-128">**GetCollapseState** 保存 **SetCollapseState** 所需的数据，以用于重建分类表类别的适当视图。</span><span class="sxs-lookup"><span data-stu-id="22e0d-128">**GetCollapseState** saves the data that is needed for **SetCollapseState** to use to rebuild the appropriate views of the categories of a categorized table.</span></span> <span data-ttu-id="22e0d-129">服务提供商确定要保存的数据。</span><span class="sxs-lookup"><span data-stu-id="22e0d-129">Service providers determine the data to be saved.</span></span> <span data-ttu-id="22e0d-130">但是，大多数实现 **GetCollapseState** 的服务提供商将保存以下内容：</span><span class="sxs-lookup"><span data-stu-id="22e0d-130">However, most service providers implementing **GetCollapseState** save the following:</span></span> 
  
- <span data-ttu-id="22e0d-131">排序键 (列和分类列) 。</span><span class="sxs-lookup"><span data-stu-id="22e0d-131">The sort keys (standard columns and category columns).</span></span>
    
- <span data-ttu-id="22e0d-132">有关实例键表示的行的信息。</span><span class="sxs-lookup"><span data-stu-id="22e0d-132">Information about the row that the instance key represents.</span></span>
    
- <span data-ttu-id="22e0d-133">还原表的折叠和展开类别的信息。</span><span class="sxs-lookup"><span data-stu-id="22e0d-133">Information to restore the collapsed and expanded categories of the table.</span></span>
    
<span data-ttu-id="22e0d-134">有关分类表的信息，请参阅排序 [和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="22e0d-134">For more information about categorized tables, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="22e0d-135">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="22e0d-135">Notes to implementers</span></span>

<span data-ttu-id="22e0d-136">将表的所有节点的当前状态存储在  _lppbCollapseState_ 参数中。</span><span class="sxs-lookup"><span data-stu-id="22e0d-136">Store the current state of all nodes of a table in the  _lppbCollapseState_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="22e0d-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="22e0d-137">Notes to callers</span></span>

<span data-ttu-id="22e0d-138">在调用 **SetCollapseState** 之前，始终调用 **GetCollapseState**。</span><span class="sxs-lookup"><span data-stu-id="22e0d-138">Always call **GetCollapseState** before you call **SetCollapseState**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="22e0d-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22e0d-139">See also</span></span>



[<span data-ttu-id="22e0d-140">IMAPITable::SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="22e0d-140">IMAPITable::SetCollapseState</span></span>](imapitable-setcollapsestate.md)
  
[<span data-ttu-id="22e0d-141">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="22e0d-141">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

