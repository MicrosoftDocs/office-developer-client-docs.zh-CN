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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0415e782a98102314ce732f744c0d29590f646c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779114"
---
# <a name="xpproviderinit"></a>XPProviderInit

  
  
**适用于**： Outlook 
  
初始化的传输提供程序操作。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|通过实现：  <br/> |传输提供程序  <br/> |
|调用：  <br/> |MAPI  <br/> |
   
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
  
> [in]传输提供程序的动态链接库 (DLL) 的 MAPI 它加载 DLL 时使用的实例。
    
 _lpMalloc_
  
> [in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。 传输提供程序可能需要使用某些如**IStream**接口时使用此分配方法。 
    
 _lpAllocateBuffer_
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。 
    
 _lpFreeBuffer_
  
> [in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。 
    
 _ulFlags_
  
> [in]Flags 的位掩码。 可以设置以下标记：
    
MAPI_NT_SERVICE 
  
> 提供程序正在加载的一项 Windows 服务，一个特殊类型没有任何用户界面的访问权限的过程的上下文中。 
    
 _ulMAPIVer_
  
> [in]Mapi.dll 使用的服务提供程序界面 (SPI) 的版本号。 当前版本号，请参阅 Mapispi.h 头文件。 
    
 _lpulProviderVer_
  
> [输出]指向该传输提供程序使用 SPI 的版本号。 
    
 _lppXPProvider_
  
> [输出]指向初始化的传输提供程序对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_VERSION 
  
> 正在使用 MAPI 的 SPI 版本不兼容与 SPI 正在使用此提供程序。
    
## <a name="remarks"></a>备注

MAPI 调用入口点函数**XPProviderInit**初始化关注客户端登录的传输提供程序。 客户端的配置文件中指定每个传输提供程序调用**XPProviderInit**一次。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

传输提供程序必须实现**XPProviderInit**作为在提供程序的 DLL 入口点函数。 实现必须基于**XPPROVIDERINIT**函数原型，还中指定 Mapispi.h。 MAPI 定义**XPPROVIDERINIT**使用标准 MAPI 初始化呼叫类型，STDMAPIINITCALLTYPE，这将导致**XPProviderInit**关注 CDECL 调用约定。 利用 CDECL 是即使调用参数数目不符定义参数数目，可以尝试呼叫。 
  
提供程序可以初始化多次由于中同时使用或多次出现在相同的配置文件显示在多个配置文件。 由于提供商对象包含上下文， **XPProviderInit**必须中为每个初始化，即使的同一进程中的多个初始化_lppXPProvider_返回不同的提供程序的对象。 
  
传输提供程序应使用指向_lpAllocateBuffer_和_lpAllocateMore_，对于大多数内存分配和释放_lpFreeBuffer_的功能。 特别是，提供程序必须使用这些函数用于客户端应用程序分配内存，调用[IMAPIProp::GetProps](imapiprop-getprops.md)等[IMAPITable::QueryRows](imapitable-queryrows.md)对象接口时。 如果还希望使用 OLE 内存分配器提供程序，它应调用_lpMalloc_参数指向分配器对象的**IUnknown::AddRef**方法。 
  
有关编写**XPProviderInit**的详细信息，请参阅[初始化传输提供程序](initializing-the-transport-provider.md)。 有关入口点函数的详细信息，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。 
  
## <a name="see-also"></a>另请参阅



[ABProviderInit](abproviderinit.md)
  
[IXPProvider: IUnknown](ixpprovideriunknown.md)
  
[MSProviderInit](msproviderinit.md)

