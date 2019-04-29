---
title: ScCountNotifications
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCountNotifications
api_type:
- COM
ms.assetid: 13e80bdc-cb59-47a5-8de0-404e22f87f82
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f5298620239d1e42e4ba613c22a98f0cf6f7d457
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437992"
---
# <a name="sccountnotifications"></a><span data-ttu-id="d9646-103">ScCountNotifications</span><span class="sxs-lookup"><span data-stu-id="d9646-103">ScCountNotifications</span></span>

  
  
<span data-ttu-id="d9646-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9646-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9646-105">确定事件通知数组的大小 (以字节为单位), 并验证与该数组关联的内存。</span><span class="sxs-lookup"><span data-stu-id="d9646-105">Determines the size, in bytes, of an array of event notifications, and validates the memory associated with the array.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d9646-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d9646-106">Header file:</span></span>  <br/> |<span data-ttu-id="d9646-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="d9646-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="d9646-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="d9646-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d9646-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d9646-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d9646-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="d9646-110">Called by:</span></span>  <br/> |<span data-ttu-id="d9646-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="d9646-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCountNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="d9646-112">参数</span><span class="sxs-lookup"><span data-stu-id="d9646-112">Parameters</span></span>

 <span data-ttu-id="d9646-113">_cntf_</span><span class="sxs-lookup"><span data-stu-id="d9646-113">_cntf_</span></span>
  
> <span data-ttu-id="d9646-114">实时由_rgntf_参数指示的数组中的[通知](notification.md)结构的计数。</span><span class="sxs-lookup"><span data-stu-id="d9646-114">[in] Count of [NOTIFICATION](notification.md) structures in the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="d9646-115">_rgntf_</span><span class="sxs-lookup"><span data-stu-id="d9646-115">_rgntf_</span></span>
  
> <span data-ttu-id="d9646-116">实时指向要确定其大小的**通知**结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="d9646-116">[in] Pointer to the array of **NOTIFICATION** structures whose size is to be determined.</span></span> 
    
 <span data-ttu-id="d9646-117">_pcb_</span><span class="sxs-lookup"><span data-stu-id="d9646-117">_pcb_</span></span>
  
> <span data-ttu-id="d9646-118">排除可选指针, 指向由_rgntf_参数指向的数组的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="d9646-118">[out] Optional pointer to the size, in bytes, of the array pointed to by the  _rgntf_ parameter.</span></span> <span data-ttu-id="d9646-119">如果为 NULL, 则**ScCountNotifications**验证通知数组。</span><span class="sxs-lookup"><span data-stu-id="d9646-119">If NULL, **ScCountNotifications** validates the array of notifications.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d9646-120">返回值</span><span class="sxs-lookup"><span data-stu-id="d9646-120">Return value</span></span>

<span data-ttu-id="d9646-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9646-121">S_OK</span></span>
  
> <span data-ttu-id="d9646-122">已成功确定 Count。</span><span class="sxs-lookup"><span data-stu-id="d9646-122">Count was determined successfully.</span></span>
    
<span data-ttu-id="d9646-123">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="d9646-123">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="d9646-124">遇到无效的通知。</span><span class="sxs-lookup"><span data-stu-id="d9646-124">An invalid notification was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d9646-125">说明</span><span class="sxs-lookup"><span data-stu-id="d9646-125">Remarks</span></span>

<span data-ttu-id="d9646-126">如果在_pcb_参数中传递 NULL, 则**ScCountNotifications**函数仅验证通知数组, 但不会进行计数。如果在_pcb_中传递非 null 值, **ScCountNotifications**将确定数组的大小并存储原因_pcb_。</span><span class="sxs-lookup"><span data-stu-id="d9646-126">If NULL is passed in the  _pcb_ parameter, the **ScCountNotifications** function only validates the array of notifications but no counting is done; if a non-null value is passed in  _pcb_, **ScCountNotifications** determines the size of the array and stores the cause  _pcb_.</span></span> <span data-ttu-id="d9646-127">_pcb_参数的大小必须足以包含整个数组。</span><span class="sxs-lookup"><span data-stu-id="d9646-127">The  _pcb_ parameter must be large enough to contain the entire array.</span></span> 
  

