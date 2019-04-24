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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325653"
---
# <a name="xpproviderinit"></a><span data-ttu-id="ffe17-103">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="ffe17-103">XPProviderInit</span></span>

  
  
<span data-ttu-id="ffe17-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ffe17-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ffe17-105">为操作初始化传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="ffe17-105">Initializes a transport provider for operation.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ffe17-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ffe17-106">Header file:</span></span>  <br/> |<span data-ttu-id="ffe17-107">Mapispi</span><span class="sxs-lookup"><span data-stu-id="ffe17-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="ffe17-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="ffe17-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ffe17-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="ffe17-109">Transport providers</span></span>  <br/> |
|<span data-ttu-id="ffe17-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="ffe17-110">Called by:</span></span>  <br/> |<span data-ttu-id="ffe17-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="ffe17-111">MAPI</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="ffe17-112">参数</span><span class="sxs-lookup"><span data-stu-id="ffe17-112">Parameters</span></span>

 <span data-ttu-id="ffe17-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="ffe17-113">_hInstance_</span></span>
  
> <span data-ttu-id="ffe17-114">实时MAPI 加载 DLL 时使用的传输提供程序的动态链接库 (DLL) 的实例。</span><span class="sxs-lookup"><span data-stu-id="ffe17-114">[in] The instance of the transport provider's dynamic-link library (DLL) that MAPI used when it loaded the DLL.</span></span>
    
 <span data-ttu-id="ffe17-115">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="ffe17-115">_lpMalloc_</span></span>
  
> <span data-ttu-id="ffe17-116">实时指向用于公开 OLE **IMalloc**接口的内存分配器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ffe17-116">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="ffe17-117">在使用某些接口 (如**IStream**) 时, 传输提供程序可能需要使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="ffe17-117">The transport provider may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="ffe17-118">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="ffe17-118">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="ffe17-119">实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="ffe17-119">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="ffe17-120">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="ffe17-120">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="ffe17-121">实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="ffe17-121">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="ffe17-122">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="ffe17-122">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="ffe17-123">实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="ffe17-123">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="ffe17-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ffe17-124">_ulFlags_</span></span>
  
> <span data-ttu-id="ffe17-125">实时标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ffe17-125">[in] Bitmask of flags.</span></span> <span data-ttu-id="ffe17-126">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ffe17-126">The following flag can be set:</span></span>
    
<span data-ttu-id="ffe17-127">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="ffe17-127">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="ffe17-128">提供程序在 Windows 服务的上下文中加载, 这是一种特殊类型的过程, 无需访问任何用户界面。</span><span class="sxs-lookup"><span data-stu-id="ffe17-128">The provider is being loaded in the context of a Windows service, a special type of process without access to any user interface.</span></span> 
    
 <span data-ttu-id="ffe17-129">_ulMAPIVer_</span><span class="sxs-lookup"><span data-stu-id="ffe17-129">_ulMAPIVer_</span></span>
  
> <span data-ttu-id="ffe17-130">实时Mapi .dll 使用的服务提供程序接口 (SPI) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="ffe17-130">[in] Version number of the service provider interface (SPI) that Mapi.dll uses.</span></span> <span data-ttu-id="ffe17-131">有关当前版本号, 请参阅 Mapispi 头文件。</span><span class="sxs-lookup"><span data-stu-id="ffe17-131">For the current version number, see the Mapispi.h header file.</span></span> 
    
 <span data-ttu-id="ffe17-132">_lpulProviderVer_</span><span class="sxs-lookup"><span data-stu-id="ffe17-132">_lpulProviderVer_</span></span>
  
> <span data-ttu-id="ffe17-133">排除指向此传输提供程序使用的 SPI 版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="ffe17-133">[out] Pointer to the version number of the SPI that this transport provider uses.</span></span> 
    
 <span data-ttu-id="ffe17-134">_lppXPProvider_</span><span class="sxs-lookup"><span data-stu-id="ffe17-134">_lppXPProvider_</span></span>
  
> <span data-ttu-id="ffe17-135">排除指向已初始化的传输提供程序对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ffe17-135">[out] Pointer to a pointer to the initialized transport provider object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ffe17-136">返回值</span><span class="sxs-lookup"><span data-stu-id="ffe17-136">Return value</span></span>

<span data-ttu-id="ffe17-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffe17-137">S_OK</span></span> 
  
> <span data-ttu-id="ffe17-138">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="ffe17-138">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="ffe17-139">MAPI_E_VERSION</span><span class="sxs-lookup"><span data-stu-id="ffe17-139">MAPI_E_VERSION</span></span> 
  
> <span data-ttu-id="ffe17-140">MAPI 使用的 spi 版本与此提供程序使用的 spi 不兼容。</span><span class="sxs-lookup"><span data-stu-id="ffe17-140">The SPI version being used by MAPI is not compatible with the SPI being used by this provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ffe17-141">注解</span><span class="sxs-lookup"><span data-stu-id="ffe17-141">Remarks</span></span>

