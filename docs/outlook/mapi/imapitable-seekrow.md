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
ms.openlocfilehash: 143ca03a5e98d638d29394f5c0803e349ab4de25
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775717"
---
# <a name="imapitableseekrow"></a><span data-ttu-id="7ab7f-103">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="7ab7f-103">IMAPITable::SeekRow</span></span>

  
  
<span data-ttu-id="7ab7f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7ab7f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7ab7f-105">将光标移到表中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-105">Moves the cursor to a specific position in the table.</span></span>
  
```cpp
HRESULT SeekRow(
BOOKMARK bkOrigin,
LONG lRowCount,
LONG FAR * lplRowsSought
);
```

## <a name="parameters"></a><span data-ttu-id="7ab7f-106">参数</span><span class="sxs-lookup"><span data-stu-id="7ab7f-106">Parameters</span></span>

 <span data-ttu-id="7ab7f-107">_bkOrigin_</span><span class="sxs-lookup"><span data-stu-id="7ab7f-107">_bkOrigin_</span></span>
  
> <span data-ttu-id="7ab7f-108">[in]书签标识的查找操作的起始位置。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-108">[in] The bookmark identifying the starting position for the seek operation.</span></span> <span data-ttu-id="7ab7f-109">可以使用[IMAPITable::CreateBookmark](imapitable-createbookmark.md)方法中，创建一个书签，也可以传递预定义的以下值之一。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-109">A bookmark can be created using the [IMAPITable::CreateBookmark](imapitable-createbookmark.md) method, or one of the following predefined values can be passed.</span></span> 
    
<span data-ttu-id="7ab7f-110">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="7ab7f-110">BOOKMARK_BEGINNING</span></span> 
  
> <span data-ttu-id="7ab7f-111">从表的开头开始查找操作。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-111">Starts the seek operation from the beginning of the table.</span></span> 
    
<span data-ttu-id="7ab7f-112">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="7ab7f-112">BOOKMARK_CURRENT</span></span> 
  
> <span data-ttu-id="7ab7f-113">启动搜索操作从光标所在的表中的一行。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-113">Starts the seek operation from the row in the table where the cursor is located.</span></span> 
    
<span data-ttu-id="7ab7f-114">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="7ab7f-114">BOOKMARK_END</span></span> 
  
> <span data-ttu-id="7ab7f-115">从表末尾开始查找操作。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-115">Starts the seek operation from the end of the table.</span></span> 
    
 <span data-ttu-id="7ab7f-116">_lRowCount_</span><span class="sxs-lookup"><span data-stu-id="7ab7f-116">_lRowCount_</span></span>
  
> <span data-ttu-id="7ab7f-117">[in]要移动的行数的签名的计数，从该书签开始_bkOrigin_参数标识。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-117">[in] The signed count of the number of rows to move, starting from the bookmark identified by the  _bkOrigin_ parameter.</span></span> 
    
 <span data-ttu-id="7ab7f-118">_lplRowsSought_</span><span class="sxs-lookup"><span data-stu-id="7ab7f-118">_lplRowsSought_</span></span>
  
> <span data-ttu-id="7ab7f-119">[输出]如果_lRowCount_上输入， _lplRowsSought_指向处理 seek 操作中的行数的有效指针，其中登录将向前或向后指示搜索的方向。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-119">[out] If  _lRowCount_ is a valid pointer on input,  _lplRowsSought_ points to the number of rows that were processed in the seek operation, the sign of which indicates the direction of search, forward or backward.</span></span> <span data-ttu-id="7ab7f-120">如果_lRowCount_为负数，则_lplRowsSought_为负数。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-120">If  _lRowCount_ is negative, then  _lplRowsSought_ is negative.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7ab7f-121">返回值</span><span class="sxs-lookup"><span data-stu-id="7ab7f-121">Return value</span></span>

<span data-ttu-id="7ab7f-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ab7f-122">S_OK</span></span> 
  
> <span data-ttu-id="7ab7f-123">Seek 操作已成功。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-123">The seek operation was successful.</span></span>
    
