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
# <a name="imapitablequerysortorder"></a><span data-ttu-id="07acf-103">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="07acf-103">IMAPITable::QuerySortOrder</span></span>

  
  
<span data-ttu-id="07acf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="07acf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="07acf-105">检索表的当前排序顺序。</span><span class="sxs-lookup"><span data-stu-id="07acf-105">Retrieves the current sort order for a table.</span></span>
  
```cpp
HRESULT QuerySortOrder(
LPSSortOrderSet FAR * lppSortCriteria
);
```

## <a name="parameters"></a><span data-ttu-id="07acf-106">参数</span><span class="sxs-lookup"><span data-stu-id="07acf-106">Parameters</span></span>

 <span data-ttu-id="07acf-107">_lppSortCriteria_</span><span class="sxs-lookup"><span data-stu-id="07acf-107">_lppSortCriteria_</span></span>
  
> <span data-ttu-id="07acf-108">排除指向包含当前排序顺序的[SSortOrderSet](ssortorderset.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="07acf-108">[out] Pointer to a pointer to the [SSortOrderSet](ssortorderset.md) structure holding the current sort order.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="07acf-109">返回值</span><span class="sxs-lookup"><span data-stu-id="07acf-109">Return value</span></span>

<span data-ttu-id="07acf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="07acf-110">S_OK</span></span> 
  
> <span data-ttu-id="07acf-111">已成功返回当前排序顺序。</span><span class="sxs-lookup"><span data-stu-id="07acf-111">The current sort order was successfully returned.</span></span>
    
<span data-ttu-id="07acf-112">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="07acf-112">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="07acf-113">正在进行另一个操作, 以阻止排序顺序检索操作开始。</span><span class="sxs-lookup"><span data-stu-id="07acf-113">Another operation is in progress that prevents the sort order retrieval operation from starting.</span></span> <span data-ttu-id="07acf-114">应允许正在进行的操作完成, 或者应已停止。</span><span class="sxs-lookup"><span data-stu-id="07acf-114">Either the operation in progress should be allowed to complete or it should be stopped.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="07acf-115">说明</span><span class="sxs-lookup"><span data-stu-id="07acf-115">Remarks</span></span>

<span data-ttu-id="07acf-116">**IMAPITable:: QuerySortOrder**方法检索表的当前排序顺序。</span><span class="sxs-lookup"><span data-stu-id="07acf-116">The **IMAPITable::QuerySortOrder** method retrieves the current sort order for a table.</span></span> <span data-ttu-id="07acf-117">排序顺序是使用[SSortOrderSet](ssortorderset.md)结构进行描述的。</span><span class="sxs-lookup"><span data-stu-id="07acf-117">Sort orders are described with an [SSortOrderSet](ssortorderset.md) structure.</span></span> 
  
- <span data-ttu-id="07acf-118">如果为以下情况, **SSortOrderSet**结构的**cSorts**成员可设置为零:</span><span class="sxs-lookup"><span data-stu-id="07acf-118">The **cSorts** member of the **SSortOrderSet** structure can be set to zero if:</span></span> 
    
- <span data-ttu-id="07acf-119">该表未排序。</span><span class="sxs-lookup"><span data-stu-id="07acf-119">The table is unsorted.</span></span>
    
- <span data-ttu-id="07acf-120">不存在有关如何对表进行排序的信息。</span><span class="sxs-lookup"><span data-stu-id="07acf-120">There is no information about how the table is sorted.</span></span>
    
- <span data-ttu-id="07acf-121">**SSortOrderSet**结构不适合用于描述排序顺序。</span><span class="sxs-lookup"><span data-stu-id="07acf-121">The **SSortOrderSet** structure is not appropriate for describing the sort order.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="07acf-122">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="07acf-122">Notes to implementers</span></span>

<span data-ttu-id="07acf-123">如果使用在排序关键字中包含零列的**SSortOrderSet**结构对[IMAPITable:: SortTable](imapitable-sorttable.md)方法进行了调用, 则删除当前排序顺序并应用默认顺序 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="07acf-123">If a call is made to your [IMAPITable::SortTable](imapitable-sorttable.md) method with an **SSortOrderSet** structure containing zero columns in the sort key, remove the current sort order and apply the default order, if there is one.</span></span> <span data-ttu-id="07acf-124">在对**QuerySortOrder**的后续调用中, 可以选择是否返回零个或多个用于排序关键字的列。</span><span class="sxs-lookup"><span data-stu-id="07acf-124">In subsequent calls to **QuerySortOrder**, you can choose whether to return zero or more columns for the sort key.</span></span> <span data-ttu-id="07acf-125">您可以返回的列数多于当前视图中的列数。</span><span class="sxs-lookup"><span data-stu-id="07acf-125">You can return more columns than are in the present view.</span></span>
  
<span data-ttu-id="07acf-126">有关排序的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。</span><span class="sxs-lookup"><span data-stu-id="07acf-126">For more information about sorting, see [Sorting and Categorization](sorting-and-categorization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="07acf-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07acf-127">See also</span></span>



[<span data-ttu-id="07acf-128">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="07acf-128">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="07acf-129">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="07acf-129">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="07acf-130">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="07acf-130">SSortOrderSet</span></span>](ssortorderset.md)
  
[<span data-ttu-id="07acf-131">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="07acf-131">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

