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
ms.openlocfilehash: ce78c6873f3a1dc034ae33f3c9e965ef8f2f1815
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563777"
---
# <a name="imapitableexpandrow"></a><span data-ttu-id="0581a-103">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="0581a-103">IMAPITable::ExpandRow</span></span>

  
  
<span data-ttu-id="0581a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0581a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0581a-105">展开折叠的表类别，添加叶或属于到表视图类别的级别较低的标题行。</span><span class="sxs-lookup"><span data-stu-id="0581a-105">Expands a collapsed table category, adding the leaf or lower-level heading rows belonging to the category to the table view.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="0581a-106">参数</span><span class="sxs-lookup"><span data-stu-id="0581a-106">Parameters</span></span>

 <span data-ttu-id="0581a-107">_cbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="0581a-107">_cbInstanceKey_</span></span>
  
> <span data-ttu-id="0581a-108">[in]_PbInstanceKey_参数指向的 PR_INSTANCE_KEY 属性中的字节数。</span><span class="sxs-lookup"><span data-stu-id="0581a-108">[in] The count of bytes in the PR_INSTANCE_KEY property pointed to by the  _pbInstanceKey_ parameter.</span></span> 
    
 <span data-ttu-id="0581a-109">_pbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="0581a-109">_pbInstanceKey_</span></span>
  
> <span data-ttu-id="0581a-110">[in]一个指向标识类别的标题行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0581a-110">[in] A pointer to the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property that identifies the heading row for the category.</span></span> 
    
 <span data-ttu-id="0581a-111">_ulRowCount_</span><span class="sxs-lookup"><span data-stu-id="0581a-111">_ulRowCount_</span></span>
  
> <span data-ttu-id="0581a-112">[in]最大_lppRows_参数中返回的行数。</span><span class="sxs-lookup"><span data-stu-id="0581a-112">[in] The maximum number of rows to return in the  _lppRows_ parameter.</span></span> 
    
 <span data-ttu-id="0581a-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0581a-113">_ulFlags_</span></span>
  
> <span data-ttu-id="0581a-114">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="0581a-114">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="0581a-115">_lppRows_</span><span class="sxs-lookup"><span data-stu-id="0581a-115">_lppRows_</span></span>
  
