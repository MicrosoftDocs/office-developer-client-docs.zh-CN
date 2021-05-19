---
title: ITableDataHrDeleteRows
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrDeleteRows
api_type:
- COM
ms.assetid: 7b351eec-9624-4b38-9978-5d0b67b64687
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fdd6f40b4d7aa7f65bf1a46d3d9a4f18472b19f7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416452"
---
# <a name="itabledatahrdeleterows"></a><span data-ttu-id="97e1b-103">ITableData::HrDeleteRows</span><span class="sxs-lookup"><span data-stu-id="97e1b-103">ITableData::HrDeleteRows</span></span>

  
  
<span data-ttu-id="97e1b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="97e1b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="97e1b-105">删除多个表格行。</span><span class="sxs-lookup"><span data-stu-id="97e1b-105">Deletes multiple table rows.</span></span>
  
```cpp
HRESULT HrDeleteRows(
  ULONG ulFlags,
  LPSRowSet lprowsetToDelete,
  ULONG FAR * cRowsDeleted
);
```

## <a name="parameters"></a><span data-ttu-id="97e1b-106">参数</span><span class="sxs-lookup"><span data-stu-id="97e1b-106">Parameters</span></span>

 <span data-ttu-id="97e1b-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="97e1b-107">_ulFlags_</span></span>
  
> <span data-ttu-id="97e1b-108">[in]控制删除的标记的位掩码。</span><span class="sxs-lookup"><span data-stu-id="97e1b-108">[in] A bitmask of flags that controls the deletion.</span></span> <span data-ttu-id="97e1b-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="97e1b-109">The following flag can be set:</span></span>
    
<span data-ttu-id="97e1b-110">TAD_ALL_ROWS</span><span class="sxs-lookup"><span data-stu-id="97e1b-110">TAD_ALL_ROWS</span></span> 
  
> <span data-ttu-id="97e1b-111">从表中删除所有行以及所有相应的视图，发送单个TABLE_RELOAD通知。</span><span class="sxs-lookup"><span data-stu-id="97e1b-111">Deletes all rows from the table and all corresponding views, sending a single TABLE_RELOAD notification.</span></span>
    
 <span data-ttu-id="97e1b-112">_lprowsetToDelete_</span><span class="sxs-lookup"><span data-stu-id="97e1b-112">_lprowsetToDelete_</span></span>
  
> <span data-ttu-id="97e1b-113">[in]指向描述要删除的行的行集的指针。</span><span class="sxs-lookup"><span data-stu-id="97e1b-113">[in] A pointer to a row set that describes the rows to be deleted.</span></span> <span data-ttu-id="97e1b-114">如果在 _ulFlags_ 参数中设置了 TAD_ALL_ROWS 标志，则 _lprowsetToDelete_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="97e1b-114">The  _lprowsetToDelete_ parameter can be NULL if the TAD_ALL_ROWS flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="97e1b-115">_cRowsDeleted_</span><span class="sxs-lookup"><span data-stu-id="97e1b-115">_cRowsDeleted_</span></span>
  
> <span data-ttu-id="97e1b-116">[out]已删除行的计数。</span><span class="sxs-lookup"><span data-stu-id="97e1b-116">[out] The count of the deleted rows.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="97e1b-117">返回值</span><span class="sxs-lookup"><span data-stu-id="97e1b-117">Return value</span></span>

<span data-ttu-id="97e1b-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="97e1b-118">S_OK</span></span> 
  
> <span data-ttu-id="97e1b-119">已成功删除表行。</span><span class="sxs-lookup"><span data-stu-id="97e1b-119">The table rows were successfully deleted.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="97e1b-120">备注</span><span class="sxs-lookup"><span data-stu-id="97e1b-120">Remarks</span></span>

<span data-ttu-id="97e1b-121">**ITableData：：HrDeleteRows** 方法查找并删除包含与行集内每个 **aRow** 条目的 **lpProps** 成员所指向的属性匹配的列的表行。</span><span class="sxs-lookup"><span data-stu-id="97e1b-121">The **ITableData::HrDeleteRows** method locates and removes the table rows that contain the columns that match the property pointed to by the **lpProps** member of each **aRow** entry in the row set.</span></span> <span data-ttu-id="97e1b-122">索引列用于标识每一行;此列必须与调用 [CreateTable](createtable.md)函数的 _ulPropTagIndexColumn_ 参数中传递的属性标记具有相同的属性标记。</span><span class="sxs-lookup"><span data-stu-id="97e1b-122">An index column is used to identify each row; this column must have the same property tag as the property tag passed in the  _ulPropTagIndexColumn_ parameter in the call to the [CreateTable](createtable.md) function.</span></span> 
  
<span data-ttu-id="97e1b-123">实际删除的行数在  _cRowsDeleted 中返回_。</span><span class="sxs-lookup"><span data-stu-id="97e1b-123">The number of rows that were actually deleted is returned in  _cRowsDeleted_.</span></span> <span data-ttu-id="97e1b-124">如果找不到一行或多行，则不返回错误。</span><span class="sxs-lookup"><span data-stu-id="97e1b-124">No error is returned if one or more rows could not be found.</span></span> 
  
<span data-ttu-id="97e1b-125">删除行后，通知将发送给所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md) 方法来注册通知的客户端或服务提供商。</span><span class="sxs-lookup"><span data-stu-id="97e1b-125">After the rows are deleted, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> 
  
<span data-ttu-id="97e1b-126">删除行不会减少可用于现有表视图或随后打开的表视图的列，即使删除的行是具有特定列的值的最后一行。</span><span class="sxs-lookup"><span data-stu-id="97e1b-126">Deleting rows does not reduce the columns available to existing table views or subsequently opened table views, even if the deleted rows are the last that have values for a specific column.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="97e1b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97e1b-127">See also</span></span>



[<span data-ttu-id="97e1b-128">CreateTable</span><span class="sxs-lookup"><span data-stu-id="97e1b-128">CreateTable</span></span>](createtable.md)
  
[<span data-ttu-id="97e1b-129">ITableData::HrDeleteRow</span><span class="sxs-lookup"><span data-stu-id="97e1b-129">ITableData::HrDeleteRow</span></span>](itabledata-hrdeleterow.md)
  
[<span data-ttu-id="97e1b-130">ITableData::HrModifyRows</span><span class="sxs-lookup"><span data-stu-id="97e1b-130">ITableData::HrModifyRows</span></span>](itabledata-hrmodifyrows.md)
  
[<span data-ttu-id="97e1b-131">SRowSet</span><span class="sxs-lookup"><span data-stu-id="97e1b-131">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="97e1b-132">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="97e1b-132">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="97e1b-133">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="97e1b-133">ITableData : IUnknown</span></span>](itabledataiunknown.md)

