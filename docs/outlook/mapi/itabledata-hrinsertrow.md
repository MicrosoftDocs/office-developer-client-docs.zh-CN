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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2709ac612fc9e2edaa57b280d52c0a5229ee9978
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278804"
---
# <a name="itabledatahrinsertrow"></a><span data-ttu-id="d3d97-103">ITableData::HrInsertRow</span><span class="sxs-lookup"><span data-stu-id="d3d97-103">ITableData::HrInsertRow</span></span>

  
  
<span data-ttu-id="d3d97-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3d97-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3d97-105">插入一个表格行。</span><span class="sxs-lookup"><span data-stu-id="d3d97-105">Inserts a table row.</span></span> 
  
```cpp
HRESULT HrInsertRow(
  ULONG uliRow,
  LPSRow lpSRow
);
```

## <a name="parameters"></a><span data-ttu-id="d3d97-106">参数</span><span class="sxs-lookup"><span data-stu-id="d3d97-106">Parameters</span></span>

 <span data-ttu-id="d3d97-107">_uliRow_</span><span class="sxs-lookup"><span data-stu-id="d3d97-107">_uliRow_</span></span>
  
> <span data-ttu-id="d3d97-108">实时一个表示特定行的按顺序的行号。</span><span class="sxs-lookup"><span data-stu-id="d3d97-108">[in] A sequential row number that represents a specific row.</span></span> <span data-ttu-id="d3d97-109">新行将放置在该数字所指示的行之后。</span><span class="sxs-lookup"><span data-stu-id="d3d97-109">The new row will be placed after the row that the number indicates.</span></span> <span data-ttu-id="d3d97-110">_uliRow_参数可以包含从0到 n 的行号, 其中 n 是表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="d3d97-110">The  _uliRow_ parameter can contains row numbers from 0 through n, where n is the total number of rows in the table.</span></span> <span data-ttu-id="d3d97-111">在_uliRow_中传递 n 会将行追加到表的末尾。</span><span class="sxs-lookup"><span data-stu-id="d3d97-111">Passing n in  _uliRow_ appends the row to the end of the table.</span></span> 
    
 <span data-ttu-id="d3d97-112">_lpSRow_</span><span class="sxs-lookup"><span data-stu-id="d3d97-112">_lpSRow_</span></span>
  
> <span data-ttu-id="d3d97-113">实时指向描述要插入的行的[SRow](srow.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="d3d97-113">[in] A pointer to an [SRow](srow.md) structure that describes the row to be inserted.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d3d97-114">返回值</span><span class="sxs-lookup"><span data-stu-id="d3d97-114">Return value</span></span>

<span data-ttu-id="d3d97-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3d97-115">S_OK</span></span> 
  
> <span data-ttu-id="d3d97-116">已成功插入该行。</span><span class="sxs-lookup"><span data-stu-id="d3d97-116">The row was successfully inserted.</span></span>
    
<span data-ttu-id="d3d97-117">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="d3d97-117">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="d3d97-118">与要插入的行在表中已存在的索引列具有相同值的行。</span><span class="sxs-lookup"><span data-stu-id="d3d97-118">A row that has the same value for its index column as the row to be inserted already exists in the table.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d3d97-119">注解</span><span class="sxs-lookup"><span data-stu-id="d3d97-119">Remarks</span></span>

<span data-ttu-id="d3d97-120">**ITableData:: HrInsertRow**方法在表中的特定位置插入一行。</span><span class="sxs-lookup"><span data-stu-id="d3d97-120">The **ITableData::HrInsertRow** method inserts a row into a table at a particular position.</span></span> <span data-ttu-id="d3d97-121">在_uliRow_参数所指定的位置中的行之后插入新行。</span><span class="sxs-lookup"><span data-stu-id="d3d97-121">The new row is inserted after the row that is in the position specified by the  _uliRow_ parameter.</span></span> 
  
<span data-ttu-id="d3d97-122">如果将_uliRow_设置为表格中的行数, 则新行将追加到表的末尾。</span><span class="sxs-lookup"><span data-stu-id="d3d97-122">If  _uliRow_ is set to the number of rows in the table, the new row is appended to the end of the table.</span></span> 
  
<span data-ttu-id="d3d97-123">充当表的索引列的属性必须包含在_lpSRow_参数指向的[SRow](srow.md)结构的**lpProps**成员中。</span><span class="sxs-lookup"><span data-stu-id="d3d97-123">The property that acts as the index column for the table must be included in the **lpProps** member of the [SRow](srow.md) structure pointed to by the  _lpSRow_ parameter.</span></span> <span data-ttu-id="d3d97-124">此索引属性 (通常为**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))) 用于唯一标识该行, 以用于将来的维护任务。</span><span class="sxs-lookup"><span data-stu-id="d3d97-124">This index property, typically **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)), is used to uniquely identify the row for future maintenance tasks.</span></span>
  
<span data-ttu-id="d3d97-125">**SRow**结构中的属性列不必与表中的属性列的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="d3d97-125">The property columns in the **SRow** structure do not have to be in the same order as the property columns in the table.</span></span> 
  
<span data-ttu-id="d3d97-126">在插入行后, 会将通知发送到具有表视图且已调用表的[IMAPITable:: Advise](imapitable-advise.md)方法以注册通知的所有客户端或服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="d3d97-126">After the row is inserted, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> <span data-ttu-id="d3d97-127">如果由于限制而在视图中不包含所插入的行, 则不会发送任何通知。</span><span class="sxs-lookup"><span data-stu-id="d3d97-127">No notification is sent if the inserted row is not included in the view due to a restriction.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d3d97-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3d97-128">See also</span></span>



[<span data-ttu-id="d3d97-129">SRow</span><span class="sxs-lookup"><span data-stu-id="d3d97-129">SRow</span></span>](srow.md)
  
[<span data-ttu-id="d3d97-130">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="d3d97-130">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="d3d97-131">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d3d97-131">ITableData : IUnknown</span></span>](itabledataiunknown.md)

