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
# <a name="msproviderinit"></a><span data-ttu-id="40bc2-103">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="40bc2-103">MSProviderInit</span></span>

  
  
<span data-ttu-id="40bc2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="40bc2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="40bc2-105">为操作初始化邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="40bc2-105">Initializes a message store provider for operation.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="40bc2-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="40bc2-106">Header file:</span></span>  <br/> |<span data-ttu-id="40bc2-107">Mapispi</span><span class="sxs-lookup"><span data-stu-id="40bc2-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="40bc2-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="40bc2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="40bc2-109">邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="40bc2-109">Message store providers</span></span>  <br/> |
|<span data-ttu-id="40bc2-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="40bc2-110">Called by:</span></span>  <br/> |<span data-ttu-id="40bc2-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="40bc2-111">MAPI</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="40bc2-112">参数</span><span class="sxs-lookup"><span data-stu-id="40bc2-112">Parameters</span></span>

 <span data-ttu-id="40bc2-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="40bc2-113">_hInstance_</span></span>
  
> <span data-ttu-id="40bc2-114">实时MAPI 链接时使用的邮件存储区提供程序的动态链接库 (DLL) 的实例。</span><span class="sxs-lookup"><span data-stu-id="40bc2-114">[in] The instance of the message store provider's dynamic-link library (DLL) that MAPI used when it linked.</span></span> 
    
 <span data-ttu-id="40bc2-115">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="40bc2-115">_lpMalloc_</span></span>
  
> <span data-ttu-id="40bc2-116">实时指向用于公开 OLE **IMalloc**接口的内存分配器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="40bc2-116">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="40bc2-117">在使用某些接口 (如**IStream**) 时, 邮件存储提供程序可能需要使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="40bc2-117">The message store provider may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="40bc2-118">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="40bc2-118">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="40bc2-119">实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="40bc2-119">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="40bc2-120">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="40bc2-120">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="40bc2-121">实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="40bc2-121">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="40bc2-122">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="40bc2-122">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="40bc2-123">实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="40bc2-123">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="40bc2-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="40bc2-124">_ulFlags_</span></span>
  
> <span data-ttu-id="40bc2-125">实时标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="40bc2-125">[in] Bitmask of flags.</span></span> <span data-ttu-id="40bc2-126">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="40bc2-126">The following flag can be set:</span></span>
    
<span data-ttu-id="40bc2-127">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="40bc2-127">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="40bc2-128">提供程序在 Windows 服务的上下文中加载, 这是一种特殊类型的过程, 无需访问任何用户界面。</span><span class="sxs-lookup"><span data-stu-id="40bc2-128">The provider is being loaded in the context of a Windows service, a special type of process without access to any user interface.</span></span> 
    
 <span data-ttu-id="40bc2-129">_ulMAPIVer_</span><span class="sxs-lookup"><span data-stu-id="40bc2-129">_ulMAPIVer_</span></span>
  
> <span data-ttu-id="40bc2-130">实时MAPI 使用的服务提供程序接口 (SPI) 版本号。</span><span class="sxs-lookup"><span data-stu-id="40bc2-130">[in] Version number of the service provider interface (SPI) that MAPI uses.</span></span> <span data-ttu-id="40bc2-131">有关当前版本号, 请参阅 Mapispi 头文件。</span><span class="sxs-lookup"><span data-stu-id="40bc2-131">For the current version number, see the Mapispi.h header file.</span></span> 
    
 <span data-ttu-id="40bc2-132">_lpulProviderVer_</span><span class="sxs-lookup"><span data-stu-id="40bc2-132">_lpulProviderVer_</span></span>
  
> <span data-ttu-id="40bc2-133">排除指向此邮件存储提供程序使用的 SPI 版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="40bc2-133">[out] Pointer to the version number of the SPI that this message store provider uses.</span></span> 
    
 <span data-ttu-id="40bc2-134">_lppMSProvider_</span><span class="sxs-lookup"><span data-stu-id="40bc2-134">_lppMSProvider_</span></span>
  
> <span data-ttu-id="40bc2-135">排除指向已初始化的邮件存储提供程序对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="40bc2-135">[out] Pointer to a pointer to the initialized message store provider object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="40bc2-136">返回值</span><span class="sxs-lookup"><span data-stu-id="40bc2-136">Return value</span></span>

<span data-ttu-id="40bc2-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="40bc2-137">S_OK</span></span> 
  
> <span data-ttu-id="40bc2-138">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="40bc2-138">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="40bc2-139">MAPI_E_VERSION</span><span class="sxs-lookup"><span data-stu-id="40bc2-139">MAPI_E_VERSION</span></span> 
  
> <span data-ttu-id="40bc2-140">MAPI 使用的 spi 版本与此提供程序使用的 spi 不兼容。</span><span class="sxs-lookup"><span data-stu-id="40bc2-140">The SPI version being used by MAPI is not compatible with the SPI being used by this provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="40bc2-141">说明</span><span class="sxs-lookup"><span data-stu-id="40bc2-141">Remarks</span></span>

