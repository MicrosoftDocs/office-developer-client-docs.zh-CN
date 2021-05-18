---
title: IMAPITableSeekRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SeekRow
api_type:
- COM
ms.assetid: 93ac63ae-f254-45e1-a9b1-347d69d2ed9f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fbc990a8c962883aa07987b200d1d2fd55434f93
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413043"
---
# <a name="imapitableseekrow"></a><span data-ttu-id="3a163-103">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="3a163-103">IMAPITable::SeekRow</span></span>

  
  
<span data-ttu-id="3a163-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3a163-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3a163-105">将光标移到表格中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="3a163-105">Moves the cursor to a specific position in the table.</span></span>
  
```cpp
HRESULT SeekRow(
BOOKMARK bkOrigin,
LONG lRowCount,
LONG FAR * lplRowsSought
);
```

## <a name="parameters"></a><span data-ttu-id="3a163-106">参数</span><span class="sxs-lookup"><span data-stu-id="3a163-106">Parameters</span></span>

 <span data-ttu-id="3a163-107">_bkOrigin_</span><span class="sxs-lookup"><span data-stu-id="3a163-107">_bkOrigin_</span></span>
  
> <span data-ttu-id="3a163-108">[in]用于标识查找操作起始位置的书签。</span><span class="sxs-lookup"><span data-stu-id="3a163-108">[in] The bookmark identifying the starting position for the seek operation.</span></span> <span data-ttu-id="3a163-109">可以使用 [IMAPITable：：CreateBookmark](imapitable-createbookmark.md) 方法创建书签，也可以传递以下预定义值之一。</span><span class="sxs-lookup"><span data-stu-id="3a163-109">A bookmark can be created using the [IMAPITable::CreateBookmark](imapitable-createbookmark.md) method, or one of the following predefined values can be passed.</span></span> 
    
<span data-ttu-id="3a163-110">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="3a163-110">BOOKMARK_BEGINNING</span></span> 
  
> <span data-ttu-id="3a163-111">从表的开头开始查找操作。</span><span class="sxs-lookup"><span data-stu-id="3a163-111">Starts the seek operation from the beginning of the table.</span></span> 
    
<span data-ttu-id="3a163-112">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="3a163-112">BOOKMARK_CURRENT</span></span> 
  
> <span data-ttu-id="3a163-113">从光标所在的表格中的行开始查找操作。</span><span class="sxs-lookup"><span data-stu-id="3a163-113">Starts the seek operation from the row in the table where the cursor is located.</span></span> 
    
<span data-ttu-id="3a163-114">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="3a163-114">BOOKMARK_END</span></span> 
  
> <span data-ttu-id="3a163-115">从表的末尾开始查找操作。</span><span class="sxs-lookup"><span data-stu-id="3a163-115">Starts the seek operation from the end of the table.</span></span> 
    
 <span data-ttu-id="3a163-116">_lRowCount_</span><span class="sxs-lookup"><span data-stu-id="3a163-116">_lRowCount_</span></span>
  
> <span data-ttu-id="3a163-117">[in]要移动的行数的有签名计数，从  _bkOrigin_ 参数标识的书签开始。</span><span class="sxs-lookup"><span data-stu-id="3a163-117">[in] The signed count of the number of rows to move, starting from the bookmark identified by the  _bkOrigin_ parameter.</span></span> 
    
 <span data-ttu-id="3a163-118">_lplRowsS以_</span><span class="sxs-lookup"><span data-stu-id="3a163-118">_lplRowsSought_</span></span>
  
> <span data-ttu-id="3a163-119">[out]如果  _lRowCount_ 是输入上的有效指针  _，lplRowsS此操作_ 将指向在 seek 操作中处理的行数，其符号指示搜索方向、向前或向后方向。</span><span class="sxs-lookup"><span data-stu-id="3a163-119">[out] If  _lRowCount_ is a valid pointer on input,  _lplRowsSought_ points to the number of rows that were processed in the seek operation, the sign of which indicates the direction of search, forward or backward.</span></span> <span data-ttu-id="3a163-120">如果  _lRowCount_ 为负数，  _则 lplRowsS以负_ 数表示。</span><span class="sxs-lookup"><span data-stu-id="3a163-120">If  _lRowCount_ is negative, then  _lplRowsSought_ is negative.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3a163-121">返回值</span><span class="sxs-lookup"><span data-stu-id="3a163-121">Return value</span></span>

<span data-ttu-id="3a163-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a163-122">S_OK</span></span> 
  
> <span data-ttu-id="3a163-123">查找操作成功。</span><span class="sxs-lookup"><span data-stu-id="3a163-123">The seek operation was successful.</span></span>
    
