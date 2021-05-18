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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 44ecf095ad24dd266dc5f603ace9c7b9f21c1b41
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408997"
---
# <a name="itabledatahrmodifyrow"></a><span data-ttu-id="b0845-103">ITableData::HrModifyRow</span><span class="sxs-lookup"><span data-stu-id="b0845-103">ITableData::HrModifyRow</span></span>

  
  
<span data-ttu-id="b0845-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b0845-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b0845-105">插入新的表格行，可能会替换现有的行。</span><span class="sxs-lookup"><span data-stu-id="b0845-105">Inserts a new table row, possibly replacing an existing row.</span></span>
  
```cpp
HRESULT HrModifyRow(
  LPSRow lpSRow
);
```

## <a name="parameters"></a><span data-ttu-id="b0845-106">参数</span><span class="sxs-lookup"><span data-stu-id="b0845-106">Parameters</span></span>

 <span data-ttu-id="b0845-107">_lpSRow_</span><span class="sxs-lookup"><span data-stu-id="b0845-107">_lpSRow_</span></span>
  
> <span data-ttu-id="b0845-108">[in]指向描述要添加的行或替换现有行的 [SRow](srow.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b0845-108">[in] A pointer to an [SRow](srow.md) structure that describes the row to be added or to replace an existing row.</span></span> <span data-ttu-id="b0845-109">**SRow** 结构的 **lpProps** 成员指向的属性值结构之一应包含索引列，该值与调用 [CreateTable](createtable.md)函数的 _ulPropTagIndexColumn_ 参数中指定的值相同。</span><span class="sxs-lookup"><span data-stu-id="b0845-109">One of the property value structures pointed to by the **lpProps** member of the **SRow** structure should contain the index column, the same value that was specified in the  _ulPropTagIndexColumn_ parameter in the call to the [CreateTable](createtable.md) function.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b0845-110">返回值</span><span class="sxs-lookup"><span data-stu-id="b0845-110">Return value</span></span>

<span data-ttu-id="b0845-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0845-111">S_OK</span></span> 
  
> <span data-ttu-id="b0845-112">该行已成功插入或修改。</span><span class="sxs-lookup"><span data-stu-id="b0845-112">The row was successfully inserted or modified.</span></span>
    
<span data-ttu-id="b0845-113">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="b0845-113">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="b0845-114">传入行没有索引列。</span><span class="sxs-lookup"><span data-stu-id="b0845-114">The passed-in row does not have an index column.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b0845-115">备注</span><span class="sxs-lookup"><span data-stu-id="b0845-115">Remarks</span></span>

<span data-ttu-id="b0845-116">**ITableData：：HrModifyRow** 方法插入 _由 lpSRow_ 参数指向 **的 SRow** 结构所描述的行。</span><span class="sxs-lookup"><span data-stu-id="b0845-116">The **ITableData::HrModifyRow** method inserts the row described by the **SRow** structure pointed to by the  _lpSRow_ parameter.</span></span> <span data-ttu-id="b0845-117">如果与  _lpSRow_ 所指向的行的索引列值相同的行在表中已存在，则替换现有行。</span><span class="sxs-lookup"><span data-stu-id="b0845-117">If a row that has the same value for its index column as the row that  _lpSRow_ points to already exists in the table, the existing row is replaced.</span></span> <span data-ttu-id="b0845-118">如果不存在与 **SRow** 结构中包含的行匹配的行， **则 HrModifyRow** 会将该行添加到表的末尾。</span><span class="sxs-lookup"><span data-stu-id="b0845-118">If no row exists that matches the one included in the **SRow** structure, **HrModifyRow** adds the row to the end of the table.</span></span> 
  
<span data-ttu-id="b0845-119">该表的所有视图都经过修改，以包括  _lpSRow 指向的行_。</span><span class="sxs-lookup"><span data-stu-id="b0845-119">All views of the table are modified to include the row pointed to by  _lpSRow_.</span></span> <span data-ttu-id="b0845-120">但是，如果视图具有排除行的就地限制，则用户可能无法看到该视图。</span><span class="sxs-lookup"><span data-stu-id="b0845-120">However, if a view has a restriction in place that excludes the row, it may not be visible to the user.</span></span> 
  
<span data-ttu-id="b0845-121">_lpSRow_ 指向的行中的列与表格中的列的顺序不一样。</span><span class="sxs-lookup"><span data-stu-id="b0845-121">The columns in the row pointed to by  _lpSRow_ do not have to be in the same order as the columns in the table.</span></span> <span data-ttu-id="b0845-122">调用方还可以包括为表中当前未包含的列属性。</span><span class="sxs-lookup"><span data-stu-id="b0845-122">The caller can also include as columns properties that are not currently in the table.</span></span> <span data-ttu-id="b0845-123">对于现有视图 **，HrModifyRow** 使这些新列可用，但不包括在当前列集内。</span><span class="sxs-lookup"><span data-stu-id="b0845-123">For existing views, **HrModifyRow** makes these new columns available but does not include them in the current column set.</span></span> <span data-ttu-id="b0845-124">对于以后的视图 **，HrModifyRow** 包括列集的新列。</span><span class="sxs-lookup"><span data-stu-id="b0845-124">For future views, **HrModifyRow** includes the new columns in the column set.</span></span> 
  
<span data-ttu-id="b0845-125">**HrModifyRow** 添加行后，通知将发送到所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md)方法来注册通知的客户端或服务提供商。</span><span class="sxs-lookup"><span data-stu-id="b0845-125">After **HrModifyRow** adds the row, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b0845-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0845-126">See also</span></span>



[<span data-ttu-id="b0845-127">SRow</span><span class="sxs-lookup"><span data-stu-id="b0845-127">SRow</span></span>](srow.md)
  
[<span data-ttu-id="b0845-128">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="b0845-128">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="b0845-129">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b0845-129">ITableData : IUnknown</span></span>](itabledataiunknown.md)

