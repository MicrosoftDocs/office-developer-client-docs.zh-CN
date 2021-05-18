---
title: ITableDataHrDeleteRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrDeleteRow
api_type:
- COM
ms.assetid: 670c2291-d5b6-4dcf-9046-9125272dd8f8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b187cccc4505256b7ab4d580c30eeb2e15ebf574
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421674"
---
# <a name="itabledatahrdeleterow"></a><span data-ttu-id="94d68-103">ITableData::HrDeleteRow</span><span class="sxs-lookup"><span data-stu-id="94d68-103">ITableData::HrDeleteRow</span></span>

  
  
<span data-ttu-id="94d68-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="94d68-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="94d68-105">删除表格行。</span><span class="sxs-lookup"><span data-stu-id="94d68-105">Deletes a table row.</span></span>
  
```cpp
HRESULT HrDeleteRow(
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a><span data-ttu-id="94d68-106">参数</span><span class="sxs-lookup"><span data-stu-id="94d68-106">Parameters</span></span>

 <span data-ttu-id="94d68-107">_lpSPropValue_</span><span class="sxs-lookup"><span data-stu-id="94d68-107">_lpSPropValue_</span></span>
  
> <span data-ttu-id="94d68-108">[in]指向描述要删除的行的索引列的属性值结构的指针。</span><span class="sxs-lookup"><span data-stu-id="94d68-108">[in] A pointer to a property value structure that describes the index column for the row to be deleted.</span></span> <span data-ttu-id="94d68-109">属性值 **结构的 ulPropTag** 成员应包含与从调用 [CreateTable](createtable.md)函数调用中的 _ulPropTagIndexColumn_ 参数相同的属性标记。</span><span class="sxs-lookup"><span data-stu-id="94d68-109">The **ulPropTag** member of the property value structure should contain the same property tag as the  _ulPropTagIndexColumn_ parameter from the call to the [CreateTable](createtable.md) function.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="94d68-110">返回值</span><span class="sxs-lookup"><span data-stu-id="94d68-110">Return value</span></span>

<span data-ttu-id="94d68-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="94d68-111">S_OK</span></span> 
  
> <span data-ttu-id="94d68-112">该行已成功删除。</span><span class="sxs-lookup"><span data-stu-id="94d68-112">The row was successfully deleted.</span></span>
    
<span data-ttu-id="94d68-113">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="94d68-113">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="94d68-114">_lpSPropValue_ 参数指向的属性不标识表中的行。</span><span class="sxs-lookup"><span data-stu-id="94d68-114">The property pointed to by the  _lpSPropValue_ parameter does not identify a row in the table.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="94d68-115">备注</span><span class="sxs-lookup"><span data-stu-id="94d68-115">Remarks</span></span>

<span data-ttu-id="94d68-116">**ITableData：：HrDeleteRow** 方法删除包含与 _lpSPropValue_ 参数指向的属性匹配的列的表行。</span><span class="sxs-lookup"><span data-stu-id="94d68-116">The **ITableData::HrDeleteRow** method removes the table row that contains the column that matches the property pointed to by the  _lpSPropValue_ parameter.</span></span> <span data-ttu-id="94d68-117">该行的数据将被删除，并且该行将从所有打开的视图中删除。</span><span class="sxs-lookup"><span data-stu-id="94d68-117">The data for the row is deleted and the row is removed from all open views.</span></span> 
  
<span data-ttu-id="94d68-118">删除行后，通知将发送给所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md) 方法来注册通知的客户端或服务提供商。</span><span class="sxs-lookup"><span data-stu-id="94d68-118">After the row is deleted, notifications are sent to all clients or service providers that have a view of the table and that have called the table's [IMAPITable::Advise](imapitable-advise.md) method to register for notifications.</span></span> 
  
<span data-ttu-id="94d68-119">删除行不会减少可用于现有视图或随后打开的视图的列集，即使删除的行是具有特定列的值的最后一行。</span><span class="sxs-lookup"><span data-stu-id="94d68-119">Deleting a row does not reduce the column set that is available to existing views or subsequently opened views, even if the deleted row is the last row that has a value for a specific column.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="94d68-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94d68-120">See also</span></span>



[<span data-ttu-id="94d68-121">CreateTable</span><span class="sxs-lookup"><span data-stu-id="94d68-121">CreateTable</span></span>](createtable.md)
  
[<span data-ttu-id="94d68-122">ITableData::HrDeleteRows</span><span class="sxs-lookup"><span data-stu-id="94d68-122">ITableData::HrDeleteRows</span></span>](itabledata-hrdeleterows.md)
  
[<span data-ttu-id="94d68-123">ITableData::HrModifyRow</span><span class="sxs-lookup"><span data-stu-id="94d68-123">ITableData::HrModifyRow</span></span>](itabledata-hrmodifyrow.md)
  
[<span data-ttu-id="94d68-124">SPropValue</span><span class="sxs-lookup"><span data-stu-id="94d68-124">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="94d68-125">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="94d68-125">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="94d68-126">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="94d68-126">ITableData : IUnknown</span></span>](itabledataiunknown.md)

