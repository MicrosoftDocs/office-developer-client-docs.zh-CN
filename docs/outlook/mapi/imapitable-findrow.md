---
title: IMAPITableFindRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.FindRow
api_type:
- COM
ms.assetid: 6511368c-9777-497e-9eea-cf390c04b92e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a5364af229721d101f38d2f054f528169b48c09e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429570"
---
# <a name="imapitablefindrow"></a><span data-ttu-id="bf897-103">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="bf897-103">IMAPITable::FindRow</span></span>

  
  
<span data-ttu-id="bf897-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bf897-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bf897-105">查找表中与特定搜索条件匹配的下一行，并移动光标到该行。</span><span class="sxs-lookup"><span data-stu-id="bf897-105">Finds the next row in a table that matches specific search criteria and moves the cursor to that row.</span></span>
  
```cpp
HRESULT FindRow(
LPSRestriction lpRestriction,
BOOKMARK BkOrigin,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="bf897-106">参数</span><span class="sxs-lookup"><span data-stu-id="bf897-106">Parameters</span></span>

 <span data-ttu-id="bf897-107">_lpRestriction_</span><span class="sxs-lookup"><span data-stu-id="bf897-107">_lpRestriction_</span></span>
  
> <span data-ttu-id="bf897-108">[in]指向描述 [搜索条件的 SRestriction](srestriction.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="bf897-108">[in] A pointer to an [SRestriction](srestriction.md) structure that describes the search criteria.</span></span> 
    
 <span data-ttu-id="bf897-109">_BkOrigin_</span><span class="sxs-lookup"><span data-stu-id="bf897-109">_BkOrigin_</span></span>
  
> <span data-ttu-id="bf897-110">[in]一个书签，用于标识 **FindRow 应** 开始搜索的行。</span><span class="sxs-lookup"><span data-stu-id="bf897-110">[in] A bookmark identifying the row where **FindRow** should begin its search.</span></span> <span data-ttu-id="bf897-111">可以使用 [IMAPITable：：CreateBookmark](imapitable-createbookmark.md) 方法创建书签，也可以传递以下预定义值之一。</span><span class="sxs-lookup"><span data-stu-id="bf897-111">A bookmark can be created using the [IMAPITable::CreateBookmark](imapitable-createbookmark.md) method, or one of the following predefined values can be passed.</span></span> 
    
<span data-ttu-id="bf897-112">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="bf897-112">BOOKMARK_BEGINNING</span></span> 
  
> <span data-ttu-id="bf897-113">从表开头搜索。</span><span class="sxs-lookup"><span data-stu-id="bf897-113">Searches from the beginning of the table.</span></span> 
    
<span data-ttu-id="bf897-114">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="bf897-114">BOOKMARK_CURRENT</span></span> 
  
> <span data-ttu-id="bf897-115">从光标所在的表格中的行进行搜索。</span><span class="sxs-lookup"><span data-stu-id="bf897-115">Searches from the row in the table where the cursor is located.</span></span> 
    
<span data-ttu-id="bf897-116">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="bf897-116">BOOKMARK_END</span></span> 
  
> <span data-ttu-id="bf897-117">从表末尾搜索。</span><span class="sxs-lookup"><span data-stu-id="bf897-117">Searches from the end of the table.</span></span> 
    
 <span data-ttu-id="bf897-118">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bf897-118">_ulFlags_</span></span>
  
> <span data-ttu-id="bf897-119">[in]控制搜索方向的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="bf897-119">[in] A bitmask of flags that controls the direction of the search.</span></span> <span data-ttu-id="bf897-120">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="bf897-120">The following flag can be set:</span></span>
    
<span data-ttu-id="bf897-121">DIR_BACKWARD</span><span class="sxs-lookup"><span data-stu-id="bf897-121">DIR_BACKWARD</span></span> 
  
> <span data-ttu-id="bf897-122">从书签标识的行向后搜索。</span><span class="sxs-lookup"><span data-stu-id="bf897-122">Searches backward from the row identified by the bookmark.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bf897-123">返回值</span><span class="sxs-lookup"><span data-stu-id="bf897-123">Return value</span></span>

<span data-ttu-id="bf897-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf897-124">S_OK</span></span> 
  
> <span data-ttu-id="bf897-125">查找操作成功。</span><span class="sxs-lookup"><span data-stu-id="bf897-125">The find operation was successful.</span></span>
    
<span data-ttu-id="bf897-126">MAPI_E_INVALID_BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="bf897-126">MAPI_E_INVALID_BOOKMARK</span></span> 
  
> <span data-ttu-id="bf897-127">_BkOrigin_ 参数中的书签无效，因为它已被删除或超出请求的最后一行。</span><span class="sxs-lookup"><span data-stu-id="bf897-127">The bookmark in the  _BkOrigin_ parameter is invalid because it has been removed or because it is beyond the last row requested.</span></span> 
    
<span data-ttu-id="bf897-128">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="bf897-128">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="bf897-129">未找到与限制匹配的行。</span><span class="sxs-lookup"><span data-stu-id="bf897-129">No rows were found that matched the restriction.</span></span>
    
<span data-ttu-id="bf897-130">MAPI_W_POSITION_CHANGED</span><span class="sxs-lookup"><span data-stu-id="bf897-130">MAPI_W_POSITION_CHANGED</span></span>
  
> <span data-ttu-id="bf897-131">调用成功，但操作中使用的书签不再与上次使用时在同一行上设置;如果尚未使用书签，则它不再处于创建时的位置。</span><span class="sxs-lookup"><span data-stu-id="bf897-131">The call succeeded, but the bookmark used in the operation is no longer set at the same row as when it was last used; if the bookmark has not been used, it is no longer in the same position as when it was created.</span></span> <span data-ttu-id="bf897-132">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="bf897-132">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="bf897-133">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="bf897-133">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="bf897-134">请参阅 [使用宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="bf897-134">See [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bf897-135">备注</span><span class="sxs-lookup"><span data-stu-id="bf897-135">Remarks</span></span>

<span data-ttu-id="bf897-136">**IMAPITable：：FindRow** 方法查找表格中的第一行，以匹配 _lpRestriction_ 参数指向的 **SRestriction** 结构中描述的一组搜索条件。</span><span class="sxs-lookup"><span data-stu-id="bf897-136">The **IMAPITable::FindRow** method locates the first row in the table to match a set of search criteria described in the **SRestriction** structure pointed to by the  _lpRestriction_ parameter.</span></span> 
  
<span data-ttu-id="bf897-137">通常 **，FindRow** 从指定书签向前搜索。</span><span class="sxs-lookup"><span data-stu-id="bf897-137">Usually, **FindRow** searches forward from the specified bookmark.</span></span> <span data-ttu-id="bf897-138">调用方可以通过在  _ulFlags_ 参数中设置 DIR_BACKWARD 标志，将搜索设置为从书签向后移动。</span><span class="sxs-lookup"><span data-stu-id="bf897-138">The caller can set the search to move backward from the bookmark by setting the DIR_BACKWARD flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="bf897-139">从当前书签开始向前搜索;从书签之前的行开始向后搜索。</span><span class="sxs-lookup"><span data-stu-id="bf897-139">Searching forward starts from the current bookmark; searching backward starts from the row prior to the bookmark.</span></span> <span data-ttu-id="bf897-140">搜索的结束位置正好在找到满足限制的第一行之前。</span><span class="sxs-lookup"><span data-stu-id="bf897-140">The end position of the search is just before the first row found that satisfied the restriction.</span></span> 
  
<span data-ttu-id="bf897-141">如果  _BkOrigin_ 参数中的书签指向的行不再存在于表中，并且表无法为书签建立新位置 **，FindRow** 将返回MAPI_E_INVALID_BOOKMARK。</span><span class="sxs-lookup"><span data-stu-id="bf897-141">If the row pointed to by the bookmark in the  _BkOrigin_ parameter no longer exists in the table and the table cannot establish a new position for the bookmark, **FindRow** returns MAPI_E_INVALID_BOOKMARK.</span></span> <span data-ttu-id="bf897-142">如果  _BkOrigin_ 指向的行不再存在，并且表能够为书签建立一个新位置 **，FindRow** 将返回MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="bf897-142">If the row pointed to by  _BkOrigin_ no longer exists and the table is able to establish a new position for the bookmark, **FindRow** returns MAPI_W_POSITION_CHANGED.</span></span> 
  
<span data-ttu-id="bf897-143">如果在  _BkOrigin_ 中传递的书签BOOKMARK_BEGINNING或BOOKMARK_END， **则 FindRow** MAPI_E_NOT_FOUND如果未找到匹配的行。</span><span class="sxs-lookup"><span data-stu-id="bf897-143">If the bookmark passed in  _BkOrigin_ is either BOOKMARK_BEGINNING or BOOKMARK_END, **FindRow** returns MAPI_E_NOT_FOUND if no matching row is found.</span></span> <span data-ttu-id="bf897-144">如果  _BkOrigin_ 中使用的书签 **BOOKMARK_CURRENT，FindRow** 可以返回 MAPI_W_POSITION_CHANGED，MAPI_E_INVALID_BOOKMARK，因为始终存在当前光标位置。</span><span class="sxs-lookup"><span data-stu-id="bf897-144">If the bookmark used in  _BkOrigin_ is BOOKMARK_CURRENT, **FindRow** can return MAPI_W_POSITION_CHANGED but not MAPI_E_INVALID_BOOKMARK because there is always a current cursor position.</span></span> 
  
<span data-ttu-id="bf897-145">所有 **表** 都需要 PR_INSTANCE_KEY ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性列， **并且 FindRow** 的所有实现都需要支持基于 PR_INSTANCE_KEY 查找行的调用。</span><span class="sxs-lookup"><span data-stu-id="bf897-145">The **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property column is required for all tables, and all implementations of **FindRow** are required to support calls seeking a row based on PR_INSTANCE_KEY.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="bf897-146">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="bf897-146">Notes to implementers</span></span>

<span data-ttu-id="bf897-147">只有当搜索遵循与表组织相同的方向时 **，FindRow** 执行的前缀搜索类型才有用。</span><span class="sxs-lookup"><span data-stu-id="bf897-147">The type of prefix searching performed by **FindRow** is only useful when the search follows the same direction as the table organization.</span></span> <span data-ttu-id="bf897-148">为了实现所需的行为，属性限制结构中传递的 RELOP_GE 隐含的比较函数应该与表排序顺序所基于的比较函数相同。</span><span class="sxs-lookup"><span data-stu-id="bf897-148">In order to achieve the required behavior, the comparison function implied by the **RELOP_GE** passed in the property restriction structure should be the same comparison function on which the table sort order is based.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="bf897-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="bf897-149">Notes to callers</span></span>

<span data-ttu-id="bf897-150">可以使用 **FindRow** 支持基于用户输入的字符串进行滚动，尤其是在地址对话框的列表框中。</span><span class="sxs-lookup"><span data-stu-id="bf897-150">You can use **FindRow** to support scrolling based on strings typed in by the user, especially in list boxes within address dialog boxes.</span></span> <span data-ttu-id="bf897-151">在此类型的滚动中，用户输入所需字符串值的逐步长前缀，你可以定期发出 **FindRow** 调用以跳转到与前缀匹配的第一行。</span><span class="sxs-lookup"><span data-stu-id="bf897-151">In this type of scrolling, users enter progressively longer prefixes of a desired string value, and you can periodically issue a **FindRow** call to jump to the first row that matches the prefix.</span></span> <span data-ttu-id="bf897-152">光标跳转的方向取决于搜索设置运行的方向。</span><span class="sxs-lookup"><span data-stu-id="bf897-152">Which direction the cursor jumps depends on which direction the search is set to run.</span></span> 
  
<span data-ttu-id="bf897-153">若要使用 **FindRow，** 必须设置书签。</span><span class="sxs-lookup"><span data-stu-id="bf897-153">To use **FindRow**, a bookmark must be set.</span></span> <span data-ttu-id="bf897-154">字符串搜索可以源自任何书签，包括来自指示当前位置以及表格开头和结尾的预设书签。</span><span class="sxs-lookup"><span data-stu-id="bf897-154">The string search can originate from any bookmark, including from the preset bookmarks indicating the current position and the beginning and end of the table.</span></span> <span data-ttu-id="bf897-155">如果表中有很多行，则搜索操作可能会很慢。</span><span class="sxs-lookup"><span data-stu-id="bf897-155">If there are a large number of rows in the table, the search operation can be slow.</span></span>
  
<span data-ttu-id="bf897-156">使用限制查找字符串前缀进行滚动，如下所示。</span><span class="sxs-lookup"><span data-stu-id="bf897-156">Use a restriction to find a string prefix for scrolling as follows.</span></span> <span data-ttu-id="bf897-157">For forward searching on a column sorted in ascending order and for backward searching on a column sorted in descending order， pass a property restriction structure in the  _lpRestriction_ parameter with the relation **RELOP_GE** and the appropriate property tag and prefix， using the format  _tag_ **GE** _prefix_.</span><span class="sxs-lookup"><span data-stu-id="bf897-157">For forward searching on a column sorted in ascending order and for backward searching on a column sorted in descending order, pass a property restriction structure in the  _lpRestriction_ parameter with the relation **RELOP_GE** and the appropriate property tag and prefix, using the format  _tag_ **GE** _prefix_.</span></span> 
  
<span data-ttu-id="bf897-158">有关使用限制结构指定筛选器的信息，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="bf897-158">For more information about using restriction structures to specify a filter, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="bf897-159">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="bf897-159">MFCMAPI reference</span></span>

<span data-ttu-id="bf897-160">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bf897-160">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="bf897-161">**文件**</span><span class="sxs-lookup"><span data-stu-id="bf897-161">**File**</span></span>|<span data-ttu-id="bf897-162">**函数**</span><span class="sxs-lookup"><span data-stu-id="bf897-162">**Function**</span></span>|<span data-ttu-id="bf897-163">**备注**</span><span class="sxs-lookup"><span data-stu-id="bf897-163">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf897-164">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="bf897-164">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="bf897-165">DwThreadFuncLoadTable</span><span class="sxs-lookup"><span data-stu-id="bf897-165">DwThreadFuncLoadTable</span></span>  <br/> |<span data-ttu-id="bf897-166">MFCMAPI 使用 **IMAPITable：：FindRow** 方法来查找与限制匹配的行。</span><span class="sxs-lookup"><span data-stu-id="bf897-166">MFCMAPI uses the **IMAPITable::FindRow** method to find rows which match a restriction.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bf897-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf897-167">See also</span></span>



[<span data-ttu-id="bf897-168">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="bf897-168">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="bf897-169">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="bf897-169">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="bf897-170">SRestriction</span><span class="sxs-lookup"><span data-stu-id="bf897-170">SRestriction</span></span>](srestriction.md)
  
[<span data-ttu-id="bf897-171">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bf897-171">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="bf897-172">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="bf897-172">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

