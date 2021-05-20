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
  
初始化通讯簿提供程序以用于操作。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi.h  <br/> |
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
  
> [in]通讯簿提供程序的动态链接库的实例 (MAPI 链接) 使用的 DLL。 
    
 _lpMalloc_
  
> [in]指向公开 OLE **IMalloc 接口的内存分配器对象的** 指针。 当使用某些接口（如 **IStream**）时，通讯簿提供程序可能需要使用此分配方法。 
    
 _lpAllocateBuffer_
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，在 MAPI 需要时用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，在 MAPI 需要时用于分配额外内存。 
    
 _lpFreeBuffer_
  
> [in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，在 MAPI 需要时用于释放内存。 
    
 _ulFlags_
  
> [in]标志的位掩码。 可以设置以下标志：
    
MAPI_NT_SERVICE 
  
> 提供程序正在服务（一种无法访问任何用户界面的一种特殊Windows服务）的上下文中加载。 
    
 _ulMAPIVer_
  
> [in]服务提供商接口的版本号 (SPI) 使用MAPI.DLL版本号。 有关当前版本号，请参阅 MAPISPI。H 头文件。 
    
 _lpulProviderVer_
  
> [out]指向此通讯簿提供程序使用的 SPI 的版本号的指针。 
    
 _lppABProvider_
  
> [out]指向指向已初始化通讯簿提供程序对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
MAPI_E_VERSION 
  
> MAPI 使用的 SPI 版本与此提供程序使用的 SPI 不兼容。
    
## <a name="remarks"></a>备注

MAPI 调用入口点函数 **ABProviderInit** 以在客户端登录后初始化通讯簿提供程序。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

通讯簿提供程序必须将 **ABProviderInit** 实现为提供程序的 DLL 中的入口点函数。 实现必须基于 **ABPROVIDERINIT** 函数原型，在 MAPISPI.H 中也指定了该原型。 MAPI 将 **ABPROVIDERINIT** 定义为使用标准 MAPI 初始化调用类型 STDMAPIINITCALLTYPE，这将导致 **ABProviderInit** 遵循 CDECL 调用约定。 
  
提供程序可以多次初始化，因为同时在多个配置文件中显示，或者在同一配置文件中多次出现。 由于提供程序对象包含上下文， **因此 ABProviderInit** 必须在  _lppABProvider_ 中针对每次初始化返回不同的提供程序对象，即使对于同一进程中的多个初始化，也必须返回该对象。 
  
通讯簿提供程序应该使用 _lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 指向的函数，以用于大多数内存分配和取消分配。  特别是，当调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md)等对象接口时，提供程序必须使用这些函数分配内存供客户端应用程序使用。 如果提供程序还希望使用 OLE 内存分配器，则它应调用 _lpMalloc_ 参数指向的分配器对象的 **IUnknown：：AddRef** 方法。 
  
有关编写 **ABProviderInit** 的信息，请参阅 [实现通讯簿提供程序入口点函数](implementing-an-address-book-provider-entry-point-function.md)。 有关入口点函数详细信息，请参阅 [实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。 
  
## <a name="see-also"></a>另请参阅

- [IABProvider : IUnknown](iabprovideriunknown.md) 
- [MSProviderInit](msproviderinit.md)
- [XPProviderInit](xpproviderinit.md)