<span data-ttu-id="7ab7f-124">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="7ab7f-124">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="7ab7f-125">正在进行中，可以防止起始行寻求操作是另一个操作。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-125">Another operation is in progress that prevents the row-seeking operation from starting.</span></span> <span data-ttu-id="7ab7f-126">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-126">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
<span data-ttu-id="7ab7f-127">MAPI_E_INVALID_BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="7ab7f-127">MAPI_E_INVALID_BOOKMARK</span></span> 
  
> <span data-ttu-id="7ab7f-128">_BkOrigin_参数中指定的书签无效，因为它已被删除或因为它超出请求的最后一行。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-128">The bookmark specified in the  _bkOrigin_ parameter is invalid because it was removed or because it is beyond the last row requested.</span></span> 
    
<span data-ttu-id="7ab7f-129">MAPI_W_POSITION_CHANGED</span><span class="sxs-lookup"><span data-stu-id="7ab7f-129">MAPI_W_POSITION_CHANGED</span></span> 
  
> <span data-ttu-id="7ab7f-130">调用成功，但上次使用时不再在同一行设置_bkOrigin_参数中指定的书签。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-130">The call succeeded, but the bookmark specified in the  _bkOrigin_ parameter is no longer set at the same row as it was when it was last used.</span></span> <span data-ttu-id="7ab7f-131">如果未用过该书签，则不再在同一位置与创建它时一样。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-131">If the bookmark has not been used, it is no longer in the same position as it was when it was created.</span></span> <span data-ttu-id="7ab7f-132">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-132">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="7ab7f-133">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-133">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="7ab7f-134">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-134">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7ab7f-135">说明</span><span class="sxs-lookup"><span data-stu-id="7ab7f-135">Remarks</span></span>

<span data-ttu-id="7ab7f-136">**IMAPITable::SeekRow**方法建立新 BOOKMARK_CURRENT 位置的指针。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-136">The **IMAPITable::SeekRow** method establishes a new BOOKMARK_CURRENT position for the cursor.</span></span> <span data-ttu-id="7ab7f-137">_LRowCount_参数指示光标移动的行和移动的方向的数量。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-137">The  _lRowCount_ parameter indicates the number of rows that the cursor moves and the direction of movement.</span></span> 
  
<span data-ttu-id="7ab7f-138">如果最终位置超出最后一行的表，将光标定位的最后一行之后。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-138">If the resulting position is beyond the last row of the table, the cursor is positioned after the last row.</span></span> <span data-ttu-id="7ab7f-139">如果结果位置表的第一行之前，光标位于第一行的开头。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-139">If the resulting position is before the first row of the table, the cursor is positioned at the beginning of the first row.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="7ab7f-140">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="7ab7f-140">Notes to implementers</span></span>

<span data-ttu-id="7ab7f-141">如果所指的_bkOrigin_行不再存在表中，但无法建立的书签的新位置，则返回 MAPI_E_INVALID_BOOKMARK。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-141">If the row pointed to by  _bkOrigin_ no longer exists in the table and you cannot establish a new position for the bookmark, return MAPI_E_INVALID_BOOKMARK.</span></span> <span data-ttu-id="7ab7f-142">如果所指的_bkOrigin_行不再存在并且可以建立的书签的新位置，则返回 MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-142">If the row pointed to by  _bkOrigin_ no longer exists and you can establish a new position for the bookmark, return MAPI_W_POSITION_CHANGED.</span></span> 
  
<span data-ttu-id="7ab7f-143">仍可用于指向折叠表视图的行的书签。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-143">A bookmark pointing to a row that is collapsed out of the table view can still be used.</span></span> <span data-ttu-id="7ab7f-144">如果呼叫者尝试将光标移到此类书签，将光标移到下一个可见的行，并返回 MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-144">If the caller attempts to move the cursor to such a bookmark, move the cursor to the next visible row and return MAPI_W_POSITION_CHANGED.</span></span> 
  
<span data-ttu-id="7ab7f-145">您可以移动折叠视图，使用时，也可以在折叠行时的位置的书签。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-145">You can move bookmarks for positions collapsed out of view, either at the time of use or at the time that the row is collapsed.</span></span> <span data-ttu-id="7ab7f-146">如果折叠行次移动一个书签，有点保留指示书签具有其最后一次使用以来移动还是，如果它具有永远不会使用情况自其创建的书签。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-146">If a bookmark is moved at the time that the row is collapsed, keep a bit in the bookmark that indicates whether the bookmark has moved since its last use or, if it has never been used, since its creation.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="7ab7f-147">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7ab7f-147">Notes to callers</span></span>

