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
# <a name="imapitableseekrow"></a><span data-ttu-id="d78b2-103">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="d78b2-103">IMAPITable::SeekRow</span></span>

  
  
<span data-ttu-id="d78b2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d78b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d78b2-105">将光标移到表中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="d78b2-105">Moves the cursor to a specific position in the table.</span></span>
  
```cpp
HRESULT SeekRow(
BOOKMARK bkOrigin,
LONG lRowCount,
LONG FAR * lplRowsSought
);
```

## <a name="parameters"></a><span data-ttu-id="d78b2-106">参数</span><span class="sxs-lookup"><span data-stu-id="d78b2-106">Parameters</span></span>

 <span data-ttu-id="d78b2-107">_bkOrigin_</span><span class="sxs-lookup"><span data-stu-id="d78b2-107">_bkOrigin_</span></span>
  
> <span data-ttu-id="d78b2-108">实时用于标识查找操作的起始位置的书签。</span><span class="sxs-lookup"><span data-stu-id="d78b2-108">[in] The bookmark identifying the starting position for the seek operation.</span></span> <span data-ttu-id="d78b2-109">可以使用[IMAPITable:: CreateBookmark](imapitable-createbookmark.md)方法创建书签, 或者可以传递下列预定义值之一。</span><span class="sxs-lookup"><span data-stu-id="d78b2-109">A bookmark can be created using the [IMAPITable::CreateBookmark](imapitable-createbookmark.md) method, or one of the following predefined values can be passed.</span></span> 
    
<span data-ttu-id="d78b2-110">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="d78b2-110">BOOKMARK_BEGINNING</span></span> 
  
> <span data-ttu-id="d78b2-111">从表的开头开始查找操作。</span><span class="sxs-lookup"><span data-stu-id="d78b2-111">Starts the seek operation from the beginning of the table.</span></span> 
    
<span data-ttu-id="d78b2-112">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="d78b2-112">BOOKMARK_CURRENT</span></span> 
  
> <span data-ttu-id="d78b2-113">从游标所在的表的行中启动 seek 操作。</span><span class="sxs-lookup"><span data-stu-id="d78b2-113">Starts the seek operation from the row in the table where the cursor is located.</span></span> 
    
<span data-ttu-id="d78b2-114">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="d78b2-114">BOOKMARK_END</span></span> 
  
> <span data-ttu-id="d78b2-115">从表的末尾开始查找操作。</span><span class="sxs-lookup"><span data-stu-id="d78b2-115">Starts the seek operation from the end of the table.</span></span> 
    
 <span data-ttu-id="d78b2-116">_lRowCount_</span><span class="sxs-lookup"><span data-stu-id="d78b2-116">_lRowCount_</span></span>
  
> <span data-ttu-id="d78b2-117">实时从_bkOrigin_参数标识的书签开始要移动的行数的已签名计数。</span><span class="sxs-lookup"><span data-stu-id="d78b2-117">[in] The signed count of the number of rows to move, starting from the bookmark identified by the  _bkOrigin_ parameter.</span></span> 
    
 <span data-ttu-id="d78b2-118">_lplRowsSought_</span><span class="sxs-lookup"><span data-stu-id="d78b2-118">_lplRowsSought_</span></span>
  
> <span data-ttu-id="d78b2-119">排除如果_lRowCount_是输入上的有效指针, 则_lplRowsSought_指向在 seek 操作中处理的行数、指示搜索方向的符号 (向前或向后)。</span><span class="sxs-lookup"><span data-stu-id="d78b2-119">[out] If  _lRowCount_ is a valid pointer on input,  _lplRowsSought_ points to the number of rows that were processed in the seek operation, the sign of which indicates the direction of search, forward or backward.</span></span> <span data-ttu-id="d78b2-120">如果_lRowCount_为负, 则_lplRowsSought_为负。</span><span class="sxs-lookup"><span data-stu-id="d78b2-120">If  _lRowCount_ is negative, then  _lplRowsSought_ is negative.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d78b2-121">返回值</span><span class="sxs-lookup"><span data-stu-id="d78b2-121">Return value</span></span>

<span data-ttu-id="d78b2-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="d78b2-122">S_OK</span></span> 
  
> <span data-ttu-id="d78b2-123">seek 操作成功完成。</span><span class="sxs-lookup"><span data-stu-id="d78b2-123">The seek operation was successful.</span></span>
    
<span data-ttu-id="d78b2-124">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="d78b2-124">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="d78b2-125">正在进行另一个操作, 以阻止启动行查找操作。</span><span class="sxs-lookup"><span data-stu-id="d78b2-125">Another operation is in progress that prevents the row-seeking operation from starting.</span></span> <span data-ttu-id="d78b2-126">应允许正在进行的操作完成, 或者应已停止。</span><span class="sxs-lookup"><span data-stu-id="d78b2-126">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="d78b2-127">MAPI_E_INVALID_BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="d78b2-127">MAPI_E_INVALID_BOOKMARK</span></span> 
  
