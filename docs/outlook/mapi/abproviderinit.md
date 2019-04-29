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
# <a name="abproviderinit"></a>ABProviderInit
 
**适用于**：Outlook 2013 | Outlook 2016 
  
为操作初始化通讯簿提供程序。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|实现者：  <br/> |通讯簿提供程序  <br/> |
|调用者：  <br/> |MAPI  <br/> |
   
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

## <a name="parameters"></a>参数

 _hInstance_
  
> 实时MAPI 链接时使用的通讯簿提供程序的动态链接库 (DLL) 的实例。 
    
 _lpMalloc_
  
> 实时指向用于公开 OLE **IMalloc**接口的内存分配器对象的指针。 通讯簿提供程序在使用某些接口 (如**IStream**) 时, 可能需要使用此分配方法。 
    
 _lpAllocateBuffer_
  
> 实时指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针, 使用 MAPI 分配内存所需的位置。 
    
 _lpAllocateMore_
  
> 实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 在 MAPI 需要使用它分配更多内存的地方。 
    
 _lpFreeBuffer_
  
> 实时指向[MAPIFreeBuffer](mapifreebuffer.md)函数的指针, 可在 MAPI 所需的地方使用, 以释放内存。 
    
 _ulFlags_
  
> 实时标志的位掩码。 可以设置以下标志:
    
MAPI_NT_SERVICE 
  
> 提供程序在 Windows 服务的上下文中加载, 这是一种特殊类型的过程, 无需访问任何用户界面。 
    
 _ulMAPIVer_
  
> 实时MAPI 的服务提供程序接口 (SPI) 的版本号。DLL 使用。 有关当前版本号, 请参阅 MAPISPI。H 头文件。 
    
 _lpulProviderVer_
  
> 排除指向此通讯簿提供程序使用的 SPI 版本号的指针。 
    
 _lppABProvider_
  
> 排除指向已初始化的通讯簿提供程序对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_VERSION 
  
> MAPI 使用的 spi 版本与此提供程序使用的 spi 不兼容。
    
## <a name="remarks"></a>说明

MAPI 调用入口点函数**ABProviderInit** , 以在客户端登录后初始化通讯簿提供程序。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

通讯簿提供程序必须将**ABProviderInit**实现为提供程序的 DLL 中的入口点函数。 实现必须基于**ABPROVIDERINIT**函数原型 (也在 MAPISPI 中指定)。水平. MAPI 将**ABPROVIDERINIT**定义为使用标准 MAPI 初始化呼叫类型 STDMAPIINITCALLTYPE, 这将导致**ABPROVIDERINIT**遵循 CDECL 调用约定。 
  
提供程序可以多次初始化, 这是由于多个配置文件中出现在同时使用或在同一配置文件中出现多次。 由于 provider 对象包含上下文, 因此**ABProviderInit**必须在_lppABProvider_中为每个初始化返回不同的提供程序对象, 即使在同一进程中进行了多次初始化也是如此。 
  
通讯簿提供程序应使用由_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指向的功能, 以实现大多数内存分配和释放。 特别是, 提供程序必须使用这些函数分配在调用对象接口 (如[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)) 时供客户端应用程序使用的内存。 如果提供程序还预期使用 OLE 内存分配器, 则它应调用分配器对象的**IUnknown:: AddRef**方法, 该对象由_lpMalloc_参数指向该对象。 
  
有关编写**ABProviderInit**的详细信息, 请参阅[实现通讯簿提供程序入口点函数](implementing-an-address-book-provider-entry-point-function.md)。 有关入口点函数的详细信息, 请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。 
  
## <a name="see-also"></a>另请参阅

- [IABProvider : IUnknown](iabprovideriunknown.md) 
- [MSProviderInit](msproviderinit.md)
- [XPProviderInit](xpproviderinit.md)

