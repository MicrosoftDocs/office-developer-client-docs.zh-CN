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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316554"
---
# <a name="imapisupportgetmemallocroutines"></a>IMAPISupport::GetMemAllocRoutines

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索 MAPI 内存分配和释放函数的地址 ([MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md))。
  
```cpp
HRESULT GetMemAllocRoutines(
  LPALLOCATEBUFFER FAR * lppAllocateBuffer,
  LPALLOCATEMORE FAR * lppAllocateMore,
  LPFREEBUFFER FAR * lppFreeBuffer
);
```

## <a name="parameters"></a>参数

 _lppAllocateBuffer_
  
> 排除指向指向**MAPIAllocateBuffer**函数的指针的指针。 **MAPIAllocateBuffer**分配内存。 
    
 _lppAllocateMore_
  
> 排除指向指向**MAPIAllocateMore**函数的指针的指针。 **MAPIAllocateMore**为使用**MAPIAllocateBuffer**最初分配的内存分配额外的内存。
    
 _lppFreeBuffer_
  
> 排除指向指向**MAPIFreeBuffer**函数的指针的指针。 **MAPIFreeBuffer**释放内存。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回了函数地址。
    
## <a name="remarks"></a>注解

**IMAPISupport:: GetMemAllocRoutines**方法是为所有支持对象实现的。 服务提供程序调用**GetMemAllocRoutines** , 以获取传递给其初始化函数的三个内存分配函数 ( [ABProviderInit](abproviderinit.md)、 [MSProviderInit](msproviderinit.md)或[XPProviderInit](xpproviderinit.md)) 的地址。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

