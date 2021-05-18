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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c251dacce0d4e1743a74f1ba45e395b6e1c05064
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408822"
---
# <a name="imapitablecreatebookmark"></a><span data-ttu-id="0eb5c-103">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="0eb5c-103">IMAPITable::CreateBookmark</span></span>

  
  
<span data-ttu-id="0eb5c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0eb5c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0eb5c-105">在表格的当前位置创建书签。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-105">Creates a bookmark at the table's current position.</span></span>
  
```cpp
HRESULT CreateBookmark(
BOOKMARK FAR * lpbkPosition
);
```

## <a name="parameters"></a><span data-ttu-id="0eb5c-106">参数</span><span class="sxs-lookup"><span data-stu-id="0eb5c-106">Parameters</span></span>

 <span data-ttu-id="0eb5c-107">_lpbkPosition_</span><span class="sxs-lookup"><span data-stu-id="0eb5c-107">_lpbkPosition_</span></span>
  
> <span data-ttu-id="0eb5c-108">[out]指向返回的 32 位书签值的指针。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-108">[out] Pointer to the returned 32-bit bookmark value.</span></span> <span data-ttu-id="0eb5c-109">此书签稍后可以在对 [IMAPITable：：SeekRow](imapitable-seekrow.md) 方法的调用中传递。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-109">This bookmark can later be passed in a call to the [IMAPITable::SeekRow](imapitable-seekrow.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0eb5c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0eb5c-110">Return value</span></span>

<span data-ttu-id="0eb5c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0eb5c-111">S_OK</span></span> 
  
> <span data-ttu-id="0eb5c-112">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="0eb5c-113">MAPI_E_UNABLE_TO_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="0eb5c-113">MAPI_E_UNABLE_TO_COMPLETE</span></span> 
  
> <span data-ttu-id="0eb5c-114">无法完成请求的操作。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-114">The requested operation could not be completed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0eb5c-115">备注</span><span class="sxs-lookup"><span data-stu-id="0eb5c-115">Remarks</span></span>

<span data-ttu-id="0eb5c-116">**IMAPITable：：CreateBookmark** 方法通过创建一个称为书签的值来标记表位置。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-116">The **IMAPITable::CreateBookmark** method marks a table position by creating a value called a bookmark.</span></span> <span data-ttu-id="0eb5c-117">书签可用于返回书签标识的位置。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-117">A bookmark can be used to return to the position identified by the bookmark.</span></span> <span data-ttu-id="0eb5c-118">书签位置与表格中该行中的对象相关联。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-118">The bookmarked position is associated with the object at that row in the table.</span></span> 
  
<span data-ttu-id="0eb5c-119">书签在附件表中不受支持，并且 **CreateBookmark** 返回标记的附件表MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-119">Bookmarks are not supported on attachment tables, and attachment table implementations of **CreateBookmark** return MAPI_E_NO_SUPPORT.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="0eb5c-120">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="0eb5c-120">Notes to implementers</span></span>

<span data-ttu-id="0eb5c-121">由于维护具有书签的游标位置的内存费用，请限制您可以创建的书签数。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-121">Because of the memory expense of maintaining cursor positions with bookmarks, limit the number of bookmarks that you can create.</span></span> <span data-ttu-id="0eb5c-122">当您达到该号码时，请返回MAPI_E_UNABLE_TO_COMPLETE调用 **CreateBookmark** 的所有结果。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-122">When you reach that number, return MAPI_E_UNABLE_TO_COMPLETE from all subsequent calls to **CreateBookmark**.</span></span>
  
<span data-ttu-id="0eb5c-123">有时，书签指向不再位于表视图中的行。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-123">Sometimes a bookmark points to a row that is no longer in the table view.</span></span> <span data-ttu-id="0eb5c-124">如果调用方使用此类书签，将光标移到下一个可见行并停止。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-124">If a caller uses such a bookmark, move the cursor to the next visible row and stop there.</span></span> 
  
<span data-ttu-id="0eb5c-125">当调用者试图使用由于已折叠而指向不可访问行的书签时，在MAPI_W_POSITION_CHANGED返回该书签。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-125">When the caller attempts to use a bookmark that is pointing to a nonvisible row because it has been collapsed, return MAPI_W_POSITION_CHANGED after moving the bookmark.</span></span> <span data-ttu-id="0eb5c-126">此时或在 **SetCollapseState** 方法中折叠时，可以将书签重新定位到下一个可见行。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-126">You can reposition the bookmark to the next visible row either at this time or when the collapsing occurs in the **SetCollapseState** method.</span></span> <span data-ttu-id="0eb5c-127">如果在折叠行时移动书签，则必须在书签中保留一个位，以准确指示书签移动的时间：自上次使用以来或自创建以来从未使用过它。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-127">If you move the bookmark at the time the row is collapsed, you must retain a bit in the bookmark that indicates exactly when the bookmark was moved: since its last use or if it has never been used since its creation.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0eb5c-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0eb5c-128">Notes to callers</span></span>

 <span data-ttu-id="0eb5c-129">**CreateBookmark** 为其创建的书签分配内存。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-129">**CreateBookmark** allocates memory for the bookmark it creates.</span></span> <span data-ttu-id="0eb5c-130">通过调用 [IMAPITable：：FreeBookmark](imapitable-freebookmark.md) 方法释放书签的资源。</span><span class="sxs-lookup"><span data-stu-id="0eb5c-130">Release the resources for the bookmark by calling the [IMAPITable::FreeBookmark](imapitable-freebookmark.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0eb5c-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0eb5c-131">See also</span></span>



[<span data-ttu-id="0eb5c-132">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="0eb5c-132">IMAPITable::FreeBookmark</span></span>](imapitable-freebookmark.md)
  
[<span data-ttu-id="0eb5c-133">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="0eb5c-133">IMAPITable::SeekRow</span></span>](imapitable-seekrow.md)
  
[<span data-ttu-id="0eb5c-134">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0eb5c-134">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

