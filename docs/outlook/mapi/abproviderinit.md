---
title: ABProviderInit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ABProviderInit
api_type:
- HeaderDef
ms.assetid: c3dcd0d4-018a-47b0-b040-227034ed59d8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e76ad936cb8dc99897bc1c74d3a47b0d2aa4be46
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590048"
---
# <a name="abproviderinit"></a><span data-ttu-id="b0896-103">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="b0896-103">ABProviderInit</span></span>
 
<span data-ttu-id="b0896-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b0896-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b0896-105">初始化通讯簿提供程序的操作。</span><span class="sxs-lookup"><span data-stu-id="b0896-105">Initializes an address book provider for operation.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b0896-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b0896-106">Header file:</span></span>  <br/> |<span data-ttu-id="b0896-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="b0896-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="b0896-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="b0896-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="b0896-109">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="b0896-109">Address book providers</span></span>  <br/> |
|<span data-ttu-id="b0896-110">调用：</span><span class="sxs-lookup"><span data-stu-id="b0896-110">Called by:</span></span>  <br/> |<span data-ttu-id="b0896-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="b0896-111">MAPI</span></span>  <br/> |
   
```cpp
HRESULT ABProviderInit(
  HINSTANCE hInstance,
  LPMALLOC lpMalloc,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPALLOCATEMORE lpAllocateMore,
  LPFREEBUFFER lpFreeBuffer,
  ULONG ulFlags,
  ULONG ulMAPIVer,
  ULONG FAR * lpulProviderVer,
  LPABPROVIDER FAR * lppABProvider
);
```

## <a name="parameters"></a><span data-ttu-id="b0896-112">参数</span><span class="sxs-lookup"><span data-stu-id="b0896-112">Parameters</span></span>

 <span data-ttu-id="b0896-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="b0896-113">_hInstance_</span></span>
  
> <span data-ttu-id="b0896-114">[in]通讯簿提供程序的动态链接库 (DLL) 它链接时，将使用 MAPI 的实例。</span><span class="sxs-lookup"><span data-stu-id="b0896-114">[in] The instance of the address book provider's dynamic-link library (DLL) that MAPI used when it linked.</span></span> 
    
 <span data-ttu-id="b0896-115">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="b0896-115">_lpMalloc_</span></span>
  
