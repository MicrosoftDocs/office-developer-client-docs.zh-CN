---
title: IMAPITableExpandRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.ExpandRow
api_type:
- COM
ms.assetid: b96dd8f6-e648-4014-8a1d-ae1da771c439
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e2ce756baaefef7bd0028e746b1dbe10756365e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415164"
---
# <a name="imapitableexpandrow"></a><span data-ttu-id="214e9-103">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="214e9-103">IMAPITable::ExpandRow</span></span>

  
  
<span data-ttu-id="214e9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="214e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="214e9-105">展开折叠的表类别，将属于该类别的叶标题行或较低级别标题行添加到表视图中。</span><span class="sxs-lookup"><span data-stu-id="214e9-105">Expands a collapsed table category, adding the leaf or lower-level heading rows belonging to the category to the table view.</span></span>
  
```cpp
HRESULT ExpandRow(
ULONG cbInstanceKey,
LPBYTE pbInstanceKey,
ULONG ulRowCount,
ULONG ulFlags,
LPSRowSet FAR * lppRows,
ULONG FAR * lpulMoreRows
);
```

## <a name="parameters"></a><span data-ttu-id="214e9-106">参数</span><span class="sxs-lookup"><span data-stu-id="214e9-106">Parameters</span></span>

 <span data-ttu-id="214e9-107">_cbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="214e9-107">_cbInstanceKey_</span></span>
  
> <span data-ttu-id="214e9-108">[in]  _pbInstanceKey_ 参数PR_INSTANCE_KEY属性中的字节数。</span><span class="sxs-lookup"><span data-stu-id="214e9-108">[in] The count of bytes in the PR_INSTANCE_KEY property pointed to by the  _pbInstanceKey_ parameter.</span></span> 
    
 <span data-ttu-id="214e9-109">_pbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="214e9-109">_pbInstanceKey_</span></span>
  
> <span data-ttu-id="214e9-110">[in]指向标识类别 **的标题** PR_INSTANCE_KEY ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性的指针。</span><span class="sxs-lookup"><span data-stu-id="214e9-110">[in] A pointer to the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property that identifies the heading row for the category.</span></span> 
    
 <span data-ttu-id="214e9-111">_ulRowCount_</span><span class="sxs-lookup"><span data-stu-id="214e9-111">_ulRowCount_</span></span>
  
> <span data-ttu-id="214e9-112">[in]  _lppRows_ 参数中要返回的最大行数。</span><span class="sxs-lookup"><span data-stu-id="214e9-112">[in] The maximum number of rows to return in the  _lppRows_ parameter.</span></span> 
    
 <span data-ttu-id="214e9-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="214e9-113">_ulFlags_</span></span>
  
> <span data-ttu-id="214e9-114">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="214e9-114">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="214e9-115">_lppRows_</span><span class="sxs-lookup"><span data-stu-id="214e9-115">_lppRows_</span></span>
  
> <span data-ttu-id="214e9-116">[out]一个指向 [SRowSet](srowset.md) 结构的指针，该结构接收 (展开时已插入到表视图中的第一)  _ulRowCount_) 行。</span><span class="sxs-lookup"><span data-stu-id="214e9-116">[out] A pointer to an [SRowSet](srowset.md) structure receiving the first (up to  _ulRowCount_) rows that have been inserted into the table view as a result of the expansion.</span></span> <span data-ttu-id="214e9-117">这些行插入到由  _pbInstanceKey_ 参数标识的标题行之后。</span><span class="sxs-lookup"><span data-stu-id="214e9-117">These rows are inserted after the heading row identified by the  _pbInstanceKey_ parameter.</span></span> <span data-ttu-id="214e9-118">如果 ulRowCount 参数为零，则 _lppRows_ 参数可以是 NULL。 </span><span class="sxs-lookup"><span data-stu-id="214e9-118">The  _lppRows_ parameter can be NULL if the  _ulRowCount_ parameter is zero.</span></span> 
    
 <span data-ttu-id="214e9-119">_lpulMoreRows_</span><span class="sxs-lookup"><span data-stu-id="214e9-119">_lpulMoreRows_</span></span>
  
> <span data-ttu-id="214e9-120">[out]指向已添加到表视图的行的总数指针。</span><span class="sxs-lookup"><span data-stu-id="214e9-120">[out] A pointer to the total number of rows that were added to the table view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="214e9-121">返回值</span><span class="sxs-lookup"><span data-stu-id="214e9-121">Return value</span></span>

<span data-ttu-id="214e9-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="214e9-122">S_OK</span></span> 
  
> <span data-ttu-id="214e9-123">已成功扩展类别。</span><span class="sxs-lookup"><span data-stu-id="214e9-123">The category was expanded successfully.</span></span>
    
<span data-ttu-id="214e9-124">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="214e9-124">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="214e9-125">_pbInstanceKey_ 参数标识的行不存在。</span><span class="sxs-lookup"><span data-stu-id="214e9-125">The row identified by the  _pbInstanceKey_ parameter does not exist.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="214e9-126">备注</span><span class="sxs-lookup"><span data-stu-id="214e9-126">Remarks</span></span>

