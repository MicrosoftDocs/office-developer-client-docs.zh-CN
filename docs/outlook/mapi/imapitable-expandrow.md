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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329038"
---
# <a name="imapitableexpandrow"></a><span data-ttu-id="0de5d-103">IMAPITable::ExpandRow</span><span class="sxs-lookup"><span data-stu-id="0de5d-103">IMAPITable::ExpandRow</span></span>

  
  
<span data-ttu-id="0de5d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0de5d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0de5d-105">展开折叠的表格类别, 将属于该类别的叶片或下层标题行添加到表格视图中。</span><span class="sxs-lookup"><span data-stu-id="0de5d-105">Expands a collapsed table category, adding the leaf or lower-level heading rows belonging to the category to the table view.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="0de5d-106">参数</span><span class="sxs-lookup"><span data-stu-id="0de5d-106">Parameters</span></span>

 <span data-ttu-id="0de5d-107">_cbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="0de5d-107">_cbInstanceKey_</span></span>
  
> <span data-ttu-id="0de5d-108">实时_pbInstanceKey_参数所指向的 PR_INSTANCE_KEY 属性中的字节数。</span><span class="sxs-lookup"><span data-stu-id="0de5d-108">[in] The count of bytes in the PR_INSTANCE_KEY property pointed to by the  _pbInstanceKey_ parameter.</span></span> 
    
 <span data-ttu-id="0de5d-109">_pbInstanceKey_</span><span class="sxs-lookup"><span data-stu-id="0de5d-109">_pbInstanceKey_</span></span>
  
> <span data-ttu-id="0de5d-110">实时一个指针, 指向用于标识该类别的标题行的**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0de5d-110">[in] A pointer to the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property that identifies the heading row for the category.</span></span> 
    
 <span data-ttu-id="0de5d-111">_ulRowCount_</span><span class="sxs-lookup"><span data-stu-id="0de5d-111">_ulRowCount_</span></span>
  
> <span data-ttu-id="0de5d-112">实时要在_lppRows_参数中返回的最大行数。</span><span class="sxs-lookup"><span data-stu-id="0de5d-112">[in] The maximum number of rows to return in the  _lppRows_ parameter.</span></span> 
    
 <span data-ttu-id="0de5d-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0de5d-113">_ulFlags_</span></span>
  
> <span data-ttu-id="0de5d-114">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="0de5d-114">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="0de5d-115">_lppRows_</span><span class="sxs-lookup"><span data-stu-id="0de5d-115">_lppRows_</span></span>
  
> <span data-ttu-id="0de5d-116">排除指向接收第一个 (最多为_ulRowCount_) 行的[SRowSet](srowset.md)结构的指针, 这些行是由于扩展而插入到表视图中的。</span><span class="sxs-lookup"><span data-stu-id="0de5d-116">[out] A pointer to an [SRowSet](srowset.md) structure receiving the first (up to  _ulRowCount_) rows that have been inserted into the table view as a result of the expansion.</span></span> <span data-ttu-id="0de5d-117">这些行在_pbInstanceKey_参数所标识的标题行后插入。</span><span class="sxs-lookup"><span data-stu-id="0de5d-117">These rows are inserted after the heading row identified by the  _pbInstanceKey_ parameter.</span></span> <span data-ttu-id="0de5d-118">如果_ulRowCount_参数为零, 则_lppRows_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0de5d-118">The  _lppRows_ parameter can be NULL if the  _ulRowCount_ parameter is zero.</span></span> 
    
 <span data-ttu-id="0de5d-119">_lpulMoreRows_</span><span class="sxs-lookup"><span data-stu-id="0de5d-119">_lpulMoreRows_</span></span>
  
> <span data-ttu-id="0de5d-120">排除一个指针, 指向已添加到表视图中的总行数。</span><span class="sxs-lookup"><span data-stu-id="0de5d-120">[out] A pointer to the total number of rows that were added to the table view.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0de5d-121">返回值</span><span class="sxs-lookup"><span data-stu-id="0de5d-121">Return value</span></span>

<span data-ttu-id="0de5d-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="0de5d-122">S_OK</span></span> 
  
> <span data-ttu-id="0de5d-123">类别已成功扩展。</span><span class="sxs-lookup"><span data-stu-id="0de5d-123">The category was expanded successfully.</span></span>
    
<span data-ttu-id="0de5d-124">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="0de5d-124">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="0de5d-125">由_pbInstanceKey_参数标识的行不存在。</span><span class="sxs-lookup"><span data-stu-id="0de5d-125">The row identified by the  _pbInstanceKey_ parameter does not exist.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="0de5d-126">注解</span><span class="sxs-lookup"><span data-stu-id="0de5d-126">Remarks</span></span>

