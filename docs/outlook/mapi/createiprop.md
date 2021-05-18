---
title: CreateIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.CreateIProp
api_type:
- COM
ms.assetid: 9bf68814-2564-433d-b762-3d2c83ca3c60
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e318d7a709a09e67ebf423db0263985523d2fc28
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406806"
---
# <a name="createiprop"></a>CreateIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个属性数据对象，即 [IPropData](ipropdataimapiprop.md) 对象。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE CreateIProp(
  LPCIID lpInterface,
  ALLOCATEBUFFER FAR * lpAllocateBuffer,
  ALLOCATEMORE FAR * lpAllocateMore,
  FREEBUFFER FAR * lpFreeBuffer,
  LPVOID lpvReserved,
  LPPROPDATA FAR * lppPropData
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> [in]指向属性数据 (IID) 接口标识符的指针。 有效的接口标识符IID_IMAPIPropData。 在  _lpInterface_ 参数中传递 NULL 还会导致  _在 lppPropData_ 参数中返回的属性数据对象强制转换到属性数据对象的标准接口。 
    
 _lpAllocateBuffer_
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。 
    
 _lpFreeBuffer_
  
> [in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。 
    
 _lpvReserved_
  
> [in]保留;必须为零。 
    
 _lppPropData_
  
> [out]指向返回的属性数据对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 此对象不支持请求的接口。
    
## <a name="remarks"></a>备注

_lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 输入参数分别指向 [MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和 [MAPIFreeBuffer](mapifreebuffer.md)函数。  [](mapiallocatemore.md) 调用 **CreateIProp** 的客户端应用程序将传递指向刚命名的 MAPI 函数的指针;服务提供商将指针传递给其在其初始化调用中收到的或通过调用 [IMAPISupport：：GetMemAllocRoutines](imapisupport-getmemallocroutines.md) 方法检索的函数。 
  

