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
ms.openlocfilehash: 9a5f8b44f9d795282ccfd61fd32a306c5478ed21
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416235"
---
# <a name="msproviderinit"></a><span data-ttu-id="7ed09-103">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="7ed09-103">MSProviderInit</span></span>

  
  
<span data-ttu-id="7ed09-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ed09-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ed09-105">初始化邮件存储提供程序以用于操作。</span><span class="sxs-lookup"><span data-stu-id="7ed09-105">Initializes a message store provider for operation.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7ed09-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7ed09-106">Header file:</span></span>  <br/> |<span data-ttu-id="7ed09-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="7ed09-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="7ed09-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7ed09-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7ed09-109">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="7ed09-109">Message store providers</span></span>  <br/> |
|<span data-ttu-id="7ed09-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7ed09-110">Called by:</span></span>  <br/> |<span data-ttu-id="7ed09-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="7ed09-111">MAPI</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="7ed09-112">参数</span><span class="sxs-lookup"><span data-stu-id="7ed09-112">Parameters</span></span>

 <span data-ttu-id="7ed09-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="7ed09-113">_hInstance_</span></span>
  
> <span data-ttu-id="7ed09-114">[in]邮件存储提供程序的动态链接库的实例 (MAPI 链接) 使用的 DLL。</span><span class="sxs-lookup"><span data-stu-id="7ed09-114">[in] The instance of the message store provider's dynamic-link library (DLL) that MAPI used when it linked.</span></span> 
    
 <span data-ttu-id="7ed09-115">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="7ed09-115">_lpMalloc_</span></span>
  
