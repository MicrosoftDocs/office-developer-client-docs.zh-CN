---
title: IMAPISupportGetMemAllocRoutines
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetMemAllocRoutines
api_type:
- COM
ms.assetid: 52d45876-367b-42da-b99a-29cdb71fa5a9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 680fd16771b62d705808a04d768115a076e54750
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415535"
---
# <a name="imapisupportgetmemallocroutines"></a>IMAPISupport::GetMemAllocRoutines

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索 MAPI 内存分配和处理函数的地址 ([MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)) 。 [](mapiallocatemore.md)
  
```cpp
HRESULT GetMemAllocRoutines(
  LPALLOCATEBUFFER FAR * lppAllocateBuffer,
  LPALLOCATEMORE FAR * lppAllocateMore,
  LPFREEBUFFER FAR * lppFreeBuffer
);
```

## <a name="parameters"></a>参数

 _lppAllocateBuffer_
  
> [out]指向指向 **MAPIAllocateBuffer 函数的指针的** 指针。 **MAPIAllocateBuffer** 分配内存。 
    
 _lppAllocateMore_
  
> [out]指向指向 **MAPIAllocateMore 函数的指针** 的指针。 **MAPIAllocateMore** 为最初使用 **MAPIAllocateBuffer 分配的内存分配额外的内存**。
    
 _lppFreeBuffer_
  
> [out]指向指向 **MAPIFreeBuffer 函数的指针的** 指针。 **MAPIFreeBuffer** 释放内存。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回函数地址。
    
## <a name="remarks"></a>备注

**IMAPISupport：：GetMemAllocRoutines** 方法针对所有支持对象实现。 服务提供商调用 **GetMemAllocRoutines，** 获取传递到其初始化函数 ( [ABProviderInit、MSProviderInit](abproviderinit.md)或 [XPProviderInit](xpproviderinit.md)) 的三个内存分配函数的地址。 [](msproviderinit.md) 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