<span data-ttu-id="ffe17-142">MAPI 调用入口点函数**XPProviderInit** , 以在客户端登录后初始化传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="ffe17-142">MAPI calls the entry point function **XPProviderInit** to initialize a transport provider following a client logon.</span></span> <span data-ttu-id="ffe17-143">对于客户端配置文件中指定的每个传输提供程序, 将调用**XPProviderInit**一次。</span><span class="sxs-lookup"><span data-stu-id="ffe17-143">**XPProviderInit** is called once for each transport provider specified in the client's profile.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="ffe17-144">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="ffe17-144">Notes to implementers</span></span>

<span data-ttu-id="ffe17-145">传输提供程序必须实现**XPProviderInit**作为提供程序 DLL 中的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="ffe17-145">A transport provider must implement **XPProviderInit** as an entry point function in the provider's DLL.</span></span> <span data-ttu-id="ffe17-146">实现必须基于**XPPROVIDERINIT**函数原型 (也在 Mapispi 中指定)。</span><span class="sxs-lookup"><span data-stu-id="ffe17-146">The implementation must be based on the **XPPROVIDERINIT** function prototype, also specified in Mapispi.h.</span></span> <span data-ttu-id="ffe17-147">MAPI 将**XPPROVIDERINIT**定义为使用标准 MAPI 初始化呼叫类型 STDMAPIINITCALLTYPE, 这将导致**XPPROVIDERINIT**遵循 CDECL 调用约定。</span><span class="sxs-lookup"><span data-stu-id="ffe17-147">MAPI defines **XPPROVIDERINIT** to use the standard MAPI initialization call type, STDMAPIINITCALLTYPE, which causes **XPProviderInit** to follow the CDECL calling convention.</span></span> <span data-ttu-id="ffe17-148">CDECL 的优势在于, 即使调用参数的数目与定义的参数数量不匹配, 也可以尝试调用。</span><span class="sxs-lookup"><span data-stu-id="ffe17-148">An advantage of CDECL is that calls can be attempted even if the number of calling parameters does not match the number of defined parameters.</span></span> 
  
<span data-ttu-id="ffe17-149">提供程序可以多次初始化, 这是由于多个配置文件在同一配置文件中同时使用或出现多次。</span><span class="sxs-lookup"><span data-stu-id="ffe17-149">A provider can be initialized multiple times as a result of appearing in several profiles in simultaneous use or of appearing more than once in the same profile.</span></span> <span data-ttu-id="ffe17-150">由于 provider 对象包含上下文, 因此**XPProviderInit**必须在_lppXPProvider_中为每个初始化返回不同的提供程序对象, 即使在同一进程中进行了多次初始化也是如此。</span><span class="sxs-lookup"><span data-stu-id="ffe17-150">Because the provider object contains context, **XPProviderInit** must return a different provider object in  _lppXPProvider_ for each initialization, even for multiple initializations in the same process.</span></span> 
  
<span data-ttu-id="ffe17-151">传输提供程序应使用由_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指向的用于大多数内存分配和释放的函数。</span><span class="sxs-lookup"><span data-stu-id="ffe17-151">The transport provider should use the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation.</span></span> <span data-ttu-id="ffe17-152">特别是, 提供程序必须使用这些函数分配在调用对象接口 (如[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)) 时供客户端应用程序使用的内存。</span><span class="sxs-lookup"><span data-stu-id="ffe17-152">In particular, the provider must use these functions to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="ffe17-153">如果提供程序还预期使用 OLE 内存分配器, 则它应调用分配器对象的**IUnknown:: AddRef**方法, 该对象由_lpMalloc_参数指向该对象。</span><span class="sxs-lookup"><span data-stu-id="ffe17-153">If the provider also expects to use the OLE memory allocator, it should call the **IUnknown::AddRef** method of the allocator object pointed to by the  _lpMalloc_ parameter.</span></span> 
  
<span data-ttu-id="ffe17-154">有关编写**XPProviderInit**的详细信息, 请参阅[初始化传输提供程序](initializing-the-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="ffe17-154">For more information about writing **XPProviderInit**, see [Initializing the Transport Provider](initializing-the-transport-provider.md).</span></span> <span data-ttu-id="ffe17-155">有关入口点函数的详细信息, 请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="ffe17-155">For more information about entry point functions, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ffe17-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffe17-156">See also</span></span>



[<span data-ttu-id="ffe17-157">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="ffe17-157">ABProviderInit</span></span>](abproviderinit.md)
  
[<span data-ttu-id="ffe17-158">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ffe17-158">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)
  
[<span data-ttu-id="ffe17-159">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="ffe17-159">MSProviderInit</span></span>](msproviderinit.md)

