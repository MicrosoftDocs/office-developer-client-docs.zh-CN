---
title: IMAPITableCreateBookmark
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.CreateBookmark
api_type:
- COM
ms.assetid: 320af2ff-c2a5-43b1-b3a1-76cb5ffd6a4f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 34bd6de95f731c03466f19e0bc4fd6e2c9910900
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775691"
---
# <a name="imapitablecreatebookmark"></a><span data-ttu-id="72fcf-103">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="72fcf-103">IMAPITable::CreateBookmark</span></span>

  
  
<span data-ttu-id="72fcf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="72fcf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="72fcf-105">在表的当前位置创建一个书签。</span><span class="sxs-lookup"><span data-stu-id="72fcf-105">Creates a bookmark at the table's current position.</span></span>
  
```cpp
HRESULT CreateBookmark(
BOOKMARK FAR * lpbkPosition
);
```

## <a name="parameters"></a><span data-ttu-id="72fcf-106">参数</span><span class="sxs-lookup"><span data-stu-id="72fcf-106">Parameters</span></span>

 <span data-ttu-id="72fcf-107">_lpbkPosition_</span><span class="sxs-lookup"><span data-stu-id="72fcf-107">_lpbkPosition_</span></span>
  
> <span data-ttu-id="72fcf-108">[输出]返回的 32 位书签值的指针。</span><span class="sxs-lookup"><span data-stu-id="72fcf-108">[out] Pointer to the returned 32-bit bookmark value.</span></span> <span data-ttu-id="72fcf-109">更高版本可以对[IMAPITable::SeekRow](imapitable-seekrow.md)方法的调用中传递该书签。</span><span class="sxs-lookup"><span data-stu-id="72fcf-109">This bookmark can later be passed in a call to the [IMAPITable::SeekRow](imapitable-seekrow.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="72fcf-110">返回值</span><span class="sxs-lookup"><span data-stu-id="72fcf-110">Return value</span></span>

<span data-ttu-id="72fcf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="72fcf-111">S_OK</span></span> 
  
> <span data-ttu-id="72fcf-112">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="72fcf-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="72fcf-113">MAPI_E_UNABLE_TO_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="72fcf-113">MAPI_E_UNABLE_TO_COMPLETE</span></span> 
  
> <span data-ttu-id="72fcf-114">无法完成所请求的操作。</span><span class="sxs-lookup"><span data-stu-id="72fcf-114">The requested operation could not be completed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="72fcf-115">备注</span><span class="sxs-lookup"><span data-stu-id="72fcf-115">Remarks</span></span>

<span data-ttu-id="72fcf-116">**IMAPITable::CreateBookmark**方法通过创建值调用书签标记的表的位置。</span><span class="sxs-lookup"><span data-stu-id="72fcf-116">The **IMAPITable::CreateBookmark** method marks a table position by creating a value called a bookmark.</span></span> <span data-ttu-id="72fcf-117">可以使用书签以返回到书签标识的位置。</span><span class="sxs-lookup"><span data-stu-id="72fcf-117">A bookmark can be used to return to the position identified by the bookmark.</span></span> <span data-ttu-id="72fcf-118">与在表中的行对象相关联的书签的位置。</span><span class="sxs-lookup"><span data-stu-id="72fcf-118">The bookmarked position is associated with the object at that row in the table.</span></span> 
  
<span data-ttu-id="72fcf-119">附件表上不支持书签和附件的**CreateBookmark**的表实现返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="72fcf-119">Bookmarks are not supported on attachment tables, and attachment table implementations of **CreateBookmark** return MAPI_E_NO_SUPPORT.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="72fcf-120">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="72fcf-120">Notes to implementers</span></span>

<span data-ttu-id="72fcf-121">由于内存费用的维护光标位置的书签，限制可以创建的书签的数目。</span><span class="sxs-lookup"><span data-stu-id="72fcf-121">Because of the memory expense of maintaining cursor positions with bookmarks, limit the number of bookmarks that you can create.</span></span> <span data-ttu-id="72fcf-122">如果看到该号码，返回从所有后续呼叫到**CreateBookmark**MAPI_E_UNABLE_TO_COMPLETE。</span><span class="sxs-lookup"><span data-stu-id="72fcf-122">When you reach that number, return MAPI_E_UNABLE_TO_COMPLETE from all subsequent calls to **CreateBookmark**.</span></span>
  
<span data-ttu-id="72fcf-123">有时书签指向不再在表视图中的行。</span><span class="sxs-lookup"><span data-stu-id="72fcf-123">Sometimes a bookmark points to a row that is no longer in the table view.</span></span> <span data-ttu-id="72fcf-124">如果呼叫者使用如书签，将光标移到下一个可见的行和存在停止。</span><span class="sxs-lookup"><span data-stu-id="72fcf-124">If a caller uses such a bookmark, move the cursor to the next visible row and stop there.</span></span> 
  
<span data-ttu-id="72fcf-125">当呼叫者尝试使用书签，因为它已被折叠指向不可见的行时，则移动书签后返回 MAPI_W_POSITION_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="72fcf-125">When the caller attempts to use a bookmark that is pointing to a nonvisible row because it has been collapsed, return MAPI_W_POSITION_CHANGED after moving the bookmark.</span></span> <span data-ttu-id="72fcf-126">此时或折叠发生在**SetCollapseState**方法时，可以重新定位到的下一个可见行的书签。</span><span class="sxs-lookup"><span data-stu-id="72fcf-126">You can reposition the bookmark to the next visible row either at this time or when the collapsing occurs in the **SetCollapseState** method.</span></span> <span data-ttu-id="72fcf-127">如果将书签移动折叠行时，您必须保留有点指示完全书签已移动时在书签： 由于其上次使用或其从未使用过创建后。</span><span class="sxs-lookup"><span data-stu-id="72fcf-127">If you move the bookmark at the time the row is collapsed, you must retain a bit in the bookmark that indicates exactly when the bookmark was moved: since its last use or if it has never been used since its creation.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="72fcf-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="72fcf-128">Notes to callers</span></span>

 <span data-ttu-id="72fcf-129">**CreateBookmark**为其创建的书签分配内存。</span><span class="sxs-lookup"><span data-stu-id="72fcf-129">**CreateBookmark** allocates memory for the bookmark it creates.</span></span> <span data-ttu-id="72fcf-130">通过调用[IMAPITable::FreeBookmark](imapitable-freebookmark.md)方法释放书签的资源。</span><span class="sxs-lookup"><span data-stu-id="72fcf-130">Release the resources for the bookmark by calling the [IMAPITable::FreeBookmark](imapitable-freebookmark.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="72fcf-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72fcf-131">See also</span></span>



[<span data-ttu-id="72fcf-132">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="72fcf-132">IMAPITable::FreeBookmark</span></span>](imapitable-freebookmark.md)
  
[<span data-ttu-id="72fcf-133">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="72fcf-133">IMAPITable::SeekRow</span></span>](imapitable-seekrow.md)
  
[<span data-ttu-id="72fcf-134">IMAPITable: IUnknown</span><span class="sxs-lookup"><span data-stu-id="72fcf-134">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

