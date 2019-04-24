---
title: HrIStorageFromStream
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrIStorageFromStream
api_type:
- HeaderDef
ms.assetid: 1cdc95b8-a156-4600-9e20-caaa02680e87
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1362b1131d937ef240aa1962db8c1b5116786c67
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347780"
---
# <a name="hristoragefromstream"></a><span data-ttu-id="ecbd0-103">HrIStorageFromStream</span><span class="sxs-lookup"><span data-stu-id="ecbd0-103">HrIStorageFromStream</span></span>

  
  
<span data-ttu-id="ecbd0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ecbd0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ecbd0-105">将**IStorage**接口分层到**IStream**对象。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-105">Layers an **IStorage** interface onto an **IStream** object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ecbd0-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ecbd0-106">Header file:</span></span>  <br/> |<span data-ttu-id="ecbd0-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="ecbd0-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ecbd0-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="ecbd0-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ecbd0-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ecbd0-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ecbd0-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="ecbd0-110">Called by:</span></span>  <br/> |<span data-ttu-id="ecbd0-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="ecbd0-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrIStorageFromStream(
  LPUNKNOWN lpUnkIn,
  PIID lpInterface,
  ULONG ulFlags,
  LPSTORAGE FAR * lppStorageOut
);
```

## <a name="parameters"></a><span data-ttu-id="ecbd0-112">参数</span><span class="sxs-lookup"><span data-stu-id="ecbd0-112">Parameters</span></span>

 <span data-ttu-id="ecbd0-113">_lpUnkIn_</span><span class="sxs-lookup"><span data-stu-id="ecbd0-113">_lpUnkIn_</span></span>
  
> <span data-ttu-id="ecbd0-114">实时指向实现**IStream**的**IUnknown**对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-114">[in] Pointer to the **IUnknown** object implementing **IStream**.</span></span> 
    
 <span data-ttu-id="ecbd0-115">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="ecbd0-115">_lpInterface_</span></span>
  
> <span data-ttu-id="ecbd0-116">实时指向 stream 对象的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-116">[in] Pointer to the interface identifier (IID) for the stream object.</span></span> <span data-ttu-id="ecbd0-117">以下任何值都可以在_lpInterface_参数中传递: NULL、IID_IStream 或 IID_ILockBytes。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-117">Any of the following values can be passed in the  _lpInterface_ parameter: NULL, IID_IStream, or IID_ILockBytes.</span></span> <span data-ttu-id="ecbd0-118">在_lpInterface_中传递 NULL 与传递 IID_IStream 相同。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-118">Passing NULL in  _lpInterface_ is the same as passing IID_IStream.</span></span> 
    
 <span data-ttu-id="ecbd0-119">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ecbd0-119">_ulFlags_</span></span>
  
> <span data-ttu-id="ecbd0-120">实时标志的位掩码, 用于控制存储对象相对于流的创建方式。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-120">[in] Bitmask of flags that controls how the storage object is to be created relative to the stream.</span></span> <span data-ttu-id="ecbd0-121">默认设置为 STGSTRM_RESET, 它将为存储对象提供只读访问权限, 并在流的位置0处启动该对象。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-121">The default setting is STGSTRM_RESET, which gives the storage object read-only access and starts it at position zero of the stream.</span></span> <span data-ttu-id="ecbd0-122">可以任意组合设置以下标志, 除了所述:</span><span class="sxs-lookup"><span data-stu-id="ecbd0-122">The following flags can be set in any combination, except as noted:</span></span>
    
<span data-ttu-id="ecbd0-123">STGSTRM_CREATE</span><span class="sxs-lookup"><span data-stu-id="ecbd0-123">STGSTRM_CREATE</span></span> 
  
> <span data-ttu-id="ecbd0-124">为 stream 对象创建一个新的存储对象。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-124">Creates a new storage object for the stream object.</span></span> <span data-ttu-id="ecbd0-125">如果设置了 STGSTRM_RESET 标志, 则不能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-125">This flag cannot be set if the STGSTRM_RESET flag is set.</span></span> 
    
<span data-ttu-id="ecbd0-126">STGSTRM_CURRENT</span><span class="sxs-lookup"><span data-stu-id="ecbd0-126">STGSTRM_CURRENT</span></span> 
  
> <span data-ttu-id="ecbd0-127">在流的当前位置启动存储。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-127">Starts storage at the current position of the stream.</span></span> <span data-ttu-id="ecbd0-128">如果设置了 STGSTRM_RESET 标志, 则不能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-128">This flag cannot be set if the STGSTRM_RESET flag is set.</span></span> 
    
<span data-ttu-id="ecbd0-129">STGSTRM_MODIFY</span><span class="sxs-lookup"><span data-stu-id="ecbd0-129">STGSTRM_MODIFY</span></span> 
  
> <span data-ttu-id="ecbd0-130">允许呼叫服务提供程序对返回的存储进行写入。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-130">Allows the calling service provider to write to the returned storage.</span></span> <span data-ttu-id="ecbd0-131">如果设置了 STGSTRM_RESET 标志, 则不能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-131">This flag cannot be set if the STGSTRM_RESET flag is set.</span></span> 
    
<span data-ttu-id="ecbd0-132">STGSTRM_RESET</span><span class="sxs-lookup"><span data-stu-id="ecbd0-132">STGSTRM_RESET</span></span> 
  
> <span data-ttu-id="ecbd0-133">在位置零处启动存储。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-133">Starts storage at position zero.</span></span> <span data-ttu-id="ecbd0-134">如果设置了任何其他标志, 则不能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-134">This flag cannot be set if any other flag is set.</span></span> 
    
 <span data-ttu-id="ecbd0-135">_lppStorageOut_</span><span class="sxs-lookup"><span data-stu-id="ecbd0-135">_lppStorageOut_</span></span>
  
> <span data-ttu-id="ecbd0-136">排除指向返回的**IStorage**对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-136">[out] Pointer to a pointer to the returned **IStorage** object.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ecbd0-137">返回值</span><span class="sxs-lookup"><span data-stu-id="ecbd0-137">Return value</span></span>

<span data-ttu-id="ecbd0-138">S_OK</span><span class="sxs-lookup"><span data-stu-id="ecbd0-138">S_OK</span></span> 
  
> <span data-ttu-id="ecbd0-139">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-139">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ecbd0-140">注解</span><span class="sxs-lookup"><span data-stu-id="ecbd0-140">Remarks</span></span>

<span data-ttu-id="ecbd0-141">邮件存储提供程序支持附件使用**IStorage**接口的**HrIStorageFromStream**函数。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-141">Message store providers support the **HrIStorageFromStream** function using the **IStorage** interface for attachments.</span></span> <span data-ttu-id="ecbd0-142">存储提供程序必须实现**IStream**接口。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-142">Store providers must implement the **IStream** interface.</span></span> <span data-ttu-id="ecbd0-143">**HrIStorageFromStream**为**IStream**对象提供**IStorage**接口。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-143">**HrIStorageFromStream** provides the **IStorage** interface for the **IStream** object.</span></span> <span data-ttu-id="ecbd0-144">可以在_lpUnkIn_中传递**ILockBytes**或**IStream**接口。</span><span class="sxs-lookup"><span data-stu-id="ecbd0-144">It is possible to pass either an **ILockBytes** or an **IStream** interface in  _lpUnkIn_.</span></span> 
  

