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
# <a name="xpproviderinit"></a>XPProviderInit

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为操作初始化传输提供程序。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|实现者：  <br/> |传输提供程序  <br/> |
|调用者：  <br/> |MAPI  <br/> |
   
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

## <a name="parameters"></a>参数

 _hInstance_
  
> 实时MAPI 加载 DLL 时使用的传输提供程序的动态链接库 (DLL) 的实例。
    
 _lpMalloc_
  
> 实时指向用于公开 OLE **IMalloc**接口的内存分配器对象的指针。 在使用某些接口 (如**IStream**) 时, 传输提供程序可能需要使用此分配方法。 
    
 _lpAllocateBuffer_
  
> 实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。 
    
 _lpAllocateMore_
  
> 实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。 
    
 _lpFreeBuffer_
  
> 实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。 
    
 _ulFlags_
  
> 实时标志的位掩码。 可以设置以下标志:
    
MAPI_NT_SERVICE 
  
> 提供程序在 Windows 服务的上下文中加载, 这是一种特殊类型的过程, 无需访问任何用户界面。 
    
 _ulMAPIVer_
  
> 实时Mapi .dll 使用的服务提供程序接口 (SPI) 的版本号。 有关当前版本号, 请参阅 Mapispi 头文件。 
    
 _lpulProviderVer_
  
> 排除指向此传输提供程序使用的 SPI 版本号的指针。 
    
 _lppXPProvider_
  
> 排除指向已初始化的传输提供程序对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_VERSION 
  
> MAPI 使用的 spi 版本与此提供程序使用的 spi 不兼容。
    
## <a name="remarks"></a>说明

MAPI 调用入口点函数**XPProviderInit** , 以在客户端登录后初始化传输提供程序。 对于客户端配置文件中指定的每个传输提供程序, 将调用**XPProviderInit**一次。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

传输提供程序必须实现**XPProviderInit**作为提供程序 DLL 中的入口点函数。 实现必须基于**XPPROVIDERINIT**函数原型 (也在 Mapispi 中指定)。 MAPI 将**XPPROVIDERINIT**定义为使用标准 MAPI 初始化呼叫类型 STDMAPIINITCALLTYPE, 这将导致**XPPROVIDERINIT**遵循 CDECL 调用约定。 CDECL 的优势在于, 即使调用参数的数目与定义的参数数量不匹配, 也可以尝试调用。 
  
提供程序可以多次初始化, 这是由于多个配置文件在同一配置文件中同时使用或出现多次。 由于 provider 对象包含上下文, 因此**XPProviderInit**必须在_lppXPProvider_中为每个初始化返回不同的提供程序对象, 即使在同一进程中进行了多次初始化也是如此。 
  
传输提供程序应使用由_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指向的用于大多数内存分配和释放的函数。 特别是, 提供程序必须使用这些函数分配在调用对象接口 (如[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)) 时供客户端应用程序使用的内存。 如果提供程序还预期使用 OLE 内存分配器, 则它应调用分配器对象的**IUnknown:: AddRef**方法, 该对象由_lpMalloc_参数指向该对象。 
  
有关编写**XPProviderInit**的详细信息, 请参阅[初始化传输提供程序](initializing-the-transport-provider.md)。 有关入口点函数的详细信息, 请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。 
  
## <a name="see-also"></a>另请参阅



[ABProviderInit](abproviderinit.md)
  
[IXPProvider : IUnknown](ixpprovideriunknown.md)
  
[MSProviderInit](msproviderinit.md)

