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
ms.openlocfilehash: 8ba00ecc1d9ff1c0b7db63d3e6d667b374245742
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776353"
---
# <a name="mapiallocatebuffer"></a>MAPIAllocateBuffer

  
  
**适用于**： Outlook 
  
分配内存缓冲区。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapix.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE MAPIAllocateBuffer(
  ULONG cbSize,
  LPVOID FAR * lppBuffer
);
```

## <a name="parameters"></a>参数

 _cbSize_
  
> [in]以字节为单位，要分配的缓冲区的大小。 
    
 _lppBuffer_
  
> [输出]指向返回分配缓冲区。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并具有返回请求的内存缓冲区。
    
## <a name="remarks"></a>说明

期间**MAPIAllocateBuffer**呼叫处理中，调用实现获取从操作系统的内存块。 内存缓冲区分配偶数字节的地址。 长整型访问其中是更高效的平台上, 操作系统分配其以字节为单位的大小是四个倍数的地址上的缓冲区。 
  
调用[MAPIFreeBuffer](mapifreebuffer.md)函数版本由**MAPIAllocateBuffer**，通过调用[MAPIAllocateMore](mapiallocatemore.md)函数和任何缓冲区分配内存缓冲区链接到，，当不再需要的内存。 
  
## <a name="see-also"></a>另请参阅



[MAPIReallocateBuffer](mapireallocatebuffer.md)