> <span data-ttu-id="0581a-116">[输出]指向接收已插入到由于扩展表视图的第一个 （最多_ulRowCount_) 行的[SRowSet](srowset.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="0581a-116">[out] A pointer to an [SRowSet](srowset.md) structure receiving the first (up to  _ulRowCount_) rows that have been inserted into the table view as a result of the expansion.</span></span> <span data-ttu-id="0581a-117">_PbInstanceKey_参数标识的标题行后面插入这些行。</span><span class="sxs-lookup"><span data-stu-id="0581a-117">These rows are inserted after the heading row identified by the  _pbInstanceKey_ parameter.</span></span> <span data-ttu-id="0581a-118">如果_ulRowCount_参数为零，则_lppRows_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0581a-118">The  _lppRows_ parameter can be NULL if the  _ulRowCount_ parameter is zero.</span></span> 
    
 <span data-ttu-id="0581a-119">_lpulMoreRows_</span><span class="sxs-lookup"><span data-stu-id="0581a-119">_lpulMoreRows_</span></span>
  
> <span data-ttu-id="0581a-120">[输出]一个指向已添加到表视图的行的总数。</span><span class="sxs-lookup"><span data-stu-id="0581a-120">[out] A pointer to the total number of rows that were added to the table view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0581a-121">返回值</span><span class="sxs-lookup"><span data-stu-id="0581a-121">Return value</span></span>

<span data-ttu-id="0581a-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="0581a-122">S_OK</span></span> 
  
> <span data-ttu-id="0581a-123">已成功展开类别。</span><span class="sxs-lookup"><span data-stu-id="0581a-123">The category was expanded successfully.</span></span>
    
<span data-ttu-id="0581a-124">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="0581a-124">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="0581a-125">_PbInstanceKey_参数标识的行不存在。</span><span class="sxs-lookup"><span data-stu-id="0581a-125">The row identified by the  _pbInstanceKey_ parameter does not exist.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="0581a-126">注解</span><span class="sxs-lookup"><span data-stu-id="0581a-126">Remarks</span></span>

<span data-ttu-id="0581a-127">**IMAPITable::ExpandRow**方法扩展折叠的表类别，添加叶或属于到表视图类别的级别较低的标题行。</span><span class="sxs-lookup"><span data-stu-id="0581a-127">The **IMAPITable::ExpandRow** method expands a collapsed table category, adding the leaf or lower-level heading rows that belong to the category to the table view.</span></span> <span data-ttu-id="0581a-128">可以_ulRowCount_参数中指定的_lppRows_参数中要返回的行数限制。</span><span class="sxs-lookup"><span data-stu-id="0581a-128">A limit to the number of rows to be returned in the  _lppRows_ parameter can be specified in the  _ulRowCount_ parameter.</span></span> <span data-ttu-id="0581a-129">时_ulRowCount_设置为的值大于零，由_lppRows_指向在行集中返回一个或多个行集 BOOKMARK_CURRENT 移至紧挨行中的最后一行的行的书签的位置。</span><span class="sxs-lookup"><span data-stu-id="0581a-129">When  _ulRowCount_ is set to a value greater than zero and one or more rows are returned in the row set pointed to by  _lppRows_, the position of the bookmark BOOKMARK_CURRENT is moved to the row immediately following the last row in the row set.</span></span>
  
<span data-ttu-id="0581a-130">当_ulRowCount_设置为零，请求的零叶或较低级别标题行添加到该类别中，或不返回零行，因为没有叶或类别中的级别较低的标题行时，到行集 BOOKMARK_CURRENT 的位置关注由_pbInstanceKey_标识的行。</span><span class="sxs-lookup"><span data-stu-id="0581a-130">When  _ulRowCount_ is set to zero, requesting that zero leaf or lower-level heading rows be added to the category, or zero rows are returned because there are no leaf or lower-level heading rows in the category, the position of BOOKMARK_CURRENT is set to the row following the row identified by  _pbInstanceKey_.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="0581a-131">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="0581a-131">Notes to implementers</span></span>

<span data-ttu-id="0581a-132">不会生成通知添加到类别扩展由于表视图的行上。</span><span class="sxs-lookup"><span data-stu-id="0581a-132">Do not generate notifications on rows that are added to a table view due to category expansion.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="0581a-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0581a-133">Notes to callers</span></span>

<span data-ttu-id="0581a-134">_LppRows_参数指向在行集中的行数不一定等于的实际已添加到表的行数，整个设置的叶或较低级别标题行类别。</span><span class="sxs-lookup"><span data-stu-id="0581a-134">The number of rows in the row set pointed to by the  _lppRows_ parameter might not equal the number of rows that were actually added to the table, the entire set of leaf or lower-level heading rows for the category.</span></span> <span data-ttu-id="0581a-135">发生错误，例如内存不足或超出_ulRowCount_参数中指定的号码的类别中的行数。</span><span class="sxs-lookup"><span data-stu-id="0581a-135">Errors can occur, such as insufficient memory, or the number of rows in the category exceeding the number specified in  _ulRowCount_ parameter.</span></span> <span data-ttu-id="0581a-136">在任一情况下，BOOKMARK_CURRENT 将放置在返回的最后一行。</span><span class="sxs-lookup"><span data-stu-id="0581a-136">In either case, BOOKMARK_CURRENT will be positioned at the last row returned.</span></span> <span data-ttu-id="0581a-137">若要立即检索其余的类别中的行，调用[IMAPITable::QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="0581a-137">To immediately retrieve the rest of the rows in the category, call [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span>
  
<span data-ttu-id="0581a-138">不希望类别更改其状态时收到表通知。</span><span class="sxs-lookup"><span data-stu-id="0581a-138">Do not expect to receive a table notification when a category changes its state.</span></span> <span data-ttu-id="0581a-139">您可以维护本地缓存可以与每个**ExpandRow**或**CollapseRow**呼叫更新的行。</span><span class="sxs-lookup"><span data-stu-id="0581a-139">You can maintain a local cache of rows that can be updated with every **ExpandRow** or **CollapseRow** call.</span></span> 
  
<span data-ttu-id="0581a-140">有关分类表的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="0581a-140">For more information about categorized tables, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="0581a-141">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="0581a-141">MFCMAPI reference</span></span>

<span data-ttu-id="0581a-142">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="0581a-142">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="0581a-143">**文件**</span><span class="sxs-lookup"><span data-stu-id="0581a-143">**File**</span></span>|<span data-ttu-id="0581a-144">**函数**</span><span class="sxs-lookup"><span data-stu-id="0581a-144">**Function**</span></span>|<span data-ttu-id="0581a-145">**Comment**</span><span class="sxs-lookup"><span data-stu-id="0581a-145">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0581a-146">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="0581a-146">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="0581a-147">CContentsTableListCtrl::DoExpandCollapse</span><span class="sxs-lookup"><span data-stu-id="0581a-147">CContentsTableListCtrl::DoExpandCollapse</span></span>  <br/> |<span data-ttu-id="0581a-148">MFCMAPI 使用**IMAPITable::ExpandRow**方法以展开折叠的表类别。</span><span class="sxs-lookup"><span data-stu-id="0581a-148">MFCMAPI uses the **IMAPITable::ExpandRow** method to expand a collapsed table category.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0581a-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0581a-149">See also</span></span>



[<span data-ttu-id="0581a-150">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="0581a-150">IMAPITable::CollapseRow</span></span>](imapitable-collapserow.md)
  
[<span data-ttu-id="0581a-151">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0581a-151">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="0581a-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="0581a-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

