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
  
创建一个属性数据对象, 即一个[IPropData](ipropdataimapiprop.md)对象。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
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
  
> 实时指向属性数据对象的接口标识符 (IID) 的指针。 有效的接口标识符为 IID_IMAPIPropData。 在_lpInterface_参数中传递 NULL 还会导致在_lppPropData_参数中返回的属性数据对象将转换为属性数据对象的标准接口。 
    
 _lpAllocateBuffer_
  
> 实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。 
    
 _lpAllocateMore_
  
> 实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。 
    
 _lpFreeBuffer_
  
> 实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。 
    
 _lpvReserved_
  
> 实时保留必须为零。 
    
 _lppPropData_
  
> 排除指向返回的属性数据对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 此对象不支持所请求的接口。
    
## <a name="remarks"></a>说明

" _lpAllocateBuffer_"、" _lpAllocateMore_" 和 " _lpFreeBuffer_ " 输入参数分别指向 " [MAPIAllocateBuffer](mapiallocatebuffer.md)"、" [MAPIAllocateMore](mapiallocatemore.md)" 和 " [MAPIFreeBuffer](mapifreebuffer.md) " 函数。 调用**CreateIProp**的客户端应用程序传递到刚刚命名的 MAPI 函数的指针。服务提供程序将指针传递给其在初始化调用中收到的这些函数, 或通过调用[IMAPISupport:: GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索到这些函数。 
  