> <span data-ttu-id="7ed09-116">[in]指向公开 OLE **IMalloc 接口的内存分配器对象的** 指针。</span><span class="sxs-lookup"><span data-stu-id="7ed09-116">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="7ed09-117">使用某些接口（如 **IStream**）时，邮件存储提供程序可能需要使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="7ed09-117">The message store provider may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="7ed09-118">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="7ed09-118">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="7ed09-119">[in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="7ed09-119">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="7ed09-120">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="7ed09-120">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="7ed09-121">[in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。</span><span class="sxs-lookup"><span data-stu-id="7ed09-121">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="7ed09-122">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="7ed09-122">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="7ed09-123">[in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="7ed09-123">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="7ed09-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7ed09-124">_ulFlags_</span></span>
  
> <span data-ttu-id="7ed09-125">[in]标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="7ed09-125">[in] Bitmask of flags.</span></span> <span data-ttu-id="7ed09-126">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="7ed09-126">The following flag can be set:</span></span>
    
<span data-ttu-id="7ed09-127">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="7ed09-127">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="7ed09-128">提供程序正在服务（一种无法访问任何用户界面的一种特殊Windows服务）的上下文中加载。</span><span class="sxs-lookup"><span data-stu-id="7ed09-128">The provider is being loaded in the context of a Windows service, a special type of process without access to any user interface.</span></span> 
    
 <span data-ttu-id="7ed09-129">_ulMAPIVer_</span><span class="sxs-lookup"><span data-stu-id="7ed09-129">_ulMAPIVer_</span></span>
  
> <span data-ttu-id="7ed09-130">[in]MAPI 使用的 SPI (接口) 版本号。</span><span class="sxs-lookup"><span data-stu-id="7ed09-130">[in] Version number of the service provider interface (SPI) that MAPI uses.</span></span> <span data-ttu-id="7ed09-131">有关当前版本号，请参阅 Mapispi.h 头文件。</span><span class="sxs-lookup"><span data-stu-id="7ed09-131">For the current version number, see the Mapispi.h header file.</span></span> 
    
 <span data-ttu-id="7ed09-132">_lpulProviderVer_</span><span class="sxs-lookup"><span data-stu-id="7ed09-132">_lpulProviderVer_</span></span>
  
> <span data-ttu-id="7ed09-133">[out]指向此邮件存储提供程序使用的 SPI 的版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="7ed09-133">[out] Pointer to the version number of the SPI that this message store provider uses.</span></span> 
    
 <span data-ttu-id="7ed09-134">_lppMSProvider_</span><span class="sxs-lookup"><span data-stu-id="7ed09-134">_lppMSProvider_</span></span>
  
> <span data-ttu-id="7ed09-135">[out]指向初始化的邮件存储提供程序对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7ed09-135">[out] Pointer to a pointer to the initialized message store provider object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7ed09-136">返回值</span><span class="sxs-lookup"><span data-stu-id="7ed09-136">Return value</span></span>

<span data-ttu-id="7ed09-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ed09-137">S_OK</span></span> 
  
> <span data-ttu-id="7ed09-138">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="7ed09-138">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="7ed09-139">MAPI_E_VERSION</span><span class="sxs-lookup"><span data-stu-id="7ed09-139">MAPI_E_VERSION</span></span> 
  
> <span data-ttu-id="7ed09-140">MAPI 使用的 SPI 版本与此提供程序使用的 SPI 不兼容。</span><span class="sxs-lookup"><span data-stu-id="7ed09-140">The SPI version being used by MAPI is not compatible with the SPI being used by this provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7ed09-141">备注</span><span class="sxs-lookup"><span data-stu-id="7ed09-141">Remarks</span></span>

<span data-ttu-id="7ed09-142">MAPI 调用入口点函数 **MSProviderInit** 以在客户端登录后初始化邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="7ed09-142">MAPI calls the entry point function **MSProviderInit** to initialize a message store provider following a client logon.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="7ed09-143">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="7ed09-143">Notes to implementers</span></span>

<span data-ttu-id="7ed09-144">邮件存储提供程序必须将 **MSProviderInit** 实现为提供程序的 DLL 中的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="7ed09-144">A message store provider must implement **MSProviderInit** as an entry point function in the provider's DLL.</span></span> <span data-ttu-id="7ed09-145">实现必须基于 **MSPROVIDERINIT** 函数原型，在 MAPISPI.H 中也指定了该原型。</span><span class="sxs-lookup"><span data-stu-id="7ed09-145">The implementation must be based on the **MSPROVIDERINIT** function prototype, also specified in MAPISPI.H.</span></span> <span data-ttu-id="7ed09-146">MAPI 将 **MSPROVIDERINIT** 定义为使用标准 MAPI 初始化调用类型 STDMAPIINITCALLTYPE，这将导致 **MSProviderInit** 遵循 CDECL 调用约定。</span><span class="sxs-lookup"><span data-stu-id="7ed09-146">MAPI defines **MSPROVIDERINIT** to use the standard MAPI initialization call type, STDMAPIINITCALLTYPE, which causes **MSProviderInit** to follow the CDECL calling convention.</span></span> <span data-ttu-id="7ed09-147">CDECL 的一个优点是，即使调用参数的数量与定义的参数数不匹配，也可以尝试呼叫。</span><span class="sxs-lookup"><span data-stu-id="7ed09-147">An advantage of CDECL is that calls can be attempted even if the number of calling parameters does not match the number of defined parameters.</span></span> 
  
<span data-ttu-id="7ed09-148">提供程序可以多次初始化，因为同时在多个配置文件中显示，或者在同一配置文件中多次出现。</span><span class="sxs-lookup"><span data-stu-id="7ed09-148">A provider can be initialized multiple times, as a result of appearing in several profiles in simultaneous use or of appearing more than once in the same profile.</span></span> <span data-ttu-id="7ed09-149">由于提供程序对象包含上下文， **因此 MSProviderInit** 必须在  _lppMSProvider_ 中针对每次初始化返回不同的提供程序对象，即使对于同一进程中的多个初始化，也必须返回该对象。</span><span class="sxs-lookup"><span data-stu-id="7ed09-149">Because the provider object contains context, **MSProviderInit** must return a different provider object in  _lppMSProvider_ for each initialization, even for multiple initializations in the same process.</span></span> 
  
<span data-ttu-id="7ed09-150">不应将提供程序 DLL 与 Mapix.dll。</span><span class="sxs-lookup"><span data-stu-id="7ed09-150">The provider DLL should not be linked with Mapix.dll.</span></span> <span data-ttu-id="7ed09-151">相反，它应使用这些指针进行内存分配或释放。</span><span class="sxs-lookup"><span data-stu-id="7ed09-151">Instead, it should use these pointers for memory allocation or deallocation.</span></span> 
  
<span data-ttu-id="7ed09-152">邮件存储提供程序应该使用 _lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 指向的函数进行大多数内存分配和取消分配。 </span><span class="sxs-lookup"><span data-stu-id="7ed09-152">The message store provider should use the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation.</span></span> <span data-ttu-id="7ed09-153">特别是，当调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md)等对象接口时，提供程序必须使用这些函数分配内存供客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="7ed09-153">In particular, the provider must use these functions to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="7ed09-154">如果提供程序还希望使用 OLE 内存分配器，则它应调用 _lpMalloc_ 参数指向的分配器对象的 **IUnknown：：AddRef** 方法。</span><span class="sxs-lookup"><span data-stu-id="7ed09-154">If the provider also expects to use the OLE memory allocator, it should call the **IUnknown::AddRef** method of the allocator object pointed to by the  _lpMalloc_ parameter.</span></span> 
  
<span data-ttu-id="7ed09-155">有关编写 **MSProviderInit** 的信息，请参阅 [加载邮件存储提供程序](loading-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="7ed09-155">For more information about writing **MSProviderInit**, see [Loading Message Store Providers](loading-message-store-providers.md).</span></span> <span data-ttu-id="7ed09-156">有关入口点函数的信息，请参阅 [实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="7ed09-156">For more information about entry point functions, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7ed09-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ed09-157">See also</span></span>



[<span data-ttu-id="7ed09-158">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="7ed09-158">ABProviderInit</span></span>](abproviderinit.md)
  
[<span data-ttu-id="7ed09-159">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7ed09-159">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)
  
[<span data-ttu-id="7ed09-160">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="7ed09-160">XPProviderInit</span></span>](xpproviderinit.md)