> <span data-ttu-id="d78b2-128">在_bkOrigin_参数中指定的书签无效, 因为它已被删除或超出了最后请求的行。</span><span class="sxs-lookup"><span data-stu-id="d78b2-128">The bookmark specified in the  _bkOrigin_ parameter is invalid because it was removed or because it is beyond the last row requested.</span></span> 
    
<span data-ttu-id="d78b2-129">MAPI_W_POSITION_CHANGED</span><span class="sxs-lookup"><span data-stu-id="d78b2-129">MAPI_W_POSITION_CHANGED</span></span> 
  
> <span data-ttu-id="d78b2-130">调用成功, 但在_bkOrigin_参数中指定的书签不再设置为与上次使用时相同的行。</span><span class="sxs-lookup"><span data-stu-id="d78b2-130">The call succeeded, but the bookmark specified in the  _bkOrigin_ parameter is no longer set at the same row as it was when it was last used.</span></span> <span data-ttu-id="d78b2-131">如果尚未使用该书签, 它将不再位于创建时的位置。</span><span class="sxs-lookup"><span data-stu-id="d78b2-131">If the bookmark has not been used, it is no longer in the same position as it was when it was created.</span></span> <span data-ttu-id="d78b2-132">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="d78b2-132">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="d78b2-133">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="d78b2-133">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="d78b2-134">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="d78b2-134">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d78b2-135">说明</span><span class="sxs-lookup"><span data-stu-id="d78b2-135">Remarks</span></span>

<span data-ttu-id="d78b2-136">**IMAPITable:: SeekRow**方法为游标建立了一个新的 BOOKMARK_CURRENT 位置。</span><span class="sxs-lookup"><span data-stu-id="d78b2-136">The **IMAPITable::SeekRow** method establishes a new BOOKMARK_CURRENT position for the cursor.</span></span> <span data-ttu-id="d78b2-137">_lRowCount_参数指示光标移动的行数和移动方向。</span><span class="sxs-lookup"><span data-stu-id="d78b2-137">The  _lRowCount_ parameter indicates the number of rows that the cursor moves and the direction of movement.</span></span> 
  
<span data-ttu-id="d78b2-138">如果生成的位置超出了表的最后一行, 则将光标定位在最后一行之后。</span><span class="sxs-lookup"><span data-stu-id="d78b2-138">If the resulting position is beyond the last row of the table, the cursor is positioned after the last row.</span></span> <span data-ttu-id="d78b2-139">如果生成的位置在表的第一行之前, 则光标定位在第一行的开头。</span><span class="sxs-lookup"><span data-stu-id="d78b2-139">If the resulting position is before the first row of the table, the cursor is positioned at the beginning of the first row.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="d78b2-140">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="d78b2-140">Notes to implementers</span></span>

<span data-ttu-id="d78b2-141">如果_bkOrigin_中不再存在指向的行, 并且无法为该书签建立新的位置, 请返回 MAPI_E_INVALID_BOOKMARK。</span><span class="sxs-lookup"><span data-stu-id="d78b2-141">If the row pointed to by  _bkOrigin_ no longer exists in the table and you cannot establish a new position for the bookmark, return MAPI_E_INVALID_BOOKMARK.</span></span> <span data-ttu-id="d78b2-142">如果_bkOrigin_所指向的行不再存在, 并且您可以为该书签建立一个新位置, 请返回 MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="d78b2-142">If the row pointed to by  _bkOrigin_ no longer exists and you can establish a new position for the bookmark, return MAPI_W_POSITION_CHANGED.</span></span> 
  
<span data-ttu-id="d78b2-143">仍然可以使用指向折叠在表视图之外的行的书签。</span><span class="sxs-lookup"><span data-stu-id="d78b2-143">A bookmark pointing to a row that is collapsed out of the table view can still be used.</span></span> <span data-ttu-id="d78b2-144">如果调用方尝试将光标移动到此类书签, 请将光标移到下一个可见的行, 并返回 MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="d78b2-144">If the caller attempts to move the cursor to such a bookmark, move the cursor to the next visible row and return MAPI_W_POSITION_CHANGED.</span></span> 
  
