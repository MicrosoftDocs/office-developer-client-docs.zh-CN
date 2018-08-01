---
title: ITableDataHrModifyRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrModifyRow
api_type:
- COM
ms.assetid: 9e255b3e-dd17-4528-ba4e-c3a1aef32b04
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a1388545597cf0000f270bf693c93f9349fb6426
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776108"
---
# <a name="itabledatahrmodifyrow"></a><span data-ttu-id="3efaf-103">ITableData::HrModifyRow</span><span class="sxs-lookup"><span data-stu-id="3efaf-103">ITableData::HrModifyRow</span></span>

  
  
<span data-ttu-id="3efaf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3efaf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3efaf-105">插入一个新的表格行，原因可能替换现有行。</span><span class="sxs-lookup"><span data-stu-id="3efaf-105">Inserts a new table row, possibly replacing an existing row.</span></span>
  
```cpp
HRESULT HrModifyRow(
  LPSRow lpSRow
);
```

## <a name="parameters"></a><span data-ttu-id="3efaf-106">参数</span><span class="sxs-lookup"><span data-stu-id="3efaf-106">Parameters</span></span>

 <span data-ttu-id="3efaf-107">_lpSRow_</span><span class="sxs-lookup"><span data-stu-id="3efaf-107">_lpSRow_</span></span>
  
> <span data-ttu-id="3efaf-108">[in]一个指向[SRow](srow.md)结构，描述要添加或替换现有行的行。</span><span class="sxs-lookup"><span data-stu-id="3efaf-108">[in] A pointer to an [SRow](srow.md) structure that describes the row to be added or to replace an existing row.</span></span> <span data-ttu-id="3efaf-109">一个指向由**SRow**结构**lpProps**成员的属性值结构应包含索引列中，已对[CreateTable 的调用中的_ulPropTagIndexColumn_参数中指定的相同值](createtable.md)函数。</span><span class="sxs-lookup"><span data-stu-id="3efaf-109">One of the property value structures pointed to by the **lpProps** member of the **SRow** structure should contain the index column, the same value that was specified in the  _ulPropTagIndexColumn_ parameter in the call to the [CreateTable](createtable.md) function.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3efaf-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3efaf-110">Return value</span></span>

<span data-ttu-id="3efaf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3efaf-111">S_OK</span></span> 
  
> <span data-ttu-id="3efaf-112">行成功插入或修改。</span><span class="sxs-lookup"><span data-stu-id="3efaf-112">The row was successfully inserted or modified.</span></span>
    
<span data-ttu-id="3efaf-113">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="3efaf-113">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="3efaf-114">传入的行不具有索引列。</span><span class="sxs-lookup"><span data-stu-id="3efaf-114">The passed-in row does not have an index column.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3efaf-115">说明</span><span class="sxs-lookup"><span data-stu-id="3efaf-115">Remarks</span></span>

<span data-ttu-id="3efaf-116">**ITableData::HrModifyRow**方法插入_lpSRow_参数指向**SRow**结构所描述的行。</span><span class="sxs-lookup"><span data-stu-id="3efaf-116">The **ITableData::HrModifyRow** method inserts the row described by the **SRow** structure pointed to by the  _lpSRow_ parameter.</span></span> <span data-ttu-id="3efaf-117">如果该行的行及其索引列的相同的值的_lpSRow_点表中已存在，将替换现有行。</span><span class="sxs-lookup"><span data-stu-id="3efaf-117">If a row that has the same value for its index column as the row that  _lpSRow_ points to already exists in the table, the existing row is replaced.</span></span> <span data-ttu-id="3efaf-118">如果没有行存在相匹配的**SRow**结构中包含的一个， **HrModifyRow**表末尾添加行。</span><span class="sxs-lookup"><span data-stu-id="3efaf-118">If no row exists that matches the one included in the **SRow** structure, **HrModifyRow** adds the row to the end of the table.</span></span> 
  
<span data-ttu-id="3efaf-119">修改表的所有视图以包括指向_lpSRow_的行。</span><span class="sxs-lookup"><span data-stu-id="3efaf-119">All views of the table are modified to include the row pointed to by  _lpSRow_.</span></span> <span data-ttu-id="3efaf-120">但是，如果视图中排除行的位置有限制，则它可能不对用户可见。</span><span class="sxs-lookup"><span data-stu-id="3efaf-120">However, if a view has a restriction in place that excludes the row, it may not be visible to the user.</span></span> 
  
<span data-ttu-id="3efaf-121">指的_lpSRow_行中的列不需要在表中的列的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="3efaf-121">The columns in the row pointed to by  _lpSRow_ do not have to be in the same order as the columns in the table.</span></span> <span data-ttu-id="3efaf-122">呼叫者还可以包括为当前不是表中的列属性。</span><span class="sxs-lookup"><span data-stu-id="3efaf-122">The caller can also include as columns properties that are not currently in the table.</span></span> <span data-ttu-id="3efaf-123">对于现有视图， **HrModifyRow**使这些新列可用，但不包括其当前列集合中。</span><span class="sxs-lookup"><span data-stu-id="3efaf-123">For existing views, **HrModifyRow** makes these new columns available but does not include them in the current column set.</span></span> <span data-ttu-id="3efaf-124">对于将来视图**HrModifyRow**列设置中包括的新列。</span><span class="sxs-lookup"><span data-stu-id="3efaf-124">For future views, **HrModifyRow** includes the new columns in the column set.</span></span> 
  
<span data-ttu-id="3efaf-125">**HrModifyRow**添加行之后，通知便发送至所有客户端或服务提供商的具有查看表的和已在调用表的[IMAPITable::Advise](imapitable-advise.md)方法注册的通知。</span><span class="sxs-lookup"><span data-stu-id="3efaf-125">After **HrModifyRow** adds the row, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3efaf-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3efaf-126">See also</span></span>



[<span data-ttu-id="3efaf-127">SRow</span><span class="sxs-lookup"><span data-stu-id="3efaf-127">SRow</span></span>](srow.md)
  
[<span data-ttu-id="3efaf-128">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="3efaf-128">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="3efaf-129">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3efaf-129">ITableData : IUnknown</span></span>](itabledataiunknown.md)

