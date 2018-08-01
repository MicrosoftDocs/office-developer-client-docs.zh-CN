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
ms.openlocfilehash: 906dc4a24b994e079a977808c3f501aaaea9d84f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774728"
---
# <a name="createiprop"></a>CreateIProp

  
  
**适用于**： Outlook 
  
创建属性的数据对象，即[IPropData](ipropdataimapiprop.md)对象。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向属性数据对象的界面标识符 (IID) 的指针。 有效的接口标识符是 IID_IMAPIPropData。 _LpInterface_参数中传递 NULL 还会导致_lppPropData_参数可强制转换到标准界面属性的数据对象中返回的属性数据对象。 
    
 _lpAllocateBuffer_
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。 
    
 _lpFreeBuffer_
  
> [in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。 
    
 _lpvReserved_
  
> [in]保留;必须为零。 
    
 _lppPropData_
  
> [输出]指向对返回的属性数据对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 此对象不支持所请求的接口。
    
## <a name="remarks"></a>说明

_LpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_输入的参数分别指向[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)，和[MAPIFreeBuffer](mapifreebuffer.md)函数。 调用**CreateIProp**客户端应用程序中指针传递给 MAPI 函数只名为;服务提供商将指针传递给它在其初始化呼叫中收到或与调用[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索这些函数。 
  

