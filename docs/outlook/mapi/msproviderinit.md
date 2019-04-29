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
  
为操作初始化邮件存储提供程序。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|实现者：  <br/> |邮件存储区提供程序  <br/> |
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
  
> 实时MAPI 链接时使用的邮件存储区提供程序的动态链接库 (DLL) 的实例。 
    
 _lpMalloc_
  
> 实时指向用于公开 OLE **IMalloc**接口的内存分配器对象的指针。 在使用某些接口 (如**IStream**) 时, 邮件存储提供程序可能需要使用此分配方法。 
    
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
  
> 实时MAPI 使用的服务提供程序接口 (SPI) 版本号。 有关当前版本号, 请参阅 Mapispi 头文件。 
    
 _lpulProviderVer_
  
> 排除指向此邮件存储提供程序使用的 SPI 版本号的指针。 
    
 _lppMSProvider_
  
> 排除指向已初始化的邮件存储提供程序对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_VERSION 
  
> MAPI 使用的 spi 版本与此提供程序使用的 spi 不兼容。
    
## <a name="remarks"></a>说明

MAPI 调用入口点函数**MSProviderInit** , 以在客户端登录后初始化邮件存储提供程序。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

邮件存储区提供程序必须实现**MSProviderInit**作为提供程序 DLL 中的入口点函数。 实现必须基于**MSPROVIDERINIT**函数原型 (也在 MAPISPI 中指定)。水平. MAPI 将**MSPROVIDERINIT**定义为使用标准 MAPI 初始化呼叫类型 STDMAPIINITCALLTYPE, 这将导致**MSPROVIDERINIT**遵循 CDECL 调用约定。 CDECL 的优势在于, 即使调用参数的数目与定义的参数数量不匹配, 也可以尝试调用。 
  
提供程序可以多次初始化, 这是由于多个配置文件中出现在同时使用或在同一配置文件中出现多次。 由于 provider 对象包含上下文, 因此**MSProviderInit**必须在_lppMSProvider_中为每个初始化返回不同的提供程序对象, 即使在同一进程中进行了多次初始化也是如此。 
  
提供程序 DLL 不应与 Mapix 链接。 相反, 它应使用这些指针来分配或释放内存。 
  
邮件存储区提供程序应使用由_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指向的函数, 以实现大多数内存分配和释放。 特别是, 提供程序必须使用这些函数分配在调用对象接口 (如[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)) 时供客户端应用程序使用的内存。 如果提供程序还预期使用 OLE 内存分配器, 则它应调用分配器对象的**IUnknown:: AddRef**方法, 该对象由_lpMalloc_参数指向该对象。 
  
有关编写**MSProviderInit**的详细信息, 请参阅[加载邮件存储提供程序](loading-message-store-providers.md)。 有关入口点函数的详细信息, 请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。 
  
## <a name="see-also"></a>另请参阅



[ABProviderInit](abproviderinit.md)
  
[IMSProvider : IUnknown](imsprovideriunknown.md)
  
[XPProviderInit](xpproviderinit.md)

