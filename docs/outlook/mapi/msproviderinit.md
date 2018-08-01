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
# <a name="msproviderinit"></a>MSProviderInit

  
  
**适用于**： Outlook 
  
初始化操作的消息存储提供程序。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|通过实现：  <br/> |消息存储提供程序  <br/> |
|调用：  <br/> |MAPI  <br/> |
   
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

## <a name="parameters"></a>参数

 _hInstance_
  
> [in]邮件实例存储在它链接时，将使用 MAPI 的提供程序的动态链接库 (DLL)。 
    
 _lpMalloc_
  
> [in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。 消息存储提供程序可能需要使用某些如**IStream**接口时使用此分配方法。 
    
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
  
> [in]使用 MAPI 服务提供程序接口 (SPI) 的版本号。 当前版本号，请参阅 Mapispi.h 头文件。 
    
 _lpulProviderVer_
  
> [输出]指向该消息存储提供程序使用 SPI 的版本号。 
    
 _lppMSProvider_
  
> [输出]指向初始化的消息存储提供程序对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_VERSION 
  
> 正在使用 MAPI 的 SPI 版本不兼容与 SPI 正在使用此提供程序。
    
## <a name="remarks"></a>说明

MAPI 调用入口点函数**MSProviderInit**初始化关注客户端登录的消息存储提供程序。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

消息存储提供程序必须实现**MSProviderInit**作为在提供程序的 DLL 入口点函数。 实现必须基于**MSPROVIDERINIT**函数原型，还中指定 MAPISPI。H。 MAPI 定义**MSPROVIDERINIT**使用标准 MAPI 初始化呼叫类型，STDMAPIINITCALLTYPE，这将导致**MSProviderInit**关注 CDECL 调用约定。 利用 CDECL 是即使调用参数数目不符定义参数数目，可以尝试呼叫。 
  
可多次，由于中同时使用或多次出现的同一配置文件中的多个配置文件中出现初始化提供程序。 由于提供商对象包含上下文， **MSProviderInit**必须中为每个初始化，即使的同一进程中的多个初始化_lppMSProvider_返回不同的提供程序的对象。 
  
不应该与 Mapix.dll 链接提供程序 DLL。 相反，它应使用这些指针的内存分配或释放。 
  
消息存储提供程序应使用指向_lpAllocateBuffer_和_lpAllocateMore_，对于大多数内存分配和释放_lpFreeBuffer_的功能。 特别是，提供程序必须使用这些函数用于客户端应用程序分配内存，调用[IMAPIProp::GetProps](imapiprop-getprops.md)等[IMAPITable::QueryRows](imapitable-queryrows.md)对象接口时。 如果还希望使用 OLE 内存分配器提供程序，它应调用_lpMalloc_参数指向分配器对象的**IUnknown::AddRef**方法。 
  
有关编写**MSProviderInit**的详细信息，请参阅[加载消息存储提供程序](loading-message-store-providers.md)。 有关入口点函数的详细信息，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。 
  
## <a name="see-also"></a>另请参阅



[ABProviderInit](abproviderinit.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)
  
[XPProviderInit](xpproviderinit.md)

