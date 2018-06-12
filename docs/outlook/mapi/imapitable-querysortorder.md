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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b5eb671be022a6c3aa22e66f68386691fe23b275
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775711"
---
# <a name="imapitablequerysortorder"></a><span data-ttu-id="d7008-103">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="d7008-103">IMAPITable::QuerySortOrder</span></span>

  
  
<span data-ttu-id="d7008-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d7008-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d7008-105">检索当前表格排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d7008-105">Retrieves the current sort order for a table.</span></span>
  
```cpp
HRESULT QuerySortOrder(
LPSSortOrderSet FAR * lppSortCriteria
);
```

## <a name="parameters"></a><span data-ttu-id="d7008-106">参数</span><span class="sxs-lookup"><span data-stu-id="d7008-106">Parameters</span></span>

 <span data-ttu-id="d7008-107">_lppSortCriteria_</span><span class="sxs-lookup"><span data-stu-id="d7008-107">_lppSortCriteria_</span></span>
  
> <span data-ttu-id="d7008-108">[输出]为存放当前的排序顺序[SSortOrderSet](ssortorderset.md)结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d7008-108">[out] Pointer to a pointer to the [SSortOrderSet](ssortorderset.md) structure holding the current sort order.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d7008-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d7008-109">Return value</span></span>

<span data-ttu-id="d7008-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7008-110">S_OK</span></span> 
  
> <span data-ttu-id="d7008-111">已成功返回当前的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d7008-111">The current sort order was successfully returned.</span></span>
    
<span data-ttu-id="d7008-112">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="d7008-112">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="d7008-113">阻止排序顺序检索操作启动的正在进行中是另一个操作。</span><span class="sxs-lookup"><span data-stu-id="d7008-113">Another operation is in progress that prevents the sort order retrieval operation from starting.</span></span> <span data-ttu-id="d7008-114">应允许正在进行的操作完成或应停止。</span><span class="sxs-lookup"><span data-stu-id="d7008-114">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d7008-115">备注</span><span class="sxs-lookup"><span data-stu-id="d7008-115">Remarks</span></span>

<span data-ttu-id="d7008-116">**IMAPITable::QuerySortOrder**方法检索当前表格排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d7008-116">The **IMAPITable::QuerySortOrder** method retrieves the current sort order for a table.</span></span> <span data-ttu-id="d7008-117">[SSortOrderSet](ssortorderset.md)结构描述都排序次序。</span><span class="sxs-lookup"><span data-stu-id="d7008-117">Sort orders are described with an [SSortOrderSet](ssortorderset.md) structure.</span></span> 
  
- <span data-ttu-id="d7008-118">**SSortOrderSet**结构的**cSorts**成员可以设置为零，如果：</span><span class="sxs-lookup"><span data-stu-id="d7008-118">The **cSorts** member of the **SSortOrderSet** structure can be set to zero if:</span></span> 
    
- <span data-ttu-id="d7008-119">表未排序。</span><span class="sxs-lookup"><span data-stu-id="d7008-119">The table is unsorted.</span></span>
    
- <span data-ttu-id="d7008-120">没有任何信息对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="d7008-120">There is no information about how the table is sorted.</span></span>
    
- <span data-ttu-id="d7008-121">**SSortOrderSet**结构不适合描述的排序次序。</span><span class="sxs-lookup"><span data-stu-id="d7008-121">The **SSortOrderSet** structure is not appropriate for describing the sort order.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="d7008-122">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="d7008-122">Notes to implementers</span></span>

<span data-ttu-id="d7008-123">如果具有包含零个列的排序关键字**SSortOrderSet**结构进行[IMAPITable::SortTable](imapitable-sorttable.md)方法调用时，删除当前的排序顺序，并应用默认的顺序，如果有。</span><span class="sxs-lookup"><span data-stu-id="d7008-123">If a call is made to your [IMAPITable::SortTable](imapitable-sorttable.md) method with an **SSortOrderSet** structure containing zero columns in the sort key, remove the current sort order and apply the default order, if there is one.</span></span> <span data-ttu-id="d7008-124">中到**QuerySortOrder**的后续呼叫，您可以选择是否返回零个或多个列的排序关键字。</span><span class="sxs-lookup"><span data-stu-id="d7008-124">In subsequent calls to **QuerySortOrder**, you can choose whether to return zero or more columns for the sort key.</span></span> <span data-ttu-id="d7008-125">您可以返回多于存在视图中的列数。</span><span class="sxs-lookup"><span data-stu-id="d7008-125">You can return more columns than are in the present view.</span></span>
  
<span data-ttu-id="d7008-126">有关排序的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="d7008-126">For more information about sorting, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d7008-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7008-127">See also</span></span>



[<span data-ttu-id="d7008-128">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="d7008-128">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="d7008-129">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="d7008-129">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="d7008-130">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="d7008-130">SSortOrderSet</span></span>](ssortorderset.md)
  
[<span data-ttu-id="d7008-131">IMAPITable: IUnknown</span><span class="sxs-lookup"><span data-stu-id="d7008-131">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

