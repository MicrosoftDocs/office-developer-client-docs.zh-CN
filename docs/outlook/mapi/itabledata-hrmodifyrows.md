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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 15d98183548d4b73c35368d690ef63d5c3dfd9af
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776102"
---
# <a name="itabledatahrmodifyrows"></a><span data-ttu-id="93961-103">ITableData::HrModifyRows</span><span class="sxs-lookup"><span data-stu-id="93961-103">ITableData::HrModifyRows</span></span>

  
  
<span data-ttu-id="93961-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="93961-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="93961-105">插入多个表行，原因可能替换现有行。</span><span class="sxs-lookup"><span data-stu-id="93961-105">Inserts multiple table rows, possibly replacing existing rows.</span></span>
  
```cpp
HRESULT HrModifyRows(
  ULONG ulFlags,
  LPSRowSet lpSRowSet
);
```

## <a name="parameters"></a><span data-ttu-id="93961-106">参数</span><span class="sxs-lookup"><span data-stu-id="93961-106">Parameters</span></span>

 <span data-ttu-id="93961-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="93961-107">_ulFlags_</span></span>
  
> <span data-ttu-id="93961-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="93961-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="93961-109">_lpSRowSet_</span><span class="sxs-lookup"><span data-stu-id="93961-109">_lpSRowSet_</span></span>
  
> <span data-ttu-id="93961-110">[in]指向[SRowSet](srowset.md)结构的指针，包含要添加的行集替换现有行，如有必要。</span><span class="sxs-lookup"><span data-stu-id="93961-110">[in] A pointer to an [SRowSet](srowset.md) structure that contains the set of rows to be added, replacing existing rows if necessary.</span></span> <span data-ttu-id="93961-111">一个指向按行中每个[SRow](srow.md)结构的**lpProps**成员设置的属性值结构应包含索引列中，已对[的调用中的_ulPropTagIndexColumn_参数中指定的相同值CreateTable](createtable.md)函数。</span><span class="sxs-lookup"><span data-stu-id="93961-111">One of the property value structures pointed to by the **lpProps** member of each [SRow](srow.md) structure in the row set should contain the index column, the same value that was specified in the  _ulPropTagIndexColumn_ parameter in the call to the [CreateTable](createtable.md) function.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="93961-112">返回值</span><span class="sxs-lookup"><span data-stu-id="93961-112">Return value</span></span>

<span data-ttu-id="93961-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="93961-113">S_OK</span></span> 
  
> <span data-ttu-id="93961-114">已成功插入或修改行。</span><span class="sxs-lookup"><span data-stu-id="93961-114">The rows were successfully inserted or modified.</span></span>
    
<span data-ttu-id="93961-115">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="93961-115">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="93961-116">一个或多个传入的行不具有索引列。</span><span class="sxs-lookup"><span data-stu-id="93961-116">One or more of the passed-in rows does not have an index column.</span></span> <span data-ttu-id="93961-117">如果将返回此错误，不更改任何行。</span><span class="sxs-lookup"><span data-stu-id="93961-117">If this error is returned, no rows are changed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="93961-118">说明</span><span class="sxs-lookup"><span data-stu-id="93961-118">Remarks</span></span>

<span data-ttu-id="93961-119">**ITableData::HrModifyRows**方法插入_lpSRowSet_参数指向[SRowSet](srowset.md)结构所描述的行。</span><span class="sxs-lookup"><span data-stu-id="93961-119">The **ITableData::HrModifyRows** method inserts the rows described by the [SRowSet](srowset.md) structure pointed to by the  _lpSRowSet_ parameter.</span></span> <span data-ttu-id="93961-120">如果在行集中的行的索引列值与现有行表中的值相匹配，将替换现有行。</span><span class="sxs-lookup"><span data-stu-id="93961-120">If the index column value of a row in the row set matches the value for an existing row in the table, the existing row is replaced.</span></span> <span data-ttu-id="93961-121">如果没有行存在相匹配的**SRowSet**结构中包含的一个， **HrModifyRows**表末尾添加行。</span><span class="sxs-lookup"><span data-stu-id="93961-121">If no row exists that matches the one included in the **SRowSet** structure, **HrModifyRows** adds the row to the end of the table.</span></span> 
  
<span data-ttu-id="93961-122">修改表的所有视图以包括指向_lpSRowSet_的行。</span><span class="sxs-lookup"><span data-stu-id="93961-122">All views of the table are modified to include the rows pointed to by  _lpSRowSet_.</span></span> <span data-ttu-id="93961-123">但是，如果视图中排除行的位置有限制，则它可能不对用户可见。</span><span class="sxs-lookup"><span data-stu-id="93961-123">However, if a view has a restriction in place that excludes a row, it may not be visible to the user.</span></span> 
  
<span data-ttu-id="93961-124">指向_lpSRowSet_的行中的列不需要在表中的列的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="93961-124">The columns in the rows pointed to by  _lpSRowSet_ do not have to be in the same order as the columns in the table.</span></span> <span data-ttu-id="93961-125">呼叫者还可以包括为当前不是表中的列属性。</span><span class="sxs-lookup"><span data-stu-id="93961-125">The caller can also include as columns properties that are not currently in the table.</span></span> <span data-ttu-id="93961-126">对于现有视图， **HrModifyRows**使这些新列可用，但不包括其当前列集合中。</span><span class="sxs-lookup"><span data-stu-id="93961-126">For existing views, **HrModifyRows** makes these new columns available but does not include them in the current column set.</span></span> <span data-ttu-id="93961-127">对于将来视图**HrModifyRows**列设置中包括的新列。</span><span class="sxs-lookup"><span data-stu-id="93961-127">For future views, **HrModifyRows** includes the new columns in the column set.</span></span> 
  
<span data-ttu-id="93961-128">**HrModifyRows**已添加行之后，通知便发送至所有客户端或服务提供商的具有查看表的和已在调用表的[IMAPITable::Advise](imapitable-advise.md)方法注册的通知。</span><span class="sxs-lookup"><span data-stu-id="93961-128">After **HrModifyRows** has added the rows, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> <span data-ttu-id="93961-129">MAPI 发送每一行，最多八个行的 TABLE_ROW_ADDED 或 TABLE_ROW_MODIFIED 的通知。</span><span class="sxs-lookup"><span data-stu-id="93961-129">MAPI sends TABLE_ROW_ADDED or TABLE_ROW_MODIFIED notifications for each row, up to eight rows.</span></span> <span data-ttu-id="93961-130">如果不会影响八个以上的行由**HrModifyRows**呼叫，MAPI 发送单个 TABLE_CHANGED 通知相反。</span><span class="sxs-lookup"><span data-stu-id="93961-130">If more than eight rows are affected by the **HrModifyRows** call, MAPI sends a single TABLE_CHANGED notification instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="93961-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93961-131">See also</span></span>



[<span data-ttu-id="93961-132">SRowSet</span><span class="sxs-lookup"><span data-stu-id="93961-132">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="93961-133">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="93961-133">ITableData : IUnknown</span></span>](itabledataiunknown.md)