<span data-ttu-id="7ab7f-148">若要指示**SeekRow**向后移动，请在_lRowCount_传递负值。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-148">To indicate a backward move for **SeekRow**, pass a negative value in  _lRowCount_.</span></span> <span data-ttu-id="7ab7f-149">若要搜索的表开头，传递零_lRowCount_和_bkOrigin_中的值 BOOKMARK_BEGINNING 中。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-149">To search to the beginning of the table, pass zero in  _lRowCount_ and the value BOOKMARK_BEGINNING in  _bkOrigin_.</span></span> 
  
<span data-ttu-id="7ab7f-150">如果有多个表中的行， **SeekRow**操作会很慢。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-150">If there are lots of rows in the table, the **SeekRow** operation can be slow.</span></span> <span data-ttu-id="7ab7f-151">如果您需要在_lplRowsSought_参数的内容中返回的行数，还会影响性能。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-151">Performance can also be affected if you require a row count to be returned in the contents of the  _lplRowsSought_ parameter.</span></span> 
  
 <span data-ttu-id="7ab7f-152">**SeekRow**实际通过搜索、 正数或负数，变量所指的_lRowCount_中返回行的数。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-152">**SeekRow** returns the number of rows actually searched through, positive or negative, in the variable pointed to by  _lRowCount_.</span></span> <span data-ttu-id="7ab7f-153">在普通操作中，它应返回_lplRowsSought_相同的值为_lRowCount_，如除非搜索达到的开头或结尾的表。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-153">In ordinary operation, it should return the same value for  _lplRowsSought_ as passed in for  _lRowCount_, unless the search reached the beginning or end of the table.</span></span> 
  
<span data-ttu-id="7ab7f-154">不要设置_lRowCount_为数大于 50。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-154">Do not set  _lRowCount_ to a number greater than 50.</span></span> <span data-ttu-id="7ab7f-155">若要 seek 通过更多的行，请使用[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-155">To seek through a larger number of rows, use the [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7ab7f-156">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="7ab7f-156">MFCMAPI reference</span></span>

<span data-ttu-id="7ab7f-157">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-157">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7ab7f-158">**文件**</span><span class="sxs-lookup"><span data-stu-id="7ab7f-158">**File**</span></span>|<span data-ttu-id="7ab7f-159">**函数**</span><span class="sxs-lookup"><span data-stu-id="7ab7f-159">**Function**</span></span>|<span data-ttu-id="7ab7f-160">**Comment**</span><span class="sxs-lookup"><span data-stu-id="7ab7f-160">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ab7f-161">MAPIProcessor.cpp</span><span class="sxs-lookup"><span data-stu-id="7ab7f-161">MAPIProcessor.cpp</span></span>  <br/> |<span data-ttu-id="7ab7f-162">CMAPIProcessor::ProcessMailboxTable</span><span class="sxs-lookup"><span data-stu-id="7ab7f-162">CMAPIProcessor::ProcessMailboxTable</span></span>  <br/> |<span data-ttu-id="7ab7f-163">MFCMAPI 使用**IMAPITable::SeekRow**方法查找表，然后处理的开头。</span><span class="sxs-lookup"><span data-stu-id="7ab7f-163">MFCMAPI uses the **IMAPITable::SeekRow** method to locate the beginning of the table before processing.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7ab7f-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ab7f-164">See also</span></span>



[<span data-ttu-id="7ab7f-165">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="7ab7f-165">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="7ab7f-166">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="7ab7f-166">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
  
[<span data-ttu-id="7ab7f-167">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="7ab7f-167">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="7ab7f-168">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="7ab7f-168">IMAPITable::SeekRowApprox</span></span>](imapitable-seekrowapprox.md)
  
[<span data-ttu-id="7ab7f-169">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7ab7f-169">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="7ab7f-170">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7ab7f-170">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

