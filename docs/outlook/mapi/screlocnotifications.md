---
title: ScRelocNotifications
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScRelocNotifications
api_type:
- COM
ms.assetid: 22de5d38-7be6-48b3-90a7-bc553dcdb042
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 81da4b77f0d2162a1119b7945b1e0ceb87ba9fb8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415199"
---
# <a name="screlocnotifications"></a><span data-ttu-id="069b0-103">ScRelocNotifications</span><span class="sxs-lookup"><span data-stu-id="069b0-103">ScRelocNotifications</span></span>

  
  
<span data-ttu-id="069b0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="069b0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="069b0-105">在指定的事件通知数组中调整指针。</span><span class="sxs-lookup"><span data-stu-id="069b0-105">Adjusts a pointer within a specified event notification array.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="069b0-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="069b0-106">Header file:</span></span>  <br/> |<span data-ttu-id="069b0-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="069b0-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="069b0-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="069b0-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="069b0-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="069b0-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="069b0-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="069b0-110">Called by:</span></span>  <br/> |<span data-ttu-id="069b0-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="069b0-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScRelocNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  LPVOID pvBaseOld,
  LPVOID pvBaseNew,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="069b0-112">参数</span><span class="sxs-lookup"><span data-stu-id="069b0-112">Parameters</span></span>

 <span data-ttu-id="069b0-113">_cntf_</span><span class="sxs-lookup"><span data-stu-id="069b0-113">_cntf_</span></span>
  
> <span data-ttu-id="069b0-114">实时由_rgntf_参数指示的数组中的[通知](notification.md)结构的计数。</span><span class="sxs-lookup"><span data-stu-id="069b0-114">[in] Count of [NOTIFICATION](notification.md) structures in the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="069b0-115">_rgntf_</span><span class="sxs-lookup"><span data-stu-id="069b0-115">_rgntf_</span></span>
  
> <span data-ttu-id="069b0-116">实时指向用于定义要在其中调整指针的事件通知的**通知**结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="069b0-116">[in] Pointer to the array of **NOTIFICATION** structures defining event notifications within which a pointer is to be adjusted.</span></span> 
    
 <span data-ttu-id="069b0-117">_pvBaseOld_</span><span class="sxs-lookup"><span data-stu-id="069b0-117">_pvBaseOld_</span></span>
  
> <span data-ttu-id="069b0-118">实时指向由_rgntf_参数指示的数组的原始基址的指针。</span><span class="sxs-lookup"><span data-stu-id="069b0-118">[in] Pointer to the original base address of the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="069b0-119">_pvBaseNew_</span><span class="sxs-lookup"><span data-stu-id="069b0-119">_pvBaseNew_</span></span>
  
> <span data-ttu-id="069b0-120">实时**ScRelocNotifications**写入由_rgntf_参数指示的数组的新基址的位置。</span><span class="sxs-lookup"><span data-stu-id="069b0-120">[in] The location to which **ScRelocNotifications** writes the new base address of the array indicated by the  _rgntf_ parameter.</span></span> 
    
 <span data-ttu-id="069b0-121">_pcb_</span><span class="sxs-lookup"><span data-stu-id="069b0-121">_pcb_</span></span>
  
> <span data-ttu-id="069b0-122">排除指向由_pvBaseNew_参数指示的数组的大小 (以字节为单位) 的指针。</span><span class="sxs-lookup"><span data-stu-id="069b0-122">[out] Pointer to the size, in bytes, of the array indicated by the  _pvBaseNew_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="069b0-123">返回值</span><span class="sxs-lookup"><span data-stu-id="069b0-123">Return value</span></span>

<span data-ttu-id="069b0-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="069b0-124">S_OK</span></span>
  
> <span data-ttu-id="069b0-125">已成功调整指针。</span><span class="sxs-lookup"><span data-stu-id="069b0-125">A pointer was adjusted successfully.</span></span>
    
<span data-ttu-id="069b0-126">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="069b0-126">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="069b0-127">遇到无效的通知。</span><span class="sxs-lookup"><span data-stu-id="069b0-127">An invalid notification was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="069b0-128">说明</span><span class="sxs-lookup"><span data-stu-id="069b0-128">Remarks</span></span>

<span data-ttu-id="069b0-129">**ScRelocNotifications**函数的_pcb_参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="069b0-129">The  _pcb_ parameter to the **ScRelocNotifications** function is optional.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="069b0-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="069b0-130">See also</span></span>



[<span data-ttu-id="069b0-131">ScRelocProps</span><span class="sxs-lookup"><span data-stu-id="069b0-131">ScRelocProps</span></span>](screlocprops.md)

