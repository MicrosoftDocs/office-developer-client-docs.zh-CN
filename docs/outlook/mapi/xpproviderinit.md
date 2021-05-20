---
title: XPProviderInit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.XPProviderInit
api_type:
- COM
ms.assetid: df6eacf4-1cf9-4c25-806f-f87c38dad597
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ee0ff8d32436f71020be2cdc91d6677bd4ec8e43
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428534"
---
# <a name="xpproviderinit"></a><span data-ttu-id="01d63-103">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="01d63-103">XPProviderInit</span></span>

  
  
<span data-ttu-id="01d63-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="01d63-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="01d63-105">初始化传输提供程序以用于操作。</span><span class="sxs-lookup"><span data-stu-id="01d63-105">Initializes a transport provider for operation.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="01d63-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="01d63-106">Header file:</span></span>  <br/> |<span data-ttu-id="01d63-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="01d63-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="01d63-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="01d63-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="01d63-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="01d63-109">Transport providers</span></span>  <br/> |
|<span data-ttu-id="01d63-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="01d63-110">Called by:</span></span>  <br/> |<span data-ttu-id="01d63-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="01d63-111">MAPI</span></span>  <br/> |
   
```cpp
HRESULT XPProviderInit(
  HINSTANCE hInstance,
  LPMALLOC lpMalloc,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPALLOCATEMORE lpAllocateMore,
  LPFREEBUFFER lpFreeBuffer,
  ULONG ulFlags,
  ULONG ulMAPIVer,
  ULONG FAR * lpulProviderVer,
  LPXPPROVIDER FAR * lppXPProvider
);
```

## <a name="parameters"></a><span data-ttu-id="01d63-112">参数</span><span class="sxs-lookup"><span data-stu-id="01d63-112">Parameters</span></span>

 <span data-ttu-id="01d63-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="01d63-113">_hInstance_</span></span>
  
> <span data-ttu-id="01d63-114">[in]传输提供程序的动态链接库实例 (DLL) 加载 DLL 时所使用的 DLL。</span><span class="sxs-lookup"><span data-stu-id="01d63-114">[in] The instance of the transport provider's dynamic-link library (DLL) that MAPI used when it loaded the DLL.</span></span>
    
 <span data-ttu-id="01d63-115">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="01d63-115">_lpMalloc_</span></span>
  