<span data-ttu-id="3a163-124">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="3a163-124">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="3a163-125">正在进行另一个操作，以防止行寻找操作启动。</span><span class="sxs-lookup"><span data-stu-id="3a163-125">Another operation is in progress that prevents the row-seeking operation from starting.</span></span> <span data-ttu-id="3a163-126">应允许完成或停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="3a163-126">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="3a163-127">MAPI_E_INVALID_BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="3a163-127">MAPI_E_INVALID_BOOKMARK</span></span> 
  
> <span data-ttu-id="3a163-128">_bkOrigin_ 参数中指定的书签无效，因为它已删除或超出了请求的最后一行。</span><span class="sxs-lookup"><span data-stu-id="3a163-128">The bookmark specified in the  _bkOrigin_ parameter is invalid because it was removed or because it is beyond the last row requested.</span></span> 
    
<span data-ttu-id="3a163-129">MAPI_W_POSITION_CHANGED</span><span class="sxs-lookup"><span data-stu-id="3a163-129">MAPI_W_POSITION_CHANGED</span></span> 
  
> <span data-ttu-id="3a163-130">调用成功，但  _bkOrigin_ 参数中指定的书签不再与上次使用时在同一行上设置。</span><span class="sxs-lookup"><span data-stu-id="3a163-130">The call succeeded, but the bookmark specified in the  _bkOrigin_ parameter is no longer set at the same row as it was when it was last used.</span></span> <span data-ttu-id="3a163-131">如果尚未使用书签，则书签不再处于创建时的位置。</span><span class="sxs-lookup"><span data-stu-id="3a163-131">If the bookmark has not been used, it is no longer in the same position as it was when it was created.</span></span> <span data-ttu-id="3a163-132">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="3a163-132">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="3a163-133">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="3a163-133">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="3a163-134">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="3a163-134">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3a163-135">备注</span><span class="sxs-lookup"><span data-stu-id="3a163-135">Remarks</span></span>

<span data-ttu-id="3a163-136">**IMAPITable：：SeekRow** 方法为游标BOOKMARK_CURRENT一个位置。</span><span class="sxs-lookup"><span data-stu-id="3a163-136">The **IMAPITable::SeekRow** method establishes a new BOOKMARK_CURRENT position for the cursor.</span></span> <span data-ttu-id="3a163-137">_lRowCount_ 参数指示光标移动的行数和移动方向。</span><span class="sxs-lookup"><span data-stu-id="3a163-137">The  _lRowCount_ parameter indicates the number of rows that the cursor moves and the direction of movement.</span></span> 
  
<span data-ttu-id="3a163-138">如果生成的位置超出表格的最后一行，光标将位于最后一行之后。</span><span class="sxs-lookup"><span data-stu-id="3a163-138">If the resulting position is beyond the last row of the table, the cursor is positioned after the last row.</span></span> <span data-ttu-id="3a163-139">如果生成的位置在表格的第一行之前，光标将位于第一行的开头。</span><span class="sxs-lookup"><span data-stu-id="3a163-139">If the resulting position is before the first row of the table, the cursor is positioned at the beginning of the first row.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="3a163-140">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="3a163-140">Notes to implementers</span></span>

<span data-ttu-id="3a163-141">如果  _bkOrigin_ 指向的行在表中不再存在，并且您无法为书签建立新位置，则返回MAPI_E_INVALID_BOOKMARK。</span><span class="sxs-lookup"><span data-stu-id="3a163-141">If the row pointed to by  _bkOrigin_ no longer exists in the table and you cannot establish a new position for the bookmark, return MAPI_E_INVALID_BOOKMARK.</span></span> <span data-ttu-id="3a163-142">如果  _bkOrigin_ 指向的行不再存在，并且您可以为书签建立一个新位置，则返回MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="3a163-142">If the row pointed to by  _bkOrigin_ no longer exists and you can establish a new position for the bookmark, return MAPI_W_POSITION_CHANGED.</span></span> 
  
<span data-ttu-id="3a163-143">指向折叠在表视图中的行的书签仍可以使用。</span><span class="sxs-lookup"><span data-stu-id="3a163-143">A bookmark pointing to a row that is collapsed out of the table view can still be used.</span></span> <span data-ttu-id="3a163-144">如果调用方尝试将光标移动到此类书签，将光标移到下一个可见行，并返回MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="3a163-144">If the caller attempts to move the cursor to such a bookmark, move the cursor to the next visible row and return MAPI_W_POSITION_CHANGED.</span></span> 
  
