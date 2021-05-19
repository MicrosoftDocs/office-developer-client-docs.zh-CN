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
# <a name="msproviderinit"></a>MSProviderInit

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
初始化邮件存储提供程序以用于操作。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi.h  <br/> |
|实现者：  <br/> |邮件存储提供程序  <br/> |
|调用者：  <br/> |MAPI  <br/> |
   
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
  
> [in]邮件存储提供程序的动态链接库的实例 (MAPI 链接) 使用的 DLL。 
    
 _lpMalloc_
  
> [in]指向公开 OLE **IMalloc 接口的内存分配器对象的** 指针。 使用某些接口（如 **IStream**）时，邮件存储提供程序可能需要使用此分配方法。 
    
 _lpAllocateBuffer_
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。 
    
 _lpFreeBuffer_
  
> [in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。 
    
 _ulFlags_
  
> [in]标志的位掩码。 可以设置以下标志：
    
MAPI_NT_SERVICE 
  
> 提供程序正在服务（一种无法访问任何用户界面的一种特殊Windows服务）的上下文中加载。 
    
 _ulMAPIVer_
  
> [in]MAPI 使用的 SPI (接口) 版本号。 有关当前版本号，请参阅 Mapispi.h 头文件。 
    
 _lpulProviderVer_
  
> [out]指向此邮件存储提供程序使用的 SPI 的版本号的指针。 
    
 _lppMSProvider_
  
> [out]指向初始化的邮件存储提供程序对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
MAPI_E_VERSION 
  
> MAPI 使用的 SPI 版本与此提供程序使用的 SPI 不兼容。
    
## <a name="remarks"></a>备注

MAPI 调用入口点函数 **MSProviderInit** 以在客户端登录后初始化邮件存储提供程序。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

邮件存储提供程序必须将 **MSProviderInit** 实现为提供程序的 DLL 中的入口点函数。 实现必须基于 **MSPROVIDERINIT** 函数原型，在 MAPISPI.H 中也指定了该原型。 MAPI 将 **MSPROVIDERINIT** 定义为使用标准 MAPI 初始化调用类型 STDMAPIINITCALLTYPE，这将导致 **MSProviderInit** 遵循 CDECL 调用约定。 CDECL 的一个优点是，即使调用参数的数量与定义的参数数不匹配，也可以尝试呼叫。 
  
提供程序可以多次初始化，因为同时在多个配置文件中显示，或者在同一配置文件中多次出现。 由于提供程序对象包含上下文， **因此 MSProviderInit** 必须在  _lppMSProvider_ 中针对每次初始化返回不同的提供程序对象，即使对于同一进程中的多个初始化，也必须返回该对象。 
  
不应将提供程序 DLL 与 Mapix.dll。 相反，它应使用这些指针进行内存分配或释放。 
  
邮件存储提供程序应该使用 _lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 指向的函数进行大多数内存分配和取消分配。  特别是，当调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md)等对象接口时，提供程序必须使用这些函数分配内存供客户端应用程序使用。 如果提供程序还希望使用 OLE 内存分配器，则它应调用 _lpMalloc_ 参数指向的分配器对象的 **IUnknown：：AddRef** 方法。 
  
有关编写 **MSProviderInit** 的信息，请参阅 [加载邮件存储提供程序](loading-message-store-providers.md)。 有关入口点函数的信息，请参阅 [实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。 
  
## <a name="see-also"></a>另请参阅



[ABProviderInit](abproviderinit.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)
  
[XPProviderInit](xpproviderinit.md)

