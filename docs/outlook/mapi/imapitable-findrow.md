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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329076"
---
# <a name="imapitablefindrow"></a><span data-ttu-id="932d6-103">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="932d6-103">IMAPITable::FindRow</span></span>

  
  
<span data-ttu-id="932d6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="932d6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="932d6-105">在表中查找与特定搜索条件匹配的下一行, 并将光标移至该行。</span><span class="sxs-lookup"><span data-stu-id="932d6-105">Finds the next row in a table that matches specific search criteria and moves the cursor to that row.</span></span>
  
```cpp
HRESULT FindRow(
LPSRestriction lpRestriction,
BOOKMARK BkOrigin,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="932d6-106">参数</span><span class="sxs-lookup"><span data-stu-id="932d6-106">Parameters</span></span>

 <span data-ttu-id="932d6-107">_lpRestriction_</span><span class="sxs-lookup"><span data-stu-id="932d6-107">_lpRestriction_</span></span>
  
> <span data-ttu-id="932d6-108">实时指向描述搜索条件的[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="932d6-108">[in] A pointer to an [SRestriction](srestriction.md) structure that describes the search criteria.</span></span> 
    
 <span data-ttu-id="932d6-109">_BkOrigin_</span><span class="sxs-lookup"><span data-stu-id="932d6-109">_BkOrigin_</span></span>
  
> <span data-ttu-id="932d6-110">实时一个书签, 用于标识**FindRow**应开始搜索的行。</span><span class="sxs-lookup"><span data-stu-id="932d6-110">[in] A bookmark identifying the row where **FindRow** should begin its search.</span></span> <span data-ttu-id="932d6-111">可以使用[IMAPITable:: CreateBookmark](imapitable-createbookmark.md)方法创建书签, 或者可以传递下列预定义值之一。</span><span class="sxs-lookup"><span data-stu-id="932d6-111">A bookmark can be created using the [IMAPITable::CreateBookmark](imapitable-createbookmark.md) method, or one of the following predefined values can be passed.</span></span> 
    
<span data-ttu-id="932d6-112">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="932d6-112">BOOKMARK_BEGINNING</span></span> 
  
> <span data-ttu-id="932d6-113">从表的开头进行搜索。</span><span class="sxs-lookup"><span data-stu-id="932d6-113">Searches from the beginning of the table.</span></span> 
    
<span data-ttu-id="932d6-114">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="932d6-114">BOOKMARK_CURRENT</span></span> 
  
> <span data-ttu-id="932d6-115">从游标所在的表中的行进行搜索。</span><span class="sxs-lookup"><span data-stu-id="932d6-115">Searches from the row in the table where the cursor is located.</span></span> 
    
<span data-ttu-id="932d6-116">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="932d6-116">BOOKMARK_END</span></span> 
  
> <span data-ttu-id="932d6-117">从表的末尾开始搜索。</span><span class="sxs-lookup"><span data-stu-id="932d6-117">Searches from the end of the table.</span></span> 
    
 <span data-ttu-id="932d6-118">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="932d6-118">_ulFlags_</span></span>
  
> <span data-ttu-id="932d6-119">实时用于控制搜索方向的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="932d6-119">[in] A bitmask of flags that controls the direction of the search.</span></span> <span data-ttu-id="932d6-120">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="932d6-120">The following flag can be set:</span></span>
    
<span data-ttu-id="932d6-121">DIR_BACKWARD</span><span class="sxs-lookup"><span data-stu-id="932d6-121">DIR_BACKWARD</span></span> 
  
> <span data-ttu-id="932d6-122">从书签标识的行向后搜索。</span><span class="sxs-lookup"><span data-stu-id="932d6-122">Searches backward from the row identified by the bookmark.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="932d6-123">返回值</span><span class="sxs-lookup"><span data-stu-id="932d6-123">Return value</span></span>

<span data-ttu-id="932d6-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="932d6-124">S_OK</span></span> 
  
> <span data-ttu-id="932d6-125">查找操作成功。</span><span class="sxs-lookup"><span data-stu-id="932d6-125">The find operation was successful.</span></span>
    
<span data-ttu-id="932d6-126">MAPI_E_INVALID_BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="932d6-126">MAPI_E_INVALID_BOOKMARK</span></span> 
  
> <span data-ttu-id="932d6-127">_BkOrigin_参数中的书签无效, 因为它已被删除或超出了最后请求的行。</span><span class="sxs-lookup"><span data-stu-id="932d6-127">The bookmark in the  _BkOrigin_ parameter is invalid because it has been removed or because it is beyond the last row requested.</span></span> 
    
<span data-ttu-id="932d6-128">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="932d6-128">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="932d6-129">找不到与限制匹配的行。</span><span class="sxs-lookup"><span data-stu-id="932d6-129">No rows were found that matched the restriction.</span></span>
    
<span data-ttu-id="932d6-130">MAPI_W_POSITION_CHANGED</span><span class="sxs-lookup"><span data-stu-id="932d6-130">MAPI_W_POSITION_CHANGED</span></span>
  
> <span data-ttu-id="932d6-131">调用成功, 但在操作中使用的书签不再设置为与上次使用时相同的行;如果书签尚未使用, 它将不再位于创建时的位置。</span><span class="sxs-lookup"><span data-stu-id="932d6-131">The call succeeded, but the bookmark used in the operation is no longer set at the same row as when it was last used; if the bookmark has not been used, it is no longer in the same position as when it was created.</span></span> <span data-ttu-id="932d6-132">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="932d6-132">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="932d6-133">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="932d6-133">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="932d6-134">请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="932d6-134">See [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="932d6-135">注解</span><span class="sxs-lookup"><span data-stu-id="932d6-135">Remarks</span></span>

<span data-ttu-id="932d6-136">**IMAPITable:: FindRow**方法定位表中的第一行, 以匹配_lpRestriction_参数指向的**SRestriction**结构中所述的一组搜索条件。</span><span class="sxs-lookup"><span data-stu-id="932d6-136">The **IMAPITable::FindRow** method locates the first row in the table to match a set of search criteria described in the **SRestriction** structure pointed to by the  _lpRestriction_ parameter.</span></span> 
  
<span data-ttu-id="932d6-137">通常情况下, **FindRow**从指定书签向前搜索。</span><span class="sxs-lookup"><span data-stu-id="932d6-137">Usually, **FindRow** searches forward from the specified bookmark.</span></span> <span data-ttu-id="932d6-138">调用方可以通过在_ulFlags_参数中设置 DIR_BACKWARD 标志, 将搜索设置为在书签中向后移动。</span><span class="sxs-lookup"><span data-stu-id="932d6-138">The caller can set the search to move backward from the bookmark by setting the DIR_BACKWARD flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="932d6-139">向前搜索从当前书签开始;向后搜索将从书签之前的行开始。</span><span class="sxs-lookup"><span data-stu-id="932d6-139">Searching forward starts from the current bookmark; searching backward starts from the row prior to the bookmark.</span></span> <span data-ttu-id="932d6-140">搜索的结束位置恰好在找到满足限制的第一行之前。</span><span class="sxs-lookup"><span data-stu-id="932d6-140">The end position of the search is just before the first row found that satisfied the restriction.</span></span> 
  
<span data-ttu-id="932d6-141">如果_BkOrigin_参数中的书签所指向的行在表中不再存在, 并且该表无法为该书签建立新的位置, 则**FindRow**将返回 MAPI_E_INVALID_BOOKMARK。</span><span class="sxs-lookup"><span data-stu-id="932d6-141">If the row pointed to by the bookmark in the  _BkOrigin_ parameter no longer exists in the table and the table cannot establish a new position for the bookmark, **FindRow** returns MAPI_E_INVALID_BOOKMARK.</span></span> <span data-ttu-id="932d6-142">如果_BkOrigin_所指向的行不再存在, 并且表格能够为该书签建立一个新位置, 则**FindRow**将返回 MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="932d6-142">If the row pointed to by  _BkOrigin_ no longer exists and the table is able to establish a new position for the bookmark, **FindRow** returns MAPI_W_POSITION_CHANGED.</span></span> 
  
<span data-ttu-id="932d6-143">如果_BkOrigin_中传递的书签是 BOOKMARK_BEGINNING 或 BOOKMARK_END, 如果找不到匹配的行, **FindRow**将返回 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="932d6-143">If the bookmark passed in  _BkOrigin_ is either BOOKMARK_BEGINNING or BOOKMARK_END, **FindRow** returns MAPI_E_NOT_FOUND if no matching row is found.</span></span> <span data-ttu-id="932d6-144">如果_BkOrigin_中使用的书签为 BOOKMARK_CURRENT, 则**FindRow**可以返回 MAPI_W_POSITION_CHANGED 而不是 MAPI_E_INVALID_BOOKMARK, 因为始终存在当前游标位置。</span><span class="sxs-lookup"><span data-stu-id="932d6-144">If the bookmark used in  _BkOrigin_ is BOOKMARK_CURRENT, **FindRow** can return MAPI_W_POSITION_CHANGED but not MAPI_E_INVALID_BOOKMARK because there is always a current cursor position.</span></span> 
  
<span data-ttu-id="932d6-145">所有表都需要**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性列, **FindRow**的所有实现都必须支持查找基于 PR_INSTANCE_KEY 的行的调用。</span><span class="sxs-lookup"><span data-stu-id="932d6-145">The **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property column is required for all tables, and all implementations of **FindRow** are required to support calls seeking a row based on PR_INSTANCE_KEY.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="932d6-146">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="932d6-146">Notes to implementers</span></span>

<span data-ttu-id="932d6-147">**FindRow**执行的前缀搜索的类型仅在搜索与表组织的方向相同时才有用。</span><span class="sxs-lookup"><span data-stu-id="932d6-147">The type of prefix searching performed by **FindRow** is only useful when the search follows the same direction as the table organization.</span></span> <span data-ttu-id="932d6-148">为了实现所需的行为, 在属性限制结构中传递的**RELOP_GE**暗示的比较函数应与表排序顺序所基于的比较函数相同。</span><span class="sxs-lookup"><span data-stu-id="932d6-148">In order to achieve the required behavior, the comparison function implied by the **RELOP_GE** passed in the property restriction structure should be the same comparison function on which the table sort order is based.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="932d6-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="932d6-149">Notes to callers</span></span>

<span data-ttu-id="932d6-150">您可以使用**FindRow**支持基于用户键入的字符串滚动, 尤其是在地址对话框内的列表框中。</span><span class="sxs-lookup"><span data-stu-id="932d6-150">You can use **FindRow** to support scrolling based on strings typed in by the user, especially in list boxes within address dialog boxes.</span></span> <span data-ttu-id="932d6-151">在这种类型的滚动中, 用户可以输入所需字符串值的渐进更长的前缀, 并且可以定期发出**FindRow**调用以跳转到与前缀匹配的第一行。</span><span class="sxs-lookup"><span data-stu-id="932d6-151">In this type of scrolling, users enter progressively longer prefixes of a desired string value, and you can periodically issue a **FindRow** call to jump to the first row that matches the prefix.</span></span> <span data-ttu-id="932d6-152">光标跳转的方向取决于搜索设置的运行方向。</span><span class="sxs-lookup"><span data-stu-id="932d6-152">Which direction the cursor jumps depends on which direction the search is set to run.</span></span> 
  
<span data-ttu-id="932d6-153">若要使用**FindRow**, 必须设置书签。</span><span class="sxs-lookup"><span data-stu-id="932d6-153">To use **FindRow**, a bookmark must be set.</span></span> <span data-ttu-id="932d6-154">字符串搜索可以来自任何书签, 包括从表示当前位置的预设书签到表格的开始和结束。</span><span class="sxs-lookup"><span data-stu-id="932d6-154">The string search can originate from any bookmark, including from the preset bookmarks indicating the current position and the beginning and end of the table.</span></span> <span data-ttu-id="932d6-155">如果表中有大量的行, 则搜索操作可能会很慢。</span><span class="sxs-lookup"><span data-stu-id="932d6-155">If there are a large number of rows in the table, the search operation can be slow.</span></span>
  
<span data-ttu-id="932d6-156">使用限制来查找用于滚动的字符串前缀, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="932d6-156">Use a restriction to find a string prefix for scrolling as follows.</span></span> <span data-ttu-id="932d6-157">对于按升序排序的列和对按降序排序的列进行的向前搜索, 请在_lpRestriction_参数中使用关系**RELOP_GE**传递属性限制结构, 并使用适当的使用格式_标记_ **GE** _前缀_的属性标记和前缀。</span><span class="sxs-lookup"><span data-stu-id="932d6-157">For forward searching on a column sorted in ascending order and for backward searching on a column sorted in descending order, pass a property restriction structure in the  _lpRestriction_ parameter with the relation **RELOP_GE** and the appropriate property tag and prefix, using the format  _tag_ **GE** _prefix_.</span></span> 
  
<span data-ttu-id="932d6-158">有关使用限制结构指定筛选器的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="932d6-158">For more information about using restriction structures to specify a filter, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="932d6-159">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="932d6-159">MFCMAPI reference</span></span>

<span data-ttu-id="932d6-160">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="932d6-160">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="932d6-161">**文件**</span><span class="sxs-lookup"><span data-stu-id="932d6-161">**File**</span></span>|<span data-ttu-id="932d6-162">**函数**</span><span class="sxs-lookup"><span data-stu-id="932d6-162">**Function**</span></span>|<span data-ttu-id="932d6-163">**备注**</span><span class="sxs-lookup"><span data-stu-id="932d6-163">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="932d6-164">ContentsTableListCtrl</span><span class="sxs-lookup"><span data-stu-id="932d6-164">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="932d6-165">DwThreadFuncLoadTable</span><span class="sxs-lookup"><span data-stu-id="932d6-165">DwThreadFuncLoadTable</span></span>  <br/> |<span data-ttu-id="932d6-166">MFCMAPI 使用**IMAPITable:: FindRow**方法查找匹配限制的行。</span><span class="sxs-lookup"><span data-stu-id="932d6-166">MFCMAPI uses the **IMAPITable::FindRow** method to find rows which match a restriction.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="932d6-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="932d6-167">See also</span></span>



[<span data-ttu-id="932d6-168">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="932d6-168">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="932d6-169">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="932d6-169">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="932d6-170">SRestriction</span><span class="sxs-lookup"><span data-stu-id="932d6-170">SRestriction</span></span>](srestriction.md)
  
[<span data-ttu-id="932d6-171">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="932d6-171">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="932d6-172">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="932d6-172">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

