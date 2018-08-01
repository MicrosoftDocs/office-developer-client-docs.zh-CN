---
title: MSProviderInit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MSProviderInit
api_type:
- HeaderDef
ms.assetid: 230c66c4-ab04-4fa6-946f-9f4b704f2842
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cf1febe89c49b29cdfaf8d27760c4fb27b4c4990
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776524"
---
# <a name="msproviderinit"></a><span data-ttu-id="4b93d-103">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="4b93d-103">MSProviderInit</span></span>

  
  
<span data-ttu-id="4b93d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4b93d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4b93d-105">初始化操作的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="4b93d-105">Initializes a message store provider for operation.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4b93d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="4b93d-106">Header file:</span></span>  <br/> |<span data-ttu-id="4b93d-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="4b93d-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="4b93d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="4b93d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="4b93d-109">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="4b93d-109">Message store providers</span></span>  <br/> |
|<span data-ttu-id="4b93d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="4b93d-110">Called by:</span></span>  <br/> |<span data-ttu-id="4b93d-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="4b93d-111">MAPI</span></span>  <br/> |
   
```cpp
HRESULT MSProviderInit(
  HINSTANCE hInstance,
  LPMALLOC lpMalloc,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPALLOCATEMORE lpAllocateMore,
  LPFREEBUFFER lpFreeBuffer,
  ULONG ulFlags,
  ULONG ulMAPIVer,
  ULONG FAR * lpulProviderVer,
  LPMSPROVIDER FAR * lppMSProvider
);
```

## <a name="parameters"></a><span data-ttu-id="4b93d-112">参数</span><span class="sxs-lookup"><span data-stu-id="4b93d-112">Parameters</span></span>

 <span data-ttu-id="4b93d-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="4b93d-113">_hInstance_</span></span>
  
> <span data-ttu-id="4b93d-114">[in]邮件实例存储在它链接时，将使用 MAPI 的提供程序的动态链接库 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="4b93d-114">[in] The instance of the message store provider's dynamic-link library (DLL) that MAPI used when it linked.</span></span> 
    
 <span data-ttu-id="4b93d-115">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="4b93d-115">_lpMalloc_</span></span>
  
