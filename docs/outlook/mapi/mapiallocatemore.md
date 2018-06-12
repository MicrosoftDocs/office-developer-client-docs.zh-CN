---
title: MAPIAllocateMore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIAllocateMore
api_type:
- HeaderDef
ms.assetid: 3e48f76a-bc97-4cbc-9082-c07dd674b73e
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: f6f986ae811f2c7a886231a3046038889b82d683
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776366"
---
# <a name="mapiallocatemore"></a>MAPIAllocateMore

  
  
**适用于**： Outlook 
  
分配一个链接到另一个缓冲区[MAPIAllocateBuffer](mapiallocatebuffer.md)函数与先前分配的内存缓冲区。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapix.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE MAPIAllocateMore(
  ULONG cbSize,
  LPVOID lpObject,
  LPVOID FAR * lppBuffer
);
```

## <a name="parameters"></a>参数

 _cbSize_
  
> [in]以字节为单位，要分配的新缓冲区的大小。 
    
 _lpObject_
  
> [in]指向分配使用**MAPIAllocateBuffer**现有 MAPI 缓冲区。
    
 _lppBuffer_
  
> [输出]返回的指向新分配缓冲区。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，到请求的内存返回一个指针。
    
## <a name="remarks"></a>备注

期间**MAPIAllocateMore**呼叫处理中，调用实现获取从操作系统的内存块。 内存缓冲区分配偶数字节的地址。 长整型访问其中是更高效的平台上, 操作系统分配其以字节为单位的大小是四个倍数的地址上的缓冲区。 
  
释放用**MAPIAllocateMore**分配缓冲区的唯一方法是将传递给[MAPIFreeBuffer](mapifreebuffer.md)函数_lpObject_参数中指定的缓冲区指针。 用[MAPIAllocateBuffer](mapiallocatebuffer.md)和**MAPIAllocateMore**分配的内存缓冲区之间的链接使**MAPIFreeBuffer**释放的单个调用进行这两个缓冲区。 
  

