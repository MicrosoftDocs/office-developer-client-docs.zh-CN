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
|标头文件：  <br/> |Mapix  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE MAPIAllocateBuffer(
  ULONG cbSize,
  LPVOID FAR * lppBuffer
);
```

## <a name="parameters"></a>参数

 _cbSize_
  
> 实时要分配的缓冲区的大小 (以字节为单位)。 
    
 _lppBuffer_
  
> 排除指向返回的已分配缓冲区的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回请求的内存缓冲区。
    
## <a name="remarks"></a>说明

在**MAPIAllocateBuffer**呼叫处理过程中, 呼叫实现将从操作系统中获取内存块。 内存缓冲区分配在偶数字节地址上。 在较长整数访问效率更高的平台上, 操作系统在大小为4个字节的地址上分配缓冲区。 
  
调用[MAPIFreeBuffer](mapifreebuffer.md)函数将释放**MAPIAllocateBuffer**分配的内存缓冲区, 方法是在不再需要内存时调用[MAPIAllocateMore](mapiallocatemore.md)函数以及链接到它的任何缓冲区。 
  
## <a name="see-also"></a>另请参阅



[MAPIReallocateBuffer](mapireallocatebuffer.md)

