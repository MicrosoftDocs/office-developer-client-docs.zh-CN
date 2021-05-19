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
ms.openlocfilehash: e6a180ceb325a705ebf226bb728c52cce7396490
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416172"
---
# <a name="imapitablecollapserow"></a><span data-ttu-id="611f8-103">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="611f8-103">IMAPITable::CollapseRow</span></span>

  
  
<span data-ttu-id="611f8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="611f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="611f8-105">折叠展开的表类别，从表视图中删除属于该类别的任何较低级别标题和叶行。</span><span class="sxs-lookup"><span data-stu-id="611f8-105">Collapses an expanded table category, removing any lower-level headings and leaf rows belonging to the category from the table view.</span></span>
  
```cpp
HRESULT CollapseRow(
ULONG cbInstanceKey,
LPBYTE pbInstanceKey,
ULONG ulFlags,
ULONG FAR * lpulRowCount
);
```

## <a name="parameters"></a><span data-ttu-id="611f8-106">参数</span><span class="sxs-lookup"><span data-stu-id="611f8-106">Parameters</span></span>

 <span data-ttu-id="611f8-107">_cbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="611f8-107">_cbInstanceKey_</span></span>
  
> <span data-ttu-id="611f8-108">[in]  _pbInstanceKey_ 参数PR_INSTANCE_KEY属性中的字节数。</span><span class="sxs-lookup"><span data-stu-id="611f8-108">[in] The count of bytes in the PR_INSTANCE_KEY property pointed to by the  _pbInstanceKey_ parameter.</span></span> 
    
 <span data-ttu-id="611f8-109">_pbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="611f8-109">_pbInstanceKey_</span></span>
  
> <span data-ttu-id="611f8-110">[in]指向标识类别 **的标题** PR_INSTANCE_KEY ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性的指针。</span><span class="sxs-lookup"><span data-stu-id="611f8-110">[in] A pointer to the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property that identifies the heading row for the category.</span></span> 
    
 <span data-ttu-id="611f8-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="611f8-111">_ulFlags_</span></span>
  
> <span data-ttu-id="611f8-112">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="611f8-112">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="611f8-113">_lpulRowCount_</span><span class="sxs-lookup"><span data-stu-id="611f8-113">_lpulRowCount_</span></span>
  
> <span data-ttu-id="611f8-114">[out]指向从表视图中删除的总行数的指针。</span><span class="sxs-lookup"><span data-stu-id="611f8-114">[out] A pointer to the total number of rows that are being removed from the table view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="611f8-115">返回值</span><span class="sxs-lookup"><span data-stu-id="611f8-115">Return value</span></span>

<span data-ttu-id="611f8-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="611f8-116">S_OK</span></span> 
  
> <span data-ttu-id="611f8-117">折叠操作已成功。</span><span class="sxs-lookup"><span data-stu-id="611f8-117">The collapse operation has succeeded.</span></span>
    
<span data-ttu-id="611f8-118">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="611f8-118">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="611f8-119">_pbInstanceKey_ 参数标识的行不存在。</span><span class="sxs-lookup"><span data-stu-id="611f8-119">The row identified by the  _pbInstanceKey_ parameter does not exist.</span></span> 
    
<span data-ttu-id="611f8-120">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="611f8-120">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="611f8-121">_pbInstanceKey_ 参数标识的行不存在。</span><span class="sxs-lookup"><span data-stu-id="611f8-121">The row identified by the  _pbInstanceKey_ parameter does not exist.</span></span> <span data-ttu-id="611f8-122">此错误是一种替代MAPI_E_NOT_FOUND;服务提供程序可以返回其中一个。</span><span class="sxs-lookup"><span data-stu-id="611f8-122">This error is an alternative to MAPI_E_NOT_FOUND; service providers can return either one.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="611f8-123">备注</span><span class="sxs-lookup"><span data-stu-id="611f8-123">Remarks</span></span>

<span data-ttu-id="611f8-124">**IMAPITable：：CollapseRow** 方法折叠表类别，并从表视图中删除该类别。</span><span class="sxs-lookup"><span data-stu-id="611f8-124">The **IMAPITable::CollapseRow** method collapses a table category and removes it from the table view.</span></span> <span data-ttu-id="611f8-125">从 _pbInstanceKey_ 参数指向的 **PR_INSTANCE_KEY** 属性所标识的行开始折叠行。</span><span class="sxs-lookup"><span data-stu-id="611f8-125">The rows are collapsed starting at the row identified by the **PR_INSTANCE_KEY** property pointed to by the  _pbInstanceKey_ parameter.</span></span> <span data-ttu-id="611f8-126">从视图中删除的行数在  _lpulRowCount_ 参数的内容中返回。</span><span class="sxs-lookup"><span data-stu-id="611f8-126">The number of rows that are removed from the view is returned in the contents of the  _lpulRowCount_ parameter.</span></span> 
  
<span data-ttu-id="611f8-127">从不为由于折叠操作而从视图中删除的表行生成通知。</span><span class="sxs-lookup"><span data-stu-id="611f8-127">Notifications are never generated for table rows that are removed from a view as the result of a collapse operation.</span></span> 
  
<span data-ttu-id="611f8-128">当书签定义的行折叠到视图外时，书签将移动到下一个可见行。</span><span class="sxs-lookup"><span data-stu-id="611f8-128">When a row that is defined by a bookmark is collapsed out of view, the bookmark is moved to point to the next visible row.</span></span> 
  
<span data-ttu-id="611f8-129">有关分类表的信息，请参阅排序 [和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="611f8-129">For more information about categorized tables, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="611f8-130">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="611f8-130">MFCMAPI reference</span></span>

<span data-ttu-id="611f8-131">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="611f8-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="611f8-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="611f8-132">**File**</span></span>|<span data-ttu-id="611f8-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="611f8-133">**Function**</span></span>|<span data-ttu-id="611f8-134">**备注**</span><span class="sxs-lookup"><span data-stu-id="611f8-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="611f8-135">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="611f8-135">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="611f8-136">CContentsTableListCtrl：:D oExpandCollapse</span><span class="sxs-lookup"><span data-stu-id="611f8-136">CContentsTableListCtrl::DoExpandCollapse</span></span>  <br/> |<span data-ttu-id="611f8-137">MFCMAPI 使用 **IMAPITable：：CollapseRow** 方法折叠表类别。</span><span class="sxs-lookup"><span data-stu-id="611f8-137">MFCMAPI uses the **IMAPITable::CollapseRow** method to collapse a table category.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="611f8-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="611f8-138">See also</span></span>



[<span data-ttu-id="611f8-139">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="611f8-139">IMAPITable::ExpandRow</span></span>](imapitable-expandrow.md)
  
[<span data-ttu-id="611f8-140">IMAPITable::GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="611f8-140">IMAPITable::GetCollapseState</span></span>](imapitable-getcollapsestate.md)
  
[<span data-ttu-id="611f8-141">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="611f8-141">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="611f8-142">IMAPITable::SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="611f8-142">IMAPITable::SetCollapseState</span></span>](imapitable-setcollapsestate.md)
  
[<span data-ttu-id="611f8-143">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="611f8-143">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="611f8-144">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="611f8-144">SSortOrderSet</span></span>](ssortorderset.md)
  
[<span data-ttu-id="611f8-145">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="611f8-145">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="611f8-146">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="611f8-146">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

