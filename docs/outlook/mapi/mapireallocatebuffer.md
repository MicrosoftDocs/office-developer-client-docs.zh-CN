---
title: MAPIReallocateBuffer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 182ab0c6-c9d3-4cc8-892f-f6b09312ceb9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 26dcc31f2ebdd1892f966bfb95fda1a65c5140cb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776391"
---
# <a name="mapireallocatebuffer"></a>MAPIReallocateBuffer

  
  
**适用于**： Outlook 
  
重新分配的内存缓冲区。 它用于[MAPIAllocateBuffer](mapiallocatebuffer.md)函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |omapix.h  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
STDMETHODIMP_(SCODE) MAPIReallocateBuffer
(
LPVOID lpv, 
ULONG ulSize, 
LPVOID * lppv
);
```

## <a name="parameters"></a>参数

 _lpv_
  
> 一个指向可以重新分配的内存。
    
 _ulSize_
  
> 以字节为单位，要分配的缓冲区的大小。
    
 _lppv_
  
> 指向返回分配的缓冲区的指针。
    
## <a name="remarks"></a>说明

 **MAPIReallocateBuffer**分配新请求大小的内存块，并将传递该缓冲区的内容复制到此新块的内存。 如果传递的内存的块包含内部的指针，指针不会更改要匹配的新位置。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)

