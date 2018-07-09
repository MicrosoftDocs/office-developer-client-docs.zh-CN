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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: cb777074d1657a3ee5c2f1e9f70d2b304858c1b2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775701"
---
# <a name="imapitablefindrow"></a><span data-ttu-id="5fb46-103">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="5fb46-103">IMAPITable::FindRow</span></span>

  
  
<span data-ttu-id="5fb46-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5fb46-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5fb46-105">在与特定的搜索条件匹配并将光标移至该行的表中查找的下一行。</span><span class="sxs-lookup"><span data-stu-id="5fb46-105">Finds the next row in a table that matches specific search criteria and moves the cursor to that row.</span></span>
  
```cpp
HRESULT FindRow(
LPSRestriction lpRestriction,
BOOKMARK BkOrigin,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="5fb46-106">参数</span><span class="sxs-lookup"><span data-stu-id="5fb46-106">Parameters</span></span>

 <span data-ttu-id="5fb46-107">_lpRestriction_</span><span class="sxs-lookup"><span data-stu-id="5fb46-107">_lpRestriction_</span></span>
  
> <span data-ttu-id="5fb46-108">[in]指向介绍搜索条件的[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="5fb46-108">[in] A pointer to an [SRestriction](srestriction.md) structure that describes the search criteria.</span></span> 
    
 <span data-ttu-id="5fb46-109">_BkOrigin_</span><span class="sxs-lookup"><span data-stu-id="5fb46-109">_BkOrigin_</span></span>
  
> <span data-ttu-id="5fb46-110">[in]标识**FindRow**开始搜索的位置行的书签。</span><span class="sxs-lookup"><span data-stu-id="5fb46-110">[in] A bookmark identifying the row where **FindRow** should begin its search.</span></span> <span data-ttu-id="5fb46-111">可以使用[IMAPITable::CreateBookmark](imapitable-createbookmark.md)方法中，创建一个书签，也可以传递预定义的以下值之一。</span><span class="sxs-lookup"><span data-stu-id="5fb46-111">A bookmark can be created using the [IMAPITable::CreateBookmark](imapitable-createbookmark.md) method, or one of the following predefined values can be passed.</span></span> 
    
<span data-ttu-id="5fb46-112">BOOKMARK_BEGINNING</span><span class="sxs-lookup"><span data-stu-id="5fb46-112">BOOKMARK_BEGINNING</span></span> 
  
> <span data-ttu-id="5fb46-113">从表开始搜索。</span><span class="sxs-lookup"><span data-stu-id="5fb46-113">Searches from the beginning of the table.</span></span> 
    
<span data-ttu-id="5fb46-114">BOOKMARK_CURRENT</span><span class="sxs-lookup"><span data-stu-id="5fb46-114">BOOKMARK_CURRENT</span></span> 
  
> <span data-ttu-id="5fb46-115">从光标位于何处表中的行进行搜索。</span><span class="sxs-lookup"><span data-stu-id="5fb46-115">Searches from the row in the table where the cursor is located.</span></span> 
    
<span data-ttu-id="5fb46-116">BOOKMARK_END</span><span class="sxs-lookup"><span data-stu-id="5fb46-116">BOOKMARK_END</span></span> 
  
> <span data-ttu-id="5fb46-117">从表末尾的搜索。</span><span class="sxs-lookup"><span data-stu-id="5fb46-117">Searches from the end of the table.</span></span> 
    
 <span data-ttu-id="5fb46-118">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5fb46-118">_ulFlags_</span></span>
  
> <span data-ttu-id="5fb46-119">[in]位掩码的标志，用于控制搜索的方向。</span><span class="sxs-lookup"><span data-stu-id="5fb46-119">[in] A bitmask of flags that controls the direction of the search.</span></span> <span data-ttu-id="5fb46-120">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="5fb46-120">The following flag can be set:</span></span>
    
<span data-ttu-id="5fb46-121">DIR_BACKWARD</span><span class="sxs-lookup"><span data-stu-id="5fb46-121">DIR_BACKWARD</span></span> 
  
> <span data-ttu-id="5fb46-122">向后搜索从书签标识的一行。</span><span class="sxs-lookup"><span data-stu-id="5fb46-122">Searches backward from the row identified by the bookmark.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5fb46-123">返回值</span><span class="sxs-lookup"><span data-stu-id="5fb46-123">Return value</span></span>

<span data-ttu-id="5fb46-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="5fb46-124">S_OK</span></span> 
  
> <span data-ttu-id="5fb46-125">查找操作成功。</span><span class="sxs-lookup"><span data-stu-id="5fb46-125">The find operation was successful.</span></span>
    
<span data-ttu-id="5fb46-126">MAPI_E_INVALID_BOOKMARK</span><span class="sxs-lookup"><span data-stu-id="5fb46-126">MAPI_E_INVALID_BOOKMARK</span></span> 
  
> <span data-ttu-id="5fb46-127">_BkOrigin_参数中的书签无效，因为它已被删除或因为它超出请求的最后一行。</span><span class="sxs-lookup"><span data-stu-id="5fb46-127">The bookmark in the  _BkOrigin_ parameter is invalid because it has been removed or because it is beyond the last row requested.</span></span> 
    
<span data-ttu-id="5fb46-128">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="5fb46-128">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="5fb46-129">符合限制不找到任何行。</span><span class="sxs-lookup"><span data-stu-id="5fb46-129">No rows were found that matched the restriction.</span></span>
    
<span data-ttu-id="5fb46-130">MAPI_W_POSITION_CHANGED</span><span class="sxs-lookup"><span data-stu-id="5fb46-130">MAPI_W_POSITION_CHANGED</span></span>
  
> <span data-ttu-id="5fb46-131">调用成功，但操作中使用的书签不再设置在所在的行时上次使用它;如果未用过该书签，，则不再中位置相同时创建它。</span><span class="sxs-lookup"><span data-stu-id="5fb46-131">The call succeeded, but the bookmark used in the operation is no longer set at the same row as when it was last used; if the bookmark has not been used, it is no longer in the same position as when it was created.</span></span> <span data-ttu-id="5fb46-132">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="5fb46-132">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="5fb46-133">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="5fb46-133">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="5fb46-134">请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb46-134">See [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5fb46-135">备注</span><span class="sxs-lookup"><span data-stu-id="5fb46-135">Remarks</span></span>

<span data-ttu-id="5fb46-136">**IMAPITable::FindRow**方法在要与一组_lpRestriction_参数指向的**SRestriction**结构中所述的搜索条件匹配的表中查找第一行。</span><span class="sxs-lookup"><span data-stu-id="5fb46-136">The **IMAPITable::FindRow** method locates the first row in the table to match a set of search criteria described in the **SRestriction** structure pointed to by the  _lpRestriction_ parameter.</span></span> 
  
<span data-ttu-id="5fb46-137">通常， **FindRow**向前搜索从指定的书签。</span><span class="sxs-lookup"><span data-stu-id="5fb46-137">Usually, **FindRow** searches forward from the specified bookmark.</span></span> <span data-ttu-id="5fb46-138">呼叫者可以设置搜索从向后移动书签通过_ulFlags_参数中设置 DIR_BACKWARD 标志。</span><span class="sxs-lookup"><span data-stu-id="5fb46-138">The caller can set the search to move backward from the bookmark by setting the DIR_BACKWARD flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="5fb46-139">从当前书签; 向前搜索开始向后搜索启动之前书签行中。</span><span class="sxs-lookup"><span data-stu-id="5fb46-139">Searching forward starts from the current bookmark; searching backward starts from the row prior to the bookmark.</span></span> <span data-ttu-id="5fb46-140">第一行找到的满足限制之前，搜索的结束位置。</span><span class="sxs-lookup"><span data-stu-id="5fb46-140">The end position of the search is just before the first row found that satisfied the restriction.</span></span> 
  
<span data-ttu-id="5fb46-141">如果所指的_BkOrigin_参数中的书签的行不再存在于表以及表无法建立的书签的新位置**FindRow**返回 MAPI_E_INVALID_BOOKMARK。</span><span class="sxs-lookup"><span data-stu-id="5fb46-141">If the row pointed to by the bookmark in the  _BkOrigin_ parameter no longer exists in the table and the table cannot establish a new position for the bookmark, **FindRow** returns MAPI_E_INVALID_BOOKMARK.</span></span> <span data-ttu-id="5fb46-142">如果所指的_BkOrigin_行不再存在并且表是能够建立的书签的新位置， **FindRow**返回 MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="5fb46-142">If the row pointed to by  _BkOrigin_ no longer exists and the table is able to establish a new position for the bookmark, **FindRow** returns MAPI_W_POSITION_CHANGED.</span></span> 
  
<span data-ttu-id="5fb46-143">如果_BkOrigin_中传递的书签，BOOKMARK_BEGINNING 或 BOOKMARK_END **FindRow**返回 MAPI_E_NOT_FOUND，如果未不找到任何匹配的行。</span><span class="sxs-lookup"><span data-stu-id="5fb46-143">If the bookmark passed in  _BkOrigin_ is either BOOKMARK_BEGINNING or BOOKMARK_END, **FindRow** returns MAPI_E_NOT_FOUND if no matching row is found.</span></span> <span data-ttu-id="5fb46-144">如果_BkOrigin_中使用的书签，BOOKMARK_CURRENT **FindRow**可以返回 MAPI_W_POSITION_CHANGED 但不是 MAPI_E_INVALID_BOOKMARK，因为始终没有当前光标位置。</span><span class="sxs-lookup"><span data-stu-id="5fb46-144">If the bookmark used in  _BkOrigin_ is BOOKMARK_CURRENT, **FindRow** can return MAPI_W_POSITION_CHANGED but not MAPI_E_INVALID_BOOKMARK because there is always a current cursor position.</span></span> 
  
<span data-ttu-id="5fb46-145">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性栏是必需的所有表，并支持呼叫寻求基于 PR_INSTANCE_KEY 行所需的所有**FindRow**实现。</span><span class="sxs-lookup"><span data-stu-id="5fb46-145">The **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property column is required for all tables, and all implementations of **FindRow** are required to support calls seeking a row based on PR_INSTANCE_KEY.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="5fb46-146">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="5fb46-146">Notes to implementers</span></span>

<span data-ttu-id="5fb46-147">仅在搜索将遵循相同的方向表组织时有用的前缀搜索由**FindRow**执行的类型。</span><span class="sxs-lookup"><span data-stu-id="5fb46-147">The type of prefix searching performed by **FindRow** is only useful when the search follows the same direction as the table organization.</span></span> <span data-ttu-id="5fb46-148">为了实现所需的行为，比较函数暗示**RELOP_GE**传递在属性限制结构应为相同的比较功能所基于的表排序次序。</span><span class="sxs-lookup"><span data-stu-id="5fb46-148">In order to achieve the required behavior, the comparison function implied by the **RELOP_GE** passed in the property restriction structure should be the same comparison function on which the table sort order is based.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5fb46-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5fb46-149">Notes to callers</span></span>

<span data-ttu-id="5fb46-150">您可以使用**FindRow**支持滚动基于用户，特别是在地址对话框内的列表框中键入的字符串。</span><span class="sxs-lookup"><span data-stu-id="5fb46-150">You can use **FindRow** to support scrolling based on strings typed in by the user, especially in list boxes within address dialog boxes.</span></span> <span data-ttu-id="5fb46-151">在此类型的滚动，用户输入的一个所需的字符串值，会越来越长前缀和定期可以发出**FindRow**呼叫跳转到前缀匹配的第一行。</span><span class="sxs-lookup"><span data-stu-id="5fb46-151">In this type of scrolling, users enter progressively longer prefixes of a desired string value, and you can periodically issue a **FindRow** call to jump to the first row that matches the prefix.</span></span> <span data-ttu-id="5fb46-152">光标跳转的方向取决于哪个方向搜索设置为运行。</span><span class="sxs-lookup"><span data-stu-id="5fb46-152">Which direction the cursor jumps depends on which direction the search is set to run.</span></span> 
  
<span data-ttu-id="5fb46-153">若要使用**FindRow**，必须设置书签。</span><span class="sxs-lookup"><span data-stu-id="5fb46-153">To use **FindRow**, a bookmark must be set.</span></span> <span data-ttu-id="5fb46-154">字符串搜索可以源自任何书签，包括预设书签指示当前位置的开头和末尾表。</span><span class="sxs-lookup"><span data-stu-id="5fb46-154">The string search can originate from any bookmark, including from the preset bookmarks indicating the current position and the beginning and end of the table.</span></span> <span data-ttu-id="5fb46-155">如果有大量的表中的行，则搜索操作会很慢。</span><span class="sxs-lookup"><span data-stu-id="5fb46-155">If there are a large number of rows in the table, the search operation can be slow.</span></span>
  
<span data-ttu-id="5fb46-156">使用限制查找字符串前缀滚动，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5fb46-156">Use a restriction to find a string prefix for scrolling as follows.</span></span> <span data-ttu-id="5fb46-157">对于按升序排序的列上向前搜索和按降序排序的列上向后搜索，传递的关系**RELOP_GE** _lpRestriction_参数和相应的属性限制结构属性标记和前缀，使用格式_标记_ **GE** _前缀_。</span><span class="sxs-lookup"><span data-stu-id="5fb46-157">For forward searching on a column sorted in ascending order and for backward searching on a column sorted in descending order, pass a property restriction structure in the  _lpRestriction_ parameter with the relation **RELOP_GE** and the appropriate property tag and prefix, using the format  _tag_ **GE** _prefix_.</span></span> 
  
<span data-ttu-id="5fb46-158">有关使用限制结构指定筛选器的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb46-158">For more information about using restriction structures to specify a filter, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="5fb46-159">MFCMAPI 参考</span><span class="sxs-lookup"><span data-stu-id="5fb46-159">MFCMAPI reference</span></span>

<span data-ttu-id="5fb46-160">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5fb46-160">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="5fb46-161">**文件**</span><span class="sxs-lookup"><span data-stu-id="5fb46-161">**File**</span></span>|<span data-ttu-id="5fb46-162">**函数**</span><span class="sxs-lookup"><span data-stu-id="5fb46-162">**Function**</span></span>|<span data-ttu-id="5fb46-163">**Comment**</span><span class="sxs-lookup"><span data-stu-id="5fb46-163">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5fb46-164">ContentsTableListCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="5fb46-164">ContentsTableListCtrl.cpp</span></span>  <br/> |<span data-ttu-id="5fb46-165">DwThreadFuncLoadTable</span><span class="sxs-lookup"><span data-stu-id="5fb46-165">DwThreadFuncLoadTable</span></span>  <br/> |<span data-ttu-id="5fb46-166">MFCMAPI 使用**IMAPITable::FindRow**方法查找与限制匹配的行。</span><span class="sxs-lookup"><span data-stu-id="5fb46-166">MFCMAPI uses the **IMAPITable::FindRow** method to find rows which match a restriction.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5fb46-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fb46-167">See also</span></span>



[<span data-ttu-id="5fb46-168">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="5fb46-168">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md)
  
[<span data-ttu-id="5fb46-169">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="5fb46-169">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="5fb46-170">SRestriction</span><span class="sxs-lookup"><span data-stu-id="5fb46-170">SRestriction</span></span>](srestriction.md)
  
[<span data-ttu-id="5fb46-171">IMAPITable: IUnknown</span><span class="sxs-lookup"><span data-stu-id="5fb46-171">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)


[<span data-ttu-id="5fb46-172">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="5fb46-172">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