> <span data-ttu-id="4b93d-116">[in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="4b93d-116">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="4b93d-117">消息存储提供程序可能需要使用某些如**IStream**接口时使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="4b93d-117">The message store provider may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="4b93d-118">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="4b93d-118">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="4b93d-119">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="4b93d-119">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="4b93d-120">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="4b93d-120">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="4b93d-121">[in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="4b93d-121">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="4b93d-122">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="4b93d-122">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="4b93d-123">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="4b93d-123">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="4b93d-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="4b93d-124">_ulFlags_</span></span>
  
> <span data-ttu-id="4b93d-125">[in]Flags 的位掩码。</span><span class="sxs-lookup"><span data-stu-id="4b93d-125">[in] Bitmask of flags.</span></span> <span data-ttu-id="4b93d-126">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="4b93d-126">The following flag can be set:</span></span>
    
<span data-ttu-id="4b93d-127">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="4b93d-127">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="4b93d-128">提供程序正在加载的一项 Windows 服务，一个特殊类型没有任何用户界面的访问权限的过程的上下文中。</span><span class="sxs-lookup"><span data-stu-id="4b93d-128">The provider is being loaded in the context of a Windows service, a special type of process without access to any user interface.</span></span> 
    
 <span data-ttu-id="4b93d-129">_ulMAPIVer_</span><span class="sxs-lookup"><span data-stu-id="4b93d-129">_ulMAPIVer_</span></span>
  
> <span data-ttu-id="4b93d-130">[in]使用 MAPI 服务提供程序接口 (SPI) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="4b93d-130">[in] Version number of the service provider interface (SPI) that MAPI uses.</span></span> <span data-ttu-id="4b93d-131">当前版本号，请参阅 Mapispi.h 头文件。</span><span class="sxs-lookup"><span data-stu-id="4b93d-131">For the current version number, see the Mapispi.h header file.</span></span> 
    
 <span data-ttu-id="4b93d-132">_lpulProviderVer_</span><span class="sxs-lookup"><span data-stu-id="4b93d-132">_lpulProviderVer_</span></span>
  
> <span data-ttu-id="4b93d-133">[输出]指向该消息存储提供程序使用 SPI 的版本号。</span><span class="sxs-lookup"><span data-stu-id="4b93d-133">[out] Pointer to the version number of the SPI that this message store provider uses.</span></span> 
    
 <span data-ttu-id="4b93d-134">_lppMSProvider_</span><span class="sxs-lookup"><span data-stu-id="4b93d-134">_lppMSProvider_</span></span>
  
> <span data-ttu-id="4b93d-135">[输出]指向初始化的消息存储提供程序对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="4b93d-135">[out] Pointer to a pointer to the initialized message store provider object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4b93d-136">返回值</span><span class="sxs-lookup"><span data-stu-id="4b93d-136">Return value</span></span>

<span data-ttu-id="4b93d-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b93d-137">S_OK</span></span> 
  
> <span data-ttu-id="4b93d-138">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="4b93d-138">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="4b93d-139">MAPI_E_VERSION</span><span class="sxs-lookup"><span data-stu-id="4b93d-139">MAPI_E_VERSION</span></span> 
  
> <span data-ttu-id="4b93d-140">正在使用 MAPI 的 SPI 版本不兼容与 SPI 正在使用此提供程序。</span><span class="sxs-lookup"><span data-stu-id="4b93d-140">The SPI version being used by MAPI is not compatible with the SPI being used by this provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4b93d-141">说明</span><span class="sxs-lookup"><span data-stu-id="4b93d-141">Remarks</span></span>

<span data-ttu-id="4b93d-142">MAPI 调用入口点函数**MSProviderInit**初始化关注客户端登录的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="4b93d-142">MAPI calls the entry point function **MSProviderInit** to initialize a message store provider following a client logon.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="4b93d-143">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="4b93d-143">Notes to implementers</span></span>

<span data-ttu-id="4b93d-144">消息存储提供程序必须实现**MSProviderInit**作为在提供程序的 DLL 入口点函数。</span><span class="sxs-lookup"><span data-stu-id="4b93d-144">A message store provider must implement **MSProviderInit** as an entry point function in the provider's DLL.</span></span> <span data-ttu-id="4b93d-145">实现必须基于**MSPROVIDERINIT**函数原型，还中指定 MAPISPI。H。</span><span class="sxs-lookup"><span data-stu-id="4b93d-145">The implementation must be based on the **MSPROVIDERINIT** function prototype, also specified in MAPISPI.H.</span></span> <span data-ttu-id="4b93d-146">MAPI 定义**MSPROVIDERINIT**使用标准 MAPI 初始化呼叫类型，STDMAPIINITCALLTYPE，这将导致**MSProviderInit**关注 CDECL 调用约定。</span><span class="sxs-lookup"><span data-stu-id="4b93d-146">MAPI defines **MSPROVIDERINIT** to use the standard MAPI initialization call type, STDMAPIINITCALLTYPE, which causes **MSProviderInit** to follow the CDECL calling convention.</span></span> <span data-ttu-id="4b93d-147">利用 CDECL 是即使调用参数数目不符定义参数数目，可以尝试呼叫。</span><span class="sxs-lookup"><span data-stu-id="4b93d-147">An advantage of CDECL is that calls can be attempted even if the number of calling parameters does not match the number of defined parameters.</span></span> 
  
<span data-ttu-id="4b93d-148">可多次，由于中同时使用或多次出现的同一配置文件中的多个配置文件中出现初始化提供程序。</span><span class="sxs-lookup"><span data-stu-id="4b93d-148">A provider can be initialized multiple times, as a result of appearing in several profiles in simultaneous use or of appearing more than once in the same profile.</span></span> <span data-ttu-id="4b93d-149">由于提供商对象包含上下文， **MSProviderInit**必须中为每个初始化，即使的同一进程中的多个初始化_lppMSProvider_返回不同的提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="4b93d-149">Because the provider object contains context, **MSProviderInit** must return a different provider object in  _lppMSProvider_ for each initialization, even for multiple initializations in the same process.</span></span> 
  
<span data-ttu-id="4b93d-150">不应该与 Mapix.dll 链接提供程序 DLL。</span><span class="sxs-lookup"><span data-stu-id="4b93d-150">The provider DLL should not be linked with Mapix.dll.</span></span> <span data-ttu-id="4b93d-151">相反，它应使用这些指针的内存分配或释放。</span><span class="sxs-lookup"><span data-stu-id="4b93d-151">Instead, it should use these pointers for memory allocation or deallocation.</span></span> 
  
<span data-ttu-id="4b93d-152">消息存储提供程序应使用指向_lpAllocateBuffer_和_lpAllocateMore_，对于大多数内存分配和释放_lpFreeBuffer_的功能。</span><span class="sxs-lookup"><span data-stu-id="4b93d-152">The message store provider should use the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation.</span></span> <span data-ttu-id="4b93d-153">特别是，提供程序必须使用这些函数用于客户端应用程序分配内存，调用[IMAPIProp::GetProps](imapiprop-getprops.md)等[IMAPITable::QueryRows](imapitable-queryrows.md)对象接口时。</span><span class="sxs-lookup"><span data-stu-id="4b93d-153">In particular, the provider must use these functions to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="4b93d-154">如果还希望使用 OLE 内存分配器提供程序，它应调用_lpMalloc_参数指向分配器对象的**IUnknown::AddRef**方法。</span><span class="sxs-lookup"><span data-stu-id="4b93d-154">If the provider also expects to use the OLE memory allocator, it should call the **IUnknown::AddRef** method of the allocator object pointed to by the  _lpMalloc_ parameter.</span></span> 
  
<span data-ttu-id="4b93d-155">有关编写**MSProviderInit**的详细信息，请参阅[加载消息存储提供程序](loading-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="4b93d-155">For more information about writing **MSProviderInit**, see [Loading Message Store Providers](loading-message-store-providers.md).</span></span> <span data-ttu-id="4b93d-156">有关入口点函数的详细信息，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="4b93d-156">For more information about entry point functions, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4b93d-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b93d-157">See also</span></span>



[<span data-ttu-id="4b93d-158">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="4b93d-158">ABProviderInit</span></span>](abproviderinit.md)
  
[<span data-ttu-id="4b93d-159">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4b93d-159">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)
  
[<span data-ttu-id="4b93d-160">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="4b93d-160">XPProviderInit</span></span>](xpproviderinit.md)

