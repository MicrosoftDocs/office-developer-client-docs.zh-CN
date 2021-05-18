---
title: ITableDataHrModifyRows
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrModifyRows
api_type:
- COM
ms.assetid: d295c896-9882-4d6f-9689-5cf40db208c0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d0074dd006fda6d44252011d0b979169e0c3d4cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405357"
---
# <a name="itabledatahrmodifyrows"></a><span data-ttu-id="a1673-103">ITableData::HrModifyRows</span><span class="sxs-lookup"><span data-stu-id="a1673-103">ITableData::HrModifyRows</span></span>

  
  
<span data-ttu-id="a1673-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a1673-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a1673-105">插入多个表格行，可能会替换现有行。</span><span class="sxs-lookup"><span data-stu-id="a1673-105">Inserts multiple table rows, possibly replacing existing rows.</span></span>
  
```cpp
HRESULT HrModifyRows(
  ULONG ulFlags,
  LPSRowSet lpSRowSet
);
```

## <a name="parameters"></a><span data-ttu-id="a1673-106">参数</span><span class="sxs-lookup"><span data-stu-id="a1673-106">Parameters</span></span>

 <span data-ttu-id="a1673-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a1673-107">_ulFlags_</span></span>
  
> <span data-ttu-id="a1673-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="a1673-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="a1673-109">_lpSRowSet_</span><span class="sxs-lookup"><span data-stu-id="a1673-109">_lpSRowSet_</span></span>
  
> <span data-ttu-id="a1673-110">[in]指向包含要添加 [的行集的 SRowSet](srowset.md) 结构的指针，如有必要，替换现有行。</span><span class="sxs-lookup"><span data-stu-id="a1673-110">[in] A pointer to an [SRowSet](srowset.md) structure that contains the set of rows to be added, replacing existing rows if necessary.</span></span> <span data-ttu-id="a1673-111">行集内每个 [SRow](srow.md)结构的 **lpProps** 成员指向的属性值结构之一应包含索引列，该值与调用 [CreateTable](createtable.md)函数的 _ulPropTagIndexColumn_ 参数中指定的值相同。</span><span class="sxs-lookup"><span data-stu-id="a1673-111">One of the property value structures pointed to by the **lpProps** member of each [SRow](srow.md) structure in the row set should contain the index column, the same value that was specified in the  _ulPropTagIndexColumn_ parameter in the call to the [CreateTable](createtable.md) function.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a1673-112">返回值</span><span class="sxs-lookup"><span data-stu-id="a1673-112">Return value</span></span>

<span data-ttu-id="a1673-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1673-113">S_OK</span></span> 
  
> <span data-ttu-id="a1673-114">已成功插入或修改行。</span><span class="sxs-lookup"><span data-stu-id="a1673-114">The rows were successfully inserted or modified.</span></span>
    
<span data-ttu-id="a1673-115">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="a1673-115">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="a1673-116">一个或多个传入行没有索引列。</span><span class="sxs-lookup"><span data-stu-id="a1673-116">One or more of the passed-in rows does not have an index column.</span></span> <span data-ttu-id="a1673-117">如果返回此错误，则不更改任何行。</span><span class="sxs-lookup"><span data-stu-id="a1673-117">If this error is returned, no rows are changed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a1673-118">备注</span><span class="sxs-lookup"><span data-stu-id="a1673-118">Remarks</span></span>

<span data-ttu-id="a1673-119">**ITableData：：HrModifyRows** 方法插入 _由 lpSRowSet_ 参数指向 [的 SRowSet](srowset.md)结构所描述的行。</span><span class="sxs-lookup"><span data-stu-id="a1673-119">The **ITableData::HrModifyRows** method inserts the rows described by the [SRowSet](srowset.md) structure pointed to by the  _lpSRowSet_ parameter.</span></span> <span data-ttu-id="a1673-120">如果行集内行的索引列值与表中现有行的值相匹配，则替换现有行。</span><span class="sxs-lookup"><span data-stu-id="a1673-120">If the index column value of a row in the row set matches the value for an existing row in the table, the existing row is replaced.</span></span> <span data-ttu-id="a1673-121">如果不存在与 **SRowSet** 结构中包含的行匹配的行， **则 HrModifyRows** 会将该行添加到表的末尾。</span><span class="sxs-lookup"><span data-stu-id="a1673-121">If no row exists that matches the one included in the **SRowSet** structure, **HrModifyRows** adds the row to the end of the table.</span></span> 
  
<span data-ttu-id="a1673-122">该表的所有视图都经过修改，以包括  _lpSRowSet 指向的行_。</span><span class="sxs-lookup"><span data-stu-id="a1673-122">All views of the table are modified to include the rows pointed to by  _lpSRowSet_.</span></span> <span data-ttu-id="a1673-123">但是，如果视图具有排除行的就地限制，则用户可能无法看到该视图。</span><span class="sxs-lookup"><span data-stu-id="a1673-123">However, if a view has a restriction in place that excludes a row, it may not be visible to the user.</span></span> 
  
<span data-ttu-id="a1673-124">_lpSRowSet_ 指向的行中的列不一定与表中的列的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="a1673-124">The columns in the rows pointed to by  _lpSRowSet_ do not have to be in the same order as the columns in the table.</span></span> <span data-ttu-id="a1673-125">调用方还可以包括为表中当前未包含的列属性。</span><span class="sxs-lookup"><span data-stu-id="a1673-125">The caller can also include as columns properties that are not currently in the table.</span></span> <span data-ttu-id="a1673-126">对于现有视图 **，HrModifyRows** 使这些新列可用，但不包括在当前列集内。</span><span class="sxs-lookup"><span data-stu-id="a1673-126">For existing views, **HrModifyRows** makes these new columns available but does not include them in the current column set.</span></span> <span data-ttu-id="a1673-127">对于将来视图 **，HrModifyRows** 包括列集内的新列。</span><span class="sxs-lookup"><span data-stu-id="a1673-127">For future views, **HrModifyRows** includes the new columns in the column set.</span></span> 
  
<span data-ttu-id="a1673-128">**在 HrModifyRows** 添加行后，通知将发送给所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md)方法来注册通知的客户端或服务提供商。</span><span class="sxs-lookup"><span data-stu-id="a1673-128">After **HrModifyRows** has added the rows, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> <span data-ttu-id="a1673-129">MAPI 发送TABLE_ROW_ADDED或TABLE_ROW_MODIFIED行（最多八行）的通知。</span><span class="sxs-lookup"><span data-stu-id="a1673-129">MAPI sends TABLE_ROW_ADDED or TABLE_ROW_MODIFIED notifications for each row, up to eight rows.</span></span> <span data-ttu-id="a1673-130">如果 **HrModifyRows** 调用影响超过 8 行，MAPI 将改为发送单个TABLE_CHANGED通知。</span><span class="sxs-lookup"><span data-stu-id="a1673-130">If more than eight rows are affected by the **HrModifyRows** call, MAPI sends a single TABLE_CHANGED notification instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a1673-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1673-131">See also</span></span>



[<span data-ttu-id="a1673-132">SRowSet</span><span class="sxs-lookup"><span data-stu-id="a1673-132">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="a1673-133">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a1673-133">ITableData : IUnknown</span></span>](itabledataiunknown.md)