> <span data-ttu-id="01d63-116">[in]指向公开 OLE **IMalloc 接口的内存分配器对象的** 指针。</span><span class="sxs-lookup"><span data-stu-id="01d63-116">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="01d63-117">使用某些接口（如 **IStream**）时，传输提供程序可能需要使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="01d63-117">The transport provider may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="01d63-118">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="01d63-118">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="01d63-119">[in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="01d63-119">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="01d63-120">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="01d63-120">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="01d63-121">[in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。</span><span class="sxs-lookup"><span data-stu-id="01d63-121">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="01d63-122">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="01d63-122">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="01d63-123">[in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="01d63-123">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="01d63-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="01d63-124">_ulFlags_</span></span>
  
> <span data-ttu-id="01d63-125">[in]标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="01d63-125">[in] Bitmask of flags.</span></span> <span data-ttu-id="01d63-126">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="01d63-126">The following flag can be set:</span></span>
    
<span data-ttu-id="01d63-127">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="01d63-127">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="01d63-128">提供程序正在服务（一种无法访问任何用户界面的一种特殊Windows服务）的上下文中加载。</span><span class="sxs-lookup"><span data-stu-id="01d63-128">The provider is being loaded in the context of a Windows service, a special type of process without access to any user interface.</span></span> 
    
 <span data-ttu-id="01d63-129">_ulMAPIVer_</span><span class="sxs-lookup"><span data-stu-id="01d63-129">_ulMAPIVer_</span></span>
  
> <span data-ttu-id="01d63-130">[in]服务提供商接口的版本号 (SPI) 使用Mapi.dll版本号。</span><span class="sxs-lookup"><span data-stu-id="01d63-130">[in] Version number of the service provider interface (SPI) that Mapi.dll uses.</span></span> <span data-ttu-id="01d63-131">有关当前版本号，请参阅 Mapispi.h 头文件。</span><span class="sxs-lookup"><span data-stu-id="01d63-131">For the current version number, see the Mapispi.h header file.</span></span> 
    
 <span data-ttu-id="01d63-132">_lpulProviderVer_</span><span class="sxs-lookup"><span data-stu-id="01d63-132">_lpulProviderVer_</span></span>
  
> <span data-ttu-id="01d63-133">[out]指向此传输提供程序使用的 SPI 的版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="01d63-133">[out] Pointer to the version number of the SPI that this transport provider uses.</span></span> 
    
 <span data-ttu-id="01d63-134">_lppXPProvider_</span><span class="sxs-lookup"><span data-stu-id="01d63-134">_lppXPProvider_</span></span>
  
> <span data-ttu-id="01d63-135">[out]指向初始化的传输提供程序对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="01d63-135">[out] Pointer to a pointer to the initialized transport provider object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="01d63-136">返回值</span><span class="sxs-lookup"><span data-stu-id="01d63-136">Return value</span></span>

<span data-ttu-id="01d63-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="01d63-137">S_OK</span></span> 
  
> <span data-ttu-id="01d63-138">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="01d63-138">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="01d63-139">MAPI_E_VERSION</span><span class="sxs-lookup"><span data-stu-id="01d63-139">MAPI_E_VERSION</span></span> 
  
> <span data-ttu-id="01d63-140">MAPI 使用的 SPI 版本与此提供程序使用的 SPI 不兼容。</span><span class="sxs-lookup"><span data-stu-id="01d63-140">The SPI version being used by MAPI is not compatible with the SPI being used by this provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="01d63-141">备注</span><span class="sxs-lookup"><span data-stu-id="01d63-141">Remarks</span></span>

<span data-ttu-id="01d63-142">MAPI 调用入口点函数 **XPProviderInit** 以在客户端登录后初始化传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="01d63-142">MAPI calls the entry point function **XPProviderInit** to initialize a transport provider following a client logon.</span></span> <span data-ttu-id="01d63-143">对于客户端配置文件中指定的每个传输提供程序，将调用一次 **XPProviderInit。**</span><span class="sxs-lookup"><span data-stu-id="01d63-143">**XPProviderInit** is called once for each transport provider specified in the client's profile.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="01d63-144">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="01d63-144">Notes to implementers</span></span>

<span data-ttu-id="01d63-145">传输提供程序必须将 **XPProviderInit** 实现为提供程序的 DLL 中的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="01d63-145">A transport provider must implement **XPProviderInit** as an entry point function in the provider's DLL.</span></span> <span data-ttu-id="01d63-146">实现必须基于 **XPPROVIDERINIT** 函数原型，在 Mapispi.h 中也指定了此原型。</span><span class="sxs-lookup"><span data-stu-id="01d63-146">The implementation must be based on the **XPPROVIDERINIT** function prototype, also specified in Mapispi.h.</span></span> <span data-ttu-id="01d63-147">MAPI 定义 **XPPROVIDERINIT** 以使用标准 MAPI 初始化调用类型 STDMAPIINITCALLTYPE，这将导致 **XPProviderInit** 遵循 CDECL 调用约定。</span><span class="sxs-lookup"><span data-stu-id="01d63-147">MAPI defines **XPPROVIDERINIT** to use the standard MAPI initialization call type, STDMAPIINITCALLTYPE, which causes **XPProviderInit** to follow the CDECL calling convention.</span></span> <span data-ttu-id="01d63-148">CDECL 的一个优点是，即使调用参数的数量与定义的参数数不匹配，也可以尝试呼叫。</span><span class="sxs-lookup"><span data-stu-id="01d63-148">An advantage of CDECL is that calls can be attempted even if the number of calling parameters does not match the number of defined parameters.</span></span> 
  
<span data-ttu-id="01d63-149">由于同时使用多个配置文件或在同一配置文件中出现多次，因此可以多次初始化提供程序。</span><span class="sxs-lookup"><span data-stu-id="01d63-149">A provider can be initialized multiple times as a result of appearing in several profiles in simultaneous use or of appearing more than once in the same profile.</span></span> <span data-ttu-id="01d63-150">由于提供程序对象包含上下文 **，XPProviderInit** 必须在  _lppXPProvider_ 中针对每次初始化返回不同的提供程序对象，即使对于同一进程中的多个初始化，也必须返回该对象。</span><span class="sxs-lookup"><span data-stu-id="01d63-150">Because the provider object contains context, **XPProviderInit** must return a different provider object in  _lppXPProvider_ for each initialization, even for multiple initializations in the same process.</span></span> 
  
<span data-ttu-id="01d63-151">传输提供程序应该使用 _lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 指向的函数进行大多数内存分配和释放。 </span><span class="sxs-lookup"><span data-stu-id="01d63-151">The transport provider should use the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation.</span></span> <span data-ttu-id="01d63-152">特别是，当调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md)等对象接口时，提供程序必须使用这些函数分配内存供客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="01d63-152">In particular, the provider must use these functions to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="01d63-153">如果提供程序还希望使用 OLE 内存分配器，则它应调用 _lpMalloc_ 参数指向的分配器对象的 **IUnknown：：AddRef** 方法。</span><span class="sxs-lookup"><span data-stu-id="01d63-153">If the provider also expects to use the OLE memory allocator, it should call the **IUnknown::AddRef** method of the allocator object pointed to by the  _lpMalloc_ parameter.</span></span> 
  
<span data-ttu-id="01d63-154">有关编写 **XPProviderInit** 的信息，请参阅 [初始化传输提供程序](initializing-the-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="01d63-154">For more information about writing **XPProviderInit**, see [Initializing the Transport Provider](initializing-the-transport-provider.md).</span></span> <span data-ttu-id="01d63-155">有关入口点函数的信息，请参阅 [实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="01d63-155">For more information about entry point functions, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="01d63-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01d63-156">See also</span></span>



[<span data-ttu-id="01d63-157">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="01d63-157">ABProviderInit</span></span>](abproviderinit.md)
  
[<span data-ttu-id="01d63-158">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="01d63-158">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)
  
[<span data-ttu-id="01d63-159">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="01d63-159">MSProviderInit</span></span>](msproviderinit.md)

