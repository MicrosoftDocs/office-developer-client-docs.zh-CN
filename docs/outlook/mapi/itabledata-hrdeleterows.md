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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278945"
---
# <a name="itabledatahrdeleterows"></a><span data-ttu-id="511aa-103">ITableData::HrDeleteRows</span><span class="sxs-lookup"><span data-stu-id="511aa-103">ITableData::HrDeleteRows</span></span>

  
  
<span data-ttu-id="511aa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="511aa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="511aa-105">删除多个表行。</span><span class="sxs-lookup"><span data-stu-id="511aa-105">Deletes multiple table rows.</span></span>
  
```cpp
HRESULT HrDeleteRows(
  ULONG ulFlags,
  LPSRowSet lprowsetToDelete,
  ULONG FAR * cRowsDeleted
);
```

## <a name="parameters"></a><span data-ttu-id="511aa-106">参数</span><span class="sxs-lookup"><span data-stu-id="511aa-106">Parameters</span></span>

 <span data-ttu-id="511aa-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="511aa-107">_ulFlags_</span></span>
  
> <span data-ttu-id="511aa-108">实时用于控制删除的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="511aa-108">[in] A bitmask of flags that controls the deletion.</span></span> <span data-ttu-id="511aa-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="511aa-109">The following flag can be set:</span></span>
    
<span data-ttu-id="511aa-110">TAD_ALL_ROWS</span><span class="sxs-lookup"><span data-stu-id="511aa-110">TAD_ALL_ROWS</span></span> 
  
> <span data-ttu-id="511aa-111">删除表中的所有行和所有对应的视图, 并发送一个 TABLE_RELOAD 通知。</span><span class="sxs-lookup"><span data-stu-id="511aa-111">Deletes all rows from the table and all corresponding views, sending a single TABLE_RELOAD notification.</span></span>
    
 <span data-ttu-id="511aa-112">_lprowsetToDelete_</span><span class="sxs-lookup"><span data-stu-id="511aa-112">_lprowsetToDelete_</span></span>
  
> <span data-ttu-id="511aa-113">实时指向描述要删除的行的行集的指针。</span><span class="sxs-lookup"><span data-stu-id="511aa-113">[in] A pointer to a row set that describes the rows to be deleted.</span></span> <span data-ttu-id="511aa-114">如果在_ulFlags_参数中设置 TAD_ALL_ROWS 标志, 则_lprowsetToDelete_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="511aa-114">The  _lprowsetToDelete_ parameter can be NULL if the TAD_ALL_ROWS flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="511aa-115">_cRowsDeleted_</span><span class="sxs-lookup"><span data-stu-id="511aa-115">_cRowsDeleted_</span></span>
  
> <span data-ttu-id="511aa-116">排除已删除行的计数。</span><span class="sxs-lookup"><span data-stu-id="511aa-116">[out] The count of the deleted rows.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="511aa-117">返回值</span><span class="sxs-lookup"><span data-stu-id="511aa-117">Return value</span></span>

<span data-ttu-id="511aa-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="511aa-118">S_OK</span></span> 
  
> <span data-ttu-id="511aa-119">已成功删除表行。</span><span class="sxs-lookup"><span data-stu-id="511aa-119">The table rows were successfully deleted.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="511aa-120">注解</span><span class="sxs-lookup"><span data-stu-id="511aa-120">Remarks</span></span>

<span data-ttu-id="511aa-121">**ITableData:: HrDeleteRows**方法查找并删除包含与行集中每个**aRow**条目的**lpProps**成员所指向的属性的列相匹配的表格行。</span><span class="sxs-lookup"><span data-stu-id="511aa-121">The **ITableData::HrDeleteRows** method locates and removes the table rows that contain the columns that match the property pointed to by the **lpProps** member of each **aRow** entry in the row set.</span></span> <span data-ttu-id="511aa-122">索引列用于标识每一行;在对[CreateTable](createtable.md)函数的调用中, 此列必须具有与在_ulPropTagIndexColumn_参数中传递的属性标记相同的属性标记。</span><span class="sxs-lookup"><span data-stu-id="511aa-122">An index column is used to identify each row; this column must have the same property tag as the property tag passed in the  _ulPropTagIndexColumn_ parameter in the call to the [CreateTable](createtable.md) function.</span></span> 
  
<span data-ttu-id="511aa-123">实际删除的行数在_cRowsDeleted_中返回。</span><span class="sxs-lookup"><span data-stu-id="511aa-123">The number of rows that were actually deleted is returned in  _cRowsDeleted_.</span></span> <span data-ttu-id="511aa-124">如果找不到一个或多个行, 则不会返回错误。</span><span class="sxs-lookup"><span data-stu-id="511aa-124">No error is returned if one or more rows could not be found.</span></span> 
  
<span data-ttu-id="511aa-125">删除行后, 会将通知发送到具有表视图且已调用表的[IMAPITable:: Advise](imapitable-advise.md)方法以注册通知的所有客户端或服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="511aa-125">After the rows are deleted, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> 
  
<span data-ttu-id="511aa-126">删除行并不会减小现有的表视图或后续打开的表视图的可用列, 即使删除的行是具有特定列的值的最后, 也是如此。</span><span class="sxs-lookup"><span data-stu-id="511aa-126">Deleting rows does not reduce the columns available to existing table views or subsequently opened table views, even if the deleted rows are the last that have values for a specific column.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="511aa-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="511aa-127">See also</span></span>



[<span data-ttu-id="511aa-128">CreateTable</span><span class="sxs-lookup"><span data-stu-id="511aa-128">CreateTable</span></span>](createtable.md)
  
[<span data-ttu-id="511aa-129">ITableData::HrDeleteRow</span><span class="sxs-lookup"><span data-stu-id="511aa-129">ITableData::HrDeleteRow</span></span>](itabledata-hrdeleterow.md)
  
[<span data-ttu-id="511aa-130">ITableData::HrModifyRows</span><span class="sxs-lookup"><span data-stu-id="511aa-130">ITableData::HrModifyRows</span></span>](itabledata-hrmodifyrows.md)
  
[<span data-ttu-id="511aa-131">SRowSet</span><span class="sxs-lookup"><span data-stu-id="511aa-131">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="511aa-132">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="511aa-132">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="511aa-133">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="511aa-133">ITableData : IUnknown</span></span>](itabledataiunknown.md)

