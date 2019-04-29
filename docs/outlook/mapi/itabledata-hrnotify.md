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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: aa2170bf4bedfb441ad4808f774f6f71d5caf85e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413267"
---
# <a name="itabledatahrnotify"></a><span data-ttu-id="88fb7-103">ITableData::HrNotify</span><span class="sxs-lookup"><span data-stu-id="88fb7-103">ITableData::HrNotify</span></span>

  
  
<span data-ttu-id="88fb7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88fb7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="88fb7-105">为表行发送通知。</span><span class="sxs-lookup"><span data-stu-id="88fb7-105">Sends a notification for a table row.</span></span>
  
```cpp
HRESULT HrNotify(
  ULONG ulFlags,
  ULONG cValues,
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a><span data-ttu-id="88fb7-106">参数</span><span class="sxs-lookup"><span data-stu-id="88fb7-106">Parameters</span></span>

 <span data-ttu-id="88fb7-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="88fb7-107">_ulFlags_</span></span>
  
> <span data-ttu-id="88fb7-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="88fb7-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="88fb7-109">_cValues_</span><span class="sxs-lookup"><span data-stu-id="88fb7-109">_cValues_</span></span>
  
> <span data-ttu-id="88fb7-110">实时由_lpSPropValue_参数指向的[SPropValue](spropvalue.md)结构中的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="88fb7-110">[in] The count of property values in the [SPropValue](spropvalue.md) structure pointed to by the  _lpSPropValue_ parameter.</span></span> 
    
 <span data-ttu-id="88fb7-111">_lpSPropValue_</span><span class="sxs-lookup"><span data-stu-id="88fb7-111">_lpSPropValue_</span></span>
  
> <span data-ttu-id="88fb7-112">实时指向描述目标行中各列的值的**SPropValue**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="88fb7-112">[in] A pointer to an **SPropValue** structure that describes the values of the columns in the target row.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="88fb7-113">返回值</span><span class="sxs-lookup"><span data-stu-id="88fb7-113">Return value</span></span>

<span data-ttu-id="88fb7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="88fb7-114">S_OK</span></span> 
  
> <span data-ttu-id="88fb7-115">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="88fb7-115">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="88fb7-116">说明</span><span class="sxs-lookup"><span data-stu-id="88fb7-116">Remarks</span></span>

<span data-ttu-id="88fb7-117">**ITableData:: HrNotify**方法发送与_lpSPropValue_参数所指向的属性所描述的行相匹配的行的 TABLE_ROW_MODIFIED 通知。</span><span class="sxs-lookup"><span data-stu-id="88fb7-117">The **ITableData::HrNotify** method sends a TABLE_ROW_MODIFIED notification for the row that matches the row described by the properties pointed to by the  _lpSPropValue_ parameter.</span></span> <span data-ttu-id="88fb7-118">**HrNotify**发送通知, 无论行是否发生了更改。</span><span class="sxs-lookup"><span data-stu-id="88fb7-118">**HrNotify** sends the notification regardless of whether changes have occurred to the row.</span></span> <span data-ttu-id="88fb7-119">所有具有表视图且已调用[IMAPITable:: 建议](imapitable-advise.md)在其视图中注册通知的客户端和服务提供程序都会收到此通知。</span><span class="sxs-lookup"><span data-stu-id="88fb7-119">All clients and service providers that have views of the table and have called [IMAPITable::Advise](imapitable-advise.md) to register for notifications on their views receive this notification.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="88fb7-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88fb7-120">See also</span></span>



[<span data-ttu-id="88fb7-121">SPropValue</span><span class="sxs-lookup"><span data-stu-id="88fb7-121">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="88fb7-122">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="88fb7-122">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="88fb7-123">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="88fb7-123">ITableData : IUnknown</span></span>](itabledataiunknown.md)

