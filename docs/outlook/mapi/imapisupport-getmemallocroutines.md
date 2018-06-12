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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 782c04d05ea5cea811784b031e8a118a9c08cbb7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775626"
---
# <a name="imapisupportgetmemallocroutines"></a>IMAPISupport::GetMemAllocRoutines

  
  
**适用于**： Outlook 
  
检索 MAPI 内存分配和释放函数 （[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)） 的地址。
  
```cpp
HRESULT GetMemAllocRoutines(
  LPALLOCATEBUFFER FAR * lppAllocateBuffer,
  LPALLOCATEMORE FAR * lppAllocateMore,
  LPFREEBUFFER FAR * lppFreeBuffer
);
```

## <a name="parameters"></a>参数

 _lppAllocateBuffer_
  
> [输出]指向**MAPIAllocateBuffer**函数的指针的指针。 **MAPIAllocateBuffer**分配内存。 
    
 _lppAllocateMore_
  
> [输出]指向**MAPIAllocateMore**函数的指针的指针。 **MAPIAllocateMore**为使用**MAPIAllocateBuffer**最初分配的内存分配更多内存。
    
 _lppFreeBuffer_
  
> [输出]指向**MAPIFreeBuffer**函数的指针的指针。 **MAPIFreeBuffer**释放内存。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回函数地址。
    
## <a name="remarks"></a>备注

对于所有支持对象实现**IMAPISupport::GetMemAllocRoutines**方法。 服务提供商调用**GetMemAllocRoutines**来获取三个内存分配函数传递给其初始化函数 （ [ABProviderInit](abproviderinit.md)、 [MSProviderInit](msproviderinit.md)或[XPProviderInit](xpproviderinit.md)） 的地址。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