<span data-ttu-id="214e9-127">**IMAPITable：：ExpandRow** 方法展开折叠的表类别，将属于该类别的叶或较低级别标题行添加到表视图。</span><span class="sxs-lookup"><span data-stu-id="214e9-127">The **IMAPITable::ExpandRow** method expands a collapsed table category, adding the leaf or lower-level heading rows that belong to the category to the table view.</span></span> <span data-ttu-id="214e9-128">可以在 _ulRowCount_ 参数中指定 _对在 lppRows_ 参数中返回的行数的限制。</span><span class="sxs-lookup"><span data-stu-id="214e9-128">A limit to the number of rows to be returned in the  _lppRows_ parameter can be specified in the  _ulRowCount_ parameter.</span></span> <span data-ttu-id="214e9-129">当  _ulRowCount_ 设置为大于零的值，并且  _lppRows_ 指向的行集返回一行或多行时，书签 BOOKMARK_CURRENT 的位置将移动到紧随行集最后一行的行。</span><span class="sxs-lookup"><span data-stu-id="214e9-129">When  _ulRowCount_ is set to a value greater than zero and one or more rows are returned in the row set pointed to by  _lppRows_, the position of the bookmark BOOKMARK_CURRENT is moved to the row immediately following the last row in the row set.</span></span>
  
<span data-ttu-id="214e9-130">当  _ulRowCount_ 设置为零时，请求将零叶或较低级别的标题行添加到类别中，或者返回零行，因为类别中没有叶标题行或较低级别标题行，BOOKMARK_CURRENT 的位置将设置为  _pbInstanceKey_ 标识的行后行。</span><span class="sxs-lookup"><span data-stu-id="214e9-130">When  _ulRowCount_ is set to zero, requesting that zero leaf or lower-level heading rows be added to the category, or zero rows are returned because there are no leaf or lower-level heading rows in the category, the position of BOOKMARK_CURRENT is set to the row following the row identified by  _pbInstanceKey_.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="214e9-131">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="214e9-131">Notes to implementers</span></span>

<span data-ttu-id="214e9-132">请勿在因类别扩展而添加到表视图中的行上生成通知。</span><span class="sxs-lookup"><span data-stu-id="214e9-132">Do not generate notifications on rows that are added to a table view due to category expansion.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="214e9-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="214e9-133">Notes to callers</span></span>

<span data-ttu-id="214e9-134">_lppRows_ 参数指向的行集的行数可能并不等于实际添加到表中的行数，即类别的整组叶标题行或较低级别标题行。</span><span class="sxs-lookup"><span data-stu-id="214e9-134">The number of rows in the row set pointed to by the  _lppRows_ parameter might not equal the number of rows that were actually added to the table, the entire set of leaf or lower-level heading rows for the category.</span></span> <span data-ttu-id="214e9-135">可能会发生错误，例如内存不足或类别中的行数超过  _ulRowCount_ 参数中指定的行数。</span><span class="sxs-lookup"><span data-stu-id="214e9-135">Errors can occur, such as insufficient memory, or the number of rows in the category exceeding the number specified in  _ulRowCount_ parameter.</span></span> <span data-ttu-id="214e9-136">在任一情况下，BOOKMARK_CURRENT将位于返回的最后一行。</span><span class="sxs-lookup"><span data-stu-id="214e9-136">In either case, BOOKMARK_CURRENT will be positioned at the last row returned.</span></span> <span data-ttu-id="214e9-137">若要立即检索类别中的其余行，请调用 [IMAPITable：：QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="214e9-137">To immediately retrieve the rest of the rows in the category, call [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span>
  
<span data-ttu-id="214e9-138">当类别更改其状态时，不要收到表通知。</span><span class="sxs-lookup"><span data-stu-id="214e9-138">Do not expect to receive a table notification when a category changes its state.</span></span> <span data-ttu-id="214e9-139">您可以维护可通过每个 **ExpandRow** 或 **CollapseRow** 调用更新的行的本地缓存。</span><span class="sxs-lookup"><span data-stu-id="214e9-139">You can maintain a local cache of rows that can be updated with every **ExpandRow** or **CollapseRow** call.</span></span> 
  
<span data-ttu-id="214e9-140">有关分类表的信息，请参阅排序 [和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="214e9-140">For more information about categorized tables, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="214e9-141">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="214e9-141">MFCMAPI reference</span></span>

<span data-ttu-id="214e9-142">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="214e9-142">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="214e9-143">**文件**</span><span class="sxs-lookup"><span data-stu-id="214e9-143">**File**</span></span>|<span data-ttu-id="214e9-144">**函数**</span><span class="sxs-lookup"><span data-stu-id="214e9-144">**Function**</span></span>|<span data-ttu-id="214e9-145">**备注**</span><span class="sxs-lookup"><span data-stu-id="214e9-145">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="214e9-146">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="214e9-146">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="214e9-147">CContentsTableListCtrl：:D oExpandCollapse</span><span class="sxs-lookup"><span data-stu-id="214e9-147">CContentsTableListCtrl::DoExpandCollapse</span></span>  <br/> |<span data-ttu-id="214e9-148">MFCMAPI 使用 **IMAPITable：：ExpandRow** 方法展开折叠的表类别。</span><span class="sxs-lookup"><span data-stu-id="214e9-148">MFCMAPI uses the **IMAPITable::ExpandRow** method to expand a collapsed table category.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="214e9-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="214e9-149">See also</span></span>



[<span data-ttu-id="214e9-150">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="214e9-150">IMAPITable::CollapseRow</span></span>](imapitable-collapserow.md)
  
[<span data-ttu-id="214e9-151">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="214e9-151">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="214e9-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="214e9-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

