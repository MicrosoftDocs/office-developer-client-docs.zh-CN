---
title: IMAPIOfflineSetCurrentState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline.SetCurrentState
api_type:
- COM
ms.assetid: c0aa0df2-79f9-2558-7eb6-accae9bef4b2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0b6837b51b09ecd9a60630c613e1806cb10c1d87
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421737"
---
# <a name="imapiofflinesetcurrentstate"></a><span data-ttu-id="48550-103">IMAPIOffline::SetCurrentState</span><span class="sxs-lookup"><span data-stu-id="48550-103">IMAPIOffline::SetCurrentState</span></span>

  
  
<span data-ttu-id="48550-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="48550-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="48550-105">将脱机对象的当前状态设置为联机或脱机。</span><span class="sxs-lookup"><span data-stu-id="48550-105">Sets the current state of an offline object to online or offline.</span></span>
  
```cpp
HRESULT SetCurrentState( 
    ULONG ulFlags, 
    ULONG ulMask, 
    ULONG ulState, 
    void* pReserved 
);
```

## <a name="parameters"></a><span data-ttu-id="48550-106">参数</span><span class="sxs-lookup"><span data-stu-id="48550-106">Parameters</span></span>

 <span data-ttu-id="48550-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="48550-107">_ulFlags_</span></span>
  
> <span data-ttu-id="48550-108">[in]修改此调用的行为。</span><span class="sxs-lookup"><span data-stu-id="48550-108">[in] Modifies the behavior of this call.</span></span> <span data-ttu-id="48550-109">受支持的值包括：</span><span class="sxs-lookup"><span data-stu-id="48550-109">The supported values are:</span></span>
    
<span data-ttu-id="48550-110">MAPIOFFLINE_FLAG_BLOCK</span><span class="sxs-lookup"><span data-stu-id="48550-110">MAPIOFFLINE_FLAG_BLOCK</span></span>
  
> <span data-ttu-id="48550-111">将  _ulFlags_ 设置为此值将阻止 **SetCurrentState** 调用，直到状态更改完成。</span><span class="sxs-lookup"><span data-stu-id="48550-111">Setting  _ulFlags_ to this value will block the **SetCurrentState** call until the state change is complete.</span></span> <span data-ttu-id="48550-112">默认情况下，切换异步进行。</span><span class="sxs-lookup"><span data-stu-id="48550-112">By default the transition takes place asynchronously.</span></span> <span data-ttu-id="48550-113">异步执行转换时，所有 **SetCurrentState** 调用 **E_PENDING直到更改** 完成。</span><span class="sxs-lookup"><span data-stu-id="48550-113">When the transition is occuring asynchronously, all **SetCurrentState** calls will return **E_PENDING** until the change is complete.</span></span> 
    
<span data-ttu-id="48550-114">MAPIOFFLINE_FLAG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="48550-114">MAPIOFFLINE_FLAG_DEFAULT</span></span>
  
> <span data-ttu-id="48550-115">设置当前状态而不阻止。</span><span class="sxs-lookup"><span data-stu-id="48550-115">Sets the current state without blocking.</span></span>
    
 <span data-ttu-id="48550-116">_ulMask_</span><span class="sxs-lookup"><span data-stu-id="48550-116">_ulMask_</span></span>
  
> <span data-ttu-id="48550-117">[in]要更改的状态部分。</span><span class="sxs-lookup"><span data-stu-id="48550-117">[in] The part of the state to change.</span></span> <span data-ttu-id="48550-118">唯一支持的值是 MAPIOFFLINE_STATE_OFFLINE_MASK。</span><span class="sxs-lookup"><span data-stu-id="48550-118">The only supported value is MAPIOFFLINE_STATE_OFFLINE_MASK.</span></span>
    
 <span data-ttu-id="48550-119">_ulState_</span><span class="sxs-lookup"><span data-stu-id="48550-119">_ulState_</span></span>
  
> <span data-ttu-id="48550-120">[in]要更改为的状态。</span><span class="sxs-lookup"><span data-stu-id="48550-120">[in] The state to change to.</span></span> <span data-ttu-id="48550-121">它必须是以下两个值之一：</span><span class="sxs-lookup"><span data-stu-id="48550-121">It must be one of these two values:</span></span>
    
<span data-ttu-id="48550-122">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="48550-122">MAPIOFFLINE_STATE_ONLINE</span></span>
  
> 
    
<span data-ttu-id="48550-123">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="48550-123">MAPIOFFLINE_STATE_OFFLINE</span></span>
  
> 
    
 <span data-ttu-id="48550-124">_pReserved_</span><span class="sxs-lookup"><span data-stu-id="48550-124">_pReserved_</span></span>
  
> <span data-ttu-id="48550-125">此参数仅供Outlook内部使用，不受支持。</span><span class="sxs-lookup"><span data-stu-id="48550-125">This parameter is reserved for Outlook internal use and is not supported.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="48550-126">返回值</span><span class="sxs-lookup"><span data-stu-id="48550-126">Return value</span></span>

<span data-ttu-id="48550-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="48550-127">S_OK</span></span>
  
> <span data-ttu-id="48550-128">脱机对象的状态已成功更改。</span><span class="sxs-lookup"><span data-stu-id="48550-128">The state of the offline object has been changed successfully.</span></span>
    
<span data-ttu-id="48550-129">E_PENDING</span><span class="sxs-lookup"><span data-stu-id="48550-129">E_PENDING</span></span>
  
> <span data-ttu-id="48550-130">这表示脱机对象的状态正在异步更改。</span><span class="sxs-lookup"><span data-stu-id="48550-130">This indicates that the state of the offline object is changing asynchronously.</span></span> <span data-ttu-id="48550-131">当在早期的 **SetCurrentState** 调用中 _将 ulFlags_ 设置为 MAPIOFFLINE_FLAG_BLOCK，并且任何后续 **SetCurrentState** 调用将返回此值，直到异步状态更改完成时，才会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="48550-131">This occurs when  _ulFlags_ is set to MAPIOFFLINE_FLAG_BLOCK in an earlier **SetCurrentState** call, and any subsequent **SetCurrentState** call will return this value until the asynchronous state change is complete.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="48550-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48550-132">See also</span></span>



[<span data-ttu-id="48550-133">IMAPIOffline::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="48550-133">IMAPIOffline::GetCapabilities</span></span>](imapioffline-getcapabilities.md)
  
[<span data-ttu-id="48550-134">IMAPIOffline::GetCurrentState</span><span class="sxs-lookup"><span data-stu-id="48550-134">IMAPIOffline::GetCurrentState</span></span>](imapioffline-getcurrentstate.md)


[<span data-ttu-id="48550-135">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="48550-135">MAPI Constants</span></span>](mapi-constants.md)

