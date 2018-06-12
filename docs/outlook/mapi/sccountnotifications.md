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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c27472a309c26882051744a23fbe05e41c36aa3f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778706"
---
# <a name="sccountnotifications"></a><span data-ttu-id="6a088-103">ScCountNotifications</span><span class="sxs-lookup"><span data-stu-id="6a088-103">ScCountNotifications</span></span>

  
  
<span data-ttu-id="6a088-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6a088-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6a088-105">确定大小，以字节为单位的数组的事件通知，并验证与数组关联的内存。</span><span class="sxs-lookup"><span data-stu-id="6a088-105">Determines the size, in bytes, of an array of event notifications, and validates the memory associated with the array.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6a088-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="6a088-106">Header file:</span></span>  <br/> |<span data-ttu-id="6a088-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="6a088-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="6a088-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="6a088-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="6a088-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="6a088-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="6a088-110">调用：</span><span class="sxs-lookup"><span data-stu-id="6a088-110">Called by:</span></span>  <br/> |<span data-ttu-id="6a088-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="6a088-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCountNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="6a088-112">参数</span><span class="sxs-lookup"><span data-stu-id="6a088-112">Parameters</span></span>

 <span data-ttu-id="6a088-113">_cntf_</span><span class="sxs-lookup"><span data-stu-id="6a088-113">_cntf_</span></span>
  
> <span data-ttu-id="6a088-114">[in][通知](notification.md)结构由_rgntf_参数指示在阵列中的计数。</span><span class="sxs-lookup"><span data-stu-id="6a088-114">[in] Count of [NOTIFICATION](notification.md) structures in the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="6a088-115">_rgntf_</span><span class="sxs-lookup"><span data-stu-id="6a088-115">_rgntf_</span></span>
  
> <span data-ttu-id="6a088-116">[in]指向其大小是确定**通知**结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="6a088-116">[in] Pointer to the array of **NOTIFICATION** structures whose size is to be determined.</span></span> 
    
 <span data-ttu-id="6a088-117">_pcb_</span><span class="sxs-lookup"><span data-stu-id="6a088-117">_pcb_</span></span>
  
> <span data-ttu-id="6a088-118">[输出]指向的大小，以字节为单位的数组_rgntf_参数指向的可选指针。</span><span class="sxs-lookup"><span data-stu-id="6a088-118">[out] Optional pointer to the size, in bytes, of the array pointed to by the  _rgntf_ parameter.</span></span> <span data-ttu-id="6a088-119">如果为空，则**ScCountNotifications**验证通知的数组。</span><span class="sxs-lookup"><span data-stu-id="6a088-119">If NULL, **ScCountNotifications** validates the array of notifications.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="6a088-120">返回值</span><span class="sxs-lookup"><span data-stu-id="6a088-120">Return value</span></span>

<span data-ttu-id="6a088-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a088-121">S_OK</span></span>
  
> <span data-ttu-id="6a088-122">已成功确定计数。</span><span class="sxs-lookup"><span data-stu-id="6a088-122">Count was determined successfully.</span></span>
    
<span data-ttu-id="6a088-123">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="6a088-123">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="6a088-124">遇到无效的通知。</span><span class="sxs-lookup"><span data-stu-id="6a088-124">An invalid notification was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6a088-125">备注</span><span class="sxs-lookup"><span data-stu-id="6a088-125">Remarks</span></span>

<span data-ttu-id="6a088-126">如果_pcb_参数中传递 NULL，则**ScCountNotifications**函数仅验证通知的数组，但没有计数完成;如果在_pcb_传递一个非空值，则**ScCountNotifications**确定数组的大小，并将存储原因_pcb_。</span><span class="sxs-lookup"><span data-stu-id="6a088-126">If NULL is passed in the  _pcb_ parameter, the **ScCountNotifications** function only validates the array of notifications but no counting is done; if a non-null value is passed in  _pcb_, **ScCountNotifications** determines the size of the array and stores the cause  _pcb_.</span></span> <span data-ttu-id="6a088-127">_Pcb_参数必须为足够大，使其包含整个数组。</span><span class="sxs-lookup"><span data-stu-id="6a088-127">The  _pcb_ parameter must be large enough to contain the entire array.</span></span> 
  

