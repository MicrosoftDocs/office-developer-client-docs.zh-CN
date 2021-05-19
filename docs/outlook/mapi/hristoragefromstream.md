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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416830"
---
# <a name="hristoragefromstream"></a><span data-ttu-id="ebaf8-103">HrIStorageFromStream</span><span class="sxs-lookup"><span data-stu-id="ebaf8-103">HrIStorageFromStream</span></span>

  
  
<span data-ttu-id="ebaf8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ebaf8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ebaf8-105">将 **IStorage 接口** 分层到 **IStream** 对象上。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-105">Layers an **IStorage** interface onto an **IStream** object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ebaf8-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ebaf8-106">Header file:</span></span>  <br/> |<span data-ttu-id="ebaf8-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="ebaf8-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ebaf8-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="ebaf8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ebaf8-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ebaf8-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ebaf8-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="ebaf8-110">Called by:</span></span>  <br/> |<span data-ttu-id="ebaf8-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ebaf8-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrIStorageFromStream(
  LPUNKNOWN lpUnkIn,
  PIID lpInterface,
  ULONG ulFlags,
  LPSTORAGE FAR * lppStorageOut
);
```

## <a name="parameters"></a><span data-ttu-id="ebaf8-112">参数</span><span class="sxs-lookup"><span data-stu-id="ebaf8-112">Parameters</span></span>

 <span data-ttu-id="ebaf8-113">_lpUnkIn_</span><span class="sxs-lookup"><span data-stu-id="ebaf8-113">_lpUnkIn_</span></span>
  
> <span data-ttu-id="ebaf8-114">[in]指向实现 **IStream 的 IUnknown** **对象的指针**。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-114">[in] Pointer to the **IUnknown** object implementing **IStream**.</span></span> 
    
 <span data-ttu-id="ebaf8-115">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="ebaf8-115">_lpInterface_</span></span>
  
> <span data-ttu-id="ebaf8-116">[in]指向流对象的 IID (接口) 指针。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-116">[in] Pointer to the interface identifier (IID) for the stream object.</span></span> <span data-ttu-id="ebaf8-117">可以在  _lpInterface_ 参数中传递以下任何值：NULL、IID_IStream 或 IID_ILockBytes。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-117">Any of the following values can be passed in the  _lpInterface_ parameter: NULL, IID_IStream, or IID_ILockBytes.</span></span> <span data-ttu-id="ebaf8-118">在  _lpInterface_ 中传递 NULL 与传递空IID_IStream。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-118">Passing NULL in  _lpInterface_ is the same as passing IID_IStream.</span></span> 
    
 <span data-ttu-id="ebaf8-119">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ebaf8-119">_ulFlags_</span></span>
  
> <span data-ttu-id="ebaf8-120">[in]控制存储对象相对于流的创建方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-120">[in] Bitmask of flags that controls how the storage object is to be created relative to the stream.</span></span> <span data-ttu-id="ebaf8-121">默认设置为 STGSTRM_RESET，这将为存储对象提供只读访问权限，并启动该对象，位置为流零。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-121">The default setting is STGSTRM_RESET, which gives the storage object read-only access and starts it at position zero of the stream.</span></span> <span data-ttu-id="ebaf8-122">以下标志可以任意组合进行设置，除非已指出：</span><span class="sxs-lookup"><span data-stu-id="ebaf8-122">The following flags can be set in any combination, except as noted:</span></span>
    
<span data-ttu-id="ebaf8-123">STGSTRM_CREATE</span><span class="sxs-lookup"><span data-stu-id="ebaf8-123">STGSTRM_CREATE</span></span> 
  
> <span data-ttu-id="ebaf8-124">为流对象创建新的存储对象。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-124">Creates a new storage object for the stream object.</span></span> <span data-ttu-id="ebaf8-125">如果设置了此标志，则STGSTRM_RESET设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-125">This flag cannot be set if the STGSTRM_RESET flag is set.</span></span> 
    
<span data-ttu-id="ebaf8-126">STGSTRM_CURRENT</span><span class="sxs-lookup"><span data-stu-id="ebaf8-126">STGSTRM_CURRENT</span></span> 
  
> <span data-ttu-id="ebaf8-127">在流的当前位置开始存储。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-127">Starts storage at the current position of the stream.</span></span> <span data-ttu-id="ebaf8-128">如果设置了此标志，则STGSTRM_RESET设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-128">This flag cannot be set if the STGSTRM_RESET flag is set.</span></span> 
    
<span data-ttu-id="ebaf8-129">STGSTRM_MODIFY</span><span class="sxs-lookup"><span data-stu-id="ebaf8-129">STGSTRM_MODIFY</span></span> 
  
> <span data-ttu-id="ebaf8-130">允许调用服务提供商写入返回的存储。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-130">Allows the calling service provider to write to the returned storage.</span></span> <span data-ttu-id="ebaf8-131">如果设置了此标志，则STGSTRM_RESET设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-131">This flag cannot be set if the STGSTRM_RESET flag is set.</span></span> 
    
<span data-ttu-id="ebaf8-132">STGSTRM_RESET</span><span class="sxs-lookup"><span data-stu-id="ebaf8-132">STGSTRM_RESET</span></span> 
  
> <span data-ttu-id="ebaf8-133">从零位置开始存储。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-133">Starts storage at position zero.</span></span> <span data-ttu-id="ebaf8-134">如果设置了任何其他标志，则不能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-134">This flag cannot be set if any other flag is set.</span></span> 
    
 <span data-ttu-id="ebaf8-135">_lppStorageOut_</span><span class="sxs-lookup"><span data-stu-id="ebaf8-135">_lppStorageOut_</span></span>
  
> <span data-ttu-id="ebaf8-136">[out]指向返回的 **IStorage 对象的指针** 的指针。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-136">[out] Pointer to a pointer to the returned **IStorage** object.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ebaf8-137">返回值</span><span class="sxs-lookup"><span data-stu-id="ebaf8-137">Return value</span></span>

<span data-ttu-id="ebaf8-138">S_OK</span><span class="sxs-lookup"><span data-stu-id="ebaf8-138">S_OK</span></span> 
  
> <span data-ttu-id="ebaf8-139">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-139">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ebaf8-140">备注</span><span class="sxs-lookup"><span data-stu-id="ebaf8-140">Remarks</span></span>

<span data-ttu-id="ebaf8-141">邮件存储提供程序使用附件的 **IStorage** 接口支持 **HrIStorageFromStream** 函数。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-141">Message store providers support the **HrIStorageFromStream** function using the **IStorage** interface for attachments.</span></span> <span data-ttu-id="ebaf8-142">存储提供程序必须实现 **IStream** 接口。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-142">Store providers must implement the **IStream** interface.</span></span> <span data-ttu-id="ebaf8-143">**HrIStorageFromStream** 为 **IStream** 对象提供 **IStorage** 接口。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-143">**HrIStorageFromStream** provides the **IStorage** interface for the **IStream** object.</span></span> <span data-ttu-id="ebaf8-144">可以传递 **ILockBytes** 或 _lpUnkIn_ 中的 **IStream** 接口。</span><span class="sxs-lookup"><span data-stu-id="ebaf8-144">It is possible to pass either an **ILockBytes** or an **IStream** interface in  _lpUnkIn_.</span></span> 
  

