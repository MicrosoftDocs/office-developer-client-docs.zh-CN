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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321208"
---
# <a name="imapiofflinesetcurrentstate"></a><span data-ttu-id="1965d-103">IMAPIOffline::SetCurrentState</span><span class="sxs-lookup"><span data-stu-id="1965d-103">IMAPIOffline::SetCurrentState</span></span>

  
  
<span data-ttu-id="1965d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1965d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1965d-105">将脱机对象的当前状态设置为 "联机" 或 "脱机"。</span><span class="sxs-lookup"><span data-stu-id="1965d-105">Sets the current state of an offline object to online or offline.</span></span>
  
```cpp
HRESULT SetCurrentState( 
    ULONG ulFlags, 
    ULONG ulMask, 
    ULONG ulState, 
    void* pReserved 
);
```

## <a name="parameters"></a><span data-ttu-id="1965d-106">参数</span><span class="sxs-lookup"><span data-stu-id="1965d-106">Parameters</span></span>

 <span data-ttu-id="1965d-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1965d-107">_ulFlags_</span></span>
  
> <span data-ttu-id="1965d-108">实时修改此调用的行为。</span><span class="sxs-lookup"><span data-stu-id="1965d-108">[in] Modifies the behavior of this call.</span></span> <span data-ttu-id="1965d-109">受支持的值包括：</span><span class="sxs-lookup"><span data-stu-id="1965d-109">The supported values are:</span></span>
    
<span data-ttu-id="1965d-110">MAPIOFFLINE_FLAG_BLOCK</span><span class="sxs-lookup"><span data-stu-id="1965d-110">MAPIOFFLINE_FLAG_BLOCK</span></span>
  
> <span data-ttu-id="1965d-111">将_ulFlags_设置为此值将阻止**SetCurrentState**调用, 直至状态更改完成。</span><span class="sxs-lookup"><span data-stu-id="1965d-111">Setting  _ulFlags_ to this value will block the **SetCurrentState** call until the state change is complete.</span></span> <span data-ttu-id="1965d-112">默认情况下, 转换会异步进行。</span><span class="sxs-lookup"><span data-stu-id="1965d-112">By default the transition takes place asynchronously.</span></span> <span data-ttu-id="1965d-113">当以异步方式进行转换时, 所有**SetCurrentState**调用将返回**E_PENDING** , 直到更改完成。</span><span class="sxs-lookup"><span data-stu-id="1965d-113">When the transition is occuring asynchronously, all **SetCurrentState** calls will return **E_PENDING** until the change is complete.</span></span> 
    
<span data-ttu-id="1965d-114">MAPIOFFLINE_FLAG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1965d-114">MAPIOFFLINE_FLAG_DEFAULT</span></span>
  
> <span data-ttu-id="1965d-115">在不阻止的情况下设置当前状态。</span><span class="sxs-lookup"><span data-stu-id="1965d-115">Sets the current state without blocking.</span></span>
    
 <span data-ttu-id="1965d-116">_ulMask_</span><span class="sxs-lookup"><span data-stu-id="1965d-116">_ulMask_</span></span>
  
> <span data-ttu-id="1965d-117">实时要更改的状态部分。</span><span class="sxs-lookup"><span data-stu-id="1965d-117">[in] The part of the state to change.</span></span> <span data-ttu-id="1965d-118">唯一受支持的值为 MAPIOFFLINE_STATE_OFFLINE_MASK。</span><span class="sxs-lookup"><span data-stu-id="1965d-118">The only supported value is MAPIOFFLINE_STATE_OFFLINE_MASK.</span></span>
    
 <span data-ttu-id="1965d-119">_ulState_</span><span class="sxs-lookup"><span data-stu-id="1965d-119">_ulState_</span></span>
  
> <span data-ttu-id="1965d-120">实时要更改为的状态。</span><span class="sxs-lookup"><span data-stu-id="1965d-120">[in] The state to change to.</span></span> <span data-ttu-id="1965d-121">它必须是以下两个值之一:</span><span class="sxs-lookup"><span data-stu-id="1965d-121">It must be one of these two values:</span></span>
    
<span data-ttu-id="1965d-122">MAPIOFFLINE_STATE_ONLINE</span><span class="sxs-lookup"><span data-stu-id="1965d-122">MAPIOFFLINE_STATE_ONLINE</span></span>
  
> 
    
<span data-ttu-id="1965d-123">MAPIOFFLINE_STATE_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="1965d-123">MAPIOFFLINE_STATE_OFFLINE</span></span>
  
> 
    
 <span data-ttu-id="1965d-124">_保护_</span><span class="sxs-lookup"><span data-stu-id="1965d-124">_pReserved_</span></span>
  
> <span data-ttu-id="1965d-125">此参数是为 Outlook 内部使用而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="1965d-125">This parameter is reserved for Outlook internal use and is not supported.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1965d-126">返回值</span><span class="sxs-lookup"><span data-stu-id="1965d-126">Return value</span></span>

<span data-ttu-id="1965d-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="1965d-127">S_OK</span></span>
  
> <span data-ttu-id="1965d-128">已成功更改脱机对象的状态。</span><span class="sxs-lookup"><span data-stu-id="1965d-128">The state of the offline object has been changed successfully.</span></span>
    
<span data-ttu-id="1965d-129">E_PENDING</span><span class="sxs-lookup"><span data-stu-id="1965d-129">E_PENDING</span></span>
  
> <span data-ttu-id="1965d-130">这表示脱机对象的状态是异步更改的。</span><span class="sxs-lookup"><span data-stu-id="1965d-130">This indicates that the state of the offline object is changing asynchronously.</span></span> <span data-ttu-id="1965d-131">在早期**SetCurrentState**调用中将_ulFlags_设置为 MAPIOFFLINE_FLAG_BLOCK, 随后的任何**SetCurrentState**调用都将返回此值, 直到异步状态更改完成。</span><span class="sxs-lookup"><span data-stu-id="1965d-131">This occurs when  _ulFlags_ is set to MAPIOFFLINE_FLAG_BLOCK in an earlier **SetCurrentState** call, and any subsequent **SetCurrentState** call will return this value until the asynchronous state change is complete.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="1965d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1965d-132">See also</span></span>



[<span data-ttu-id="1965d-133">IMAPIOffline::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="1965d-133">IMAPIOffline::GetCapabilities</span></span>](imapioffline-getcapabilities.md)
  
[<span data-ttu-id="1965d-134">IMAPIOffline::GetCurrentState</span><span class="sxs-lookup"><span data-stu-id="1965d-134">IMAPIOffline::GetCurrentState</span></span>](imapioffline-getcurrentstate.md)


[<span data-ttu-id="1965d-135">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="1965d-135">MAPI Constants</span></span>](mapi-constants.md)

