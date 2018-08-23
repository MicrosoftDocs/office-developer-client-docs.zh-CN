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
ms.openlocfilehash: 38b60180ae7c417bf34998e72f96b353ace02859
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592533"
---
# <a name="xpproviderinit"></a><span data-ttu-id="2ddd4-103">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="2ddd4-103">XPProviderInit</span></span>

  
  
<span data-ttu-id="2ddd4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ddd4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ddd4-105">初始化的传输提供程序操作。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-105">Initializes a transport provider for operation.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ddd4-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2ddd4-106">Header file:</span></span>  <br/> |<span data-ttu-id="2ddd4-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="2ddd4-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="2ddd4-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2ddd4-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2ddd4-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="2ddd4-109">Transport providers</span></span>  <br/> |
|<span data-ttu-id="2ddd4-110">调用：</span><span class="sxs-lookup"><span data-stu-id="2ddd4-110">Called by:</span></span>  <br/> |<span data-ttu-id="2ddd4-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="2ddd4-111">MAPI</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="2ddd4-112">参数</span><span class="sxs-lookup"><span data-stu-id="2ddd4-112">Parameters</span></span>

 <span data-ttu-id="2ddd4-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="2ddd4-113">_hInstance_</span></span>
  
> <span data-ttu-id="2ddd4-114">[in]传输提供程序的动态链接库 (DLL) 的 MAPI 它加载 DLL 时使用的实例。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-114">[in] The instance of the transport provider's dynamic-link library (DLL) that MAPI used when it loaded the DLL.</span></span>
    
 <span data-ttu-id="2ddd4-115">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="2ddd4-115">_lpMalloc_</span></span>
  