<span data-ttu-id="3a163-145">您可以在使用时或折叠行时移动折叠在视图外的位置的书签。</span><span class="sxs-lookup"><span data-stu-id="3a163-145">You can move bookmarks for positions collapsed out of view, either at the time of use or at the time that the row is collapsed.</span></span> <span data-ttu-id="3a163-146">如果在折叠行时移动了书签，则保留书签中的一个位，以指示书签自上次使用以来是否移动过，或者，如果从未使用过，则自创建以来。</span><span class="sxs-lookup"><span data-stu-id="3a163-146">If a bookmark is moved at the time that the row is collapsed, keep a bit in the bookmark that indicates whether the bookmark has moved since its last use or, if it has never been used, since its creation.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="3a163-147">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3a163-147">Notes to callers</span></span>

<span data-ttu-id="3a163-148">若要指示 **SeekRow** 向后移动，在  _lRowCount_ 中传递负值。</span><span class="sxs-lookup"><span data-stu-id="3a163-148">To indicate a backward move for **SeekRow**, pass a negative value in  _lRowCount_.</span></span> <span data-ttu-id="3a163-149">若要搜索到表的开头，在  _lRowCount_ 中传递零，将值BOOKMARK_BEGINNING  _bkOrigin 中_。</span><span class="sxs-lookup"><span data-stu-id="3a163-149">To search to the beginning of the table, pass zero in  _lRowCount_ and the value BOOKMARK_BEGINNING in  _bkOrigin_.</span></span> 
  
<span data-ttu-id="3a163-150">如果表中有很多行 **，SeekRow** 操作可能会很慢。</span><span class="sxs-lookup"><span data-stu-id="3a163-150">If there are lots of rows in the table, the **SeekRow** operation can be slow.</span></span> <span data-ttu-id="3a163-151">如果您需要在  _lplRowsS操作_ 参数的内容中返回行计数，则也会影响性能。</span><span class="sxs-lookup"><span data-stu-id="3a163-151">Performance can also be affected if you require a row count to be returned in the contents of the  _lplRowsSought_ parameter.</span></span> 
  
 <span data-ttu-id="3a163-152">**SeekRow 返回 lRowCount** 指向的变量中实际搜索的行数（正数或  _负数_）。</span><span class="sxs-lookup"><span data-stu-id="3a163-152">**SeekRow** returns the number of rows actually searched through, positive or negative, in the variable pointed to by  _lRowCount_.</span></span> <span data-ttu-id="3a163-153">在普通操作中，它应返回与 _lRowCount_ 传入的 _lplRowsS操作_ 相同的值，除非搜索到达表的开头或结尾。</span><span class="sxs-lookup"><span data-stu-id="3a163-153">In ordinary operation, it should return the same value for  _lplRowsSought_ as passed in for  _lRowCount_, unless the search reached the beginning or end of the table.</span></span> 
  
<span data-ttu-id="3a163-154">不要将  _lRowCount_ 设置为大于 50 的数。</span><span class="sxs-lookup"><span data-stu-id="3a163-154">Do not set  _lRowCount_ to a number greater than 50.</span></span> <span data-ttu-id="3a163-155">若要查找更多行，请使用 [IMAPITable：：SeekRowApprox](imapitable-seekrowapprox.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="3a163-155">To seek through a larger number of rows, use the [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3a163-156">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="3a163-156">MFCMAPI reference</span></span>

<span data-ttu-id="3a163-157">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3a163-157">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3a163-158">**文件**</span><span class="sxs-lookup"><span data-stu-id="3a163-158">**File**</span></span>|<span data-ttu-id="3a163-159">**函数**</span><span class="sxs-lookup"><span data-stu-id="3a163-159">**Function**</span></span>|<span data-ttu-id="3a163-160">**备注**</span><span class="sxs-lookup"><span data-stu-id="3a163-160">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a163-161">MAPIProcessor.cpp</span><span class="sxs-lookup"><span data-stu-id="3a163-161">MAPIProcessor.cpp</span></span>  <br/> |<span data-ttu-id="3a163-162">CMAPIProcessor：:P rocessMailboxTable</span><span class="sxs-lookup"><span data-stu-id="3a163-162">CMAPIProcessor::ProcessMailboxTable</span></span>  <br/> |<span data-ttu-id="3a163-163">MFCMAPI 使用 **IMAPITable：：SeekRow** 方法来在处理之前找到表的开头。</span><span class="sxs-lookup"><span data-stu-id="3a163-163">MFCMAPI uses the **IMAPITable::SeekRow** method to locate the beginning of the table before processing.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3a163-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a163-164">See also</span></span>



[<span data-ttu-id="3a163-165">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="3a163-165">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="3a163-166">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="3a163-166">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
  
[<span data-ttu-id="3a163-167">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="3a163-167">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="3a163-168">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="3a163-168">IMAPITable::SeekRowApprox</span></span>](imapitable-seekrowapprox.md)
  
[<span data-ttu-id="3a163-169">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3a163-169">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="3a163-170">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="3a163-170">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

