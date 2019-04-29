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
  
释放通过调用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数或[MAPIAllocateMore](mapiallocatemore.md)函数分配的内存缓冲区。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
ULONG MAPIFreeBuffer(
  LPVOID lpBuffer
);
```

## <a name="parameters"></a>参数

 _lpBuffer_
  
> 实时指向以前分配的内存缓冲区的指针。 如果在_lpBuffer_参数中传递 NULL, 则**MAPIFreeBuffer**不执行任何操作。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并释放了请求的内存。 **MAPIFreeBuffer**还可以在已释放的位置上返回 S_OK, 或者如果未使用**MAPIAllocateBuffer**和**MAPIAllocateMore**分配内存块。
    
## <a name="remarks"></a>说明

通常情况下, 当客户端应用程序或服务提供程序调用[MAPIAllocateBuffer](mapiallocatebuffer.md)或[MAPIAllocateMore](mapiallocatemore.md)时, 操作系统会在一个连续的内存缓冲区中构造一个或多个具有多个指针级别的复杂结构。 当 mapi 函数或方法创建具有此类内容的缓冲区时, 客户端可以通过向**MAPIFreeBuffer**传递指向由创建该缓冲区的 MAPI 函数返回的缓冲区来释放该缓冲区中包含的所有结构。 若要使服务提供程序使用**MAPIFreeBuffer**释放内存缓冲区, 它必须将指针传递给提供程序的支持对象返回的那个缓冲区。 
  
当客户端或提供程序使用此缓冲区完成后, 必须立即调用**MAPIFreeBuffer**以释放特定的缓冲区。 在 MAPI 会话结束时只需调用[IMAPISession:: 注销](imapisession-logoff.md)方法, 就不会自动释放内存缓冲区。 
  
客户端或服务提供商应假定在从**MAPIFreeBuffer**成功返回后, 在_lpBuffer_中传递的指针无效。 如果指针指示邮件系统未通过**MAPIAllocateBuffer**或**MAPIAllocateMore**或可用内存块分配的内存块, 则**MAPIFreeBuffer**的行为未定义。 
  
> [!NOTE]
> 将 null 指针传递给**MAPIFreeBuffer**会使应用程序清理代码更简单且更小, 因为**MAPIFreeBuffer**可以将指针初始化为 null, 然后在清理代码中释放它们, 而无需先对其进行测试。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)

