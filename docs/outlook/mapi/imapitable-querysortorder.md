---
title: IMAPITableQuerySortOrder
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.QuerySortOrder
api_type:
- COM
ms.assetid: 7b4ca523-0703-417c-8586-c4324c200020
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 61991972fdf8674a9ffd2b790e26c7fa669df357
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407548"
---
# <a name="imapitablequerysortorder"></a><span data-ttu-id="72432-103">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="72432-103">IMAPITable::QuerySortOrder</span></span>

  
  
<span data-ttu-id="72432-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="72432-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="72432-105">检索表的当前排序顺序。</span><span class="sxs-lookup"><span data-stu-id="72432-105">Retrieves the current sort order for a table.</span></span>
  
```cpp
HRESULT QuerySortOrder(
LPSSortOrderSet FAR * lppSortCriteria
);
```

## <a name="parameters"></a><span data-ttu-id="72432-106">参数</span><span class="sxs-lookup"><span data-stu-id="72432-106">Parameters</span></span>

 <span data-ttu-id="72432-107">_lppSortCriteria_</span><span class="sxs-lookup"><span data-stu-id="72432-107">_lppSortCriteria_</span></span>
  
> <span data-ttu-id="72432-108">[out]指向保持当前排序 [顺序的 SSortOrderSet](ssortorderset.md) 结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="72432-108">[out] Pointer to a pointer to the [SSortOrderSet](ssortorderset.md) structure holding the current sort order.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="72432-109">返回值</span><span class="sxs-lookup"><span data-stu-id="72432-109">Return value</span></span>

<span data-ttu-id="72432-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="72432-110">S_OK</span></span> 
  
> <span data-ttu-id="72432-111">已成功返回当前排序顺序。</span><span class="sxs-lookup"><span data-stu-id="72432-111">The current sort order was successfully returned.</span></span>
    
<span data-ttu-id="72432-112">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="72432-112">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="72432-113">正在进行另一个操作，以防止排序顺序检索操作启动。</span><span class="sxs-lookup"><span data-stu-id="72432-113">Another operation is in progress that prevents the sort order retrieval operation from starting.</span></span> <span data-ttu-id="72432-114">应允许完成或停止进行中的操作。</span><span class="sxs-lookup"><span data-stu-id="72432-114">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="72432-115">备注</span><span class="sxs-lookup"><span data-stu-id="72432-115">Remarks</span></span>

<span data-ttu-id="72432-116">**IMAPITable：：QuerySortOrder** 方法检索表的当前排序顺序。</span><span class="sxs-lookup"><span data-stu-id="72432-116">The **IMAPITable::QuerySortOrder** method retrieves the current sort order for a table.</span></span> <span data-ttu-id="72432-117">排序顺序使用 [SSortOrderSet](ssortorderset.md) 结构进行描述。</span><span class="sxs-lookup"><span data-stu-id="72432-117">Sort orders are described with an [SSortOrderSet](ssortorderset.md) structure.</span></span> 
  
- <span data-ttu-id="72432-118">SSortOrderSet 结构的 **cSorts** 成员可以设置为零（如果：</span><span class="sxs-lookup"><span data-stu-id="72432-118">The **cSorts** member of the **SSortOrderSet** structure can be set to zero if:</span></span> 
    
- <span data-ttu-id="72432-119">该表未排序。</span><span class="sxs-lookup"><span data-stu-id="72432-119">The table is unsorted.</span></span>
    
- <span data-ttu-id="72432-120">没有关于表的排序方式的信息。</span><span class="sxs-lookup"><span data-stu-id="72432-120">There is no information about how the table is sorted.</span></span>
    
- <span data-ttu-id="72432-121">**SSortOrderSet** 结构不适合描述排序顺序。</span><span class="sxs-lookup"><span data-stu-id="72432-121">The **SSortOrderSet** structure is not appropriate for describing the sort order.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="72432-122">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="72432-122">Notes to implementers</span></span>

<span data-ttu-id="72432-123">如果对 [IMAPITable：：SortTable](imapitable-sorttable.md) 方法调用的 **SSortOrderSet** 结构在排序键中包含零列，请删除当前的排序顺序并应用默认顺序（如果有）。</span><span class="sxs-lookup"><span data-stu-id="72432-123">If a call is made to your [IMAPITable::SortTable](imapitable-sorttable.md) method with an **SSortOrderSet** structure containing zero columns in the sort key, remove the current sort order and apply the default order, if there is one.</span></span> <span data-ttu-id="72432-124">在随后对 **QuerySortOrder** 的调用中，您可以选择是返回排序键的零列还是多列。</span><span class="sxs-lookup"><span data-stu-id="72432-124">In subsequent calls to **QuerySortOrder**, you can choose whether to return zero or more columns for the sort key.</span></span> <span data-ttu-id="72432-125">可以返回的列数多于当前视图中的列数。</span><span class="sxs-lookup"><span data-stu-id="72432-125">You can return more columns than are in the present view.</span></span>
  
<span data-ttu-id="72432-126">有关排序详细信息，请参阅排序 [和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="72432-126">For more information about sorting, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="72432-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72432-127">See also</span></span>



[<span data-ttu-id="72432-128">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="72432-128">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="72432-129">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="72432-129">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="72432-130">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="72432-130">SSortOrderSet</span></span>](ssortorderset.md)
  
[<span data-ttu-id="72432-131">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="72432-131">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

