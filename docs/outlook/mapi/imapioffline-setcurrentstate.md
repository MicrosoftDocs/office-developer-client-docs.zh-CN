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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 15e2d5c2aca595c3a06d215cd069c23da3e48125
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775489"
---
# <a name="imapiofflinesetcurrentstate"></a><span data-ttu-id="1e61f-103">IMAPIOffline::SetCurrentState</span><span class="sxs-lookup"><span data-stu-id="1e61f-103">IMAPIOffline::SetCurrentState</span></span>

  
  
<span data-ttu-id="1e61f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1e61f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1e61f-105">设置为联机或脱机脱机对象的当前状态。</span><span class="sxs-lookup"><span data-stu-id="1e61f-105">Sets the current state of an offline object to online or offline.</span></span>
  
```cpp
HRESULT SetCurrentState( 
    ULONG ulFlags, 
    ULONG ulMask, 
    ULONG ulState, 
    void* pReserved 
);
```

## <a name="parameters"></a><span data-ttu-id="1e61f-106">参数</span><span class="sxs-lookup"><span data-stu-id="1e61f-106">Parameters</span></span>

 <span data-ttu-id="1e61f-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1e61f-107">_ulFlags_</span></span>
  
> <span data-ttu-id="1e61f-108">[in]修改此呼叫的行为。</span><span class="sxs-lookup"><span data-stu-id="1e61f-108">[in] Modifies the behavior of this call.</span></span> <span data-ttu-id="1e61f-109">支持的值包括：</span><span class="sxs-lookup"><span data-stu-id="1e61f-109">The supported values are:</span></span>
    
<span data-ttu-id="1e61f-110">MAPIOFFLINE_FLAG_BLOCK</span><span class="sxs-lookup"><span data-stu-id="1e61f-110">MAPIOFFLINE_FLAG_BLOCK</span></span>
  
> <span data-ttu-id="1e61f-111">此值设置为_ulFlags_将阻止**SetCurrentState**呼叫，直至完成状态更改。</span><span class="sxs-lookup"><span data-stu-id="1e61f-111">Setting  _ulFlags_ to this value will block the **SetCurrentState** call until the state change is complete.</span></span> <span data-ttu-id="1e61f-112">默认情况下切换异步会发生。</span><span class="sxs-lookup"><span data-stu-id="1e61f-112">By default the transition takes place asynchronously.</span></span> <span data-ttu-id="1e61f-113">转换异步后发生，所有**SetCurrentState**呼叫将都返回**E_PENDING** ，直至完成更改。</span><span class="sxs-lookup"><span data-stu-id="1e61f-113">When the transition is occuring asynchronously, all **SetCurrentState** calls will return **E_PENDING** until the change is complete.</span></span> 
    
<span data-ttu-id="1e61f-114">MAPIOFFLINE_FLAG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1e61f-114">MAPIOFFLINE_FLAG_DEFAULT</span></span>
  
> <span data-ttu-id="1e61f-115">不阻止设置的当前状态。</span><span class="sxs-lookup"><span data-stu-id="1e61f-115">Sets the current state without blocking.</span></span>
    
 <span data-ttu-id="1e61f-116">_ulMask_</span><span class="sxs-lookup"><span data-stu-id="1e61f-116">_ulMask_</span></span>
  
> <span data-ttu-id="1e61f-117">[in]状态更改的一部分。</span><span class="sxs-lookup"><span data-stu-id="1e61f-117">[in] The part of the state to change.</span></span> <span data-ttu-id="1e61f-118">仅受支持的值是 MAPIOFFLINE_STATE_OFFLINE_MASK。</span><span class="sxs-lookup"><span data-stu-id="1e61f-118">The only supported value is MAPIOFFLINE_STATE_OFFLINE_MASK.</span></span>
    
 <span data-ttu-id="1e61f-119">_ulState_</span><span class="sxs-lookup"><span data-stu-id="1e61f-119">_ulState_</span></span>
  
> <span data-ttu-id="1e61f-120">[in]要更改的状态。</span><span class="sxs-lookup"><span data-stu-id="1e61f-120">[in] The state to change to.</span></span> <span data-ttu-id="1e61f-121">它必须是这两个值之一：</span><span class="sxs-lookup"><span data-stu-id="1e61f-121">It must be one of these two values:</span></span>
    
<span data-ttu-id="1e61f-122">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="1e61f-122">MAPIOFFLINE_STATE_ONLINE</span></span>
  
> 
    
<span data-ttu-id="1e61f-123">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="1e61f-123">MAPIOFFLINE_STATE_OFFLINE</span></span>
  
> 
    
 <span data-ttu-id="1e61f-124">_保留_</span><span class="sxs-lookup"><span data-stu-id="1e61f-124">_pReserved_</span></span>
  
> <span data-ttu-id="1e61f-125">此参数仅供 Outlook 内部使用，不支持。</span><span class="sxs-lookup"><span data-stu-id="1e61f-125">This parameter is reserved for Outlook internal use and is not supported.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1e61f-126">返回值</span><span class="sxs-lookup"><span data-stu-id="1e61f-126">Return value</span></span>

<span data-ttu-id="1e61f-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e61f-127">S_OK</span></span>
  
> <span data-ttu-id="1e61f-128">已成功更改脱机对象的状态。</span><span class="sxs-lookup"><span data-stu-id="1e61f-128">The state of the offline object has been changed successfully.</span></span>
    
<span data-ttu-id="1e61f-129">E_PENDING</span><span class="sxs-lookup"><span data-stu-id="1e61f-129">E_PENDING</span></span>
  
> <span data-ttu-id="1e61f-130">这指示正在异步更改脱机对象的状态。</span><span class="sxs-lookup"><span data-stu-id="1e61f-130">This indicates that the state of the offline object is changing asynchronously.</span></span> <span data-ttu-id="1e61f-131">在以前**SetCurrentState**调用， _ulFlags_设置为 MAPIOFFLINE_FLAG_BLOCK 和任何后续**SetCurrentState**调用异步状态更改完成之前将返回此值时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="1e61f-131">This occurs when  _ulFlags_ is set to MAPIOFFLINE_FLAG_BLOCK in an earlier **SetCurrentState** call, and any subsequent **SetCurrentState** call will return this value until the asynchronous state change is complete.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="1e61f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e61f-132">See also</span></span>



[<span data-ttu-id="1e61f-133">IMAPIOffline::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="1e61f-133">IMAPIOffline::GetCapabilities</span></span>](imapioffline-getcapabilities.md)
  
[<span data-ttu-id="1e61f-134">IMAPIOffline::GetCurrentState</span><span class="sxs-lookup"><span data-stu-id="1e61f-134">IMAPIOffline::GetCurrentState</span></span>](imapioffline-getcurrentstate.md)


[<span data-ttu-id="1e61f-135">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="1e61f-135">MAPI Constants</span></span>](mapi-constants.md)

