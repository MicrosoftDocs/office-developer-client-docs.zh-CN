---
title: MAPIFreeBuffer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIFreeBuffer
api_type:
- HeaderDef
ms.assetid: 9412594f-8acc-4c7e-a668-4ec1da0ad9cf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8794bb233eb69d0f246fb1019954ab718db6f464
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410551"
---
# <a name="mapifreebuffer"></a>MAPIFreeBuffer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
释放通过调用 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数或 [MAPIAllocateMore](mapiallocatemore.md) 函数分配的内存缓冲区。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
ULONG MAPIFreeBuffer(
  LPVOID lpBuffer
);
```

## <a name="parameters"></a>参数

 _lpBuffer_
  
> [in]指向以前分配的内存缓冲区的指针。 如果在  _lpBuffer_ 参数中传递 NULL， **则 MAPIFreeBuffer** 不执行任何操作。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并释放所请求的内存。 **MAPIFreeBuffer** 还可以返回S_OK释放位置的内存，或者如果未使用 **MAPIAllocateBuffer** 和 **MAPIAllocateMore** 分配内存块。
    
## <a name="remarks"></a>备注

通常，当客户端应用程序或服务提供商调用 [MAPIAllocateBuffer](mapiallocatebuffer.md) 或 [MAPIAllocateMore](mapiallocatemore.md)时，操作系统在一个具有多个指针级别的连续内存缓冲区中构造一个或多个复杂结构。 当 MAPI 函数或方法创建包含此类内容的缓冲区时，客户端稍后可以通过将指针传递到 **MAPIFreeBuffer** 来释放缓冲区中包含的所有结构，方法是将指针传递给创建缓冲区的 MAPI 函数返回的缓冲区。 对于使用 **MAPIFreeBuffer** 释放内存缓冲区的服务提供商，它必须将指针传递到使用提供程序的支持对象返回的缓冲区。 
  
在客户端或提供程序使用此缓冲区完成后，必须立即调用 **MAPIFreeBuffer** 以释放特定缓冲区。 只需在 MAPI 会话结束时调用 [IMAPISession：：Logoff](imapisession-logoff.md) 方法，不会自动释放内存缓冲区。 
  
客户端或服务提供商应假定传入  _lpBuffer_ 的指针在 **从 MAPIFreeBuffer** 成功返回后无效。 如果指针指示邮件系统未通过 **MAPIAllocateBuffer** 或 **MAPIAllocateMore** 分配的内存块或可用内存块， **则 MAPIFreeBuffer** 的行为未定义。 
  
> [!NOTE]
> 将空指针传递到 **MAPIFreeBuffer** 可以使应用程序清理代码更简单、更小，因为 **MAPIFreeBuffer** 可以初始化指向 NULL 的指针，然后在清理代码中释放它们，而不必首先测试它们。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)

