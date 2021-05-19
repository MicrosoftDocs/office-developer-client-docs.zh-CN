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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435437"
---
# <a name="itabledatahrinsertrow"></a><span data-ttu-id="70e79-103">ITableData::HrInsertRow</span><span class="sxs-lookup"><span data-stu-id="70e79-103">ITableData::HrInsertRow</span></span>

  
  
<span data-ttu-id="70e79-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70e79-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70e79-105">插入表格行。</span><span class="sxs-lookup"><span data-stu-id="70e79-105">Inserts a table row.</span></span> 
  
```cpp
HRESULT HrInsertRow(
  ULONG uliRow,
  LPSRow lpSRow
);
```

## <a name="parameters"></a><span data-ttu-id="70e79-106">参数</span><span class="sxs-lookup"><span data-stu-id="70e79-106">Parameters</span></span>

 <span data-ttu-id="70e79-107">_一起_</span><span class="sxs-lookup"><span data-stu-id="70e79-107">_uliRow_</span></span>
  
> <span data-ttu-id="70e79-108">[in]一个代表特定行的顺序行号。</span><span class="sxs-lookup"><span data-stu-id="70e79-108">[in] A sequential row number that represents a specific row.</span></span> <span data-ttu-id="70e79-109">新行将放置在数字指示的行之后。</span><span class="sxs-lookup"><span data-stu-id="70e79-109">The new row will be placed after the row that the number indicates.</span></span> <span data-ttu-id="70e79-110">_uliRow_ 参数可包含 0 到 n 之间的行号，其中 n 是表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="70e79-110">The  _uliRow_ parameter can contains row numbers from 0 through n, where n is the total number of rows in the table.</span></span> <span data-ttu-id="70e79-111">在  _一行中传递_ n 将行追加到表的末尾。</span><span class="sxs-lookup"><span data-stu-id="70e79-111">Passing n in  _uliRow_ appends the row to the end of the table.</span></span> 
    
 <span data-ttu-id="70e79-112">_lpSRow_</span><span class="sxs-lookup"><span data-stu-id="70e79-112">_lpSRow_</span></span>
  
> <span data-ttu-id="70e79-113">[in]指向描述要插入的行的 [SRow](srow.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="70e79-113">[in] A pointer to an [SRow](srow.md) structure that describes the row to be inserted.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="70e79-114">返回值</span><span class="sxs-lookup"><span data-stu-id="70e79-114">Return value</span></span>

<span data-ttu-id="70e79-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="70e79-115">S_OK</span></span> 
  
> <span data-ttu-id="70e79-116">该行已成功插入。</span><span class="sxs-lookup"><span data-stu-id="70e79-116">The row was successfully inserted.</span></span>
    
<span data-ttu-id="70e79-117">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="70e79-117">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="70e79-118">表中已存在与要插入的行具有相同的索引列值的行。</span><span class="sxs-lookup"><span data-stu-id="70e79-118">A row that has the same value for its index column as the row to be inserted already exists in the table.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="70e79-119">备注</span><span class="sxs-lookup"><span data-stu-id="70e79-119">Remarks</span></span>

<span data-ttu-id="70e79-120">**ITableData：：HrInsertRow** 方法将一行插入到表中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="70e79-120">The **ITableData::HrInsertRow** method inserts a row into a table at a particular position.</span></span> <span data-ttu-id="70e79-121">新行将插入到 一行之后，该行位于  _一行中由 一行参数_ 指定的位置。</span><span class="sxs-lookup"><span data-stu-id="70e79-121">The new row is inserted after the row that is in the position specified by the  _uliRow_ parameter.</span></span> 
  
<span data-ttu-id="70e79-122">如果  _一行_ 设置为表格中的行数，则新行将追加到表格的末尾。</span><span class="sxs-lookup"><span data-stu-id="70e79-122">If  _uliRow_ is set to the number of rows in the table, the new row is appended to the end of the table.</span></span> 
  
<span data-ttu-id="70e79-123">充当表的索引列的属性必须包含在 _lpSRow_ 参数指向 [的 SRow](srow.md)结构的 **lpProps** 成员中。</span><span class="sxs-lookup"><span data-stu-id="70e79-123">The property that acts as the index column for the table must be included in the **lpProps** member of the [SRow](srow.md) structure pointed to by the  _lpSRow_ parameter.</span></span> <span data-ttu-id="70e79-124">此索引属性通常PR_INSTANCE_KEY ( [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) ，用于唯一标识用于将来维护任务的行。</span><span class="sxs-lookup"><span data-stu-id="70e79-124">This index property, typically **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)), is used to uniquely identify the row for future maintenance tasks.</span></span>
  
<span data-ttu-id="70e79-125">**SRow** 结构中的属性列不一定与表中的属性列的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="70e79-125">The property columns in the **SRow** structure do not have to be in the same order as the property columns in the table.</span></span> 
  
<span data-ttu-id="70e79-126">插入行后，通知将发送给所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md) 方法来注册通知的客户端或服务提供商。</span><span class="sxs-lookup"><span data-stu-id="70e79-126">After the row is inserted, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> <span data-ttu-id="70e79-127">如果由于限制而未在视图中包含插入的行，则不发送任何通知。</span><span class="sxs-lookup"><span data-stu-id="70e79-127">No notification is sent if the inserted row is not included in the view due to a restriction.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="70e79-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70e79-128">See also</span></span>



[<span data-ttu-id="70e79-129">SRow</span><span class="sxs-lookup"><span data-stu-id="70e79-129">SRow</span></span>](srow.md)
  
[<span data-ttu-id="70e79-130">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="70e79-130">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="70e79-131">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="70e79-131">ITableData : IUnknown</span></span>](itabledataiunknown.md)

