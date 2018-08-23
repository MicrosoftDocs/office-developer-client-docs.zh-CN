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
ms.openlocfilehash: 39f28d5a8e9c8c7f3dfc6a8d09cf022cea08800c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563919"
---
# <a name="hristoragefromstream"></a><span data-ttu-id="d1146-103">HrIStorageFromStream</span><span class="sxs-lookup"><span data-stu-id="d1146-103">HrIStorageFromStream</span></span>

  
  
<span data-ttu-id="d1146-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1146-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1146-105">Layers **IStorage**接口到**IStream**对象。</span><span class="sxs-lookup"><span data-stu-id="d1146-105">Layers an **IStorage** interface onto an **IStream** object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d1146-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="d1146-106">Header file:</span></span>  <br/> |<span data-ttu-id="d1146-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="d1146-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="d1146-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="d1146-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d1146-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d1146-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d1146-110">调用：</span><span class="sxs-lookup"><span data-stu-id="d1146-110">Called by:</span></span>  <br/> |<span data-ttu-id="d1146-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="d1146-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrIStorageFromStream(
  LPUNKNOWN lpUnkIn,
  PIID lpInterface,
  ULONG ulFlags,
  LPSTORAGE FAR * lppStorageOut
);
```

## <a name="parameters"></a><span data-ttu-id="d1146-112">参数</span><span class="sxs-lookup"><span data-stu-id="d1146-112">Parameters</span></span>

 <span data-ttu-id="d1146-113">_lpUnkIn_</span><span class="sxs-lookup"><span data-stu-id="d1146-113">_lpUnkIn_</span></span>
  
> <span data-ttu-id="d1146-114">[in]为实现**IStream**的**IUnknown**对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d1146-114">[in] Pointer to the **IUnknown** object implementing **IStream**.</span></span> 
    
 <span data-ttu-id="d1146-115">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="d1146-115">_lpInterface_</span></span>
  
> <span data-ttu-id="d1146-116">[in]Stream 对象的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="d1146-116">[in] Pointer to the interface identifier (IID) for the stream object.</span></span> <span data-ttu-id="d1146-117">可以在_lpInterface_参数中传递的任何以下值： NULL、 IID_IStream 或 IID_ILockBytes。</span><span class="sxs-lookup"><span data-stu-id="d1146-117">Any of the following values can be passed in the  _lpInterface_ parameter: NULL, IID_IStream, or IID_ILockBytes.</span></span> <span data-ttu-id="d1146-118">在_lpInterface_传递 NULL 是传递 IID_IStream 相同。</span><span class="sxs-lookup"><span data-stu-id="d1146-118">Passing NULL in  _lpInterface_ is the same as passing IID_IStream.</span></span> 
    
 <span data-ttu-id="d1146-119">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d1146-119">_ulFlags_</span></span>
  
> <span data-ttu-id="d1146-120">[in]位掩码的标志，控制如何存储对象是相对于流创建。</span><span class="sxs-lookup"><span data-stu-id="d1146-120">[in] Bitmask of flags that controls how the storage object is to be created relative to the stream.</span></span> <span data-ttu-id="d1146-121">默认设置是 STGSTRM_RESET，其中提供存储对象的只读访问并在位置零流的启动它。</span><span class="sxs-lookup"><span data-stu-id="d1146-121">The default setting is STGSTRM_RESET, which gives the storage object read-only access and starts it at position zero of the stream.</span></span> <span data-ttu-id="d1146-122">可以在以下标志设置以任意组合，除所述：</span><span class="sxs-lookup"><span data-stu-id="d1146-122">The following flags can be set in any combination, except as noted:</span></span>
    
<span data-ttu-id="d1146-123">STGSTRM_CREATE</span><span class="sxs-lookup"><span data-stu-id="d1146-123">STGSTRM_CREATE</span></span> 
  
> <span data-ttu-id="d1146-124">创建新的存储对象的 stream 对象。</span><span class="sxs-lookup"><span data-stu-id="d1146-124">Creates a new storage object for the stream object.</span></span> <span data-ttu-id="d1146-125">如果设置了 STGSTRM_RESET 标志，则不能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="d1146-125">This flag cannot be set if the STGSTRM_RESET flag is set.</span></span> 
    
<span data-ttu-id="d1146-126">STGSTRM_CURRENT</span><span class="sxs-lookup"><span data-stu-id="d1146-126">STGSTRM_CURRENT</span></span> 
  
> <span data-ttu-id="d1146-127">启动存储 stream 的当前的位置。</span><span class="sxs-lookup"><span data-stu-id="d1146-127">Starts storage at the current position of the stream.</span></span> <span data-ttu-id="d1146-128">如果设置了 STGSTRM_RESET 标志，则不能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="d1146-128">This flag cannot be set if the STGSTRM_RESET flag is set.</span></span> 
    
<span data-ttu-id="d1146-129">STGSTRM_MODIFY</span><span class="sxs-lookup"><span data-stu-id="d1146-129">STGSTRM_MODIFY</span></span> 
  
> <span data-ttu-id="d1146-130">允许写入返回的存储调用服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="d1146-130">Allows the calling service provider to write to the returned storage.</span></span> <span data-ttu-id="d1146-131">如果设置了 STGSTRM_RESET 标志，则不能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="d1146-131">This flag cannot be set if the STGSTRM_RESET flag is set.</span></span> 
    
<span data-ttu-id="d1146-132">STGSTRM_RESET</span><span class="sxs-lookup"><span data-stu-id="d1146-132">STGSTRM_RESET</span></span> 
  
> <span data-ttu-id="d1146-133">启动存储位置为零。</span><span class="sxs-lookup"><span data-stu-id="d1146-133">Starts storage at position zero.</span></span> <span data-ttu-id="d1146-134">如果设置了任何其他标志，则不能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="d1146-134">This flag cannot be set if any other flag is set.</span></span> 
    
 <span data-ttu-id="d1146-135">_lppStorageOut_</span><span class="sxs-lookup"><span data-stu-id="d1146-135">_lppStorageOut_</span></span>
  
> <span data-ttu-id="d1146-136">[输出]为返回**IStorage**对象指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d1146-136">[out] Pointer to a pointer to the returned **IStorage** object.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d1146-137">返回值</span><span class="sxs-lookup"><span data-stu-id="d1146-137">Return value</span></span>

<span data-ttu-id="d1146-138">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1146-138">S_OK</span></span> 
  
> <span data-ttu-id="d1146-139">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="d1146-139">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d1146-140">注解</span><span class="sxs-lookup"><span data-stu-id="d1146-140">Remarks</span></span>

<span data-ttu-id="d1146-141">消息存储提供程序支持的附件使用**IStorage**接口的**HrIStorageFromStream**函数。</span><span class="sxs-lookup"><span data-stu-id="d1146-141">Message store providers support the **HrIStorageFromStream** function using the **IStorage** interface for attachments.</span></span> <span data-ttu-id="d1146-142">存储提供程序必须实现**IStream**接口。</span><span class="sxs-lookup"><span data-stu-id="d1146-142">Store providers must implement the **IStream** interface.</span></span> <span data-ttu-id="d1146-143">**HrIStorageFromStream** **IStream**对象提供的**IStorage**接口。</span><span class="sxs-lookup"><span data-stu-id="d1146-143">**HrIStorageFromStream** provides the **IStorage** interface for the **IStream** object.</span></span> <span data-ttu-id="d1146-144">就可以传递**ILockBytes**或中_lpUnkIn_ **IStream**接口。</span><span class="sxs-lookup"><span data-stu-id="d1146-144">It is possible to pass either an **ILockBytes** or an **IStream** interface in  _lpUnkIn_.</span></span> 
  