> <span data-ttu-id="b0896-116">[in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b0896-116">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="b0896-117">通讯簿提供程序可能需要使用某些如**IStream**接口时使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="b0896-117">The address book provider may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="b0896-118">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="b0896-118">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="b0896-119">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于在需要时通过 MAPI 分配内存。</span><span class="sxs-lookup"><span data-stu-id="b0896-119">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used where required by MAPI to allocate memory.</span></span> 
    
 <span data-ttu-id="b0896-120">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="b0896-120">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="b0896-121">[in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于在需要时通过 MAPI 分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="b0896-121">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used where required by MAPI to allocate additional memory.</span></span> 
    
 <span data-ttu-id="b0896-122">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="b0896-122">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="b0896-123">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，用于在需要时通过 MAPI 以释放内存。</span><span class="sxs-lookup"><span data-stu-id="b0896-123">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used where required by MAPI to free memory.</span></span> 
    
 <span data-ttu-id="b0896-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b0896-124">_ulFlags_</span></span>
  
> <span data-ttu-id="b0896-125">[in]Flags 的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b0896-125">[in] Bitmask of flags.</span></span> <span data-ttu-id="b0896-126">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="b0896-126">The following flag can be set:</span></span>
    
<span data-ttu-id="b0896-127">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="b0896-127">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="b0896-128">提供程序正在加载的一项 Windows 服务，一个特殊类型没有任何用户界面的访问权限的过程的上下文中。</span><span class="sxs-lookup"><span data-stu-id="b0896-128">The provider is being loaded in the context of a Windows service, a special type of process without access to any user interface.</span></span> 
    
 <span data-ttu-id="b0896-129">_ulMAPIVer_</span><span class="sxs-lookup"><span data-stu-id="b0896-129">_ulMAPIVer_</span></span>
  
> <span data-ttu-id="b0896-130">[in]服务提供程序接口 (SPI) 的 MAPI 的版本号。使用 DLL。</span><span class="sxs-lookup"><span data-stu-id="b0896-130">[in] Version number of the service provider interface (SPI) that MAPI.DLL uses.</span></span> <span data-ttu-id="b0896-131">当前版本号，请参阅 MAPISPI。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="b0896-131">For the current version number, see the MAPISPI.H header file.</span></span> 
    
 <span data-ttu-id="b0896-132">_lpulProviderVer_</span><span class="sxs-lookup"><span data-stu-id="b0896-132">_lpulProviderVer_</span></span>
  
> <span data-ttu-id="b0896-133">[输出]指向 SPI 通讯簿提供商使用的版本号。</span><span class="sxs-lookup"><span data-stu-id="b0896-133">[out] Pointer to the version number of the SPI that this address book provider uses.</span></span> 
    
 <span data-ttu-id="b0896-134">_lppABProvider_</span><span class="sxs-lookup"><span data-stu-id="b0896-134">_lppABProvider_</span></span>
  
> <span data-ttu-id="b0896-135">[输出]为指向初始化的通讯簿提供程序对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b0896-135">[out] Pointer to a pointer to the initialized address book provider object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b0896-136">返回值</span><span class="sxs-lookup"><span data-stu-id="b0896-136">Return value</span></span>

<span data-ttu-id="b0896-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0896-137">S_OK</span></span> 
  
> <span data-ttu-id="b0896-138">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="b0896-138">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="b0896-139">MAPI_E_VERSION</span><span class="sxs-lookup"><span data-stu-id="b0896-139">MAPI_E_VERSION</span></span> 
  
> <span data-ttu-id="b0896-140">正在使用 MAPI 的 SPI 版本不兼容与 SPI 正在使用此提供程序。</span><span class="sxs-lookup"><span data-stu-id="b0896-140">The SPI version being used by MAPI is not compatible with the SPI being used by this provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b0896-141">注解</span><span class="sxs-lookup"><span data-stu-id="b0896-141">Remarks</span></span>

<span data-ttu-id="b0896-142">MAPI 调用入口点函数**ABProviderInit**初始化通讯簿提供程序关注客户端登录。</span><span class="sxs-lookup"><span data-stu-id="b0896-142">MAPI calls the entry point function **ABProviderInit** to initialize an address book provider following a client logon.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="b0896-143">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="b0896-143">Notes to implementers</span></span>

<span data-ttu-id="b0896-144">通讯簿提供程序必须实现**ABProviderInit**作为在提供程序的 DLL 入口点函数。</span><span class="sxs-lookup"><span data-stu-id="b0896-144">An address book provider must implement **ABProviderInit** as an entry point function in the provider's DLL.</span></span> <span data-ttu-id="b0896-145">实现必须基于**ABPROVIDERINIT**函数原型，还中指定 MAPISPI。H。</span><span class="sxs-lookup"><span data-stu-id="b0896-145">The implementation must be based on the **ABPROVIDERINIT** function prototype, also specified in MAPISPI.H.</span></span> <span data-ttu-id="b0896-146">MAPI 定义**ABPROVIDERINIT**使用标准 MAPI 初始化呼叫类型，STDMAPIINITCALLTYPE，这将导致**ABProviderInit**关注 CDECL 调用约定。</span><span class="sxs-lookup"><span data-stu-id="b0896-146">MAPI defines **ABPROVIDERINIT** to use the standard MAPI initialization call type, STDMAPIINITCALLTYPE, which causes **ABProviderInit** to follow the CDECL calling convention.</span></span> 
  
<span data-ttu-id="b0896-147">可多次，由于中同时使用或多次出现的同一配置文件中的多个配置文件中出现初始化提供程序。</span><span class="sxs-lookup"><span data-stu-id="b0896-147">A provider can be initialized multiple times, as a result of appearing in several profiles in simultaneous use or of appearing more than once in the same profile.</span></span> <span data-ttu-id="b0896-148">由于提供商对象包含上下文， **ABProviderInit**必须中为每个初始化，即使的同一进程中的多个初始化_lppABProvider_返回不同的提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="b0896-148">Because the provider object contains context, **ABProviderInit** must return a different provider object in  _lppABProvider_ for each initialization, even for multiple initializations in the same process.</span></span> 
  
<span data-ttu-id="b0896-149">通讯簿提供程序应使用指向_lpAllocateBuffer_和_lpAllocateMore_，对于大多数内存分配和释放_lpFreeBuffer_的功能。</span><span class="sxs-lookup"><span data-stu-id="b0896-149">The address book provider should use the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation.</span></span> <span data-ttu-id="b0896-150">特别是，提供程序必须使用这些函数用于客户端应用程序分配内存，调用[IMAPIProp::GetProps](imapiprop-getprops.md)等[IMAPITable::QueryRows](imapitable-queryrows.md)对象接口时。</span><span class="sxs-lookup"><span data-stu-id="b0896-150">In particular, the provider must use these functions to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="b0896-151">如果还希望使用 OLE 内存分配器提供程序，它应调用_lpMalloc_参数指向分配器对象的**IUnknown::AddRef**方法。</span><span class="sxs-lookup"><span data-stu-id="b0896-151">If the provider also expects to use the OLE memory allocator, it should call the **IUnknown::AddRef** method of the allocator object pointed to by the  _lpMalloc_ parameter.</span></span> 
  
<span data-ttu-id="b0896-152">编写**ABProviderInit**的详细信息，请参阅[实现地址簿提供程序入口点函数](implementing-an-address-book-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="b0896-152">For more information on writing **ABProviderInit**, see [Implementing an Address Book Provider Entry Point Function](implementing-an-address-book-provider-entry-point-function.md).</span></span> <span data-ttu-id="b0896-153">入口点函数的详细信息，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="b0896-153">For more information on entry point functions, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b0896-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0896-154">See also</span></span>

- [<span data-ttu-id="b0896-155">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b0896-155">IABProvider : IUnknown</span></span>](iabprovideriunknown.md) 
- [<span data-ttu-id="b0896-156">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="b0896-156">MSProviderInit</span></span>](msproviderinit.md)
- [<span data-ttu-id="b0896-157">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="b0896-157">XPProviderInit</span></span>](xpproviderinit.md)

