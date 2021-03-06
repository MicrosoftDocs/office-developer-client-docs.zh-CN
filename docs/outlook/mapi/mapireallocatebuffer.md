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
ms.openlocfilehash: 59d0ce192605257dc0aebed46d8093a352fce05f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435283"
---
# <a name="mapireallocatebuffer"></a>MAPIReallocateBuffer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
重新分配内存缓冲区。 它与 [MAPIAllocateBuffer 函数](mapiallocatebuffer.md) 一起使用。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |omapix.h  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> 指向要重新分配的内存的指针。
    
 _ulSize_
  
> 要分配的缓冲区的大小（以字节为单位）。
    
 _lppv_
  
> 指向返回的已分配缓冲区的指针。
    
## <a name="remarks"></a>备注

 **MAPIReallocateBuffer** 分配请求大小的新内存块，并复制传递到此新内存块的缓冲区内容。 如果传递的内存块包含内部指针，则指针不会更改以匹配新位置。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)

