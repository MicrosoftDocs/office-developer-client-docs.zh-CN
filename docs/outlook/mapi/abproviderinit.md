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
# <a name="abproviderinit"></a>ABProviderInit
 
**适用于**： Outlook 2013 |Outlook 2016 
  
初始化通讯簿提供程序的操作。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|通过实现：  <br/> |通讯簿提供程序  <br/> |
|调用：  <br/> |MAPI  <br/> |
   
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
  
> [in]通讯簿提供程序的动态链接库 (DLL) 它链接时，将使用 MAPI 的实例。 
    
 _lpMalloc_
  
> [in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。 通讯簿提供程序可能需要使用某些如**IStream**接口时使用此分配方法。 
    
 _lpAllocateBuffer_
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于在需要时通过 MAPI 分配内存。 
    
 _lpAllocateMore_
  
> [in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于在需要时通过 MAPI 分配更多内存。 
    
 _lpFreeBuffer_
  
> [in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，用于在需要时通过 MAPI 以释放内存。 
    
 _ulFlags_
  
> [in]Flags 的位掩码。 可以设置以下标记：
    
MAPI_NT_SERVICE 
  
> 提供程序正在加载的一项 Windows 服务，一个特殊类型没有任何用户界面的访问权限的过程的上下文中。 
    
 _ulMAPIVer_
  
> [in]服务提供程序接口 (SPI) 的 MAPI 的版本号。使用 DLL。 当前版本号，请参阅 MAPISPI。H 头文件。 
    
 _lpulProviderVer_
  
> [输出]指向 SPI 通讯簿提供商使用的版本号。 
    
 _lppABProvider_
  
> [输出]为指向初始化的通讯簿提供程序对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_VERSION 
  
> 正在使用 MAPI 的 SPI 版本不兼容与 SPI 正在使用此提供程序。
    
## <a name="remarks"></a>注解

MAPI 调用入口点函数**ABProviderInit**初始化通讯簿提供程序关注客户端登录。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

通讯簿提供程序必须实现**ABProviderInit**作为在提供程序的 DLL 入口点函数。 实现必须基于**ABPROVIDERINIT**函数原型，还中指定 MAPISPI。H。 MAPI 定义**ABPROVIDERINIT**使用标准 MAPI 初始化呼叫类型，STDMAPIINITCALLTYPE，这将导致**ABProviderInit**关注 CDECL 调用约定。 
  
可多次，由于中同时使用或多次出现的同一配置文件中的多个配置文件中出现初始化提供程序。 由于提供商对象包含上下文， **ABProviderInit**必须中为每个初始化，即使的同一进程中的多个初始化_lppABProvider_返回不同的提供程序的对象。 
  
通讯簿提供程序应使用指向_lpAllocateBuffer_和_lpAllocateMore_，对于大多数内存分配和释放_lpFreeBuffer_的功能。 特别是，提供程序必须使用这些函数用于客户端应用程序分配内存，调用[IMAPIProp::GetProps](imapiprop-getprops.md)等[IMAPITable::QueryRows](imapitable-queryrows.md)对象接口时。 如果还希望使用 OLE 内存分配器提供程序，它应调用_lpMalloc_参数指向分配器对象的**IUnknown::AddRef**方法。 
  
编写**ABProviderInit**的详细信息，请参阅[实现地址簿提供程序入口点函数](implementing-an-address-book-provider-entry-point-function.md)。 入口点函数的详细信息，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。 
  
## <a name="see-also"></a>另请参阅

- [IABProvider : IUnknown](iabprovideriunknown.md) 
- [MSProviderInit](msproviderinit.md)
- [XPProviderInit](xpproviderinit.md)

