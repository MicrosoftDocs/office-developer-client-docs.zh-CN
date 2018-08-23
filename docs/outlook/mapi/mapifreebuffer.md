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
ms.openlocfilehash: ad3d9d12e1073610747b0ab078c6d65c09f8c7c1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569139"
---
# <a name="mapifreebuffer"></a>MAPIFreeBuffer

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
释放内存缓冲区分配为[MAPIAllocateBuffer](mapiallocatebuffer.md)函数或[MAPIAllocateMore](mapiallocatemore.md)函数的调用。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapix.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
ULONG MAPIFreeBuffer(
  LPVOID lpBuffer
);
```

## <a name="parameters"></a>参数

 _lpBuffer_
  
> [in]指向以前分配的内存缓冲区。 如果_lpBuffer_参数中传递 NULL，则**MAPIFreeBuffer**无实际作用。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功并释放请求的内存。 **MAPIFreeBuffer**也可以在已释放的位置或如果内存块则不会分配与**MAPIAllocateBuffer** **MAPIAllocateMore**返回 S_OK。
    
## <a name="remarks"></a>注解

通常，当客户端应用程序或服务提供商调用[MAPIAllocateBuffer](mapiallocatebuffer.md)或[MAPIAllocateMore](mapiallocatemore.md)，一个连续内存缓冲区中的操作系统构造一个或多个复杂的指针的多个级别结构。 当 MAPI 函数或方法创建此类内容缓冲区时，客户端可以更高版本来释放通过将传递给**MAPIFreeBuffer**指向创建缓冲区的 MAPI 函数返回的缓冲区的缓冲区中包含的所有结构。 以释放内存缓冲区使用**MAPIFreeBuffer**服务提供程序，它必须将指针传递给提供程序的支持对象返回的缓冲区。 
  
必须尽快客户端进行**MAPIFreeBuffer**调用以释放特定缓冲区或提供程序是使用此缓冲区完。 只需在 MAPI 会话结束调用[IMAPISession::Logoff](imapisession-logoff.md)方法不会自动释放内存缓冲区。 
  
假设后从**MAPIFreeBuffer**的成功返回_lpBuffer_中传递的指针是无效的客户端或服务提供程序应对执行操作。 如果将指针指示通过**MAPIAllocateBuffer**或**MAPIAllocateMore**或可用内存块消息系统未分配的内存块，未定义**MAPIFreeBuffer**的行为。 
  
> [!NOTE]
> 将 null 指针传递给**MAPIFreeBuffer**会使应用程序清理代码简单和较小因为**MAPIFreeBuffer**可以指针初始化为 NULL，而不必先测试它们然后释放它们在清理代码。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)