> <span data-ttu-id="2ddd4-116">[in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-116">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="2ddd4-117">传输提供程序可能需要使用某些如**IStream**接口时使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-117">The transport provider may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="2ddd4-118">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="2ddd4-118">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="2ddd4-119">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-119">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="2ddd4-120">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="2ddd4-120">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="2ddd4-121">[in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-121">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="2ddd4-122">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="2ddd4-122">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="2ddd4-123">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-123">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="2ddd4-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2ddd4-124">_ulFlags_</span></span>
  
> <span data-ttu-id="2ddd4-125">[in]Flags 的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-125">[in] Bitmask of flags.</span></span> <span data-ttu-id="2ddd4-126">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="2ddd4-126">The following flag can be set:</span></span>
    
<span data-ttu-id="2ddd4-127">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="2ddd4-127">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="2ddd4-128">提供程序正在加载的一项 Windows 服务，一个特殊类型没有任何用户界面的访问权限的过程的上下文中。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-128">The provider is being loaded in the context of a Windows service, a special type of process without access to any user interface.</span></span> 
    
 <span data-ttu-id="2ddd4-129">_ulMAPIVer_</span><span class="sxs-lookup"><span data-stu-id="2ddd4-129">_ulMAPIVer_</span></span>
  
> <span data-ttu-id="2ddd4-130">[in]Mapi.dll 使用的服务提供程序界面 (SPI) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-130">[in] Version number of the service provider interface (SPI) that Mapi.dll uses.</span></span> <span data-ttu-id="2ddd4-131">当前版本号，请参阅 Mapispi.h 头文件。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-131">For the current version number, see the Mapispi.h header file.</span></span> 
    
 <span data-ttu-id="2ddd4-132">_lpulProviderVer_</span><span class="sxs-lookup"><span data-stu-id="2ddd4-132">_lpulProviderVer_</span></span>
  
> <span data-ttu-id="2ddd4-133">[输出]指向该传输提供程序使用 SPI 的版本号。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-133">[out] Pointer to the version number of the SPI that this transport provider uses.</span></span> 
    
 <span data-ttu-id="2ddd4-134">_lppXPProvider_</span><span class="sxs-lookup"><span data-stu-id="2ddd4-134">_lppXPProvider_</span></span>
  
> <span data-ttu-id="2ddd4-135">[输出]指向初始化的传输提供程序对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-135">[out] Pointer to a pointer to the initialized transport provider object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2ddd4-136">返回值</span><span class="sxs-lookup"><span data-stu-id="2ddd4-136">Return value</span></span>

<span data-ttu-id="2ddd4-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ddd4-137">S_OK</span></span> 
  
> <span data-ttu-id="2ddd4-138">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-138">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="2ddd4-139">MAPI_E_VERSION</span><span class="sxs-lookup"><span data-stu-id="2ddd4-139">MAPI_E_VERSION</span></span> 
  
> <span data-ttu-id="2ddd4-140">正在使用 MAPI 的 SPI 版本不兼容与 SPI 正在使用此提供程序。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-140">The SPI version being used by MAPI is not compatible with the SPI being used by this provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2ddd4-141">注解</span><span class="sxs-lookup"><span data-stu-id="2ddd4-141">Remarks</span></span>

<span data-ttu-id="2ddd4-142">MAPI 调用入口点函数**XPProviderInit**初始化关注客户端登录的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-142">MAPI calls the entry point function **XPProviderInit** to initialize a transport provider following a client logon.</span></span> <span data-ttu-id="2ddd4-143">客户端的配置文件中指定每个传输提供程序调用**XPProviderInit**一次。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-143">**XPProviderInit** is called once for each transport provider specified in the client's profile.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2ddd4-144">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="2ddd4-144">Notes to implementers</span></span>

<span data-ttu-id="2ddd4-145">传输提供程序必须实现**XPProviderInit**作为在提供程序的 DLL 入口点函数。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-145">A transport provider must implement **XPProviderInit** as an entry point function in the provider's DLL.</span></span> <span data-ttu-id="2ddd4-146">实现必须基于**XPPROVIDERINIT**函数原型，还中指定 Mapispi.h。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-146">The implementation must be based on the **XPPROVIDERINIT** function prototype, also specified in Mapispi.h.</span></span> <span data-ttu-id="2ddd4-147">MAPI 定义**XPPROVIDERINIT**使用标准 MAPI 初始化呼叫类型，STDMAPIINITCALLTYPE，这将导致**XPProviderInit**关注 CDECL 调用约定。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-147">MAPI defines **XPPROVIDERINIT** to use the standard MAPI initialization call type, STDMAPIINITCALLTYPE, which causes **XPProviderInit** to follow the CDECL calling convention.</span></span> <span data-ttu-id="2ddd4-148">利用 CDECL 是即使调用参数数目不符定义参数数目，可以尝试呼叫。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-148">An advantage of CDECL is that calls can be attempted even if the number of calling parameters does not match the number of defined parameters.</span></span> 
  
<span data-ttu-id="2ddd4-149">提供程序可以初始化多次由于中同时使用或多次出现在相同的配置文件显示在多个配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-149">A provider can be initialized multiple times as a result of appearing in several profiles in simultaneous use or of appearing more than once in the same profile.</span></span> <span data-ttu-id="2ddd4-150">由于提供商对象包含上下文， **XPProviderInit**必须中为每个初始化，即使的同一进程中的多个初始化_lppXPProvider_返回不同的提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-150">Because the provider object contains context, **XPProviderInit** must return a different provider object in  _lppXPProvider_ for each initialization, even for multiple initializations in the same process.</span></span> 
  
<span data-ttu-id="2ddd4-151">传输提供程序应使用指向_lpAllocateBuffer_和_lpAllocateMore_，对于大多数内存分配和释放_lpFreeBuffer_的功能。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-151">The transport provider should use the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation.</span></span> <span data-ttu-id="2ddd4-152">特别是，提供程序必须使用这些函数用于客户端应用程序分配内存，调用[IMAPIProp::GetProps](imapiprop-getprops.md)等[IMAPITable::QueryRows](imapitable-queryrows.md)对象接口时。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-152">In particular, the provider must use these functions to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="2ddd4-153">如果还希望使用 OLE 内存分配器提供程序，它应调用_lpMalloc_参数指向分配器对象的**IUnknown::AddRef**方法。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-153">If the provider also expects to use the OLE memory allocator, it should call the **IUnknown::AddRef** method of the allocator object pointed to by the  _lpMalloc_ parameter.</span></span> 
  
<span data-ttu-id="2ddd4-154">有关编写**XPProviderInit**的详细信息，请参阅[初始化传输提供程序](initializing-the-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-154">For more information about writing **XPProviderInit**, see [Initializing the Transport Provider](initializing-the-transport-provider.md).</span></span> <span data-ttu-id="2ddd4-155">有关入口点函数的详细信息，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="2ddd4-155">For more information about entry point functions, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2ddd4-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ddd4-156">See also</span></span>



[<span data-ttu-id="2ddd4-157">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="2ddd4-157">ABProviderInit</span></span>](abproviderinit.md)
  
[<span data-ttu-id="2ddd4-158">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2ddd4-158">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)
  
[<span data-ttu-id="2ddd4-159">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="2ddd4-159">MSProviderInit</span></span>](msproviderinit.md)

