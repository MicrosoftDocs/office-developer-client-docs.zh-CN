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
ms.openlocfilehash: acec07df0b72685cf9ec6b21499c730b72f58c59
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428282"
---
# <a name="abproviderinit"></a><span data-ttu-id="7647f-103">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="7647f-103">ABProviderInit</span></span>
 
<span data-ttu-id="7647f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7647f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7647f-105">初始化通讯簿提供程序以用于操作。</span><span class="sxs-lookup"><span data-stu-id="7647f-105">Initializes an address book provider for operation.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7647f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7647f-106">Header file:</span></span>  <br/> |<span data-ttu-id="7647f-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="7647f-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="7647f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7647f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7647f-109">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="7647f-109">Address book providers</span></span>  <br/> |
|<span data-ttu-id="7647f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7647f-110">Called by:</span></span>  <br/> |<span data-ttu-id="7647f-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="7647f-111">MAPI</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="7647f-112">参数</span><span class="sxs-lookup"><span data-stu-id="7647f-112">Parameters</span></span>

 <span data-ttu-id="7647f-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="7647f-113">_hInstance_</span></span>
  
> <span data-ttu-id="7647f-114">[in]通讯簿提供程序的动态链接库的实例 (MAPI 链接) 使用的 DLL。</span><span class="sxs-lookup"><span data-stu-id="7647f-114">[in] The instance of the address book provider's dynamic-link library (DLL) that MAPI used when it linked.</span></span> 
    
 <span data-ttu-id="7647f-115">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="7647f-115">_lpMalloc_</span></span>
  
