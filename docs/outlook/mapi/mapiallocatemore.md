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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 01980b2da735838eeffa9afa5a0d139b69e76d0c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435388"
---
# <a name="mapiallocatemore"></a>MAPIAllocateMore

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
分配链接到以前使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数分配的另一个缓冲区的内存缓冲区。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE MAPIAllocateMore(
  ULONG cbSize,
  LPVOID lpObject,
  LPVOID FAR * lppBuffer
);
```

## <a name="parameters"></a>参数

 _cbSize_
  
> 实时要分配的新缓冲区的大小 (以字节为单位)。 
    
 _lpObject_
  
> 实时指向使用**MAPIAllocateBuffer**分配的现有 MAPI 缓冲区的指针。
    
 _lppBuffer_
  
> 排除指向返回的新分配的缓冲区的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回指向请求的内存的指针。
    
## <a name="remarks"></a>说明

在**MAPIAllocateMore**呼叫处理过程中, 呼叫实现将从操作系统中获取内存块。 内存缓冲区分配在偶数字节地址上。 在较长整数访问效率更高的平台上, 操作系统在大小为4个字节的地址上分配缓冲区。 
  
释放用**MAPIAllocateMore**分配的缓冲区的唯一方法是将_lpObject_参数中指定的缓冲区指针传递给[MAPIFreeBuffer](mapifreebuffer.md)函数。 使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和**MAPIAllocateMore**分配的内存缓冲区之间的链接使**MAPIFreeBuffer**能够通过单个调用释放两个缓冲区。 
  