<span data-ttu-id="d78b2-145">您可以在使用时或在行折叠时, 将位置的书签移动到视图之外。</span><span class="sxs-lookup"><span data-stu-id="d78b2-145">You can move bookmarks for positions collapsed out of view, either at the time of use or at the time that the row is collapsed.</span></span> <span data-ttu-id="d78b2-146">如果在折叠行时移动书签, 则在书签中保留一位, 以指示该书签自上次使用后是否已移动, 或者, 自创建以来, 如果从未使用过该书签。</span><span class="sxs-lookup"><span data-stu-id="d78b2-146">If a bookmark is moved at the time that the row is collapsed, keep a bit in the bookmark that indicates whether the bookmark has moved since its last use or, if it has never been used, since its creation.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="d78b2-147">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d78b2-147">Notes to callers</span></span>

<span data-ttu-id="d78b2-148">若要指示**SeekRow**的后向移动, 请在_lRowCount_中传递一个负值。</span><span class="sxs-lookup"><span data-stu-id="d78b2-148">To indicate a backward move for **SeekRow**, pass a negative value in  _lRowCount_.</span></span> <span data-ttu-id="d78b2-149">若要搜索到表的开头, 请在_lRowCount_中传递零, 并在_bkOrigin_中传递值 BOOKMARK_BEGINNING。</span><span class="sxs-lookup"><span data-stu-id="d78b2-149">To search to the beginning of the table, pass zero in  _lRowCount_ and the value BOOKMARK_BEGINNING in  _bkOrigin_.</span></span> 
  
<span data-ttu-id="d78b2-150">如果表中有很多行, 则**SeekRow**操作可能会很慢。</span><span class="sxs-lookup"><span data-stu-id="d78b2-150">If there are lots of rows in the table, the **SeekRow** operation can be slow.</span></span> <span data-ttu-id="d78b2-151">如果您需要在_lplRowsSought_参数的内容中返回行数, 也会影响性能。</span><span class="sxs-lookup"><span data-stu-id="d78b2-151">Performance can also be affected if you require a row count to be returned in the contents of the  _lplRowsSought_ parameter.</span></span> 
  
 <span data-ttu-id="d78b2-152">**SeekRow**返回在_lRowCount_指向的变量中实际搜索的行数 (正数或负数)。</span><span class="sxs-lookup"><span data-stu-id="d78b2-152">**SeekRow** returns the number of rows actually searched through, positive or negative, in the variable pointed to by  _lRowCount_.</span></span> <span data-ttu-id="d78b2-153">在普通操作中, 它应为在_lRowCount_中传递的_lplRowsSought_返回相同的值, 除非搜索到达表的开头或结尾。</span><span class="sxs-lookup"><span data-stu-id="d78b2-153">In ordinary operation, it should return the same value for  _lplRowsSought_ as passed in for  _lRowCount_, unless the search reached the beginning or end of the table.</span></span> 
  
<span data-ttu-id="d78b2-154">请勿将_lRowCount_设置为大于50的数字。</span><span class="sxs-lookup"><span data-stu-id="d78b2-154">Do not set  _lRowCount_ to a number greater than 50.</span></span> <span data-ttu-id="d78b2-155">若要查找更多的行, 请使用[IMAPITable:: SeekRowApprox](imapitable-seekrowapprox.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d78b2-155">To seek through a larger number of rows, use the [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="d78b2-156">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="d78b2-156">MFCMAPI reference</span></span>

<span data-ttu-id="d78b2-157">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d78b2-157">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d78b2-158">**文件**</span><span class="sxs-lookup"><span data-stu-id="d78b2-158">**File**</span></span>|<span data-ttu-id="d78b2-159">**函数**</span><span class="sxs-lookup"><span data-stu-id="d78b2-159">**Function**</span></span>|<span data-ttu-id="d78b2-160">**备注**</span><span class="sxs-lookup"><span data-stu-id="d78b2-160">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d78b2-161">MAPIProcessor</span><span class="sxs-lookup"><span data-stu-id="d78b2-161">MAPIProcessor.cpp</span></span>  <br/> |<span data-ttu-id="d78b2-162">CMAPIProcessor::P rocessmailboxtable</span><span class="sxs-lookup"><span data-stu-id="d78b2-162">CMAPIProcessor::ProcessMailboxTable</span></span>  <br/> |<span data-ttu-id="d78b2-163">MFCMAPI 使用**IMAPITable:: SeekRow**方法在处理前查找表的开头。</span><span class="sxs-lookup"><span data-stu-id="d78b2-163">MFCMAPI uses the **IMAPITable::SeekRow** method to locate the beginning of the table before processing.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d78b2-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d78b2-164">See also</span></span>



[<span data-ttu-id="d78b2-165">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="d78b2-165">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="d78b2-166">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="d78b2-166">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
  
[<span data-ttu-id="d78b2-167">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="d78b2-167">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="d78b2-168">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="d78b2-168">IMAPITable::SeekRowApprox</span></span>](imapitable-seekrowapprox.md)
  
[<span data-ttu-id="d78b2-169">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d78b2-169">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="d78b2-170">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d78b2-170">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