> <span data-ttu-id="7647f-116">[in]指向公开 OLE **IMalloc 接口的内存分配器对象的** 指针。</span><span class="sxs-lookup"><span data-stu-id="7647f-116">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="7647f-117">当使用某些接口（如 **IStream**）时，通讯簿提供程序可能需要使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="7647f-117">The address book provider may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="7647f-118">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="7647f-118">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="7647f-119">[in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，在 MAPI 需要时用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="7647f-119">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used where required by MAPI to allocate memory.</span></span> 
    
 <span data-ttu-id="7647f-120">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="7647f-120">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="7647f-121">[in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，在 MAPI 需要时用于分配额外内存。</span><span class="sxs-lookup"><span data-stu-id="7647f-121">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used where required by MAPI to allocate additional memory.</span></span> 
    
 <span data-ttu-id="7647f-122">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="7647f-122">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="7647f-123">[in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，在 MAPI 需要时用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="7647f-123">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used where required by MAPI to free memory.</span></span> 
    
 <span data-ttu-id="7647f-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7647f-124">_ulFlags_</span></span>
  
> <span data-ttu-id="7647f-125">[in]标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="7647f-125">[in] Bitmask of flags.</span></span> <span data-ttu-id="7647f-126">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="7647f-126">The following flag can be set:</span></span>
    
<span data-ttu-id="7647f-127">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="7647f-127">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="7647f-128">提供程序正在服务（一种无法访问任何用户界面的一种特殊Windows服务）的上下文中加载。</span><span class="sxs-lookup"><span data-stu-id="7647f-128">The provider is being loaded in the context of a Windows service, a special type of process without access to any user interface.</span></span> 
    
 <span data-ttu-id="7647f-129">_ulMAPIVer_</span><span class="sxs-lookup"><span data-stu-id="7647f-129">_ulMAPIVer_</span></span>
  
> <span data-ttu-id="7647f-130">[in]服务提供商接口的版本号 (SPI) 使用MAPI.DLL版本号。</span><span class="sxs-lookup"><span data-stu-id="7647f-130">[in] Version number of the service provider interface (SPI) that MAPI.DLL uses.</span></span> <span data-ttu-id="7647f-131">有关当前版本号，请参阅 MAPISPI。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="7647f-131">For the current version number, see the MAPISPI.H header file.</span></span> 
    
 <span data-ttu-id="7647f-132">_lpulProviderVer_</span><span class="sxs-lookup"><span data-stu-id="7647f-132">_lpulProviderVer_</span></span>
  
> <span data-ttu-id="7647f-133">[out]指向此通讯簿提供程序使用的 SPI 的版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="7647f-133">[out] Pointer to the version number of the SPI that this address book provider uses.</span></span> 
    
 <span data-ttu-id="7647f-134">_lppABProvider_</span><span class="sxs-lookup"><span data-stu-id="7647f-134">_lppABProvider_</span></span>
  
> <span data-ttu-id="7647f-135">[out]指向指向已初始化通讯簿提供程序对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7647f-135">[out] Pointer to a pointer to the initialized address book provider object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7647f-136">返回值</span><span class="sxs-lookup"><span data-stu-id="7647f-136">Return value</span></span>

<span data-ttu-id="7647f-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="7647f-137">S_OK</span></span> 
  
> <span data-ttu-id="7647f-138">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="7647f-138">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="7647f-139">MAPI_E_VERSION</span><span class="sxs-lookup"><span data-stu-id="7647f-139">MAPI_E_VERSION</span></span> 
  
> <span data-ttu-id="7647f-140">MAPI 使用的 SPI 版本与此提供程序使用的 SPI 不兼容。</span><span class="sxs-lookup"><span data-stu-id="7647f-140">The SPI version being used by MAPI is not compatible with the SPI being used by this provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7647f-141">备注</span><span class="sxs-lookup"><span data-stu-id="7647f-141">Remarks</span></span>

<span data-ttu-id="7647f-142">MAPI 调用入口点函数 **ABProviderInit** 以在客户端登录后初始化通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="7647f-142">MAPI calls the entry point function **ABProviderInit** to initialize an address book provider following a client logon.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="7647f-143">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="7647f-143">Notes to implementers</span></span>

<span data-ttu-id="7647f-144">通讯簿提供程序必须将 **ABProviderInit** 实现为提供程序的 DLL 中的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="7647f-144">An address book provider must implement **ABProviderInit** as an entry point function in the provider's DLL.</span></span> <span data-ttu-id="7647f-145">实现必须基于 **ABPROVIDERINIT** 函数原型，在 MAPISPI.H 中也指定了该原型。</span><span class="sxs-lookup"><span data-stu-id="7647f-145">The implementation must be based on the **ABPROVIDERINIT** function prototype, also specified in MAPISPI.H.</span></span> <span data-ttu-id="7647f-146">MAPI 将 **ABPROVIDERINIT** 定义为使用标准 MAPI 初始化调用类型 STDMAPIINITCALLTYPE，这将导致 **ABProviderInit** 遵循 CDECL 调用约定。</span><span class="sxs-lookup"><span data-stu-id="7647f-146">MAPI defines **ABPROVIDERINIT** to use the standard MAPI initialization call type, STDMAPIINITCALLTYPE, which causes **ABProviderInit** to follow the CDECL calling convention.</span></span> 
  
<span data-ttu-id="7647f-147">提供程序可以多次初始化，因为同时在多个配置文件中显示，或者在同一配置文件中多次出现。</span><span class="sxs-lookup"><span data-stu-id="7647f-147">A provider can be initialized multiple times, as a result of appearing in several profiles in simultaneous use or of appearing more than once in the same profile.</span></span> <span data-ttu-id="7647f-148">由于提供程序对象包含上下文， **因此 ABProviderInit** 必须在  _lppABProvider_ 中针对每次初始化返回不同的提供程序对象，即使对于同一进程中的多个初始化，也必须返回该对象。</span><span class="sxs-lookup"><span data-stu-id="7647f-148">Because the provider object contains context, **ABProviderInit** must return a different provider object in  _lppABProvider_ for each initialization, even for multiple initializations in the same process.</span></span> 
  
<span data-ttu-id="7647f-149">通讯簿提供程序应该使用 _lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 指向的函数，以用于大多数内存分配和取消分配。 </span><span class="sxs-lookup"><span data-stu-id="7647f-149">The address book provider should use the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation.</span></span> <span data-ttu-id="7647f-150">特别是，当调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md)等对象接口时，提供程序必须使用这些函数分配内存供客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="7647f-150">In particular, the provider must use these functions to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="7647f-151">如果提供程序还希望使用 OLE 内存分配器，则它应调用 _lpMalloc_ 参数指向的分配器对象的 **IUnknown：：AddRef** 方法。</span><span class="sxs-lookup"><span data-stu-id="7647f-151">If the provider also expects to use the OLE memory allocator, it should call the **IUnknown::AddRef** method of the allocator object pointed to by the  _lpMalloc_ parameter.</span></span> 
  
<span data-ttu-id="7647f-152">有关编写 **ABProviderInit** 的信息，请参阅 [实现通讯簿提供程序入口点函数](implementing-an-address-book-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="7647f-152">For more information on writing **ABProviderInit**, see [Implementing an Address Book Provider Entry Point Function](implementing-an-address-book-provider-entry-point-function.md).</span></span> <span data-ttu-id="7647f-153">有关入口点函数详细信息，请参阅 [实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="7647f-153">For more information on entry point functions, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7647f-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7647f-154">See also</span></span>

- [<span data-ttu-id="7647f-155">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7647f-155">IABProvider : IUnknown</span></span>](iabprovideriunknown.md) 
- [<span data-ttu-id="7647f-156">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="7647f-156">MSProviderInit</span></span>](msproviderinit.md)
- [<span data-ttu-id="7647f-157">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="7647f-157">XPProviderInit</span></span>](xpproviderinit.md)

