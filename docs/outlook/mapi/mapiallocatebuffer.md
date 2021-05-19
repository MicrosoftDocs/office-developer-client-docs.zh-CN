---
title: MAPIAllocateBuffer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIAllocateBuffer
api_type:
- HeaderDef
ms.assetid: f1fc7fc5-c71f-44f7-930a-571773eb6809
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 589ad42199e6f2ec1039499dfd9beda044ccc3dd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425692"
---
# <a name="mapiallocatebuffer"></a>MAPIAllocateBuffer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
分配内存缓冲区。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE MAPIAllocateBuffer(
  ULONG cbSize,
  LPVOID FAR * lppBuffer
);
```

## <a name="parameters"></a>参数

 _cbSize_
  
> [in]要分配的缓冲区的大小（以字节为单位）。 
    
 _lppBuffer_
  
> [out]指向返回的已分配缓冲区的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功，并且已返回请求的内存缓冲区。
    
## <a name="remarks"></a>备注

在 **MAPIAllocateBuffer** 调用处理期间，调用实现从操作系统获取内存块。 内存缓冲区在一个多数字节地址上分配。 在长整型访问效率更高的平台上，操作系统在地址上分配缓冲区，地址的大小（以字节为单位）为四的倍数。 
  
调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数可释放 **MAPIAllocateBuffer** 分配的内存缓冲区，当不再需要内存时，通过调用 [MAPIAllocateMore](mapiallocatemore.md) 函数以及链接到该函数的任何缓冲区。 
  
## <a name="see-also"></a>另请参阅



[MAPIReallocateBuffer](mapireallocatebuffer.md)

