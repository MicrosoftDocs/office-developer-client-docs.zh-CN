---
title: ITableDataHrNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrNotify
api_type:
- COM
ms.assetid: 98548b50-342e-434a-9ad3-c37ba418c5ce
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1be4fd95d29859c542fe553bdc3728ea23444694
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776103"
---
# <a name="itabledatahrnotify"></a><span data-ttu-id="e8022-103">ITableData::HrNotify</span><span class="sxs-lookup"><span data-stu-id="e8022-103">ITableData::HrNotify</span></span>

  
  
<span data-ttu-id="e8022-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e8022-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e8022-105">发送通知的表格行。</span><span class="sxs-lookup"><span data-stu-id="e8022-105">Sends a notification for a table row.</span></span>
  
```cpp
HRESULT HrNotify(
  ULONG ulFlags,
  ULONG cValues,
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a><span data-ttu-id="e8022-106">参数</span><span class="sxs-lookup"><span data-stu-id="e8022-106">Parameters</span></span>

 <span data-ttu-id="e8022-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e8022-107">_ulFlags_</span></span>
  
> <span data-ttu-id="e8022-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="e8022-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="e8022-109">_cValues_</span><span class="sxs-lookup"><span data-stu-id="e8022-109">_cValues_</span></span>
  
> <span data-ttu-id="e8022-110">[in]_LpSPropValue_参数指向[SPropValue](spropvalue.md)结构中的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="e8022-110">[in] The count of property values in the [SPropValue](spropvalue.md) structure pointed to by the  _lpSPropValue_ parameter.</span></span> 
    
 <span data-ttu-id="e8022-111">_lpSPropValue_</span><span class="sxs-lookup"><span data-stu-id="e8022-111">_lpSPropValue_</span></span>
  
> <span data-ttu-id="e8022-112">[in]指向介绍的目标行中的列的值的**SPropValue**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="e8022-112">[in] A pointer to an **SPropValue** structure that describes the values of the columns in the target row.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e8022-113">返回值</span><span class="sxs-lookup"><span data-stu-id="e8022-113">Return value</span></span>

<span data-ttu-id="e8022-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8022-114">S_OK</span></span> 
  
> <span data-ttu-id="e8022-115">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="e8022-115">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e8022-116">说明</span><span class="sxs-lookup"><span data-stu-id="e8022-116">Remarks</span></span>

<span data-ttu-id="e8022-117">**ITableData::HrNotify**方法发送 TABLE_ROW_MODIFIED 通知匹配_lpSPropValue_参数指向属性并由它们所述的行的行。</span><span class="sxs-lookup"><span data-stu-id="e8022-117">The **ITableData::HrNotify** method sends a TABLE_ROW_MODIFIED notification for the row that matches the row described by the properties pointed to by the  _lpSPropValue_ parameter.</span></span> <span data-ttu-id="e8022-118">**HrNotify**发送无论是否发生了更改行的通知。</span><span class="sxs-lookup"><span data-stu-id="e8022-118">**HrNotify** sends the notification regardless of whether changes have occurred to the row.</span></span> <span data-ttu-id="e8022-119">所有客户端和视图的表的和具有其视图上的通知调用[IMAPITable::Advise](imapitable-advise.md)注册的服务提供商收到此通知。</span><span class="sxs-lookup"><span data-stu-id="e8022-119">All clients and service providers that have views of the table and have called [IMAPITable::Advise](imapitable-advise.md) to register for notifications on their views receive this notification.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e8022-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8022-120">See also</span></span>



[<span data-ttu-id="e8022-121">SPropValue</span><span class="sxs-lookup"><span data-stu-id="e8022-121">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="e8022-122">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="e8022-122">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="e8022-123">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e8022-123">ITableData : IUnknown</span></span>](itabledataiunknown.md)

