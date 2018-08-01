---
title: ITableDataHrInsertRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrInsertRow
api_type:
- COM
ms.assetid: e5ae37ea-81a5-49c7-9ad0-0bfac518426c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 29fdbf060576ee9309473fddf8740b06229dae9c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776080"
---
# <a name="itabledatahrinsertrow"></a><span data-ttu-id="0a71c-103">ITableData::HrInsertRow</span><span class="sxs-lookup"><span data-stu-id="0a71c-103">ITableData::HrInsertRow</span></span>

  
  
<span data-ttu-id="0a71c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0a71c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0a71c-105">插入表格行。</span><span class="sxs-lookup"><span data-stu-id="0a71c-105">Inserts a table row.</span></span> 
  
```cpp
HRESULT HrInsertRow(
  ULONG uliRow,
  LPSRow lpSRow
);
```

## <a name="parameters"></a><span data-ttu-id="0a71c-106">参数</span><span class="sxs-lookup"><span data-stu-id="0a71c-106">Parameters</span></span>

 <span data-ttu-id="0a71c-107">_uliRow_</span><span class="sxs-lookup"><span data-stu-id="0a71c-107">_uliRow_</span></span>
  
> <span data-ttu-id="0a71c-108">[in]代表对特定行顺序的行号。</span><span class="sxs-lookup"><span data-stu-id="0a71c-108">[in] A sequential row number that represents a specific row.</span></span> <span data-ttu-id="0a71c-109">将数字表示的行后面放置新行。</span><span class="sxs-lookup"><span data-stu-id="0a71c-109">The new row will be placed after the row that the number indicates.</span></span> <span data-ttu-id="0a71c-110">_UliRow_参数可以包含从 0 到 n 的行号，其中 n 是表中的行的总数。</span><span class="sxs-lookup"><span data-stu-id="0a71c-110">The  _uliRow_ parameter can contains row numbers from 0 through n, where n is the total number of rows in the table.</span></span> <span data-ttu-id="0a71c-111">_UliRow_中传递 n 追加表末尾的行。</span><span class="sxs-lookup"><span data-stu-id="0a71c-111">Passing n in  _uliRow_ appends the row to the end of the table.</span></span> 
    
 <span data-ttu-id="0a71c-112">_lpSRow_</span><span class="sxs-lookup"><span data-stu-id="0a71c-112">_lpSRow_</span></span>
  
> <span data-ttu-id="0a71c-113">[in]一个指向[SRow](srow.md)结构，描述要插入的行。</span><span class="sxs-lookup"><span data-stu-id="0a71c-113">[in] A pointer to an [SRow](srow.md) structure that describes the row to be inserted.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0a71c-114">返回值</span><span class="sxs-lookup"><span data-stu-id="0a71c-114">Return value</span></span>

<span data-ttu-id="0a71c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a71c-115">S_OK</span></span> 
  
> <span data-ttu-id="0a71c-116">成功插入行。</span><span class="sxs-lookup"><span data-stu-id="0a71c-116">The row was successfully inserted.</span></span>
    
<span data-ttu-id="0a71c-117">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="0a71c-117">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="0a71c-118">都有其索引列的值相同，如下表中存在已插入的行的行。</span><span class="sxs-lookup"><span data-stu-id="0a71c-118">A row that has the same value for its index column as the row to be inserted already exists in the table.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0a71c-119">说明</span><span class="sxs-lookup"><span data-stu-id="0a71c-119">Remarks</span></span>

<span data-ttu-id="0a71c-120">**ITableData::HrInsertRow**方法插入表格中的特定位置插入一行。</span><span class="sxs-lookup"><span data-stu-id="0a71c-120">The **ITableData::HrInsertRow** method inserts a row into a table at a particular position.</span></span> <span data-ttu-id="0a71c-121">_UliRow_参数指定的位置中的行后面插入新行。</span><span class="sxs-lookup"><span data-stu-id="0a71c-121">The new row is inserted after the row that is in the position specified by the  _uliRow_ parameter.</span></span> 
  
<span data-ttu-id="0a71c-122">_UliRow_设置为表中的行数，如果新行所追加到末尾的表。</span><span class="sxs-lookup"><span data-stu-id="0a71c-122">If  _uliRow_ is set to the number of rows in the table, the new row is appended to the end of the table.</span></span> 
  
<span data-ttu-id="0a71c-123">[SRow](srow.md)结构_lpSRow_参数指向的**lpProps**成员必须包含充当表的索引列的属性。</span><span class="sxs-lookup"><span data-stu-id="0a71c-123">The property that acts as the index column for the table must be included in the **lpProps** member of the [SRow](srow.md) structure pointed to by the  _lpSRow_ parameter.</span></span> <span data-ttu-id="0a71c-124">此索引属性，通常**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))，用于唯一标识未来的维护任务的行。</span><span class="sxs-lookup"><span data-stu-id="0a71c-124">This index property, typically **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)), is used to uniquely identify the row for future maintenance tasks.</span></span>
  
<span data-ttu-id="0a71c-125">**SRow**结构中的属性列不必为表中的属性列的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="0a71c-125">The property columns in the **SRow** structure do not have to be in the same order as the property columns in the table.</span></span> 
  
<span data-ttu-id="0a71c-126">插入行之后，通知便发送至所有客户端或服务提供商的具有查看表的和已在调用表的[IMAPITable::Advise](imapitable-advise.md)方法注册的通知。</span><span class="sxs-lookup"><span data-stu-id="0a71c-126">After the row is inserted, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> <span data-ttu-id="0a71c-127">如果由于限制的视图中不包含插入的行，则不发送任何通知。</span><span class="sxs-lookup"><span data-stu-id="0a71c-127">No notification is sent if the inserted row is not included in the view due to a restriction.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0a71c-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a71c-128">See also</span></span>



[<span data-ttu-id="0a71c-129">SRow</span><span class="sxs-lookup"><span data-stu-id="0a71c-129">SRow</span></span>](srow.md)
  
[<span data-ttu-id="0a71c-130">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="0a71c-130">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="0a71c-131">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0a71c-131">ITableData : IUnknown</span></span>](itabledataiunknown.md)