<span data-ttu-id="40bc2-142">MAPI 调用入口点函数**MSProviderInit** , 以在客户端登录后初始化邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="40bc2-142">MAPI calls the entry point function **MSProviderInit** to initialize a message store provider following a client logon.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="40bc2-143">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="40bc2-143">Notes to implementers</span></span>

<span data-ttu-id="40bc2-144">邮件存储区提供程序必须实现**MSProviderInit**作为提供程序 DLL 中的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="40bc2-144">A message store provider must implement **MSProviderInit** as an entry point function in the provider's DLL.</span></span> <span data-ttu-id="40bc2-145">实现必须基于**MSPROVIDERINIT**函数原型 (也在 MAPISPI 中指定)。水平.</span><span class="sxs-lookup"><span data-stu-id="40bc2-145">The implementation must be based on the **MSPROVIDERINIT** function prototype, also specified in MAPISPI.H.</span></span> <span data-ttu-id="40bc2-146">MAPI 将**MSPROVIDERINIT**定义为使用标准 MAPI 初始化呼叫类型 STDMAPIINITCALLTYPE, 这将导致**MSPROVIDERINIT**遵循 CDECL 调用约定。</span><span class="sxs-lookup"><span data-stu-id="40bc2-146">MAPI defines **MSPROVIDERINIT** to use the standard MAPI initialization call type, STDMAPIINITCALLTYPE, which causes **MSProviderInit** to follow the CDECL calling convention.</span></span> <span data-ttu-id="40bc2-147">CDECL 的优势在于, 即使调用参数的数目与定义的参数数量不匹配, 也可以尝试调用。</span><span class="sxs-lookup"><span data-stu-id="40bc2-147">An advantage of CDECL is that calls can be attempted even if the number of calling parameters does not match the number of defined parameters.</span></span> 
  
<span data-ttu-id="40bc2-148">提供程序可以多次初始化, 这是由于多个配置文件中出现在同时使用或在同一配置文件中出现多次。</span><span class="sxs-lookup"><span data-stu-id="40bc2-148">A provider can be initialized multiple times, as a result of appearing in several profiles in simultaneous use or of appearing more than once in the same profile.</span></span> <span data-ttu-id="40bc2-149">由于 provider 对象包含上下文, 因此**MSProviderInit**必须在_lppMSProvider_中为每个初始化返回不同的提供程序对象, 即使在同一进程中进行了多次初始化也是如此。</span><span class="sxs-lookup"><span data-stu-id="40bc2-149">Because the provider object contains context, **MSProviderInit** must return a different provider object in  _lppMSProvider_ for each initialization, even for multiple initializations in the same process.</span></span> 
  
<span data-ttu-id="40bc2-150">提供程序 DLL 不应与 Mapix 链接。</span><span class="sxs-lookup"><span data-stu-id="40bc2-150">The provider DLL should not be linked with Mapix.dll.</span></span> <span data-ttu-id="40bc2-151">相反, 它应使用这些指针来分配或释放内存。</span><span class="sxs-lookup"><span data-stu-id="40bc2-151">Instead, it should use these pointers for memory allocation or deallocation.</span></span> 
  
<span data-ttu-id="40bc2-152">邮件存储区提供程序应使用由_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指向的函数, 以实现大多数内存分配和释放。</span><span class="sxs-lookup"><span data-stu-id="40bc2-152">The message store provider should use the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation.</span></span> <span data-ttu-id="40bc2-153">特别是, 提供程序必须使用这些函数分配在调用对象接口 (如[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)) 时供客户端应用程序使用的内存。</span><span class="sxs-lookup"><span data-stu-id="40bc2-153">In particular, the provider must use these functions to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> <span data-ttu-id="40bc2-154">如果提供程序还预期使用 OLE 内存分配器, 则它应调用分配器对象的**IUnknown:: AddRef**方法, 该对象由_lpMalloc_参数指向该对象。</span><span class="sxs-lookup"><span data-stu-id="40bc2-154">If the provider also expects to use the OLE memory allocator, it should call the **IUnknown::AddRef** method of the allocator object pointed to by the  _lpMalloc_ parameter.</span></span> 
  
<span data-ttu-id="40bc2-155">有关编写**MSProviderInit**的详细信息, 请参阅[加载邮件存储提供程序](loading-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="40bc2-155">For more information about writing **MSProviderInit**, see [Loading Message Store Providers](loading-message-store-providers.md).</span></span> <span data-ttu-id="40bc2-156">有关入口点函数的详细信息, 请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="40bc2-156">For more information about entry point functions, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="40bc2-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40bc2-157">See also</span></span>



[<span data-ttu-id="40bc2-158">ABProviderInit</span><span class="sxs-lookup"><span data-stu-id="40bc2-158">ABProviderInit</span></span>](abproviderinit.md)
  
[<span data-ttu-id="40bc2-159">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="40bc2-159">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)
  
[<span data-ttu-id="40bc2-160">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="40bc2-160">XPProviderInit</span></span>](xpproviderinit.md)