<span data-ttu-id="0de5d-127">**IMAPITable:: ExpandRow**方法展开一个折叠的表类别, 将属于该类别的叶或低级标题行添加到表视图中。</span><span class="sxs-lookup"><span data-stu-id="0de5d-127">The **IMAPITable::ExpandRow** method expands a collapsed table category, adding the leaf or lower-level heading rows that belong to the category to the table view.</span></span> <span data-ttu-id="0de5d-128">可以在_ulRowCount_参数中指定对_lppRows_参数中要返回的行数的限制。</span><span class="sxs-lookup"><span data-stu-id="0de5d-128">A limit to the number of rows to be returned in the  _lppRows_ parameter can be specified in the  _ulRowCount_ parameter.</span></span> <span data-ttu-id="0de5d-129">如果将_ulRowCount_设置为大于零的值, 并且在_lppRows_指向的行集中返回一个或多个行, 则书签 BOOKMARK_CURRENT 的位置将移至紧跟在行集中最后一行后面的行。</span><span class="sxs-lookup"><span data-stu-id="0de5d-129">When  _ulRowCount_ is set to a value greater than zero and one or more rows are returned in the row set pointed to by  _lppRows_, the position of the bookmark BOOKMARK_CURRENT is moved to the row immediately following the last row in the row set.</span></span>
  
<span data-ttu-id="0de5d-130">如果将_ulRowCount_设置为零, 请求将零点或较低级别的标题行添加到类别中, 或由于类别中没有叶或低级标题行而返回零行, 则 BOOKMARK_CURRENT 的位置将设置为行。关注由_pbInstanceKey_标识的行。</span><span class="sxs-lookup"><span data-stu-id="0de5d-130">When  _ulRowCount_ is set to zero, requesting that zero leaf or lower-level heading rows be added to the category, or zero rows are returned because there are no leaf or lower-level heading rows in the category, the position of BOOKMARK_CURRENT is set to the row following the row identified by  _pbInstanceKey_.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="0de5d-131">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="0de5d-131">Notes to implementers</span></span>

<span data-ttu-id="0de5d-132">请勿在由于类别扩展而添加到表视图中的行上生成通知。</span><span class="sxs-lookup"><span data-stu-id="0de5d-132">Do not generate notifications on rows that are added to a table view due to category expansion.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="0de5d-133">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0de5d-133">Notes to callers</span></span>

<span data-ttu-id="0de5d-134">由_lppRows_参数指向的行集内的行数可能不等于实际添加到表中的行数, 即类别的整个叶或低级标题行的数目。</span><span class="sxs-lookup"><span data-stu-id="0de5d-134">The number of rows in the row set pointed to by the  _lppRows_ parameter might not equal the number of rows that were actually added to the table, the entire set of leaf or lower-level heading rows for the category.</span></span> <span data-ttu-id="0de5d-135">错误可能会发生, 如内存不足, 或超出_ulRowCount_参数中指定的数字的类别中的行数。</span><span class="sxs-lookup"><span data-stu-id="0de5d-135">Errors can occur, such as insufficient memory, or the number of rows in the category exceeding the number specified in  _ulRowCount_ parameter.</span></span> <span data-ttu-id="0de5d-136">在这两种情况下, BOOKMARK_CURRENT 将放置在返回的最后一行上。</span><span class="sxs-lookup"><span data-stu-id="0de5d-136">In either case, BOOKMARK_CURRENT will be positioned at the last row returned.</span></span> <span data-ttu-id="0de5d-137">若要立即检索类别中的其余行, 请调用[IMAPITable:: QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="0de5d-137">To immediately retrieve the rest of the rows in the category, call [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span>
  
<span data-ttu-id="0de5d-138">不希望在类别更改其状态时收到表格通知。</span><span class="sxs-lookup"><span data-stu-id="0de5d-138">Do not expect to receive a table notification when a category changes its state.</span></span> <span data-ttu-id="0de5d-139">您可以维护可使用每个**ExpandRow**或**CollapseRow**调用更新的行的本地缓存。</span><span class="sxs-lookup"><span data-stu-id="0de5d-139">You can maintain a local cache of rows that can be updated with every **ExpandRow** or **CollapseRow** call.</span></span> 
  
<span data-ttu-id="0de5d-140">有关分类表的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="0de5d-140">For more information about categorized tables, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="0de5d-141">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="0de5d-141">MFCMAPI reference</span></span>

<span data-ttu-id="0de5d-142">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="0de5d-142">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="0de5d-143">**文件**</span><span class="sxs-lookup"><span data-stu-id="0de5d-143">**File**</span></span>|<span data-ttu-id="0de5d-144">**函数**</span><span class="sxs-lookup"><span data-stu-id="0de5d-144">**Function**</span></span>|<span data-ttu-id="0de5d-145">**备注**</span><span class="sxs-lookup"><span data-stu-id="0de5d-145">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0de5d-146">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="0de5d-146">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="0de5d-147">CContentsTableListCtrl::D oexpandcollapse</span><span class="sxs-lookup"><span data-stu-id="0de5d-147">CContentsTableListCtrl::DoExpandCollapse</span></span>  <br/> |<span data-ttu-id="0de5d-148">MFCMAPI 使用**IMAPITable:: ExpandRow**方法展开折叠的表类别。</span><span class="sxs-lookup"><span data-stu-id="0de5d-148">MFCMAPI uses the **IMAPITable::ExpandRow** method to expand a collapsed table category.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0de5d-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0de5d-149">See also</span></span>



[<span data-ttu-id="0de5d-150">IMAPITable::CollapseRow</span><span class="sxs-lookup"><span data-stu-id="0de5d-150">IMAPITable::CollapseRow</span></span>](imapitable-collapserow.md)
  
[<span data-ttu-id="0de5d-151">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0de5d-151">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="0de5d-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="0de5d-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

