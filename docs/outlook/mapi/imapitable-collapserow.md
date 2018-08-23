---
title: IMAPITableCollapseRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.CollapseRow
api_type:
- COM
ms.assetid: 1a23e555-be26-43fb-a715-cfc4ffa623cd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b4dd7e9715c2d3c99eda44f7eed0b3360a2e33be
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595298"
---
# <a name="imapitablecollapserow"></a><span data-ttu-id="9dcad-103">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="9dcad-103">IMAPITable::CollapseRow</span></span>

  
  
<span data-ttu-id="9dcad-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9dcad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9dcad-105">折叠的扩展的表类别，删除任何级别较低的标题和叶行属于表视图中的类别。</span><span class="sxs-lookup"><span data-stu-id="9dcad-105">Collapses an expanded table category, removing any lower-level headings and leaf rows belonging to the category from the table view.</span></span>
  
```cpp
HRESULT CollapseRow(
ULONG cbInstanceKey,
LPBYTE pbInstanceKey,
ULONG ulFlags,
ULONG FAR * lpulRowCount
);
```

## <a name="parameters"></a><span data-ttu-id="9dcad-106">参数</span><span class="sxs-lookup"><span data-stu-id="9dcad-106">Parameters</span></span>

 <span data-ttu-id="9dcad-107">_cbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="9dcad-107">_cbInstanceKey_</span></span>
  
> <span data-ttu-id="9dcad-108">[in]_PbInstanceKey_参数指向的 PR_INSTANCE_KEY 属性中的字节数。</span><span class="sxs-lookup"><span data-stu-id="9dcad-108">[in] The count of bytes in the PR_INSTANCE_KEY property pointed to by the  _pbInstanceKey_ parameter.</span></span> 
    
 <span data-ttu-id="9dcad-109">_pbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="9dcad-109">_pbInstanceKey_</span></span>
  
> <span data-ttu-id="9dcad-110">[in]一个指向标识类别的标题行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="9dcad-110">[in] A pointer to the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property that identifies the heading row for the category.</span></span> 
    
 <span data-ttu-id="9dcad-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9dcad-111">_ulFlags_</span></span>
  
> <span data-ttu-id="9dcad-112">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="9dcad-112">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="9dcad-113">_lpulRowCount_</span><span class="sxs-lookup"><span data-stu-id="9dcad-113">_lpulRowCount_</span></span>
  
> <span data-ttu-id="9dcad-114">[输出]一个指向正在删除表视图中的行的总数。</span><span class="sxs-lookup"><span data-stu-id="9dcad-114">[out] A pointer to the total number of rows that are being removed from the table view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9dcad-115">返回值</span><span class="sxs-lookup"><span data-stu-id="9dcad-115">Return value</span></span>

<span data-ttu-id="9dcad-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="9dcad-116">S_OK</span></span> 
  
> <span data-ttu-id="9dcad-117">折叠操作已成功。</span><span class="sxs-lookup"><span data-stu-id="9dcad-117">The collapse operation has succeeded.</span></span>
    
<span data-ttu-id="9dcad-118">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="9dcad-118">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="9dcad-119">_PbInstanceKey_参数标识的行不存在。</span><span class="sxs-lookup"><span data-stu-id="9dcad-119">The row identified by the  _pbInstanceKey_ parameter does not exist.</span></span> 
    
<span data-ttu-id="9dcad-120">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="9dcad-120">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="9dcad-121">_PbInstanceKey_参数标识的行不存在。</span><span class="sxs-lookup"><span data-stu-id="9dcad-121">The row identified by the  _pbInstanceKey_ parameter does not exist.</span></span> <span data-ttu-id="9dcad-122">此错误是 MAPI_E_NOT_FOUND; 替代方法服务提供商可以返回其中任何一个。</span><span class="sxs-lookup"><span data-stu-id="9dcad-122">This error is an alternative to MAPI_E_NOT_FOUND; service providers can return either one.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="9dcad-123">注解</span><span class="sxs-lookup"><span data-stu-id="9dcad-123">Remarks</span></span>

<span data-ttu-id="9dcad-124">**IMAPITable::CollapseRow**方法折叠表类别，并将其删除表视图中。</span><span class="sxs-lookup"><span data-stu-id="9dcad-124">The **IMAPITable::CollapseRow** method collapses a table category and removes it from the table view.</span></span> <span data-ttu-id="9dcad-125">行折叠开始_pbInstanceKey_参数指向**PR_INSTANCE_KEY**属性标识的行。</span><span class="sxs-lookup"><span data-stu-id="9dcad-125">The rows are collapsed starting at the row identified by the **PR_INSTANCE_KEY** property pointed to by the  _pbInstanceKey_ parameter.</span></span> <span data-ttu-id="9dcad-126">从视图中删除的行数返回_lpulRowCount_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="9dcad-126">The number of rows that are removed from the view is returned in the contents of the  _lpulRowCount_ parameter.</span></span> 
  
<span data-ttu-id="9dcad-127">从视图中删除折叠操作的结果的表格行的永远不会生成通知。</span><span class="sxs-lookup"><span data-stu-id="9dcad-127">Notifications are never generated for table rows that are removed from a view as the result of a collapse operation.</span></span> 
  
<span data-ttu-id="9dcad-128">时由书签定义行折叠视图，该书签会移到下一个可见行指向。</span><span class="sxs-lookup"><span data-stu-id="9dcad-128">When a row that is defined by a bookmark is collapsed out of view, the bookmark is moved to point to the next visible row.</span></span> 
  
<span data-ttu-id="9dcad-129">有关分类表的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="9dcad-129">For more information about categorized tables, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9dcad-130">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="9dcad-130">MFCMAPI reference</span></span>

<span data-ttu-id="9dcad-131">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9dcad-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9dcad-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="9dcad-132">**File**</span></span>|<span data-ttu-id="9dcad-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="9dcad-133">**Function**</span></span>|<span data-ttu-id="9dcad-134">**Comment**</span><span class="sxs-lookup"><span data-stu-id="9dcad-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9dcad-135">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="9dcad-135">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="9dcad-136">CContentsTableListCtrl::DoExpandCollapse</span><span class="sxs-lookup"><span data-stu-id="9dcad-136">CContentsTableListCtrl::DoExpandCollapse</span></span>  <br/> |<span data-ttu-id="9dcad-137">MFCMAPI 使用**IMAPITable::CollapseRow**方法折叠表类别。</span><span class="sxs-lookup"><span data-stu-id="9dcad-137">MFCMAPI uses the **IMAPITable::CollapseRow** method to collapse a table category.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9dcad-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9dcad-138">See also</span></span>



[<span data-ttu-id="9dcad-139">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="9dcad-139">IMAPITable::ExpandRow</span></span>](imapitable-expandrow.md)
  
[<span data-ttu-id="9dcad-140">IMAPITable::GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="9dcad-140">IMAPITable::GetCollapseState</span></span>](imapitable-getcollapsestate.md)
  
[<span data-ttu-id="9dcad-141">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="9dcad-141">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="9dcad-142">IMAPITable::SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="9dcad-142">IMAPITable::SetCollapseState</span></span>](imapitable-setcollapsestate.md)
  
[<span data-ttu-id="9dcad-143">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="9dcad-143">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="9dcad-144">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="9dcad-144">SSortOrderSet</span></span>](ssortorderset.md)
  
[<span data-ttu-id="9dcad-145">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9dcad-145">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="9dcad-146">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9dcad-146">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

